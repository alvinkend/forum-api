FORMAT: 1A
HOST: https://private-17b18-forumapi7.apiary-mock.com

# Forum API

Simple API allowing consumers to view forum members, their posts and replies.

## Categories [/category]

### List All Categories [GET]

List all categories.

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "name": "Computers",
                "description": "All things related to computers"
            },
            {
                "id": "2",
                "name": "Culinary",
                "description": "All things related to cooking"
            },
            {
                "id": "3",
                "name": "Science",
                "description": "All things related to science"
            }
        ]

### Create New Category [POST]

Create new category.

+ Request (application/json)

        {
            "name": "Politics",
            "description": "All things related to politics"
        }

+ Response 201 (application/json)

    + Headers

            Location: /category/4

    + Body

            {
                "id": "4",
                "name": "Politics",
                "description": "All things related to politics"
            }
            
## Categories Resource [/author/{id}]

+ Parameters
    + id : 1 (number, required) - An unique identifier of the message

### List Category with ID [GET]

List specific category using its ID.

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "name": "Computers",
                "description": "All things related to computers"
            }
        ]

### Edit a Category [PATCH]

Edit specific category using its ID.

+ Request (application/json)

        {
            "description": "All things related to computers and gadgets"
        }

+ Response 201 (application/json)

        [
            {
                "id": "1",
                "name": "Computers",
                "description": "All things related to computers and gadgets"
            }
        ]
        
### Delete a Category [DELETE]

Delete a category.

+ Response 204


## Members [/member]

### List All Members [GET]

List all members.

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "username": "ripin",
                "password": "*********",
                "email": "ripin@email.com",
                "full_name": "Ricky Alvin",
                "popularity": "Master"
            },
            {
                "id": "2",
                "username": "Jipang",
                "password": "*********",
                "email": "jipang@email.com",
                "full_name": "Aji Pangestu",
                "popularity": "Beginer"
            },
            {
                "id": "3",
                "username": "kelep",
                "password": "*********",
                "email": "kelep@email.com",
                "full_name": "Fredy Gunawan",
                "popularity": "Intermediate"
            },
            {
                "id": "4",
                "username": "pinoy",
                "password": "*********",
                "email": "pinoy@email.com",
                "full_name": "Alvin Ramadhani",
                "popularity": "Intermediate"
            }
        ]

### Create New Member [POST]

Create new member.

+ Request (application/json)

        {
            "username": "ripin",
            "password": "*********",
            "email": "ripin@email.com",
            "full_name": "Ricky Alvin"
        }

+ Response 201 (application/json)

    + Headers

            Location: /member/4

    + Body

            {
                "id": "5",
                "username": "ripin",
                "password": "*********",
                "email": "ripin@email.com",
                "full_name": "Ricky Alvin",
                "popularity": "Newbie"
            }
            
## Members Resource [/member/{id}]

+ Parameters
    + id : 1 (number, required) - An unique identifier of the message

### List Member with ID [GET]

List specific member using its ID.

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "username": "jipang",
                "password": "*********",
                "email": "jipang@email.com",
                "full_name": "Aji Pangestu",
                "popularity": "Master"
            }
        ]

### Edit a Member [PATCH]

Edit specific member using its ID.

+ Request (application/json)

        {
            "email": "jipang@email.com"
        }

+ Response 201 (application/json)

        [
            {
                "id": "1",
                "username": "jipang",
                "password": "*********",
                "email": "jipang@email.com",
                "full_name": "Aji Pangestu",
                "popularity": "Master"
            }
        ]
        
### Delete a Member [DELETE]

Delete a member.

+ Response 204


## Topics [/topic]

### List All Topics [GET]

List all topics.

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "content": "content 1",
                "title": "Title 1",
                "member_id": "1"
            },
            {
                "id": "2",
                "content": "content 2",
                "title": "Title 2",
                "member_id": "2"
            },
            {
                "id": "3",
                "content": "content 3",
                "title": "Title 3",
                "member_id": "3"
            }
        ]

### Create New Topic [POST]

Create new topic.

+ Request (application/json)

        {
            "content": "content 4",
            "title": "Title 4",
            "member_id": "4"
        }

+ Response 201 (application/json)

    + Headers

            Location: /topic/4

    + Body

            {
                "id": "4",
                "content": "content 4",
                "title": "Title 4",
                "member_id": "4"
            }
            
## Topics Resource [/topic/{id}]

+ Parameters
    + id : 1 (number, required) - An unique identifier of the message

### List Topic with ID [GET]

List specific topic using its ID.

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "content": "content 1",
                "title": "Title 1",
                "member_id": "1"
            }
        ]

### Edit a Topic [PATCH]

Edit specific topic using its ID.

+ Request (application/json)

        {
            "content": "content 1a"
        }

+ Response 201 (application/json)

        [
            {
                "id": "1",
                "content": "content 1a",
                "title": "Title 1",
                "member_id": "1"
            }
        ]
        
### Delete a Topic [DELETE]

Delete a topic.

+ Response 204

## Replies [/reply]

### List All Replies [GET]

List all replies.

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "content": "content 1",
                "member_id": "2",
                "topic_id": "1"
            },
            {
                "id": "2",
                "content": "content 2",
                "member_id": "3",
                "topic_id": "2"
            },
            {
                "id": "3",
                "content": "content 3",
                "member_id": "1",
                "topic_id": "3"
            }
        ]

### Create New Reply [POST]

Create new reply.

+ Request (application/json)

        {
            "content": "content 4",
            "member_id": "4",
            "topic_id": "3"
        }

+ Response 201 (application/json)

    + Headers

            Location: /reply/4

    + Body

            {
                "id": "4",
                "content": "content 4",
                "member_id": "4",
                "topic_id": "3"
            }
            
## Topics Resource [/reply/{id}]

+ Parameters
    + id : 1 (number, required) - An unique identifier of the message

### List Reply with ID [GET]

List specific reply using its ID.

+ Response 200 (application/json)

        [
            {
                "id": "1",
                "content": "content 1",
                "member_id": "2",
                "topic_id": "1"
            }
        ]

### Edit a Reply [PATCH]

Edit specific reply using its ID.

+ Request (application/json)

        {
            "content": "content 1a"
        }

+ Response 201 (application/json)

        [
            {
                "id": "1",
                "content": "content 1a",
                "member_id": "2",
                "topic_id": "1"
            }
        ]
        
### Delete a Reply [DELETE]

Delete a reply.

+ Response 204
