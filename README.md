# nexus-cli
A command line interface for Nexus

# Setup

As seen in http://click.pocoo.org/7/setuptools/#setuptools-integration
```
   <install conda - https://conda.io/projects/conda/en/latest/user-guide/install/index.html>

   conda create -n nexus-cli python=3.5
   conda activate nexus-cli
   git clone https://github.com/BlueBrain/nexus-cli
   cd nexus-cli
   git checkout nexus_v1
   pip install --editable .
```

or with straight from github:
```
    conda create -n nexus-cli python=3.5
    conda activate nexus-cli
    pip install git+https://github.com/BlueBrain/nexus-cli
```

Start using the CLI:
```
    nexus --help
    nexus --version
```

# Currently supported features

## profiles
* create: adding a new profile (create <name> <URL>)
* delete: deleting a locally registered profile (delete <name>)
* list: list locally registered profiles (list), 
* select: select a locally registered profile (select <name>)
* current: show currently selected profile

## auth
* login: initiates an interactive login, prompting the user's name, password and client ID for the selected realm
* set-token: saves a token in the currently selected profile
* view-token: prints token from the currently selected profile (encoded, decoded, expiry time)

## orgs
* list: list all organizations
* create: create a new organization
* fetch: show the json payload of an organization
* update: update an organization (name and description only!)
* deprecate: deprecate an organization
* select: select the organization to use in subsequent calls of the CLI (local to the currently selected profile)
* current: show the currently selected organization

## projects (local to a specific organization)
* list: list all projects
* create: create a new project
* fetch: show the json payload of an project
* update: update an project (name and description only!)
* deprecate: deprecate an project
* select: select the project to use in subsequent calls of the CLI (local to the currently selected profile)
* current: show the currently selected project

## resources (local to a specific organization and project)
* list: list all resources
* create: create a new resource
* fetch: show the json payload of a resource
* update: update a resource
* deprecate: deprecate a resource

## schemas (local to a specific organization and project)
* list: list all schemas
* create: create a new schema or import a collection of schemas stored in a directory
* fetch: show the json payload of a schema
* update: update a schema
* deprecate: deprecate a schema

## views (local to a specific organization and project)
* list: list all views
* create: create a new ElasticSearchView
* fetch: show the json payload of a view
* update: update a view configuration
* deprecate: deprecate a view
* query-es: run a query against a specific ElasticSearch view
* query-sparql: run a query against the default SPARQL view

## acls
* list: list acls
* show-identities: show identities that can be added in ACLs
* show-permissions: show permissions that can be added in ACLs
* make-public: make a project public to the world
* append: add permission to a given identity (group, user, authenticated, anonymous)
* subtract: remove permission from a given identity (group, user, authenticated, anonymous)

## realms
* list: list all realms
* create: create a new realm
* fetch: show the json payload of a realm
* update: update a realm configuration
* deprecate: deprecate a realm
* select: select the default realm
* current: show the selected realm

## Funding & Acknowledgment

The development of this software was supported by funding to the Blue Brain Project, a research center of the École polytechnique fédérale de
Lausanne (EPFL), from the Swiss government's ETH Board of the Swiss Federal Institutes of Technology.

Copyright © 2015-2022 Blue Brain Project/EPFL

