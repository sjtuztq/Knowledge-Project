# Reimplement baseline ROLO

## TODO:
 - [x] virtualenv: `py2-tensorflow-gpu-1.0`
 - [x] convert script on new branch
 - [x] merge master
 - [ ] run the experiment
    - [ ] :boom: qsub on AISIG01?
    - [ ]
 - [ ] align experiment results

## Contents
- [Related work & code](#related-work--code)
- [Reimplement Detail](#reimplement-detail)
    - [Code & data](#code--data)
    - [Migrating to Tensorflow 1.0](#migrating-to-tensorflow-10)
- [Experiment Result](#experiment-result)


## Related work & code

[Project page](http://guanghan.info/projects/ROLO/)

[Project code](https://github.com/Guanghan/ROLO)

[Paper on Arxiv](https://arxiv.org/pdf/1607.05781.pdf)


## Reimplement Detail
### Code & data
code: `ssh://tianling@AISIG01:/home/tianling/Projects/ROLO`

data: `ssh://tianling@AISIG01:/slwork/tianling/data/2018_01_ROLO/OTB30`

The project is written in `python2`
### Migrating to Tensorflow 1.0
The original project code was written with Tensorflow 0.11.0, which I think is too old for further development. However, Tensorflow does provide a script for [migrating projects to 1.0 version](https://www.tensorflow.org/install/migration), so I decide to try it out.


## Experiment Result

