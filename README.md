# FMS_BitterKola
A Hallowgate project

[![Software License][ico-license]](LICENSE.md)

## Description
FMS_BitterKola is a File Management System, meant to reduce or eliminate the manual handling, transfer and storage of file in an Organization. It creates a close structure to share and manage files and file folders within an organization.

## Features (Most are not implemented yet, and come serve as development road map)
* Based on Laravel 5.1 [LTS]
* Theme engine using
* Includes 3 themes
* Custom Error pages: 
    * 403: Forbidden access.
    * 404: Page not found.
    * 500: Internal server error.
* Context sensitive help.
* Authentication & Authorization.
    * User authentication using Laravel's default model and middleware.
    * Role based authorization
        * User login.
        * User registration.
        * Reset forgot password.
    * User based permissions.
    * Dynamic assignment of permissions to application routes with matching authorization module.
    * Full management of users, roles, permissions & routes.
    * Automatically refresh role assignment on user login.
* Dynamic and security-aware menus system and breadcrumb trail. Menu editor included in the admin section
* Audit log of user actions.
    * Allows to "replay" some user actions.
    * Allows to hook a custom data parser and blade partial to render the "replay" data.
* Flash notifications
* Advanced datatables
* CRUD widgets, datatable, grids, and forms
* User profile with Gravatar integration
* Gulp and Elixir ready to compile and minimize Sass & CoffeeScript.
* Laravel Exception Recorder and Notifier using [LERN] with admin pages to view logged errors and link to user.
* Bootstrap v3.3.4.
* Font-awesome v4.4.0.
* Ionicons v2.0.1.
* jQuery v2.1.4.
* jQuery UI v1.11.4, two themes included: Base and Trontastic.
* Select2 v4.0.0
* Select2 Bootstrap Theme v0.1.0-beta.4



## Dependencies
* [PHP](http://php.net/supported-versions.php) >= 5.5.9
* [Composer](https://getcomposer.org/)
* [Node.js](https://nodejs.org):
* [npm](https://www.npmjs.com/):


## Installing

### Clone a copy
There are multiple ways to acquire a copy. You can download a ZIP archive, clone the project and finally fork your own repository then clone it.

### Fetch dependencies

#### Composer
This project includes the file 'composer.lock'. The purpose of the 'composer.lock' file is to lock the version of the various
packages needed by a project as this one. By using the included lock file you are sure to use the same version of those 
packages as were used during the design. 

Fetch all dependencies using *composer* by issuing one of the following commands depending on which environment you are 
trying to configure:

For a development environment use:
```
composer install
```


#### Node.js
Fetch all dependencies for Node.js using *npm* by using the following command:

```
npm install
```

### Basic configuration

#### Create your *.env* file
Create a *.env* file from the example supplied.

For example in the Development environment use:
```
cp .env.example-dev .env
```

#### Create your *.settings* file
Create a *.settings* file from the example supplied.

For example in the Development environment use:
```
cp .settings-development.example .settings-development
```


### Basic configuration

#### Generate application key
Generate the unique application key:
````
./artisan key:generate
````

#### Grant permissions to some directories. 
Either grant permission to all users, or just to the Web Server user by making it a member of the group that owns these folders.
````
chmod -R ugo+rw storage/
chmod -R ugo+rw bootstrap/cache/
````

#### Review default configuration
Review and edit the *.env* file and all the files under */config*. Paying particular attention to */config/app.php* and 
*/config/database.php*.



### Migration
After having configured your database settings, you will want to build the database.
 
If you kept the default database settings your will first have to initialize the SQLite file
```
touch storage/database.sqlite
```

To run the migration scripts run this command
 ```
 ./artisan migrate
 ```
 
 To seed the database run the command below
 ```
 ./artisan db:seed
 ```

### First login and test
You should now be able to launch a Web browser and see your new Web application. To log in using the *root* account
the default password is *Password1*. Please change it ASAP.


## Configuration

### Authentication & Authorization
During the installation the database seeder scripts created a few things to help get started:

* The super user *root*.
* The roles *admins* and *users*.
* The permissions *basic-authenticated*, *guest-only* & *open-to-all*.

Additionally, on a development environment a few more test users and permissions would have been created.

The relationship between users, roles & permissions is relatively simple: users are assigned roles (many-to-many)
and roles are assigned permissions (many-to-many). This enables a simple role based permission assignment system.

Permissions can be directly assigned to individual users if needed.


 
Once *Routes* are assigned a single *Permission* each and permissions are assigned to *Roles* and finally *Users* are 
granted *Roles*, then the matching *AuthorizeRoute* middleware can authorize or block access to all routes for both 
guest and authenticated users. This feature will probably not be used by any site user or even administrators,
but by the site developer(s). In fact one of the first things that I would recommend is to restrict all routes
to the *Route* management pages to a permission given to developers only. What this feature does is make 
the authorization process very flexible, powerful and easy to change on the fly.
  
Some important hard-set rules to note are:

* Except when specifically stated otherwise below, routes, permissions, roles and users can be disabled.

##More Information to be added as the project progresses.