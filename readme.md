## Installation Instructions

- Run git clone https://github.com/Jinearth9/internship.git
- Create a MySQL database for the project
    - mysql -u root -p
    - create database 'your-db-name';
    - \q
- Copy .env.example to .env
- Configure your .env file
    - DB_DATABASE=your-db-name
    - DB_USERNAME=root
    - DB_PASSWORD=null
    - add following lines
        TWITTER_ACCESS_TOKEN=4655987189-08zXuE9IR27MMprt9vYocLaMriTCOA8iotBmGO5\n
        TWITTER_ACCESS_TOKEN_SECRET=sZlx1Ea5ryeaSa6Ys3aPDzoJyQCl8cbcW3qPPFsirIXGa\n
        TWITTER_CONSUMER_KEY=sILFCHnZqhChSKsZRZjFqqzQK\n
        TWITTER_CONSUMER_SECRET=v9j6oHliAnbUxkrOJunecI22t5MmvQ4CyRuQy0iUSKx9MSJhxR\n
- Run 'composer update' from the projects root folder.
- Run 'npm install' from the projects root folder.
- From the projects root folder run 'php artisan key:generate'
- From the projects root folder run 'php artisan migrate'
- Run 'php artisan serve'
- Run 'php artisan twitter:listen 1'
- Run 'php artisan twitter:listen 2'
- Start server at http://localhost:8000
