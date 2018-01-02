# Reimplement baseline ROLO

## Contents
- [Related work & code](#related-work-code)


## Related work & code

[Project page](http://guanghan.info/projects/ROLO/)

[Project code](https://github.com/Guanghan/ROLO)

[Paper on Arxiv](https://arxiv.org/pdf/1607.05781.pdf)


## Reimplement
### Project location
ssh://tianling@AISIG01:/home/tianling/Projects/ROLO

### Migrating to Tensorflow 1.0
The original project code was written with Tensorflow 0.11.0, which I think is too old for further development. However, Tensorflow does provide a script for [migrating projects to 1.0 version](https://www.tensorflow.org/install/migration), so I decide to try it out

The project is written in python2

#### TODO:
 - [ ] virtualenv: `py2\_tf\_1.0\_gpu`
 - [ ] recompile python
    - https://stackoverflow.com/questions/1446347/how-to-find-out-if-python-is-compiled-with-ucs-2-or-ucs-4 
    - https://stackoverflow.com/questions/40500194/install-tensorflow-using-pip#comment68267151_40500194
 - [x] convert script
