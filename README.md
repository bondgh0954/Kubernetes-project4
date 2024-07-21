<h1>Kubernetes Demo Project4</h1>
<h2>Technologies used</h2>

- <b>Kubernetes</b> 
- <b>Helm</b>
- <b>AWS ECR</b>
- <b>Docker</b>



<h2>Detailed Description of Project </h2>
1. Create Secret for credentials for the private Docker registry<br/>
2. Configure the Docker registry secret in application Deployment component<br/>
3. Deploy web application image from our private Docker registry in K8s cluster<br/>

   <p align="">
   <h2>step1</h2>
   create a private docker registry in AWS (AWS Elastic Container Registry)<br/>
      
   <img src='./kam/im1.png' height="80%" width="80%" alt="Disk Sanitization Steps">

   private registry is created in AWS
   <img src='./kam/im2.png' height="80%" width="80%" alt="Disk Sanitization Steps">


   

   build the application into docker image and push to the registry<br/>
   docker build -t java-web-app:1.0 .<br/>
   docker tag java-web-app:1.0 975050175231.dkr.ecr.eu-central-1.amazonaws.com/java-web-app:1.0<br/>
   docker push 975050175231.dkr.ecr.eu-central-1.amazonaws.com/java-web-app:1.0<br/>
   
   java-web-application with the tag 1.0 has successfully been push to the registry<br/>
   <img src='./kam/im3.png' height="80%" width="80%" alt="Disk Sanitization Steps">



   <h2>step2</h2>
   get the access token from AWS (aws ecr get-login-password)<br/>
   ssh into minikube (minikube ssh)<br/>
   login to ecr using the access token as password in minikube<br/>
   docker login --username AWS -p (paste the accesstoken after password) + url of repo<br/>
   
   <img src='./kam/im4.png' height="80%" width="80%" alt="Disk Sanitization Steps">
   
   .docker directory will be created and the access token will be saved in .docker/config.json <br/>
   <img src='./kam/im5.png' height="80%" width="80%" alt="Disk Sanitization Steps">
  

   <h2>step3</h2>
   Create a secret for kubernetes cluster with the secret token<br/>
   copy the content of the the (.docker/config.json) file in minikube to the host (.docker/config.json) dir<br/>
   minikube cp minikube:/home/docker/.docker/config.json ~/.docker/config.json<br/>

   create a secret with the access token in base64 encoded<br/>
   <img src='./kam/im6.png' height="80%" width="80%" alt="Disk Sanitization Steps">
   

 <h2>step4</h2>
 Create a deployment for the application to pull the image from the registry using the secret created in minikube<br/>
 <img src='./kam/im7.png' height="80%" width="80%" alt="Disk Sanitization Steps">

 Deployment is created 
<img src='./kam/im8.png' height="80%" width="80%" alt="Disk Sanitization Steps">

  pod is running in minikube
<img src='./kam/im9.png' height="80%" width="80%" alt="Disk Sanitization Steps">



  
 

   
    
    
   
     

</p>
