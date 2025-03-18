### To create a django project
django-admin startproject <name of applicatiom>

### How to run django project 
python manage.py runserver 

### DJANGO PROJECT FILES 
1. Manage.py :: command line utility that allows us to interact with our django project : entry file 
2. todolist :: this directory is the python project 
3. __init__.py :: this is an empty file that indicates above directory is a python project
4. asgi.py :: an entry file for ASGI compatible web servers to create your project 
5. wsgi.py :: an entry file for WSGI compatible web servers to create your project
6. setting.py :: settings/configuration for the django project 
7. urls.py :: these url declaration that map to our django app


### How to create an app inside a django project 
python manage.py startapp <name of the app>


   ###JINJA TEMPLATING
This is a syntax used to create djando interfaces 
  - to create templates 
   a. Inside the app folder create a template folder
   b. Inside the templates you can create .html files, .css, .js
   c. To consolidate the templating for our projects , modify the following 
  - set a global templates directory for referencing our templates i.e move the todolist 
    templates folder to the global perspective 
   i.e. root directory level
  - register this change in settings.py for the project under the templates directory settings
               DIRS': [BASE_DIR / 'templates'],

### DATABASES
- Organised collection of data that allows to store, retrieve,update and delete information more efficiently
### TYPES OF DATA BASES
-Relational databases
   They store data in tables : rows(records ) and columns(fields) 
   Tables can be related 
   uses the SQL 
   
- NoSQL Databases 
- InMemory Databases

### WHY USE DATABASES 
1. Persistent data storage 
2. Efficient data retrieval 
3. Data relationship
4. Security and integrity
   
### USING DB'S IN DJANGO
1. Define our models data 
2. Use django migrations commands to convert our models into actual database tables 
3. Object Relational Mappers(ORM'S) to interact with the DB using python code instead of raw SQL statements 
  ### TO CONVERT MODELS TO TABLES 
1. python manage.py makemigrations  appname
2. python manage.py migrate 

### STEPS TO INCLUDE DB PERSISTENCY FOR PROJECTS IN DJANGO
models.py : converted to db tables by django
After defining our models.py 
1/ python manage.py make migrations appname 
2/ python manage.py migrate 

### STEPS TO A DB DATASOURCE 
1. Double click on db.sqlite3 file 
2. or simply from pycharm select the database icon 
3. Click the + sign or the prompt to create the data source 
     (for develoment use sqlite3 )

### HOW TO ADD IMAGES (STATIC)
1. Django uses static directory 
  project-root directory/ => static => images/
2. Add {% load static %} at the top of the html file 
3. Remember to import os 

### DJANGO ADMIN
Create a super user for content management purposes 
1. Register your models in admin.py
2. Create a super admin user for the project
  - python manage.py createsuperuser
3. Visit the link appurl/admin - use the superuser credentials to login credentials

### DJANGO APIS (APPLICATION PROGRAMMING INTERFACE)
Is a set of rules that allows different software apps to communicate with each other 

### Think of an API as a waiter in a restaurant
1. You(Frontend/client) make an order(request)
2. The waiter(API) takes the request to the kitchen(server/backend)
3. The kitchen (server) prepares the food (process the request)
4. The waiter (API) Brings back the meal(response ) to you

### TYPES OF APIS
1. REST API => HTTP method :: whatever you are trying to access is already coded
  - GET :: use this to request data from server (default)
  - POST :: use this to send or save data to servers
  - PUT :: use this to update data on servers
  - PATCH :: use this to update only a section of your data 
  - DELETE :: use this to remove data from our servers
2. GraphQL API => Allows clients/front end to access data only when needed
3. SOAP API => uses XML methods :: it is older but most secure 
4. WebSocket API => Enable real time data transfer (chat applications )

## STEPS TO CREATE AN AP IN DJANGO 
1. Install djangorestframework :: pip install djangorestframework
2. Add djangorestframework as part of the installed apps
3. Make sure you have the models 
4. Have views return data as .json files 
5. 

### JSON (JavaScript object notation)
This is an interchangeable data format that can be used across any application and device 

### AUTHENTICATION AND AUTHORIZATION
Authentication : IDENTITY MANAGEMENT :: WHO IS USING THE APP 
Authorization : USER PRIVILEDGES :: WHAT USER CAN DO ONCE AUTHENTICATED


### STEPS IN CREATING AUTHENTICATION MODEL 
1. Within settings.py of the project settings modify the authentication settings
   - LOGIN_URL :: ## redirect unauthenticated users back to the login screen 
   - LOGIN_REDIRECT_URL :: After login what page will they see 
   - LOGOUT_REDIRECT_URL :: After logout redirect user back to the login screen
2. Create views for the register ,login and logout processes 
3. Create the rendered/ redirected templates 
4. Register the urls to map the authentication functions in urls 
5. Do migrations: python manage.py migrate 







