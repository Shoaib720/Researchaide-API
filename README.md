# Researchaide-API
This repository enlists all the API endpoints of the Researchaide Project.

## Models
### College
```
{
    name: { String, required },
    registrationNo: { String, required } 
}
```

### Paper
```
{
    title: { String, required },
    keywords: { [String], required },
    areaOfResearch: { String, required },
    authors: { [String], required },
    uploadedBy: { String, required },
    college: { ObjectId },
    publicationDate: { Date, default: null },
    path: { String, required },
    statusCode: { Number, enum: [0,1,2], default: 0, required }
}
```

### User
```
{
      email: { String, required, unique },
      name: { String, required },
      contact: { String, required },
      password: { String, required },
      college: { ObjectId },
      registeredBy: { String, default: 'NA'},
      role: { String, enum:['admin', 'spoc', 'student'], required }
}
```

---

## API Endpoints

Base url: **https://researchaide-backend.herokuapp.com/api/v1**

### College

#### GET '/'
Admin authentication and JWT token required.

##### Response
