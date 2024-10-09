# Server Client Communication

## Setting up the repo

### Set up the REST Client

- Add the [REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client) VSCode extension to your VSCode.
- Issue an `Open user settings (JSON)` VSCode command, use `CTRL+SHIFT+P` and search for the command.
- Add the following line to the top level of the `settings.json`:  `"rest-client.previewOption": "exchange"`
- With this setting you will see both the request and the response in the REST Client.

### Install NPM dependencies

- Issue an `npm install` command.

## Tasks

### Task 1

- Open the `requests.http` file.
- Issue a GET request to the `http://developer.mozilla.org`.
- Examine the request and the response in the upcoming tab.

Answer the following questions:

- What information can you read from the first line of the **request**? 
- What is the method of this **request**?
- How do we call the other lines belongs to the **request**, e.g.: `User-Agent: vscode-restclient`
- What information can be read from the first line of the **response**?
- What does the `Content-Length` and `Content-Type` headers represent in the response?
- How do we separate the headers from the body?
- What does the body contains?

### Task 2

- Issue a new GET request to the `GET https://rickandmortyapi.com/api/character/2` endpoint.

Answer the following questions.

- What is the Status Code of the response?
- What do you see in the body?
- How do we now what is the "format" of the body?
- Can you create a new HTTP request to get the image of the character?

### Task 3

- Issue the `npm run serve` command. It spins up a server on `http://localhost:4444`.
- You can test it, by initiating a GET request to `http://localhost:4444/pets`. It should return a `200 OK` with an empty array (JSON) in the body.

- Create a new pet, using a POST request on `http://localhost:4444/pets`.
- The body of the POST request looks like this:

```json
{
  "name": "Fido",
  "kind": "dog"
}
```

- `name` is a string, it should not be empty. `kind` can be: "dog", "cat", "insect" or "reptile".

- You can always list your existing pets with `GET http://localhost:4444/pets`. If you restart the server, it always start with an empty array.

Answer the following questions:

- What is the difference between the request body and the response body?
- What is happening, if you miss the content type header?
- What is happening, if you send a malformed JSON?
- What is happening, if you send correctly formed JSON but, its values are invalid (e.g. the kind is "spider" or the name is an empty string)?
- Why it is not needed to send a `Content-Type` header for the GET requests?

