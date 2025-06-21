completely checked in manual using postman

login data

{
    "email": "dummy@example.com",
    "password": "dummy123"
}

access token

{
    "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJkdW1teUBleGFtcGxlLmNvbSIsImV4cCI6MTc0MjM4NjQzMX0.VJ0chk7tzlfv3SaP3LgHix_OBoJB9bWHmcntuLrev7c",
    "token_type": "bearer"
}

create new user 

post http://127.0.0.1:8000/signup   
{
    "email": "dummy@example.com",
    "password": "dummy123"
}

login and get jwt token 

post http://127.0.0.1:8000/login
{
    "email": "dummy@example.com",
    "password": "dummy123"
}


create a book

post http://127.0.0.1:8000/books/
bearer token  eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJkdW1teUBleGFtcGxlLmNvbSIsImV4cCI6MTc0MjM4NjQzMX0.VJ0chk7tzlfv3SaP3LgHix_OBoJB9bWHmcntuLrev7c

{
    "name": "The Catcher in the Rye",
    "author": "J.D. Salinger",
    "published_year": 1951,
    "book_summary": "A story about teenage alienation and angst."
}

get a book by id

get http://127.0.0.1:8000/books/1
bearer token  eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJkdW1teUBleGFtcGxlLmNvbSIsImV4cCI6MTc0MjM4NjQzMX0.VJ0chk7tzlfv3SaP3LgHix_OBoJB9bWHmcntuLrev7c


to delete a book by id

delete http://127.0.0.1:8000/books/1
bearer token  eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJkdW1teUBleGFtcGxlLmNvbSIsImV4cCI6MTc0MjM4NjQzMX0.VJ0chk7tzlfv3SaP3LgHix_OBoJB9bWHmcntuLrev7c

to get all books

get http://127.0.0.1:8000/books/
bearer token  eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJkdW1teUBleGFtcGxlLmNvbSIsImV4cCI6MTc0MjM4NjQzMX0.VJ0chk7tzlfv3SaP3LgHix_OBoJB9bWHmcntuLrev7c