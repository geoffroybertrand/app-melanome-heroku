# Heroku Deployment of the Early Melanoma Detection App

https://app-melanoma.herokuapp.com/

## Manual deployment

- Wrote Application using python and javascript
- Build Image from Dockerfile
- Pushed the Image to Heroku Web Service

First, you will need to create a Heroku account and install the Heroku CLI, eg.
`brew install heroku`. Then

- ***Download Heroku Client***
- ***Clone the project:*** git clone git@github.com:geoffroybertrand/app-melanome-heroku.git
- ***Link with the executable:***  ln -s $chemin_vers_le_bin_heroku /usr/bin/heroku
- ***Connect to the API:*** heroku login -i  (token API ~/.netrc)
- ***Create the application container:*** heroku create --app detection_melanome
- ***Get the authentification token:*** sudo heroku auth:token
- ***Connect to heroku's docker registery:*** sudo docker login --username=_ --password=${YOUR_TOKEN} registry.heroku.com
- ***Build local image of the application:*** sudo docker build -t registry.heroku.com/app-melanoma/web .
- ***Commit the image towards heroku's docker registery:*** sudo docker push registry.heroku.com/app-melanoma/web
- ***Deploy the service on heroku:*** heroku container:release web -a app-melanoma

## Create Javascript Model compatible with TensorflowJs
$ tensorflowjs_converter --input_format=model/model.h5 tfjs_model

