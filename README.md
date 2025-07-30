# message-bird
A repo for providing programmatic API access where developers can send push notifications to this site and you can see all your notifications.

The main website will be dedicated so that developers can set up their dashboard, set up any messaging channels, get the API fetching code to send messages to those channels.

## Data structure

- `users`: users will need email, usage, and possibly stripe info
- `channels`: channels that contain messages. Each user can have many channels, and each channel can only have one user. There is a default channel.
- `messages`: Each individual message sent, and messages can only be sent to a specific channel. If a dev tries to send a message to a channel that doesn't exist, it will error out. A channel can have many messages but a message can only have one channel
