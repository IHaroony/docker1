# **Docker Project Documentation: My First Container**

## **1. Setting Up the Project Environment**

### **1.1 Create a Directory for Docker Projects**

First, create a dedicated folder for storing all your Docker projects.


`cd ~/documents mkdir docker cd docker`

This creates a `docker` directory in your `documents` folder and navigates to it.

### **1.2 Clone the Docker Example Repository**

Clone the official `welcome-to-docker` GitHub repository to have a starting point for your project.



`git clone https://github.com/docker/welcome-to-docker.git cd welcome-to-docker`

This command clones the project into a folder named `welcome-to-docker` inside your `docker` directory.

---

## **2. Understanding the Repository**

### **2.1 Review Project Files**

After cloning, let's check the files inside the repository:


`ls`

Expected files you might find:

- **Dockerfile**: This is where Docker image instructions are defined.
- **docker-compose.yml** (if exists): For managing multi-container Docker applications.
- **README.md**: This file often contains project setup, configuration, and usage instructions.

### **2.2 Check the README.md**

Open the `README.md` to understand how the project works. You can view the file contents like this:

`cat README.md`

---

## **3. Build Docker Image**

### **3.1 Ensure Docker is Installed**

Make sure Docker is installed and running on your machine. You can verify by typing:


`docker --version`

This should return the Docker version currently installed.

### **3.2 Build the Docker Image from Dockerfile**

The next step is to build the Docker image using the `Dockerfile` in the project. This creates an image based on the specifications in the `Dockerfile`.

`docker build -t docker-learning .`

- `-t docker-learning`: Names the image `docker-learning`.
- `.` (dot): Tells Docker to use the `Dockerfile` in the current directory.

### **3.3 Verify the Image Build**

To verify that your image was built successfully:

`docker image ls`

This will list all images, and you should see `docker-learning` in the list.

---

## **4. Run the Docker Container**

### **4.1 Start the Container**

Now that you have the Docker image, you can run it. Since the application inside the Docker container listens on port `3000`, map this port to a port on your local machine (e.g., port 8080).

`docker run -d -p 8080:3000 docker-learning`

- `-d`: Runs the container in detached mode (in the background).
- `-p 8080:3000`: Maps port 3000 in the container to port 8080 on your machine.

### **4.2 Verify Running Containers**

To check if your container is running:


`docker ps`

This will list all running containers. You should see your container listed with the port mapping.

---

## **5. Access the Application**

Once the container is running, you can access the app:

1. Open a browser and visit `http://localhost:8080`.
    
2. If the page does not load, double-check the port mapping or inspect the container logs.
    

---

## **6. Inspect the Container Logs (if needed)**

If something's not working or you want to troubleshoot, you can check the logs for more details:

`docker logs <container-id>`

Replace `<container-id>` with the ID from `docker ps`.

---

## **7. Stop the Container**

Once you're done testing or need to stop the container, use the following commands:

1. Stop the container:
    
    
    `docker stop <container-id>`
    
2. Remove the container:

    
    `docker rm <container-id>`
    

---

## **8. Push Changes to GitHub (if applicable)**

### **8.1 Initialize Git (if not done already)**

In case you want to track changes or push your work to GitHub, you can initialize a Git repository:


`git init git add . git commit -m "docker-learning"`

### **8.2 Add Remote Repository and Push Changes**

If you haven't already, add a remote repository and push your changes:


`git remote add origin https://github.com/IHaroony/docker1.git git push -u origin main`

---

## **9. Next Steps**

- **Explore Dockerfile**: Dive deeper into the `Dockerfile` to understand how images are built and learn the syntax.
- **Learn about Docker Compose**: If you plan to work with multi-container setups, explore `docker-compose.yml`.
- **Experiment with Modifying Code**: Modify the application in the repository and rebuild the image to see how changes reflect in the container.

---

## **Conclusion**

You’ve successfully:

1. Set up a Docker environment.
2. Cloned a GitHub repository.
3. Built and ran your first Docker container.
4. Learned how to troubleshoot and access the application inside the container.

Feel free to explore more Docker concepts, and let me know if you have any questions!