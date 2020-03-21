* [Display All Users](#Display-All-Users)
* [Current User](#Current-Users)
* [Create New User](#Create-New-Users)

## Display All Users

### Handler

* **Handler** : GET /api/users
* Description : Returns all users from database
* No parameters

### Example

**Request**:
```bash
curl --insecure -i -H "Content-Type: application/json"  -X GET -d https://localhost:1337/api/users?token=oa2vqer0si0rhehvwgvg3ncgec06hlb5ts58hmle
```

**Response**:
```json
{
    "users": [
        {
            "ID": 1,
            "admin": true,
            "enabled": true,
            "last_logon_time": "2020-03-21 18:57:36",
            "username": "empireadmin"
        }
    ]
}
```

## Current User

### Handler

* **Handler** : POST /api/users/me
* Description : Returns the current user
* No parameters

### Example

**Request**:
```bash
curl --insecure -i -H "Content-Type: application/json" -X POST -d https://localhost:1337/api/users/me?token=oa2vqer0si0rhehvwgvg3ncgec06hlb5ts58hmle
```

**Response**:
```json
{
    "admin": true,
    "api_token": "oa2vqer0si0rhehvwgvg3ncgec06hlb5ts58hmle",
    "enabled": true,
    "id": 1,
    "last_logon_time": "2020-03-21 18:57:36",
    "username": "empireadmin"
}
```

## Create New User

### Handler

* **Handler** : POST /api/users
* Description : Creates a new users.
* No parameters

### Example

**Request**:
```bash
curl --insecure -i -H "Content-Type: application/json" -X POST -d https://localhost:1337/api/users?token=oa2vqer0si0rhehvwgvg3ncgec06hlb5ts58hmle '{"username":"user", "password":"pass"}'
```

**Response**:
```json
{
    "admin": true,
    "api_token": "oa2vqer0si0rhehvwgvg3ncgec06hlb5ts58hmle",
    "enabled": true,
    "id": 1,
    "last_logon_time": "2020-03-21 18:57:36",
    "username": "empireadmin"
}
```