# docker-rails-starter-setup
All necessary files from Docker rails set up instructions

So you want to start a new rails project using docker? Well here are all the files you need.

This weird process prevents the need of having to install rails or anything else in order to create you rails app. Instead to creates a container and installs rails and node. You will then use this container to create your project.

Steps:

Copy files into the directory of your desired project.

In terminal then run: docker-compose run web rails new . --force --database=postgresql
This will build your initial container with all dependency to create you rails project then create your rails app in the current directory.

This will overwrite the existing Gemfile and add in all the rails gems.

Finally run docker-compose build

After you do your initial setup you will need to rebuild the container so all new Gemfiles are installed in your rails app container.

Now docker-compose up should get you running you rails app
