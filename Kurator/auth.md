# Auth

{% swagger baseUrl="https://biosite" method="post" path="/signin" summary="auth user in system" fullWidth="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="username" required="false" type="string" %}
name of user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" required="true" type="string" %}
user password
{% endswagger-parameter %}

{% swagger-response status="200" description="user successfully authorization (token contains userID)" %}
{token}
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Incorrect data" %}
```javascript
{
    "status_response": false,
    "description": "bad data"
}
```
{% endswagger-response %}

{% swagger-response status="403: Forbidden" description="wrong password" %}
```javascript
{
    "status_response": false,
    "description": "wrong password!"
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="no user in system" %}
```javascript
{
    "status_response": false,
    "description": "no user"
}
```
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="server error" %}
```javascript
{
   "status_response": false,
   "description": "server error!"
}
```
{% endswagger-response %}
{% endswagger %}
