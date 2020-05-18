Order of start a new docker ROR:
1. Create a new ROR
    1. locate at the root folder, where you are going to create an app here
    2. docker run -i -t --rm -v ${PWD}:/usr/src/app ruby:2.6 bash
    3. cd /usr/src/app
    4. gem install rails
    5. rails new myapp --skip-test --skip-bundle
    6. exit current docker container
        1. sudo chmod 666 myapp2/
    7. put below files into your application folder by execute this [cp -r .env .gitignore docker-compose.yml docker-entrypoint.sh Dockerfile ../testDocker1/]
        1. .env/ (folder)
        2. .gitignore
        3. Dockerfile
        4. docker-compose.yml
        5. docker-entrypoint.sh
    8. sudo chmod 666 myapp2/
        1. because you move some files and folder in to your application
    9. Get into your application folder and execute [docker-compose build]
    10. docker-compose run web yarn install
    11. docker-compose run web bin/rails webpacker:install
    12. docker-compose run web bin/rails webpacker:install:react


2. Using an existence ROR
    1. locate at the root folder, where you are going to copy an app here
    2. copy app folder here, only 1 folder(now you can understand what will be put here.)
    3. put below files into your application folder
        1. .env/ (folder)
        1. .gitignore
        2. Dockerfile
        3. docker-compose.yml
        4. docker-entrypoint.sh