#Users
* User object
```
{
  id: integer
  username: string
  email: string
  password:hash
  foto:File (nullable/optional)
}


```

**Post /Register**
----
  Register  users in the system.
* **Method**  
  Post
  * **Url**  
  
  ```/register```
* **Data Params**  
*  ```name``` as ```string```
*  ```email``` as  ```string```, must be  ```Unique```
*  ```password``` as ```string```, must be at least ```8 characters```
* **Headers**  
  Content-Type: application/json  
* **Success Response:**  
```
{
  "error": false,
  "message": "User Created"
}
```
* **Code:** 200  





**Post /Login**
----
 Login for users in the system.
* **Method**  
  Post
  * **Url**  
  Post
  ```/Login```
* **Data Params**  

*  ```email``` as  ```string```, must be  ```Unique```
*  ```password``` as ```string```, must be at least ```8 characters```
* **Headers**  
  Content-Type: application/json  
* **Success Response:**  
```
{
    "error": false,
    "message": "success",
    "loginResult": {
        "id": "1",
        "name": "Budi",
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiJ1c2VyLXlqNXBjX0xBUkNfQWdLNjEiLCJpYXQiOjE2NDE3OTk5NDl9.flEMaQ7zsdYkxuyGbiXjEDXO8kuDTcI__3UjCwt6R_I"
    }
}
```
* **Code:** 200  


**get /User/:id**
----
  Get  users data in the system.
* **Method**  
  Get
  * **Url**  
  
  ```/user/:id```
* **Data Params**  
 ```Authorization```: ```Bearer <token>```
* **Headers**  
  Content-Type: application/json  
  
* **Success Response:**  
```
{
    "error": false,
    "message": "success",
    "loginResult": {
                      id: integer
                      username: string
                      email: string
                      password:hash
                      foto:File (nullable/optional)
  }
}
```
* **Code:** 200  



**Patch /user/:id**
----
  Update users in the system.
* **Method**  
  Patch
  * **Url**  

  ``` /user/:id```
* **Data Params**  

*  ```name``` as  ```string```
*  ```foto``` as ```file```, must be a valid image file, max size 1MB
*  ```password``` as ```string```, must be at least ```8 characters```
* **Headers**  
  Content-Type: application/json  
* **Success Response:**  
```
{
  "error": false,
  "message": "User Updated"
}
```

* **Code:** 200  


