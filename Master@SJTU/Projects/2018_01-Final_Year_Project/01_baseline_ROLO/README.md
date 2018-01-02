# Reimplement baseline ROLO

## Contents
- [Related work & code](#related-work-code)


## Related work & code

[Project page](http://guanghan.info/projects/ROLO/)

[Project code](https://github.com/Guanghan/ROLO)

[Paper on Arxiv](https://arxiv.org/pdf/1607.05781.pdf)


## Reimplement
### Code and data
code: `ssh://tianling@AISIG01:/home/tianling/Projects/ROLO`
data: `ssh://tianling@AISIG01:/slwork/tianling/data/2018_01_ROLO/OTB30`

### Migrating to Tensorflow 1.0
The original project code was written with Tensorflow 0.11.0, which I think is too old for further development. However, Tensorflow does provide a script for [migrating projects to 1.0 version](https://www.tensorflow.org/install/migration), so I decide to try it out

The project is written in python2

#### TODO:
 - [x] virtualenv: `py2-tensorflow-gpu-1.0`
 - [x] convert script
