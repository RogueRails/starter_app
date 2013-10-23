# Rogue Rails Starter App

This app is the initial project you should start with at the Rogue Rails workshop.

## Setup

First ensure you have [Vagrant](http://www.vagrantup.com) and [VirtualBox](https://www.virtualbox.org/wiki/Downloads) installed.

You should have already received the `roguerails.box` file. If you do not have it, ask one of the team mentors. Then add the box if you haven't already.

```
vagrant box add roguerails-box path/to/roguerails.box
```

Next clone this repository and run this command inside.

```
vagrant up
```

This will start up the virtual environment. If you receive an error, you may want to try it again with `vagrant halt` and `vagrant up`.

Then you can SSH into the virtual box:

```
vagrant ssh
```

This will drop you into the `/vagrant` directory which is a shared folder allowing you to run the application. Run the following commands in the box to finish setting up the project.

```
bundle install
cp config/database.example.yml config/database.yml
rake db:create
rails s
```

From here you should be able to access the application at http://localhost:3000/

You will need to run any other Rails dependent commands (such as `rake db:migrate`) within `vagrant ssh`. However, run `git` commands outside of this (on your local system).