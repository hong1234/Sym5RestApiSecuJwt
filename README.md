# Sym5RestApiSecuJwt
git clone https://github.com/hong1234/Sym5RestApiSecuJwt.git

cd Sym5RestApiSecuJwt

composer install

// config  .env

DATABASE_URL=mysql://root:xxx@127.0.0.1:3306/demo_api

// run the command to create a database table according to entities.

php bin/console doctrine:schema:create

// php bin/console doctrine:schema:update -- force

// Generate SSH Keys

mkdir config/jwt

openssl genrsa -out config/jwt/private.pem -aes256 4096

// PASSPHRASE=abcxxx 

openssl rsa -pubout -in config/jwt/private.pem -out config/jwt/public.pem

// config

//.env

###> lexik/jwt-authentication-bundle ###

JWT_SECRET_KEY=%kernel.project_dir%/config/jwt/private.pem

JWT_PUBLIC_KEY=%kernel.project_dir%/config/jwt/public.pem

JWT_PASSPHRASE=abcxxx


// Test the API

php -S localhost:8000 -t public/

// register

POST localhost:8000/register

Body
 
    Raw | JSON

{
    "username":"hong",
    "password":"vuanh",
    "email":"abc@gmail.com"
}

// get TOKEN

POST localhost:8000/api/login_check

Body
 
    Raw | JSON

{
    "username":"hong",
    "password":"vuanh"
}

