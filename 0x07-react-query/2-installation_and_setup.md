# Installation and set up

## Installing React Query in your project

To install React Query in you project, run:

```bash
npm install @tanstack/react-query
```

## Setting up a fake server

Since we don't have a real backend, we can use a fake server.

The fake server allows us to practice fetching, mutating, and handling data responses without needing a real backend.

For this we will use json server npm package.

Install json-server to your project:

```bash
npm install json-server
```

In the root directory, create a db.json file and past in the following data:

```json
{
  "students": [
    {
      "firstName": "John",
      "lastName": "Doe",
      "age": 20
    },
    {
      "firstName": "Jane",
      "lastName": "Smith",
      "age": 22
    },
    {
      "firstName": "Michael",
      "lastName": "Johnson",
      "age": 21
    },
    {
      "firstName": "Emily",
      "lastName": "Davis",
      "age": 19
    },
    {
      "firstName": "Daniel",
      "lastName": "Brown",
      "age": 23
    }
  ]
}
```

Finally, run:

```bash
npx json-server db.json
```

This will start the server on port 3000.

If you want a custom port, you can set up a script, add the following script to your package.json under scripts:

```json
"serve-json": "json-server --watch db.json --port 4000"
```

Finally, run:

```bash
npm run serve-json
```