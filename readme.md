Not intended for any commercial use, purely for the fun of re-creating a simple redis clone.

## How it works

When the service is run, it will look for or create an append-only-file which will serve as a cache of data. This is useful otherwise the data will be lost if the service fails or is exited as the main point of REDIS is to be a in memory database.

The service will listen for a TCP RESP (redis serialization protocol) data packet. This then gets deserialized in the service, handled and possibly a response gets serialized and sent back to the client.