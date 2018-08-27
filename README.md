Every crafted object lives in its own file. The name of the file is the name of the object. It has basic data types like `string` or `int8` but also can reference a whole new object like `Address`. Both basic types and objects can be crafted as arrays.

Person.json

```javascript
{
    name: "string",
    age: "int8",
    address: "Address",
    contactDetails: "ContactDetail[]",
    friends: "int64[]",
}
```

If you need more details for a property you can present a whole JSON object instead of only the type.

Address.json

```javascript
{
    street: {
        type: "string",
        validation: "required|unique|min:3|max:40",
        description: "Street without house number"
    },
    number: "int16",
    zip: "int16",
    country: "Country"
}
```

You need to craft enums in a special way because they are not part of the JSON. We felt the most natural and simple way was if you define a JSON array containing the enum values.

Country.json

```javascript
[
    "DE", "EN", ...
]
```

You can also define inheritance. This here is the base object.

ContactDetail.json

```javascript
{
    type: "string",
}
```

And here are two sub objects. `Phone` and `Mail`. Their super class is determined in the filename.

ContactDetail.Phone.json

```javascript
{
    number: "string"
}
```

ContactDetail.Mail.json

```javascript
{
    mail: {
        type: "string",
        validation: "required|mail"
    }
}
```
