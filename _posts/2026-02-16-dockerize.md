--- 
tags: [production, deployment,docker]  
---


Notebooks are good to test out an idea, for quick data exploration & visualization, and code to check out an ML model. However, they are bad at modularization (reusability), testability, reproducability, versioning, and collaboration. Notebook codes do not specify versions of libraries imported, have hard-coded paths, and untested logic.

For the code to be production-ready, it must be versioned, reproducible, organised, and tested.

📌 Steps to be followed for the aformentioned:

1. Package your code - create setup.py

2. Create txt file of requirements 

3. Add unit test files - use unittest or pytest libraries

   <img width="491" height="233" alt="01" src="https://github.com/user-attachments/assets/71f4fee3-3597-40c5-bd48-4cde95e102c4" />

4. Containerize your code for deployment - create Dockerfile (you may label your container with a tag).

   <img width="462" height="157" alt="02" src="https://github.com/user-attachments/assets/82a4fa0f-1fa5-445d-b191-143c2f7da7b0" />



    
