# REST-API-WITHOUT-DB
#### In this project, I follow MVC .
- need to install: npm install express nodemon cors body-parser dotenv uuid

- for cors `app.use(cors())`;

- for body-parser `app.use(bodyParser.urlencoded({extended: true}))` `app.use(bodyParser.json())`

- user.controller.js file is logical portion of this code.

```javascript
// get user
const getAllUsers = (req,res) =>{
    res.status(200).json({users});
}


// create user 
const createUser = (req,res) =>{
    const newUser = {
        id: uuidv4(),
        username: req.body.username,
        email: req.body.email,
    }
    users.push(newUser)
    res.status(201).json(users);
}

// update user 
const updateUser = (req,res) =>{
    
    const userid = req.params.id;
    const {username,email} = req.body;
    users.filter((user) => user.id == userid).map(
        (selecteduser) =>{
            selecteduser.username = username;
            selecteduser.email = email;
        }
    )

    res.status(200).json(users);
}
// delete user 
const deleteUser = (req,res) =>{
    
    const userid = req.params.id;
    
    users = users.filter((user) => user.id != userid)

    res.status(200).json(users);
}
```