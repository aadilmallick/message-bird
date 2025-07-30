# message-bird

A repo for providing programmatic API access where developers can send messages via an API endpoint, and that message will be stored in a cloud database to this site and you can see all your messages in each channel,
kind of like slack, but offering any way to programmatically send messages.

The main website will be dedicated so that developers can set up their dashboard, set up any messaging channels, get the API fetching code to send messages to those channels.

## Data structure

- `users`: users will need email, usage, any api keys, and possibly stripe info. Api keys will be stored on user, each one will have usage amount, active, not-active, etc.
- `channels`: channels that contain messages. Each user can have many channels, and each channel can only have one user. There is a default channel.
- `messages`: Each individual message sent, and messages can only be sent to a specific channel. If a dev tries to send a message to a channel that doesn't exist, it will error out. A channel can have many messages but a message can only have one channel

## Website purposes

- Users can sign up for a free account and get an API key, once they have an API key, they can perform crud operations on them, rotating them out, where there can only be one active key at a time.
- Users can go on a pro plan for $7 a month or $48 a year or $79 for lifetime to get unlimited API usage, giving them unlimited channels (free users only get 3) and unlimited messages (free users only get 200)
- Users can view all their messages and all their channels. 


## API design

The server should expose an API that takes in an API key, checks usage and if valid for use.

- CRUD capabilities for messages
- CRUD capabilities for channels
- API send a message to a specific channel
