# docker-rails-starter-setup

So you want to start a new rails project using docker? Well here are all the files you need.

This weird process prevents the need of having to install rails or anything else on to your system to start a new rails app. Instead to creates a container and installs rails and node. You will then use this container to create your project.

##

### What this contains:

* Ruby 2.3.3
* Rails 5.1.1
* Node/npm
* Yarn
* Chrome Stable (for testing)
* Postgres

##

### Getting Started:

* Copy or clone repo files into the directory of your desired project.

* In terminal then run: 

		docker-compose run web rails new . --force --database=postgresql

	This will build your initial container with all dependency to create your rails project. It will then call rails new with you desired arguments.

	This will overwrite the existing Gemfile and add in all the rails gems.

* Copy `database.yml.example` to `config/` and rename it to `database.yml`

* Run: 

 		docker-compose build

	After you do your initial setup you will need to rebuild the container so all new Gemfiles are installed in your rails app container.

* Now `docker-compose up` should get you running your new rails app when you want to start developing

You now have your rails app running in a docker container called web. 

##

### Tips for developing using Docker

* Running database migrations:
 	
    	docker-compose run web rake db:create
        
* Running any command for you rails app:

        docker-compose run web <command>
        
	This tells docker you would like to run a command inside your web container, the web container is where you rails app is running.
    

* If you find that you want different to run all sort of commands on your rails app then you can do the following:
 		
        docker-compose run web bash
        
	This will open a command line session inside your web container allowing you to quickly run rake tasks, rails console and use other utils without the need of having to prepend `docker-compose run web` all the time
