# Sym5RestApiSecuJwt
git clone https://github.com/hong1234/Sym5RestApiSecuJwt.git

cd Sym5RestApiSecuJwt

composer install



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

