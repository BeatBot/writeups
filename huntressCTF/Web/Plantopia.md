### Challenge description

Plantopia is our brand new, cutting edge plant care management website! Built for hobbiests and professionals alike, it's your one stop shop for all plant care management.

Please perform a penetration test ahead of our site launch and let us know if you find anything.

- Username: `testuser`
- Password: `testpassword`

### Solution

We login and notice that there is an API documentation, its Swagger. It requires admin auth and explains a bit about it.

```
Bearer token with Base64-encoded cookie. The cookie is a Base64-encoded string in the format 'username.isAdmin.expirationTime'. Example: 'admin.1.1695658567' encoded in Base64.
```

We grab our cookie and modifie it and base64 encode it. We look around the api and use this new base64 value to try out the endpoints.

We noticed the `/api/admin/sendmail` which send mail? okey, another interesitng enpoint is `/api/admin/setting` and here we can set the `alert_command` which is path to `sendmail` in this situation, we can abuse this using this payload:
```json
{
  "plant_id": 1,
  "alert_command": "/usr/sbin/sendmail -t && cat flag.txt",
  "watering_threshold": 50
}
```
Now we can call `/api/admin/sendmail` and check the `/api/admin/logs` endpoint for the flag, and it is there!

flag{c29c4d53fc432f7caeb573a9f6eae6c6}