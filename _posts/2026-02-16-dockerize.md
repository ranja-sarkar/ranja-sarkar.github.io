--- 
tags: [production, deployment,docker]  
---

<img width="224" height="168" alt="ship" src="https://github.com/user-attachments/assets/e5ba7380-9692-490b-baa2-a51122b7497a" />


Notebooks are good to test out an idea, for quick data exploration & visualization, and to code for checking out or experimenting with a model. However, they are bad at modularization (reusability), testability, reproducability, versioning, and collaboration. Notebook codes do not specify versions of libraries imported, have hard-coded paths, and untested logic. For the code to be production-ready, it must be versioned, reproducible, organised, and tested. And finally shipped for operations!

---

The process encompasses containerizng the code, and shipping the container. 

✔️ **Containerize code**

📌 Steps to follow:

1. Package your code - create setup.py

  It is however the traditional method. Developrs have moved towards declarative configuration using [*pyproject.toml*](https://packaging.python.org/en/latest/guides/modernize-setup-py-project/#modernize-setup-py-project).
  The use of [*setup.py*](https://packaging.python.org/en/latest/discussions/setup-py-deprecated/) as a command line tool is deprecated.
  
2. Create txt file of requirements 

3. Add unit test files - use unittest or pytest libraries

   <img width="491" height="233" alt="01" src="https://github.com/user-attachments/assets/71f4fee3-3597-40c5-bd48-4cde95e102c4" />

4. Containerize your code for deployment - create Dockerfile (you may label your container with a tag).

   <img width="462" height="157" alt="02" src="https://github.com/user-attachments/assets/82a4fa0f-1fa5-445d-b191-143c2f7da7b0" />

5. Check if the Docker container works everywhere - **portability**

<img width="389" height="173" alt="03" src="https://github.com/user-attachments/assets/35b8ddf9-b7eb-4759-b8e2-10d073842113" />

✔️ **Ship the container** 

📌 Main ingredients for container runtime:

1. **Build** - use a tool to let us declare what we need in the container to run our application. *Buildkit* is probably the most well-known (used by Docker too).

2. **Store** - need a place to host the images so our runtime is able to fetch the images and run them as containers. This is typically called a *container registry*. *Docker Hub* is by and large the most popular for this. Other cloud service examples are Azure Container Registry, AWS Elastic Container Registry (ECR).

3. **Run** - need a container runtime to let us run our freshly built images, [*containerd*](https://containerd.io/) is probably the most widely used. 
    
After running your container, you get the output in the form of logs and results.

---

[Here's](https://github.com/ranja-sarkar/ranja-sarkar.github.io/blob/e14d878047908d69e24654e829f168bf1c08f7ad/_posts/assets/dockerize%20for%20deployment.pdf) an example of how to ship a container to Azure using GitHub Actions. It also shows the CI/CD components in the entire process. 


