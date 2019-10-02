# Conda instruction for UTS iHPC
## Step 1: Anaconda or Miniconda?
- __Anaconda®__ is a package manager, an environment manager, a Python/R data science distribution, and a collection of over 1,500+ open source packages. 
- Want to install conda and use conda to install just the packages you need? Get __Miniconda__.
## Step 2: How to install conda?
To install conda on your server correctly, please follow the related part in the UTS iHPC documentation strictly.  
[https://ihpc.research.uts.edu.au/pages/documentation_rhel75/applications/anaconda](https://ihpc.research.uts.edu.au/pages/documentation_rhel75/applications/anaconda)  
## Step 3: How to use conda?
With conda, you can create, export, list, remove, and update environments that have different versions of Python and/or packages installed in them. Switching or moving between environments is called activating the environment. You can also share an environment file.
### 3.1 Create a new environment
By default, environments are installed into the `envs` directory in your conda directory.  
1. To create an environment:  
`conda create --name myenv`
> Replace `myenv` with the environment name.  


2. To create an environment with a specific version of Python:  
`conda create -n myenv python=3.6`
3. To create an environment with a specific version of Python and multiple packages:  
`conda create -n myenv python=3.4 scipy=0.15.0`
### 3.2 Activate the new environment
1. Verify the installed environment:  
`conda env list`
2. To activate a certain environment:  
`conda activate myenv`
3. To deactivate the environment:  
`conda deactivate myenv`
### 3.3 Cloning an environment
You can make an exact copy of an environment by creating a clone of it.  
1. To clone a certain environment:  
`conda create --name myclone --clone myenv`
> Replace myclone with the name of the new environment. Replace myenv with the name of the existing environment that you want to copy.  


### 3.4 Install packages
1. To install packages with conda:  
```conda install pkg``` 
> Replace pkg with the names of the packages you want to install.  


2. To install packages with conda:  
`pip install pkg`

> Issues may arise when using pip and conda together. When combining conda and pip, it is best to use an isolated conda environment. Only after conda has been used to install as many packages as possible should pip be used to install any remaining software. If modifications are needed to the environment, it is best to create a new environment rather than running conda after pip.  


### 3.5 Sharing an environment
You may want to share your environment with someone else, so they can re-create a test that you have done. To allow them to quickly reproduce your environment, with all of its packages and versions, give them a copy of your `environment.yml` file.
 
1. Activate the environment to export:  
`conda activate myenv`
2. Export your active environment to a new file:  
`conda env export > environment.yml`
> This file handles both the environment's pip packages and conda packages.  


3. Create the environment from the environment.yml file:  
`conda env create -f environment.yml`
### 3.6 Remove an environment
1. To remove an environment, run:  
`conda remove --name myenv --all`  
You may instead use:   
`conda env remove --name myenv`  
  
__Above is the simple instrution of using conda for UTS iHPC, all the content is obtained by reference to the documentation of [UTS iHPC](https://ihpc.research.uts.edu.au/pages/documentation_rhel75) and [conda](https://conda.io/projects/conda/en/latest/index.html).__  
 __Note:__ If you have any doubt about this instruction, please check the corresponding part from the original documentation.  
   
   
--  
__Jiwei Wang__  
02/10/19
