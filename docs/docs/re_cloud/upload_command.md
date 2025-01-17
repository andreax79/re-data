---
sidebar_position: 3
---

# Uploading reports

re_cloud library has one command for uploading all the reports: `re_cloud upload`

You can upload different reports with this command. Here is the list of how to do it: 😊

## Currently supported

### dbt-docs

```
re_cloud upload dbt-docs --name TEXT --project-dir TEXT

Options:
  --project-dir TEXT  Which directory to look in for the dbt_project.yml file.
                      Default is the current working directory and its parents
  --name TEXT         Name of the upload used for identification
```

You don't need to pass project-dir paramter if calling this command from witin dbt main directory. Otherwise pass `project-dir` to upload generated docs from this directory.

### pandas-profiling

```
re_cloud upload pandas-profiling --name TEXT  --report-file TEXT

Options:
--report-file TEXT  Pandas profiling file with html report  [required]
--name TEXT         Name of the upload used for identification
```

For pandas profiling --report-file is required paramter. re_data will upload your docs in `uncommitted/data_docs/local_site/` path then.

### great-expectations

```
re_cloud upload great-expectations --name TEXT

Options:
  --name TEXT  Name of the upload used for identification
```

For great-expectation `cd` to great-expectations directory. re_data uploads 


### jupyter notebook

Usage: re_cloud upload jupyter-notebook --name TEXT  --file TEXT

Options:
  --file TEXT  ipynb notebooks file to upload  [required]
  --name TEXT  Name of the upload used for identification
  --help       Show this message and exit.

### re-data

```
re_cloud upload re-data --name TEXT --project-dir TEXT --re-data-target-dir TEXT

Options:
  --project-dir TEXT         Which directory to look in for the
                             dbt_project.yml file. Default is the current
                             working directory and its parents

  --re-data-target-dir TEXT  Which directory to store artefacts generated by
                             re_data Defaults to the 'target-path' used in
                             dbt_project.yml

  --name TEXT                Name of the upload used for identification
```

If you are inside dbt project dir and didn't changed default `target` directory for docs and re_data both `project-dir` and `re-data-target-dir` are optional.


### custom

Using re_cloud you can also upload your custom html files with information about your data. Some of the popular libraries will generate html for you (for example [pandas to_html command](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.to_html.html)) can can html created solely by yourself.

```
Usage: re_cloud upload custom --name TEXT  --file TEXT

Options:
  --file TEXT  custom html file to upload  [required]
  --name TEXT  Name of the upload used for identification
  --help       Show this message and exit.
```

## common parameters

### `name`

Name which you would like to give to the report, this will show in the interface. Names don't need to and often will not be unique, given that in most of the pipelines you will be uploading similar reports every day / hours, etc.

## Help

Are you not familiar with some the mentioned tools and reports mentioned? We include sample reports from all of the tools on re_cloud **[free account 😊](https://cloud.getre.io/#/register)**

If you need any help with setting up the upload, let us know on **[Slack](https://www.getre.io/slack)**, we will try to help right away 😊