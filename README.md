# Terraform Beginner Bootcamp 2023

## Semantic Versioning :mage:

This project is going to utilize semantic versioning for its tagging
[semver.org](https://semver.org)

Given a version number **MAJOR.MINOR.PATCH**, increment the:

- **MAJOR** version when you make incompatible API changes
- **MINOR** version when you add functionality in a backward cmpatible manner
- **PATCH** version when you make backcompatible bug fixes


## Install the Terraform CLI

### Considerations with the Terraform CLI changes
The terraform CLI installation instructions have changed due to gpg keyring changes. Need to refer to the latest install CLI insturctions via Terraform Docs and change the scripting for install

[Install Terraform CLI](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)


### Refactoring into Bash Scripts
While fixing the Terraform CLI gpg depreciation issues, noticed that bash scrips steps were a considerable amount more code. Solution was to create a bash script to install the Terraform CLI
- Tidy the Gitpod Task File ([.gitpod.yml](.gitpod.yml))
- Bash script is located here [./bin/install_terraform_cli](./bin/install_terraform_cli)

### Working with Environment Variables
#### `ENV` command
In Gitpod, you can list all env variables using the `env` command
- grep can be used to filter specific env var eg `env | grep terraform`

#### Setting & Unsetting Env Var
From the terminal,
Set using `export {variable name}={value}`
Unset using `unset {variable name}`

Temp setting an env var when running a command
```sh
AWS_ACCESS_KEY='xxxx' ./bin/print_message
```

Within a bash script we can set env var without writing export
```sh
#!/usr/bin/env bash
AWS_ACCESS_KEY='xxxx'

echo $AWS_ACCESS_KEY
```

#### Printing Environment Variables
Can be done using `echo $AWS_ACCESS_KEY`

#### Environment Variable Scoping
Each terminal session has it's own env var..it's scope dependendent

If you want to persist env vars, you need to set env vars in the bash profile eg `.bash_profile`

- To persist env vars in Gitpod
    - Store them in Gitpod secrets storage
    ```
    gp env AWS_KEY='sxxx
    ```
    - You can also set it in `.gitpod.yml`