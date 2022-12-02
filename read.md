HOW TO START THE SERVER
-
***********************

cd "[project dir]"
1. django-admin startproject <password-generator-project(project name)
2. using settings "<password-generator-project(project name)"
3. python manage.py runserver


HOW PROJECTS SETUP:
-
*****************
password_generator : this is main django folder project dir
different file details are explained below

1. asig.py: important when we deploy the website
2. wsgi.py: important when we deploy the website
3. setting.py: project location secret key etc
4. urls.py: contains 

HOW TO ADD APP IN YOUR DJANGO PROJ
-
1. Create generator package through command line.
    -
    > python manage.py startapp generator
2. Project details will be created as below 
   - 
   - Migration > __init__.py
   - __init__.py
   - app.py
   - admin.py
   - model.py
   - tests.py
   - views.py

URL
-
    1.locate url.py file in DJANGO proj app
    2. import respective project package and module 
        > from generator import views
    3. locate urlpatterns dictionary
        > urlpatterns = [
            path("", views.home),
            path("eggs", views.eggs)
           ]
    4. locate views.py in APP dir and add function with request and return

TEMPLATE
-
    this section is for main HTML website view part
    1. create templates folder
    2. add app specific template folder for eg. 'generator' here
    3. inside create HTML template
    4. navigate to views.py and return your HTML response.

REFERENCING THE URL NAME WITH OTHER NAME
-
      1. go to DJANGO urls.py and add path
         > path("generatedpassword", views.password, name="password")
      2. Now this [ name = "password" ] will reference to the URL in HTML page.
      3. views.py password function will looks like below
         > def password(request):
            return render(request, "generator/password.html")
      3. navigate to HTML password.html will have reference in action with url replacement
         > action="{% url 'password' %}"

CHAPTER3: Making Random Password
-
      Modify views.py and password functions to return the password to HTML page.

USING FORM DATA
-
      request.GET.get('length') : we can get data from one sender HTML to second

INSTALL GIT
--
      in macbook https://git-scm.com/download/mac
      > /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"