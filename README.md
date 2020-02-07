# Broken Hashserver Tests

## System

To test the Broken Hashserver, I used Postman and several consoles with curl.

My postman setup is available in the repo as the environment Base Environment and the collection Hashing Application.

The collection can be imported using the steps found here: https://learning.postman.com/docs/postman/collections/data-formats/#importing-postman-data

The environment can be imported by clicking the gear at the top right of Postman, then clicking the import button on the window that opens.

## Environment Variables
port - Allows you to change the port that you are running the HashServe on

url - Allows you to change where the host of the HashServe is located

request_count - Used by tests within Postman, Current value should be set to the most recent jobid to function properly in tests

hash - Used by tests only, changing this value does nothing as it is always set before it is read

password - The password you'd like hashed while running the collection.

## Notes
I only have one bug report written, but I found some behaviour that could be considered bugs if they are not intended.  

I noticed that sending an empty string resulted in that empty string being hashed.  The hashing algorithm I used to check the hash verified, so I wasn't able to decide if this was intended or not.

Also, due to the nature of the program, a user could end up sending a password to be hashed, but be unable to retrieve if another user shutdown the server.  While it was intended behaviour to finish hashing, the program does not save anything on shutdown, giving the user no benefit of having their hash completed.
