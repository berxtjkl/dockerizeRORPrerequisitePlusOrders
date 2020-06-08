Order of starting a new docker on Chinese Server with ROR:
1. Create a new ROR(better do it on your local dev env, not on server side)
    1. git clone https://github.com/berxtjkl/dockerizeRORPrerequisitePlusOrders.git
    2. create a repo on git, and replace the "randomName" with repo's "name" of all command.sh files.
    3. execute dockerizeRORPrerequisitePlusOrders/command1.sh
    4. cd /usr/src/app/
    5. execute dockerizeRORPrerequisitePlusOrders/command2.sh and exit temp container
    6. execute dockerizeRORPrerequisitePlusOrders/command3.sh(move below files/folder to specific path)
        1. .env/ (folder)
        2. .gitignore
        3. Dockerfile
        4. docker-compose.yml
        5. docker-entrypoint.sh
    7. execute dockerizeRORPrerequisitePlusOrders/command4.sh
        1. make sure there is only one DockerizeROR running, because port is not dynamic
    8. now you can access ip:3000 to check whether it is okay
    9. git push to repo
    10. go to dockerizeRORPrerequisitePlusOrders/ folder and checkout . operation, make sure randomName is back.


2. Using an existence ROR
    1. locate at the root folder, where you are going to copy an app here
    2. cp -r source_app destination_app (here the name is just an example)
        1. copy app folder here, only 1 folder(now you can understand what will be put here.)
    3. git clone https://github.com/berxtjkl/dockerizeRORPrerequisitePlusOrders.git
    4. then get into dockerizeRORPrerequisitePlusOrders folder
    5. put below files into your application folder by execute this [cp -r .env .gitignore docker-compose.yml docker-entrypoint.sh Dockerfile ../destination_app/]
        1. .env/ (folder)
        2. .gitignore
        3. Dockerfile
        4. docker-compose.yml
        5. docker-entrypoint.sh
    6. sudo chmod 666 myapp2/
    7. Get into your destination_app folder and execute [docker-compose build]
        1. make sure there is only one DockerizeROR running, because port is not dynamic
    8. docker-compose run web yarn install
    9. docker-compose run web bundle install
        1. have no idea why I have to run bundle install here.....
    9. docker-compose run web bin/rails webpacker:install
        1. please make sure whether you are going to click y to overwrite some webpacker files
    10. docker-compose run web bin/rails webpacker:install:react
    11. docker-compose up -d 
    12. now you can access ip:3000 to check whether it is okay