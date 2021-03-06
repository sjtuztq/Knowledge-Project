# Projects One Page
## Contents
 - [Project list](#project-specifications)
 - [Project specifications](#project-specifications)

## Project list
 - [2018_01-Final_Year_Project](2018_01-Final_Year_Project)

## Project specifications
### Definition
A project is a group of stages, whose final target is a paper. Each stage is represented by a subproject.

Basic stages are:
- prerequesites(optional)
- survey
- baseline
- experiment
- paper
### Naming protocol
#### Project name
Project naming should be consistent. For now, project naming rules are:
 > For projects, name should be `year_month-Name`, where each word in Name should be capitalized in the 1st letter
 > For sub-projects, name should be `number-stage-Name(optional)`, 

 - Project example: `2018_01-Final_Year_Project`
 - Sub-project: `01-baseline_ROLO`
### Directory organization
#### In knowledge project
Only markdown files should be included. Under each project/subproject folder, a `README.md` must exist as a `project one page`

Also, there should be a folder named `Weekly_Trac`, TODO lists must only be included in the weekly trac files.
#### In real server/PC
A project exist in server/PC as a git repo. Directories should be organized in such way:
```
Project_Root (No code)
├── Sub_Project (Code)
│   ├── code
│   ├── tools
│   ├── data
│   ├── exp_classify
│   │   └── V00
│   ├── exp_tracking
│   │   └── V00
│   └── README.md(copy from KP)
├── Sub_Project (Paper)
├── Project_Trac
└── README.md(copy from KP)
```

### Coding style
Python: [Google Python Style Guide](https://google.github.io/styleguide/pyguide.html#Naming)

### File management
Use `YAML` files for configurations
Use `JSON` files for data

### Paper Reading
#### Annotation
| Color | Meaning |
| ---   | ---     |
| Yellow | Question Definition Related|
| Blue   | Related work        |
| Green  | Method description  |
| Red    | Contribution        |
| Pink   | Experiment result   |
| Orange | Questions           |

