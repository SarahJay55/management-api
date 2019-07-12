The module to interact with the Auth0Management API

## To run this:

1. Clone the repo: `git@github.com:sarahjay55/auth0-management-api.git`.
2. Add Auth0 credentials to a new `.env` file.
3. Run `npm install` to install the dependencies.
3. Run files with the command `node get-client.js` and `node update-client.js`.
4. See changes in newly created file, `update-client.js`.

## Requirements:

- Have an Auth0 account and an account name.
- Have a management API: https://manage.auth0.com/dashboard/us/{CLIENT}/apis

## How this works:

1.  Requests an access token using client_id and client_secret
2.  Uses the access token to create a new ManagementClient
3.  Use the ManagementClient to interact with the API:
    https://auth0.github.io/node-auth0/module-management.ManagementClient.html

## Example usage to get a client:

```
Auth0Manager.init()
    .then(() => Auth0Manager.getClient())
    .then(client => {

        var data = fs.writeFileSync('./client-data.json', JSON.stringify(client), { encoding: 'utf8' });
        console.log(data);
        return client;
    })
    .catch(console.error);
```
