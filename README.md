<h1 align="center">Snippets for Flask</h1>
<p align="center"><b>Type Less Copy/Paste More</b></p>

## Boilerplate

This is the most basic flask app, most of the developers start from here.

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def index():
    return "Hello World!"


if __name__ == "__main__":
    app.run(debug=True)
```
## Flask SqlAlchemy
Sample code that people usually include in their file when they use SqlAlchemy. You can use it to initialise SqlAlchemy and configure the web app.
 
```python
from flask_sqlalchemy import SQLAlchemy

#Add this after Flask(__name__)
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///test.db'
app.config['SQLALCHEMY_TRACK_MODIFICATIONS'] = False

db = SQLAlchemy(app)

```

### Database Models

This is how you can create models in Flask.
```python

class TableName(db.Model): 
column_1 = db.Column(db.Integer, primary_key=True)
column_2 = db.Column(db.String(80), nullable=False)
column_3 = db.Column(db.String(12), nullable=False)
```


## Get Data from Database

Get All of the the data from database

```python
data = ClassName.query.filter_by().all()
```

Add data to Database

```python
data_to_send = ClassName(column_1=dataset1, column_2=dataset2) 
db.session.add(data_to_send) 
db.session.commit()
```

Create a Database file

```python
from yourapplicationname import db 
db.create_all() 
exit()
```


## Flask Documentation
[https://flask.palletsprojects.com/en/latest/](https://flask.palletsprojects.com/en/latest/)



## Flask SQLAlchemy Documentation
[https://flask-sqlalchemy.palletsprojects.com/en/2.x/](https://flask-sqlalchemy.palletsprojects.com/en/2.x/)

