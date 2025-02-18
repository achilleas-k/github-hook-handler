# github-hook-handler

Tiny client for receiving and handling GitHub hook payloads

## Usage

The main component is the Listener class defined in [ghooklistener/listener.py](ghooklistener/listener.py).
In order to create a service that listens for events and performs certain tasks, an instance of this class needs to be created with a given name and a callback `handlefunc` function.

The `handlefunc` function will be called whenever a push event is received.
The function should return a boolean indicating success (True) or failure (False) and a message.

## Examples

An example handler can be found in [handlers/example.py](handlers/example.py).
This handler simply prints the data it receives to stdout and reports success.

## Cloner

A more concrete example (and the reason for creating this project) is the [cloner](handlers/cloner.py) handler.
The cloner handler checks the branch ref and if it's *master* (`refs/heads/master`), it initiates pull of the repository.
