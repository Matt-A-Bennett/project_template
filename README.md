# project_template

## directory structure

```
.
├── data
│   ├── processed_data
│   └── raw_data
├── description.md
├── misc
├── models
├── README.md
├── reports
│   └── figures
├── scripts
│   ├── python
│   └── r
└── todo.md
```

## using this template
Once you have forked this template as a repository and cloned it onto your
local machine, the first thing to do is uncomment the .gitignore file so it
looks like this:

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
```

This will mean that git only tracks stuff in the scripts and reports
directories. Note that the figures directory (inside the reports directory)
will also not be tracked.
