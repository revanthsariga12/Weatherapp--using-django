# Weatherapp using django
This repo contains implementation of a weather app that uses Open Weather API and Django as a backend framework and hosted on AWS EC2.

### Prequesites:
* [openweatherapi documentation](https://openweathermap.org/current)
* Python
* Django
* requests

# Setup
1. Create a new directory and activate a virtualenv.
2. Install Django framework in that directory.
3. Create our project:

   > python -m django startproject weatherproject

4. Create a new app:

   > python -m django startapp weatherapp

5. Add our app to the INSTALLED_APPS tuple.

## Add Basic URLs and Views
1. Map our Project’s urls.py file to the new app.
2. In our weatherapp directory, create a urls.py file to define our weatherapp’s URLs.
3. Add views, associated with the URLs, in your weatherapp’s views.py; make sure they return a HttpResponse object. Depending on the situation, we may also need to query the model (database) to get the required data back requested by the end user.
## Templates and Static Files
1. Create a templates directory within our project root.
2. Update settings.py to include the paths to our templates.
3. Add a template (HTML file) to the templates directory.
4. Update the views.py file as necessary.
## Models and Databases
1. Update the database engine to settings.py (if necessary, as it defaults to SQLite).
2. Create and apply a new migration and a super user to access admin page.
3. Add an admin.py file in each App that we want access to in the Admin.
4. Create our models for each weatherapp and apply a new migration. (Do this whenever we make any change to a model).
## Forms
1. Create a forms.py file at the weatherpp to define form-related classes; define our ModelForm classes here.
2. Add or update a view for handling the form logic - e.g., displaying the form, saving the form data, alerting the user about validation errors, etc.
3. Add or update a template to display the form.
4. Add a urlpattern in the weatherapp’s urls.py file for the new view.
## User Registration and User Login
1. Create a UserForm add a view for creating a new user.
2. Add a template to display the form and a urlpattern for the new view.
3. Add a view for handling user credentials.
4. Create a template to display a login form and add a urlpattern for the new view.
## Hosting on AWS
1. Create an EC2 instance with AMI ubuntu and rest as default.
2. Instead of using SSH we can use EC2 Instance Connect.

![image](https://user-images.githubusercontent.com/120722376/230352201-98118a8c-75a5-4cde-a2fe-6af75727065d.png)

![image](https://user-images.githubusercontent.com/120722376/230352338-d9852161-f683-4f5c-b7d1-e85fd735c977.png)

3. We have to update the system

   > sudo apt-get update
  
![image](https://user-images.githubusercontent.com/120722376/230352979-bf6d5b35-bbf8-4d68-8375-19dae725233f.png)

4. To get our code from reposiory we have to clone it.

   > git clone https://github.com/revanthsariga12/Weatherapp--using-django.git

![image](https://user-images.githubusercontent.com/120722376/230353960-9edaf87a-cc61-4bfd-a8f1-ebac147bd169.png)

5. Switch to our project folder.

![image](https://user-images.githubusercontent.com/120722376/230355091-3e12e025-3394-4e30-80ac-b6896d0efd22.png)

6. We have to install python, pip and django.
  
   > sudo apt install python3-pip -y
 
![image](https://user-images.githubusercontent.com/120722376/230355472-0230ec4d-c3d7-4300-9453-215b22704495.png)

   > pip install django
   
![image](https://user-images.githubusercontent.com/120722376/230355851-4deadc3d-43f1-4dde-88b7-50a187741fb3.png)

7. To run our application, but we can't our application because we are in EC2 instance and we have to configure our security group which is attached to EC2 instance to allow port 8000.

   > python3 manage.py runserver
   
![image](https://user-images.githubusercontent.com/120722376/230356339-cc0170e2-d295-46a7-bcd3-396ba5dea005.png)


8. We can use this command to run our server.

   > python3 manage.py runserver 0.0.0.0:8000

![image](https://user-images.githubusercontent.com/120722376/230357824-6f918729-c8e8-498f-9694-b07817e46122.png)

9. We have to add inbound rule in our security group to allow port 8000 So, we add simply a inbound route to allow all traffic.

![image](https://user-images.githubusercontent.com/120722376/230358620-6c0b9fb9-87ca-4d3c-a760-ca69af674bb4.png)

10. We have to allocate our public ip to ALLOWED_HOSTS in settings.py

11. If we enter the public ip with port num we can access our weatherapp where can add our cities to know their current temperatures and delete it.

![image](https://user-images.githubusercontent.com/120722376/230361343-7a075dc3-166e-455f-b80b-9ddf339f764f.png)


