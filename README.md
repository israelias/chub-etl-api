<!-- Anchor for Back To Top -->
<a name="readme-top"></a>

<div align="center">
  <a href="https://github.com/israelias/chub-etl-api">
    <img src="https://raw.githubusercontent.com/israelias/cheathub_mono/dev/images/logo_dash_red.png" alt="Logo" width="80" height="80">
  </a>

<h3 align="center">cHub ETL Model and API</h3>

  <p align="center">

Application Serverless ETL Query and Resource API
for [@israelias/cheathub/frontend](https://github.com/israelias/cheathub/tree/master/frontend)
<br />
<a href="https://israelias.github.io/chub-etl-api/"><strong>Explore the docs »</strong></a>
<br />
<br />
·
<a href="https://github.com/israelias/chub-etl-api/issues">Report Bug</a>
·
<a href="https://github.com/israelias/chub-etl-api/pulls">Create a PR</a>
  </p>
</div>

<!-- ABOUT THE PROJECT -->

[//]: # (## About The Project)


[//]: # (<p align="right"><a href="#readme-top">back to top</a></p>)

## Getting Started

> Jump to [mongodb env vars](#database)

<!-- ENVIRONMENT PREREQUISITES -->

### Environment Prerequisites

> The latest releases Python 3.4+ and Python 2.7.9+, as well as the virtual environments `virtualenv` and `pyvenv`,
> automatically ship with PIP

[Source](https://www.dataquest.io/blog/install-pip-windows/#:~:text=The%20latest%20releases%20Python%203.4,have%20this%20advantage%20by%20default.)

- Please have [`python3`](https://realpython.com/installing-python/) globally installed on your machine.

### Installation

* Clone this Repo
    ```sh
    git clone ssh://git@github.com/israelias/chub-etl-api.git
    ```
* Jump into this directory
    ```sh
    cd chub-etl-api
    ```
* Create a Virtual Env
    ```sh
     python -m venv venv   
    ```
* Activate your environment
  ```sh
   source venv/bin/activate 
  ```
* Install existing `requirements`
  ```sh
  (venv) pip install -r requirements.txt
  ```
* Run the development environment
  ```sh
  (venv) python run.py
  ```

<p align="right"><a href="#readme-top">back to top</a></p>

## Available Scripts

### `python run.py`

Serves the Databse backend.\
Runs the backend app in the development mode.\
Open [http://localhost:5000/admin](http://localhost:5000/admin) to view the admin panel in the browser (
ensure `BASIC_AUTH` variables are set).

Open [http://localhost:5000/api/snippets](http://localhost:5000/api/snippets) to view the JSON response format of all
public snippets -- assuming `snippet` objects have been created. Otherwise, use Postman to create documents locally.

The page will reload if you make edits.\
You will also see any errors in the console.

### Deployed Resources

- [/docs](https://israelias.github.io/chub-etl-api/)
- [/admin](https://chub-etl-api.vercel.app/admin)
- [/api/snippets](https://chub-etl-api.vercel.app/api/snippets)

## Database

To recreate this server, the following environment variables are required:

### `MONGOODB_HOST`

A connection string from Mongo Atlas for `Mongo Engine` to connect to remotely.

To recreate:

- Create an account with [MongoDB Atlas](https://www.mongodb.com).
- Create a Cluster named `hub`.
- Create a Database named `cheathubdb`.
- Click `Connect` to generate a connection string.

Set the variable to this connection string:

```python
# env.py
os.environ.setdefault("MONGODB_HOST",
                      "mongodb+srv://<username>:<password>@hub.4kotr.mongodb.net/cheathubdb?retryWrites=true&w=majority")
```

### `SECRET_KEY`

Any key for `Sessions` to work.

Set the variable to this key:

```python
# env.py
os.environ.setdefault("SECRET_KEY", "<your secret key>")
```

### `MONGODB_PORT`

The port to connect to.

Set the variable to this key:

```python
# env.py
os.environ.setdefault("MONGODB_PORT", "5000")
```

### `JWT_SECRET_KEY`

Any string key for JWT to work.

Set the variable to this key:

```python
# env.py
os.environ.setdefault("JWT_SECRET_KEY", "<your JWT secret key>")
```

### `BASIC_AUTH_USERNAME`

Superuser username to access admin panel at `/admin`

Set the variable to this key:

```python
# env.py
os.environ.setdefault("BASIC_AUTH_USERNAME", "<your superuser username>")
```

### `BASIC_AUTH_PASSWORD`

Superuser password to access admin panel at `/admin`

Set the variable to this key:

```python
# env.py
os.environ.setdefault("BASIC_AUTH_USERNAME", "<your superuser password>")
```

### Flask Mail Option

> See [Flask Mail](https://pythonhosted.org/Flask-Mail/)
> Similarly, apply the same logic to:

- `MAIL_SERVER`
- `MAIL_PORT`
- `MAIL_USERNAME`
- `MAIL_PASSWORD`
- `MAIL_DEFAULT_SENDER`

## Database Server

Want to create this Database from scratch that works with this code?

Add the above environment variables to a local `env.py`.
Configure the app's Flask instance to these variables:

```python
# as written in app.py
app.config['SAMPLE_ENV_VAR'] = os.environ.get("SAMPLE_ENV_VAR")
```

The Collections named `snippet`, `user`, and `collection` will automatically be created when documents are made
following the classes in this repo. You can also create these collections manually, and add documents on the atlas Cloud
interface or Mongo Compass.

### Mongo Shell

You can interact with the database via Mongo shell:

```python
show
dbs
use
cheathubdb
show
collections
db.users.find().pretty()
```

### Adding New Documents

You can add documents via Postman or Mongo Compass.

## Module Documentation

- [Flask Mongo Engine](http://docs.mongoengine.org/projects/flask-mongoengine/en/latest/)

- [Flask CORS](https://flask-cors.readthedocs.io/en/latest/)

- [Flask JWT Extended](https://flask-jwt-extended.readthedocs.io/en/latest/)

- [Flask Admin](https://flask-admin.readthedocs.io/en/latest/)

- [Flask Session](https://flask-session.readthedocs.io/en/latest/)

- [Flask Restful](https://flask-restful.readthedocs.io/en/latest/)

- [Flask Mail](https://pythonhosted.org/Flask-Mail/)

## Resources

- [mkdocs-material](https://squidfunk.github.io/mkdocs-material/getting-started/)
- [mkdocstrings](https://mkdocstrings.github.io/usage/#autodoc-syntax)
- [mkdocs](https://www.mkdocs.org/getting-started/#adding-pages)

<p align="right"><a href="#readme-top">back to top</a></p>