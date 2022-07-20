# project_template

## directory structure

```
.
├── data
│   ├── processed_data
│   └── raw_data
├── misc
├── project_description.md
├── README.md
├── reports
│   └── figures
├── scripts
│   ├── python
│   └── r
└── todo.md
```

## using this template
The `.gitignore` file only has been configured to only track stuff in the
scripts and reports directories (and any markdown files). Note that the figures
directory (inside the reports directory) will also not be tracked.

If you add a new directory and want it to be tracked by git (or if you want
e.g. the `misc` directory to be tracked), you have to explicitly add it to the
`.gitignore`  file like so:

```
# start by ignoring all root files and all root directories
/*
/*/

# then explicitly un-ignore the things I want
!.gitignore
!/scripts
!/reports
/reports/figures
!*.md
!*.placeholder

# I want the following directory to be tracked by git
!/my_new_dir
```

Git doesn't recognise empty directories, so I include a hidden file called
`.placeholder` in all directories to make them show up here

