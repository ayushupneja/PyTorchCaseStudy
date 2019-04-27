# Ayush's Case Study of PyTorch

Problem Statement: Analyze the package in your own words, 5-10 pages total, a concise analysis without vague generalities, including the following. Percentages are approximate percent of written report case study grade.

# 1. Technology and Platform used for Development

A: What coding languages are used? Do you think the same languages would be used if the project was started today? What languages would you use for the project if starting it today?

- You utilize pytorch as a library in python but it is written in Python, C++. and Cuda
- I believe yes, the same languages would be used if the project was started today. It's not as if it's using Fortran or some ancient language, all three of the written languages are fairly common today, in fact the BU curriculum teaches only C++ in computer engineering. Additionally, its front side is only Python based. Any user would not be programming in any other language and Python is fairly future proof as of right now.
- I have absolutely no experience in using machine learning let alone developing a machine learning library, but from what I've read and based on the fact that PyTorch was first released only in October 2016, I would keep things relatively the same.


B: What build system is used (e.g. Bazel, CMake, Meson)? What build tools / environment are needed to build (e.g. does it require Visual Studio or just GCC or ?)

- All of the libraries in the backend contain CMakeLists.txt which means CMake is the build system that is used in the build system of PyTorch.
- It is compiled with C++, CUDA, and GCC

C: What frameworks / libraries are used in the project? At least one of these projects don’t use any external libraries or explicit threading, yet is noted for being the fastest in its category--in that case, what intrinsic language techniques is it using to get this speed.
- It is a library in and of itself
- It uses several dependencies, including numpy, mkl, cmake, pyyaml, etc.


# 2. Testing: describe unit/integration/module tests and the test framework

A: How are they ensuring the testing is meaningful? Do they have code coverage metrics for example?

- Pypi has published torch_testing which is used for user testing.
- Open source, so coverage is done by users and appreciated to be added to the database

B: What CI platform(s) are they using (e.g. Travis-CI, AppVeyor)?
- Both Travis-CI and Circle-CI have been used for PyTorch.

C: What computing platform combinations are tested on their CI? E.g. Windows 10, Cygwin, Linux, Mac, GCC, Clang

- Linux, Clang, Mac, and Gcc are all tested on their CI according to the commits.

# 3. Software architecture in your own words

A: How would you add / edit functionality if you wanted to? How would one use this project from external projects, or is it only usable as a standalone program?

- Pytorch is incredibly useful in adding/editing functionalities, specifically in its dynamic graphing system. You can use tenser, nn, etc to get started on applying it to existing and new projects.

B: What parts of the software are asynchronous (if any)?
- Not applicable, no asynchronous parts.

C: Please make diagrams as appropriate for your explanation
- Unnecessary, asynchronous.

D: How are separation of concerns and information hiding handled?
- Tensors control the information and share it with the numpy structures. Not much concern of the hiding of information since models are built locally. This is unlike other technlogies that deal with publishing applications online.

E: What architectural patterns are used
- Depends on the project being implemented by the user.


F: Does the project lean more towards object oriented or functional components
- All object oriented programming.

# 4. Analyze two defects in the project


There are two major defects that I found in the project.

1: The first defect that I found was that visualizing models in pytorch is fairly difficult. In Tensorflow for example, you can easily use something like tensorboard, which allows you to visualize models directly into the browser. There are third party applications which allow you to access tensorboard with pytorch, but an official tensorboard equivalent would be beneficial for pytorch.

2: The second defect is that you have to track what gradients are needed, and you have to set requires_grad and volatile. Saving and loading the model requires you to write many things to bundle the model, optimizer, and global step. You also can't load old checkpoints, so you have to keep altering your model back and forth.


a: Does the issue require an architecture change, or is it just adding a new function or?

B: Make a patch / pull request for the project to fix problem / add feature

# 5. Demonstration of application of the system

Attached in main.py! Loading random data points and applying gradient descent to an ReLU model. 
