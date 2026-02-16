--- 
tags: [production, deployment,docker]  
---


Notebooks are good to test out an idea, for quick data exploration & visualization, and code to check out an ML model. However, they are bad at modularization (reusability), testability, reproducability, versioning, and collaboration. Notebook codes do not specify versions of libraries imported, have hard-coded paths, and untested logic.

For the code to be production-ready, it must be versioned, reproducible, organised, and tested.

📌 Steps to be followed for the aformentioned:

1. Package your code - create setup.py

2. Create txt file of requirements 

3. Add unit test files
