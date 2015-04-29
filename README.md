# meteor-issue-4286
Reproduction https://github.com/meteor/meteor/issues/4286

At `/meteor-issue-4286-server`, I run `meteor`. It's `localhost:3000` server at browser.

At `/meteor-issue-4286-client`, I run `meteor --port 400`. It's `localhost:4000` client at browser.

I create an account with `accounts-ui` at server, then log in that account at client. What I want is that the `accounts-ui` show me it has got me logged in to the server's accounts from the client. But it shows nothing. At browser's console, both server and client's localstorages have `Meteor.loginToken`, `Meteor.loginTokenExpires` and the same `Meteor.userId`. But if I refresh the client page, all of them will be gone.

If I uncommented `Meteor.users = new Mongo.Collection("users", {connection: connection});` of the client. The `accounts-ui` will show me I have logged in, but has the same problem as I refresh the page.

I'm not sure it's a bug or not. I think I'm lack of the knowledge about `Accounts` and `DDP` of Meteor to resolve this problem. Please show me the way. Thank you.
