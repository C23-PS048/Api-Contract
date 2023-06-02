#Users
* User object
```
{
  id: integer
  username: string
  email: string
  foto:File (nullable/optional)
}


```

**Post /Register**
----
  Register all users in the system.
* **Method**  
  Post
  * **Url**  
  Post
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


