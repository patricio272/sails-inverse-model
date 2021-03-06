![enter image description here](http://sailsjs.org/images/bkgd_squiddy.png)

# Inverse modeling for SailsJS & Waterline

[![Build Status](https://travis-ci.org/juliandavidmr/sails-inverse-model.svg?branch=master)](https://travis-ci.org/juliandavidmr/sails-inverse-model)

## Sails-inverse-model is an module that helps you generate models, controllers and views SailsJS from a any database.

> Available for PostgreSQL and MySQL :)

This NPM also provides all the functions necessary to convert between different data types.

- [Installation](#installation)
- [Usage](#Usage)
- [Import](#Import)

--------------------------------------------------------------------------------

## Installation

Linux or MacOS

```bash
$ sudo npm install sails-inverse-model -g
```

Microsoft Windows

```bash
$ npm install sails-inverse-model -g
```

## Usage

In the bash o cmd:

```bash
$ sails-inverse-model --help
Generate models, controllers and views (MVC) for Sails.js from the database any.

                .-..-.                                                                      

Sails-inverse-model    <|    .-..-.    v. 1.1.4                 
                        |                                                                   
        ~    ~   ~     /|.                                                                    
           ~  ~       / ||                                                                    
             ~  ~   ,'  |'                                                                 
                 .-'.-==|/_--'                                                               
                 `--'-------'                                                                
    __--___--___---___---___--___---___--___                             
  ____---___--___---___--___---___--___-__---___                       

 -----------------------------------------------------------------                        
 :: Sun Jul 17 2016 10:25:35 GMT-0500 (COT)                                                        
 -----------------------------------------------------------------                        
Example:
  $ mkdir sails-output
  $ cd sails-output
  $ sails-inverse-model -u postgres -p root -d almacen -t pg -m -v -c

User         : postgres
Password     : root
Database     : almacen
Host         : localhost
Pluralize    : No pluralize
Models       : /home/julian/Documents/sails-output/models
Views        : /home/julian/Documents/sails-output/views
Controllers  : /home/julian/Documents/sails-output/controllers
DB           : pg
Schema (pg)  : public
=====================================
Complete views.
=====================================
Complete Models.
=====================================
Complete Controllers.

    Note: Copy models      => your/project_sails/api
          Copy controllers => your/project_sails/api
          Copy views/*     => your/project_sails/views/
 Then:
 $ cd your/project_sails/
 $ sails lift

 More info: https://github.com/juliandavidmr/sails-inverse-model
 -----------------------------------------------------------------                        
Options
  -u, --user         User of database
  -p, --pass         Password of database
  -d, --database     Database name
  -h, --host         Host server                 Default: localhost
  -m, --models       Folder output models        Default: Folder actual
  -c, --controllers  Folder output    controllers Default: Folder actual
  -v, --views        Folder output    views       Default: Folder actual (Experimental)
  -l, --lang         Pluralize models and controllers: es|en|fr  Default: no pluralize
  -t, --type         Type gestor database: mysql|postgres        Default: mysql
  -s, --schema       Schema of database postgres: Default: public (Only PostgreSQL)
```

# MySQL

```bash
$ sails-inverse-model -u root -p root -d mydbmysql -m -v -c
User         : root
Password     : root
Database     : mydbmysql
Host         : localhost
Pluralize    : No pluralize
Models       : /home/julian/Documentos/Project/models
Views        : /home/julian/Documentos/Project/views
Controllers  : /home/julian/Documentos/Project/controllers
DB           : mysql
Schema (pg)  : public
2 tables
==
Complete views.
==
Complete Models.
==
Complete Controllers.
```

# PostgreSQL

Go to folder of project SailsJS and:

```bash
$ sails-inverse-model -u postgres -p root -d almacen -t pg -m -v -c
User         : postgres
Password     : root
Database     : almacen
Host         : localhost
Pluralize    : No pluralize
Models       : /home/julian/Documentos/Node_Projects/sails-inverse-model/models
Views        : /home/julian/Documentos/Node_Projects/sails-inverse-model/views
Controllers  : /home/julian/Documentos/Node_Projects/sails-inverse-model/controllers
DB           : pg
Schema (pg)  : public
=====================================
Complete views.
=====================================
Complete Models.
=====================================
Complete Controllers.
```

## Import ##

_Step 1:_

```bash
$ npm install sails-inverse-model --save
```

_Step 2 with MySQL_

```js
var sim = require('sails-inverse-model');

var config = {
  host: "localhost",
  database: "almacen",
  user: "root",
  pass: "root",
  port: 3306
}

var folder_controllers = "/your/project/sails/api/"; //if folder_models == "" then: no generate controllers
var folder_models = "/your/project/sails/api/"; //if folder_models == "" then: no generate models
var folder_views = "/your/project/sails/"; //if folder_models == "" then: no generate views
var plurallang = "es"; //en|es|fr

sim.generatemy(config, folder_models, folder_controllers, folder_views, plurallang);
```

_Step 2 with PostgreSQL_

```js
var sim = require('sails-inverse-model');

var config = {
  host: "localhost",
  database: "example",
  user: "postgres",
  pass: "root",
  port: 5432,
  schema: "public"
}

var folder_controllers = "/your/project/sails/api/"; //if folder_models == "" then: no generate controllers
var folder_models = "/your/project/sails/api/"; //if folder_models == "" then: no generate models
var folder_views = "/your/project/sails/"; //if folder_models == "" then: no generate views
var plurallang = "es"; //en|es|fr

sim.generatepg(config, folder_models, folder_controllers, folder_views, plurallang);
```

### Then navigate to the output folder and can find the js generated.

### Fork me :)

--------------------------------------------------------------------------------
