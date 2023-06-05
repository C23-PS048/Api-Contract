# Users
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
 *  **Url**  
    ```/register```
* **Request Body**  
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
```/Login```
* **Request Body**  
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
    * Get
* **Url**  
   * ```/user/:id```
* **Headers**  
    * ```Authorization```: ```Bearer <token>```
    *  ```Content-Type: application/json  ```
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
* **Request Body**  
    *  ```name``` as  ```string```
    *  ```foto``` as ```file```, must be a valid image file, max size 1MB
    *  ```password``` as ```string```, must be at least ```8 characters```
* **Headers**  
    * ```Authorization```: ```Bearer <token>```
    *  ```Content-Type: application/json```
* **Success Response:**  
```
{
  "error": false,
  "message": "User Updated"
}
```

* **Code:** 200  


# UserPlant
* UserPlant object
```
{
  id: integer
  location: string
  startDate: long
  lastScheduledDate: long
  nextScheduledDate: long
  plantId: integer
  UserId: integer
}
```

**get /user/:id/plant**
----
  Get all users plant  data in the system.
* **Method**  
Get
* **Url**  
    ```/user/:id/plant```
* **URL Params**  
  *Required:* `id=[integer]`
* **Headers**  
* ```Authorization```: ```Bearer <token>```
*  ```Content-Type: application/json```
* **Success Response:**  
```
{
    "error": false,
    "message": "success",
    "userPlant": [
           {<userPlant_object>},
           {<userPlant_object>},
           {<userPlant_object>}
         ]
}

```
* **Code:** 200  

**Post /userPlant**
----
  Register users plant in the system.
* **Method**  
    * ```Post```
 *  **Url**  
    *  ```/userPlant```
* **Request Body**  
    *  ```location``` as ```string```
    *  ```startDate``` as  ```long```
    *  ```lastScheduledDate``` as  ```long```
    *  ```nextScheduledDate``` as ```long```
    *  ```plantid``` as ```Integer```
    *  ```userId``` as ```Integer```
* **Headers**  
    * ```Authorization```: ```Bearer <token>```
    * ``` Content-Type: application/json ``` 
* **Success Response:**  
```
{
  "error": false,
  "message": "Plant Saved"
}
```
* **Code:** 200  


**get /userPlant/:id**
----
* **URL Params**  
  *Required:* `id=[integer]`
  get detail of specific users plant in the system.
* **Method**  
  get
 * **Url**  
  ``` /userPlant/:id```

* **Headers**  
    * ```Authorization```: ```Bearer <token>```
    *  ```Content-Type: application/json```
* **Success Response:**  
```
{
    "error": false,
    "message": "success",
    "userPlant": {
                    id: integer
                    location: string
                    startDate: long
                    lastScheduledDate: long
                    nextScheduledDate: long
                    plantId: integer
                    UserId: integer
  }
}
```

* **Code:** 200  




**PATCH /userPlant/:id**
----
 update users plant in the system.
 * **URL Params**  
  *Required:* `id=[integer]`
* **Method**  
  * ```Patch```
 * **Url**  
    * ```/userPlant/:id```
* **Request Body**  
    *  ```location``` as ```string```
    *  ```startDate``` as  ```long```
    *  ```lastScheduledDate``` as  ```long```
    *  ```nextScheduledDate``` as ```long```
    *  ```plantid``` as ```Integer```
    *  ```userId``` as ```Integer```
* **Headers**  
    * ```Authorization```: ```Bearer <token>```
    * ``` Content-Type: application/json ``` 
* **Success Response:**  
```
{
  "error": false,
  "message": "Plant Updated"
}
```
* **Code:** 200  

**Delete /userPlant/:id**
----
 Delete users plant in the system.
 * **URL Params**  
  *Required:* `id=[integer]`
* **Method**  
  * ```Delete```
 * **Url**  
    * ```/userPlant/:id```

* **Headers**  
    * ```Authorization```: ```Bearer <token>```
    * ``` Content-Type: application/json ``` 
* **Success Response:**  
```
{
  "error": false,
  "message": "Plant Deleted"
}
```
* **Code:** 200  

# Plant
* Plant object
```
{
    id: integer,
    slug: string (Unique),
    plantName: string,
    scientificName:string,
    description:String,
    plantTips:String,
    humidity:String,
    wateringFrequency:String,
    temperature:String,
    image:arrayof(String)
  
}
```

**Get /plant/:slug**
----
  Get  plant data in the system.
* **Method**  
    * Get
* **Url**  
   * ```/plant/:slug```
* **URL Params**  
  *Required:* `slug=[string]`
* **Headers** 
    *  ```Content-Type: application/json  ```
* **Success Response:**  
```
{
    "error": false,
    "message": "success",
    "plantResult": {
                       "id": integer,
                        "slug": string (Unique),
                        "plantName": string,
                        "scientificName":string,
                        "description":String,
                        "plantTips":String,
                        "humidity":String,
                        "wateringFrequency":String,
                        "temperature":String,
                        "image":[String,string,String]
  }
}
```
* **Code:** 200  

**Get /plant**
----
  Get  plant data in the system.
* **Method**  
    * Get
* **Url**  
   * ```/plant```
* **Headers**  
    *  ```Content-Type: application/json  ```
* **Success Response:**  
```
{
    "error": false,
    "message": "success",
    "palntList": {
                    [
           {<plant_object>},
           {<plant_object>},
           {<plant_object>}
         ]
  }
}
```
* **Code:** 200  

# Disease
* Disease object
```
{
    id: integer,
    slug: string (Unique),
    plantName: string,
    diseaseName:string,
    care:String,
  
}
```

**Get /disease/:slug**
----
  Get  disease data in the system.
* **Method**  
    * Get
* **Url**  
   * ```/disease/:slug```
* **URL Params**  
  *Required:* `slug=[string]`
* **Headers** 
    *  ```Content-Type: application/json  ```
* **Success Response:**  
```
{
    "error": false,
    "message": "success",
    "diseaseResult": {
                       "id": integer,
                        "slug": string (Unique),
                        "plantName": string,
                        "diseaseName":string,
                        "care":String,
  }
}
```
* **Code:** 200  

**Get /disease**
----
  Get  disease data in the system.
* **Method**  
    * Get
* **Url**  
   * ```/disease```
* **Headers**  
    *  ```Content-Type: application/json  ```
* **Success Response:**  
```
{
    "error": false,
    "message": "success",
    "diseaseList": {
                    [
           {<disease_object>},
           {<disease_object>},
           {<disease_object>}
         ]
  }
}
```
* **Code:** 200  

