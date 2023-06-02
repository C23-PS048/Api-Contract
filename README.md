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
* **URL Params**  
  None
* **Data Params**  
 * name as string
 * email as string, must be unique
 * password as string, must be at least 8 characters
* **Headers**  
  Content-Type: application/json  
* **Success Response:**  
* **Code:** 200  
  **Content:**  
```
{
  users: [
           {<user_object>},
           {<user_object>},
           {<user_object>}
         ]
}
```
