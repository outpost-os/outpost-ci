<!--
SPDX-FileCopyrightText: 2024 Ledger SAS

SPDX-License-Identifier: Apache-2.0
-->

# Outpost-OS reusable workflows for Python packages

[![REUSE status](https://api.reuse.software/badge/github.com/outpost-os/pipeline-python)](https://api.reuse.software/info/github.com/outpost-os/pipeline-python)

## Introduction

This repository hold the python-related reusable workflows in order to limit redundancy between each python package CI/CD usage.

This repository also impose some restrictions on python packages quality and tooling for Outpost, such as:

   - using ToX for manipulating python venv and proper targets
   - having the following tox targets:

      - unittests for unit testing
      - docs for doc generation
      - lint for linting

## Workflows

The following workflows exists:

   - doc.yml: built for running tox docs target
   - unittest.yml: built for executing tox unittests target
   - lint.yml: built for executing tox lint target

## reusable workflows usage

Reusing workflows is made in the way described in [Github docs](https://docs.github.com/en/enterprise-cloud@latest/actions/using-workflows/reusing-workflows)

the lonely required input, shared by all workflows is `python-version`, that
define the python release to execute the workflow on.

A typical usage is the following:

```
uses: outpost-os/pipeline-python/.github/workflows/lint.yml@v1
    with:
      python-version: '3.12'
```
