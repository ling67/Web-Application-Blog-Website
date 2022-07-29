# Web-Application-Blog-Website

## Describption


## Design


## Detail introduction
 PPT 

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

* Method 2: set your email and application password manually when you run the project.

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


## Related technology


