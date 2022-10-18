# Heroku Deployment of the Early Melanoma Detection App

https://app-melanoma.herokuapp.com/

## Manual deployment

- Wrote Application using python and javascript
- Build Image from Dockerfile
- Pushed the Image to Heroku Web Service

First, you will need to create a Heroku account and install the Heroku CLI, eg.
`brew install heroku`. Then

```
0. git clone git@github.com:geoffroybertrand/app-melanome-heroku.git
1. ln -s $chemin_vers_le_bin_heroku /usr/bin/heroku
2. heroku login -i  (token API ~/.netrc)
3. heroku create --app detection_melanome
4. sudo heroku auth:token
5. sudo docker login --username=_ --password=${YOUR_TOKEN} registry.heroku.com
6. sudo docker build -t registry.heroku.com/app-melanoma/web .
7. sudo docker push registry.heroku.com/app-melanoma/web
8. heroku container:release web -a app-melanoma
```
