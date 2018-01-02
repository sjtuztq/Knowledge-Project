# Reimplement baseline ROLO

## TODO:
 - [x] virtualenv: `py2-tensorflow-gpu-1.0`
 - [x] convert script
 - [ ] run the experiment
 - [ ] align experiment results

## Contents
- [Related work & code](#related-work-and-code)
- [Reimplement Detail](#reimplement-detail)
    - [Code and data](#code-and-data)
    - [Migrating to Tensorflow 1.0](#migrating-to-tensorflow-1.0)
- [Experiment Result](#experiment-result)


## Related work and code

[Project page](http://guanghan.info/projects/ROLO/)

[Project code](https://github.com/Guanghan/ROLO)

[Paper on Arxiv](https://arxiv.org/pdf/1607.05781.pdf)


## Reimplement Detail
### Code and data
code: `ssh://tianling@AISIG01:/home/tianling/Projects/ROLO`

data: `ssh://tianling@AISIG01:/slwork/tianling/data/2018_01_ROLO/OTB30`

The project is written in `python2`
### Migrating to Tensorflow 1.0
The original project code was written with Tensorflow 0.11.0, which I think is too old for further development. However, Tensorflow does provide a script for [migrating projects to 1.0 version](https://www.tensorflow.org/install/migration), so I decide to try it out.


## Experiment Result
