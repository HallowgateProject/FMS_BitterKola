# FMS_BitterKola
A Hallowgate project

## Description
FMS_BitterKola is a File Management System, meant to reduce or eliminate the manual handling, transfer and storage of file in an Organization. It creates a close structure to share and manage files and file folders within an organization.

## Features (Most are not implemented yet, and come serve as development road map)
* Based on Laravel 5.1 [LTS]
* Includes 3 themes
* Custom Error pages: 
    * 403: Forbidden access.
    * 404: Page not found.
    * 500: Internal server error.
* Authentication & Authorization.
    * Role based authorization
        * User login.
        * User registration.
        * Reset forgot password.
    * User based permissions.
    * Full management of users, roles, permissions & routes.
* Bootstrap v3.3.4.
* Font-awesome v4.4.0.
* Ionicons v2.0.1.
* jQuery v2.1.4.

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
Grant permission using
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
Launch a Web browser and see your new Web application. To log in using the *root* account
the default password is *Password1*. Please change it ASAP.


## Configuration

### Authentication & Authorization
During the installation the database seeder scripts created a few things to help get started:

* The super user *root*.
* The roles *admins* and *users*.
* The permissions *basic-authenticated*, *guest-only* & *open-to-all*.

Permissions can be directly assigned to individual users if needed.
  
##More Information to be added as the project progresses.