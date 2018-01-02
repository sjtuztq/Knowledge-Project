# Setting up python environment
This article focus on setting up a python environment on **any linux machine** for **coding**.
## System Python
Working with system python is always painful. I highly recommend using your own python distribution. Anaconda/Miniconda is one of the best choices.

## Conda Python
Miniconda and Anaconda are both provided by Anaconda Inc. Anaconda has more packages preinstalled. Aside from that, they have no difference.

I like `Miniconda` for it is much smaller and easy to access from any machine. You can even include it in your project!

In the following parts, I will use `Miniconda` to demonstrate how to set up a python environment for coding.
### Normal virtualenv
In most cases, virtualenv works just fine, and it is certainly the best choice as long as it works.
```bash
# for miniconda3
python3 -m venv $your_env_name
# for miniconda2
python2 -m virtualenv $your_env_name
```

### Conda virtualenv
I have ran into cases when normal virtualenv doesn't work. Then I found this solution, which also looks neat.
Creating virtualenv with conda is a little different. A full guide can be found [Create virtual environments for python with conda](http://uoa-eresearch.github.io/eresearch-cookbook/recipe/2014/11/20/conda/)
```bash
# create venv, under miniconda2/envs/$env_name
conda create -n $env_name 
# activate
source miniconda2/bin/activate $env_name
# deactivate
source deactivate
```
This looks neat because it keeps all venv in one place under miniconda directory. You can put the activation command into a script and **SOURCE** it (if you execute it, the environment prompt will not appear)

However, virtualenv created in this way does not support pip package management(No tuna mirror!). It is a pain in the ass to install packages. Consult [Create virtual environments for python with conda #6](http://uoa-eresearch.github.io/eresearch-cookbook/recipe/2014/11/20/conda/) 
