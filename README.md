`Person.json`

```javascript
{
    name: "string[]",
    age: "number",
    address: "Address"
}
```

`Address.json`

```javascript
{
    street: {
        type: "string",
        validation: "required|unique|min:3|max:40",
        description: ""
    },
    zip: "number",
    country: "Country[]"
}
```

`Country.json`

```javascript
[
    "DE", "EN", ...
]
```
