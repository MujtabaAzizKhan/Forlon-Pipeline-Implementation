# Forlorn-Pipeline-Implementation
In this repo I made a pipeline on Jenkins for Forlorn game so everytime a new code is pushed to the GitHub it also pushes on the Docker Hub after building the image.

# Steps

# 1. Setting up Jenkins, Docker and Kubernetes.  
The first step was to set up the mentioned tools.  

# 2. Pushed the code   
After that pushed the code to Github.  
![image](https://github.com/user-attachments/assets/29b44695-0b1d-41dd-8344-f7b1d84a2e7a)  

# 3. Writing a Dockerfile and docker-compose file.  
The next step was to write Dockerfile and docker-compose file to create docker image of the web app.    
![image](https://github.com/user-attachments/assets/9737ef16-4889-458b-8235-eb0814024256)
![image](https://github.com/user-attachments/assets/619f9eb5-3926-41e7-b054-fbd930f5f72d)

# 4. Pushing the image to Docker hub.  
Pushed the image to Docker hub after building it by using the command docker-compose up --build  
![image](https://github.com/user-attachments/assets/a11c9f31-35a0-4bf4-a703-535edb49d87d)


# 5. Creating a pipeline on Jenkins.  
Made a pipeline on Jenkins for Continuous Integration.  
![image](https://github.com/user-attachments/assets/87b97d07-26d4-4edb-bfe6-9f05fa6cfe7b)

# 6. Attaching a webhook.  
From the repository settings in Github, attached the webhook with Jenkins. So that on every push or pull we get info on Jenkins logs.  
![image](https://github.com/user-attachments/assets/080ca450-87d7-4a0a-bab4-ef86e1434333)

I also used serveo.net to expose local server to the internet. Because I cant connect the webhook with Jenkins on a localhost.  
![image](https://github.com/user-attachments/assets/c99577f8-c4e2-4e08-8713-caab4ca221db)

# 7. Writing the pipeline code.  
And finally wrote the pipeline code to connect all the steps together.  
![image](https://github.com/user-attachments/assets/aa4f3759-e744-49d7-90f2-335acd0671e4)


Forlorn A very simple narrative/ interactive fiction game created by my dear friend [Tayyab Naveed](https://github.com/TayyabNaveed16).  
Original Repo Link: https://github.com/TayyabNaveed16/forlorn
