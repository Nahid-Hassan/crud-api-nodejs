# CRUD-API
CRUD (Create, Read, Update and Delete) operations with the help of Rest API using Node.js, MongoDB as our database, and Expess.

HOST: https://democurdapi.herokuapp.com/


# This are the sample data not actual data.

# simple-crudapi

simple-crudapi that can be used for showing some informations about some 
products. One can easily do the operation of create, read, update and delete
operation on them.

## Product Collection [/products]

### List All Products [GET]

This action will show this list of the products that the database contains.

+ Response 200 (application/json)

        [
            {
                "_id": "5ddd932676bed349fc418209",
                "title": "Macbook",
                "description": "13 inch Macbook Pro",
                "price": 1200,
                "company": "Apple",
                "createdAt": "2019-11-26T21:03:34.898Z",
                "updatedAt": "2019-11-26T21:03:34.898Z",
                "__v": 0
            },
            {
                "_id": "5ddd954076bed349fc41820c",
                "title": "Dell-Inspiron",
                "description": "15.6 inch",
                "price": 3000,
                "createdAt": "2019-11-26T21:12:32.357Z",
                "updatedAt": "2019-12-03T03:32:37.075Z",
                "__v": 0,
                "company": "Dell"
            },
            {
                "_id": "5de67c51a12dbb00048a5106",
                "title": "Acer Laptop",
                "description": "15.6 inch",
                "price": 10000,
                "company": "Acer",
                "createdAt": "2019-12-03T15:16:33.045Z",
                "updatedAt": "2019-12-03T15:16:33.045Z",
                "__v": 0
            },
            {
                "_id": "5de68212a12dbb00048a5108",
                "title": "Asus Predator",
                "description": "21 inch gaming laptop",
                "price": 5000,
                "company": "Asus",
                "createdAt": "2019-12-03T15:41:06.083Z",
                "updatedAt": "2019-12-03T15:44:07.936Z",
                "__v": 0
            }
        ]

### Create a New Product [POST]

You may create your own product using this action. It takes a JSON
object containing the followings-
    1. title
    2. description
    3. price
    4. company

+ Request (application/json)
    
            {   
                "title": "Asus Laptop",
                "description": "15.6 inch",
                "price": "10000",
                "company": "Asus"
            }

+ Response 201 (application/json)

    + Headers

            Location: /questions/5de689cca12dbb00048a5109

    + Body

            {
                "_id": "5de689cca12dbb00048a5109",
                "title": "Asus Laptop",
                "description": "15.6 inch",
                "price": 10000,
                "company": "Asus",
                "createdAt": "2019-12-03T16:14:04.722Z",
                "updatedAt": "2019-12-03T16:14:04.722Z",
                "__v": 0
            }
            
### Update an Existing Product [PUT]

The upadate of an existing product can be done through this action. As the
put function is implemented for this action, the whole information of that
product will be changed and this will be done using the id of that product.

using the id: 5de689cca12dbb00048a5109

+ Request (application/json)

        {
            "title": "Laptop",
            "description": "15.6 inch simple laptop",
            "price": "10000",
            "company": "Asus"
        }

+ Response 200 (application/json)

    + Headers

            Location: /questions/5de689cca12dbb00048a5109

    + Body

            {
                "_id": "5de689cca12dbb00048a5109",
                "title": "Asus Laptop",
                "description": "15.6 inch simple laptop",
                "price": 10000,
                "company": "Asus",
                "createdAt": "2019-12-03T16:14:04.722Z",
                "updatedAt": "2019-12-03T16:22:27.110Z",
                "__v": 0
            }
            
### Delete an Existing Product [DELETE]

Any existing product can be deleted through this action using the id of 
the product. If this action is made then the whole information of that
product will be deleted.

using the id: 5de689cca12dbb00048a5109

+ Request (application/json)

        {
            "title": "Asus Laptop",
            "description": "15.6 inch simple laptop",
            "price": "10000",
            "company": "Asus"
        }

+ Response 200 (application/json)

    + Headers

            Location: /questions/5de689cca12dbb00048a5109

    + Body

            {
                "message": "Product deleted successfully!"
            }
