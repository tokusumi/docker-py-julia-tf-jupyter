# docker-py-julia-tf-jupyter
the followings are available,
- Python3: able to import and use Julia function. See demo/demo.ipynb
- tensorflow: determine the version in src/Dockerfile you would love to use. default version is 2.0.0
- Jupyter: login with password. set PORT in /docker-compose.yml . default PORT is 80
- Julia: available in Jupyter Notebook. determine the version in src/Dockerfile. default version is 1.3.0


# Run Jupyter Notebook Server
Build docker image
```
$ docker-compose build
```

Run
```
$ docker-compose up
```

Access 0.0.0.0/
Password (default): test

## Change Password
```
$ docker-compose run tf jupyter notebook password
# Enter password:
# Verify password:
# [NotebookPasswordApp] Wrote hashed password to /root/.jupyter/jupyter_notebook_config.json
```

