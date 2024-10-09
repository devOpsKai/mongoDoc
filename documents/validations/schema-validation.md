# Schema Validations

```javascript
{
    validator: {
        $jsonSchema: {
            bsonType: "object",
            required: ["name", "age", "memberTier"],
            properties: {
                name: {
                    bsonType: "string"
                },
                age: {
                    bsonType: "int",
                    minimum: 18
                },
                memberTier: {
                    enum: ["gold", "silver", "bronze"],
                    description: "can only be one of the three allowed tiers"
                },
                height: {
                    bsonType: "number",
                    description: "Height must be a number between 100 and 10000 and is required",
                    minimum: 100,
                    maximum: 10000
                },
                location: {
                    bsonType: "array",
                    description: "Location must be an array of strings",
                    minItems: 1,
                    uniqueItems: true,
                    items: {
                        "bsonType": "string"
                    }
                },
                ascents: {
                    bsonType: "object",
                    description: "Ascent attempts information",
                    required: ["total"],
                    properties: {
                        total: {
                            bsonType: "number",
                            description: "Total number of ascents must be 0 or higher",
                            minimum: 0
                        }
                    }
                }
            },
        },
        if: {
            properties: { memberTier: { const: "gold" } }
        },
        then: {
            required: ["premiumFeatures"],
            properties: {
                premiumFeatures: {
                    bsonType: "array",
                    items: {
                        bsonType: "string"
                    }
                }
            }
        },
        else: {
            properties: {
                premiumFeatures: {
                    bsonType: "null"
                }
            }
        }
    }
};
```
