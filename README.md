# Workindia
A web application that keeps a record of users' passwords. Users can log into the panel to see the username and passwords of websites they
have saved.
Requirements:
User account registration:
Create a user account. These credentials will be used to log into this panel.

[POST] /app/user
Request Data: {
'username': str,
'password': str
}
Response Data: {
'status': 'account created'
}

User account login:
Provide ability to log into the panel using the user credentials.

[POST] /app/user/auth
Request Data: {
'username': str,
'password': str
}
Response Data: {
'status': 'success',
'userId': int
}

List of saved usernames and passwords for different websites:
Provide ability for user to see list of previously stored website usernames & passwords.

[GET] /app/sites/list/?user={userId}
Request Data: None
Response Data: [List of stored website username & passwords]

List returned should be belong to the userId passed with the request
Save a new username & password for website:
Provide ability for user to add new username & password for a website.

[POST] /app/sites?user={userId}
Request Data: {
'website': str,
'username': str,
'password': str
}
Response Data: {
'status': 'success'
}

Mandatory Requirement: All the passwords stored in the database have to be encrypted.
No one should be able to read the stored passwords without a secret key. The key can be stored in the code itself.
Tech Stack:
Any web-server of your choice (Python Flask / Django, NodeJS Express / Koa, Java, etc)
Database: MySQL (Compulsory)
