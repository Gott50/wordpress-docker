# WordPress Docker

WordPress Docker makes developing for WordPress easy and predictable. It
sets up everything for you, so that you can dive straight into developing
your plugins and themes without any hassle.

There in a more in-depth blog post is available called [Develop
WordPress plugins and themes using
Docker](http://johnny.chadda.se/develop-wordpress-plugins-and-themes-using-docker/).

## Requirements

- [Docker](https://www.docker.com/)
- [Docker-Compose](https://docs.docker.com/compose/)

## Getting Started

1. Clone this repostory:
    `git clone https://github.com/gott50/wordpress-docker.git`
2. Run `docker-compose up` to start the containers.
3. sudo chmod -R 777 ./wordpress
4. Browse to http://[docker ip]:8000/ and you are ready to go! (find the
   ip using `boot2docker ip`).
   phpMyAdmin is accessible at http://[docker ip]:8100/

## Restore form Backup
1. use a Plugin like [UpdraftPlus](https://updraftplus.com/)
2. login to [adminer](http://localhost:8080) with your WORDPRESS_DB_USER and WORDPRESS_DB_PASSWORD
3. update wp_options: 
   1. siteurl: http://[docker ip]:8000/
   2. home: http://[docker ip]:8000/
4. wp_users
   1. user_login: wordpress
   2. user_pass: $P$B3JPafrPC9oiNOkN9jvxhUZK/Rfu6m.

## Clear Docker
    
    docker system prune

## Tmuxp workspace

A predefined workspace is provided to easily get going.

1. Install tmuxp (`sudo pip install tmuxp` on a Mac)
2. Run `tmuxp load tmuxp.yml` (provided that you have tmux installed)
3. A tmux session will be started with a vim window located in the
   plugins directory. The containers are started automatically in the
   second window.

## If you're new to Docker

If you are running `boot2docker`, you can easily find your Docker IP by
running `boot2docker ip`.

The easiest way to install boot2docker and fig is to use
[Homebrew](http://brew.sh) and follow these steps:

1. Install [VirtualBox](https://www.virtualbox.org).
2. Install the software: `brew install boot2docker fig`.
3. Create a virtual machine: `boot2docker init`.
4. Finally start the virtual machine: `boot2docker up`.

## Acknowledgements

The setup is based on the excellent [Repository by joch](https://github.com/joch/wordpress-docker)