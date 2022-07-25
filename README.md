# project_template

## Directory structure

```
project_name/
├── data
│   ├── processed_data
│   └── raw_data
├── misc
├── reports
│   └── images
├── scripts
│   ├── python
│   └── r
├── project_description.md
├── README.md
└── todo.md
```

## Using this template
The `.gitignore` file has been configured to only track stuff in the scripts
and reports directories (and any markdown files). Note that the images 
directory (inside the reports directory) will also not be tracked.

If you add a new directory and want it to be tracked by git (or if you want
e.g. the `misc` directory to be tracked), you have to explicitly add an
exception to the `.gitignore`  file like so:

```
# start by ignoring all root files and all root directories
/*
/*/

# then explicitly un-ignore the things I want
!.gitignore
!/scripts
!/reports
/reports/images
!*.md
!*.placeholder

# I also want to have following directory to be tracked by git
!/my_new_dir
```

Git doesn't recognise empty directories, so I include a hidden file called
`.placeholder` in all directories to make them show up here

## Using other repositories in your project
Since this template will form a repository of some project, other repositories
(e.g containing useful code) are most easily stored elsewhere (unless you like
using `git submodule`). For instance, you can have a directory called
`code_base` in which you keep repositories that might be useful to one or more
of your projects (N.B. below, any directory that has a README.md file is
supposed to be a repository):

```
.
├── code_base
│   ├── bash
│   │   └── summarise_all_projects
│   │       ├── overview_summary.sh
│   │       └── README.md
│   ├── python
│   └── r
│       ├── base_functions
│       │   ├── some_cool_functions.R
│       │   └── README.md
│       └── plotting_scripts
│           ├── make_my_favourite_plots.R
│           ├── set_theme.R
│           └── README.md
└── projects
    ├── project_name
    ├── different_project
    └── side_project
```

This will have the added benefit that your code in (for example)
`projects/project_name/scripts/my_analysis.R` will use the **same** path to
access the repositories in `code_base` as code sitting in **any other project**
like `different_project` or in `side_project` (e.g. `source
'../../../code_base/r/base_functions/some_cool_functions.R'`. Therefore
whenever you write some code that could be used in other projects, consider
putting it into a separate repository somewhere under the code_base directory. 
