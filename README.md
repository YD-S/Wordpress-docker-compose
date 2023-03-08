# WordPress with Docker

This makes local WordPress development easy by spinning up a website using WordPress, MySQL and PhpMyAdmin.

### Getting started

---

1. [Install docker in your system](https://docs.docker.com/get-docker/).
2. Pull this repository.
3. Create `.env` from `.env-sample`.
4. Set the required values in `.env`. Whatever you set in this file will be used to install `mysql` and setting up database for your website.
5. Execute `docker-compose up -d` from a terminal inside the directory.
6. Open up your browser and hit http://localhost:8000.
7. Proceed and complete installation.
8. Your website is ready to be developed to its next awesome level.

WordPress and phpMyAdmin are set to be exposed at port `8000` and `8080` respectively in your local machine. You may change this if these ports are not free in your system.

If you are doing this for the first time, then it will take some time to pull the images from Docker Hub. Everything will be done in seconds when you will have the images for WordPress, MySQl and phpMyAdmin in your local machine.

## Key Commands

---

`docker-compose down` to stop the container.  
`docker-compose build` to rebuild the container.

See this for further reference on `docker-compose`, https://docs.docker.com/compose/reference/

## Extend

---

If you want to install themes or plugins during the website setup, edit the `docker-compose.yml` file and map the files in the WordPress' volume.

For example, if I were to install Divi, which is a theme, I would add the following,  
`- ./themes/:/var/www/html/wp-content/themes/`

And if I were to install Sucuri Scanner, which is a plugin, I would add,

`- ./plugins/:/var/www/html/wp-content/plugins/`

Here, `./themes/` and `./plugins/` are local directories where you I would paste the files. You can create different directories on local to store the files. However, rest of the part for the mapping needs follow the directory structure of WordPress.

You will find commented out plugin, theme installation in the `docker-compose.yml`, you can remove those, add your own, or edit those. I left those as is because my frequent use of those.
