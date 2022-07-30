# Web-Application-Blog-Website

## Describption

* This project mainly use flask to implement the Blog Website. A blog is a type of website that is updated regularly with new content. Most blogs contain short, informal articles called blog posts. In our project support lots of features: User's register and login, post blog, edit blog, comment the blog, follow other users.
* In this Blog Website we use Flask framework to implement. Flask is a micro web framework written in Python, it is Easier to use for simple cases.

## Related technology

* Front end: html, css
* Back end: Flask, REST API
* Database
* Security: Token Authentication

## Design

### modules design

* User Authentication
* User Role
* User Profiles
* Blog Posts
* Followers
* User Comments

### Database design

<img width="500" alt="image" src="https://user-images.githubusercontent.com/93315926/181863066-aabea854-2dd4-4408-8951-71e808da6089.png">

## How to run the project

**Step 1. download the repo.**
```
$ git clone https://github.com/miguelgrinberg/flasky
```

**Step 2. go to project folder**
```
$ cd flasky
```

**Step 3. set virtual environment**
```
$ python3 -m venv venv
```

**Step 4. activate virt. environment**
```
$ . venv/bin/activate
```

**Step 5. install requirements and dependencies**
```
$ pip install -r requirements/prod.txt
```

**Step 6. -export environ. variable**
```
$ export FLASK_APP=flasky.py
```

**Step 7. -set database and migrations.**
```
$ flask db stamp head
$ flask db migrate
$ flask db upgrade
```

**Step 8. - run app**
```
$ flask run
```
Then
- go to http://127.0.0.1:5000/
- register using email and pwd.

**Step 9. Solve can not receive the comfirm email problem**

Now after you register, if you do not receive the confirm link, you have two ways to solve it.
I think it because the google has not provide service.

* Method 1: change the database directly, set your user as confirmed statue manually. 

```
$ sqlite3 data-dev.sqlite
$ UPDATE users SET confirmed=1 WHERE id=1;
```

Then re-run app
```
$ flask run
```

* Method 2: set your email and application password manually when you run the project.（how to set application password see Appendix ）

```
$ export MAIL_USERNAME=********
$ export MAIL_PASSWORD=********
$ flask run
```
Then
- go to http://127.0.0.1:5000/
- re-register using email and pwd.

Now you can receive the comfirm email and login, but you cannot post the blog.

**Step 10. change the user role in database manually**
```
sqlite3 data-dev.sqlite
update users set role_id = 3 where id = 1;
```

Now, you can post your blog.

## User Interface Presentation

* Register and Login

<img width="646" alt="image" src="https://user-images.githubusercontent.com/93315926/181683344-c0c8cfd1-3bb3-4cd5-b7e1-c1741ce655fd.png">

* User profile Edit
<img width="400" alt="image" src="https://user-images.githubusercontent.com/93315926/181683170-374f3ddc-6c29-4f38-a33c-7c654f793380.png">

* Post and Edit Blog
<img width="400" alt="image" src="https://user-images.githubusercontent.com/93315926/181683095-89fba136-2a2e-480e-b171-ff2b2d987f20.png">

## Appendix

How to set a App Passwords: https://support.google.com/accounts/answer/185833.

* step1: Setting a App Passwords.(eg. If you use visual studio code, setting application:visual studio code, password: google automatic generate)
* step2: Use the gmail account and App passwords in your code.
* step3: Run the code in visual studio code.

## Detail Introduction

[Blog_Website_Ling_Chen](https://docs.google.com/presentation/d/1Lee_zVk9rq1S_nsPHbsHAm5eYuFxA-HceGm09rBvWMM/edit#slide=id.g25f6af9dd6_0_0)



