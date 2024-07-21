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
   <img src='./kam/im2.png' height="80%" width="80%" alt="Disk Sanitization Steps">

   build the application into docker image and push to the registry<br/>
   docker build -t java-web-app:1.0 .
   docker tag java-web-app:1.0 975050175231.dkr.ecr.eu-central-1.amazonaws.com/java-web-app:1.0
   docker push 975050175231.dkr.ecr.eu-central-1.amazonaws.com/java-web-app:1.0
   <img src='./kam/im3.png' height="80%" width="80%" alt="Disk Sanitization Steps">



   
 

  <h2>step2</h2>
  

 

<h2>step3</h2>


  
 <img src='./sp/kimage8.png' height="80%" width="80%" alt="Disk Sanitization Steps">

 <h2>step4</h2>



  
 <img src='./sp/kimage10.png' height="80%" width="80%" alt="Disk Sanitization Steps">

 <h2>step5</h2>


   
    
    
   
     

</p>
