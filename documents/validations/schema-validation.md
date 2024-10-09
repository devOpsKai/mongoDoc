# Schema Validations

``{
 `"validator": {`
   ` $jsonSchema: {`
      "bsonType": "object",
      "description": "Document describing a mountain peak",
      "required": ["name", "height", "location"],
      "properties": {
        "name": {
                    "bsonType": "string",
                    "description": "Name must be a string and is required"
                },
                "height": {
                    "bsonType": "number",
                    "description": "Height must be a number between 100 and 10000 and is required",
                    "minimum": 100,
                    "maximum": 10000
                },
                "location": {
                    "bsonType": "array",
                    "description": "Location must be an array of strings",
                    "minItems": 1,
                    "uniqueItems": true,
                    "items": {
                        "bsonType": "string"
                    }
                }
            },
        }
    }
})
``
