# Napas Mock Server

I create this piece of software to simulate/mock the Vietnam Card Switching network (NAPAS) messaging server using jPOS (https://jpos.org). The code base is Groovy/JAVA.

This Napas Mock Server runs on port ```8001```, using ```org.jpos.iso.channel.NACChannel``` and ```devatnight.napas.NapasPackager```.

I suggest you read this excellent document from jPOS [here](http://jpos.org/doc/proguide-draft.pdf) before marching on.

The packager is located [here](https://github.com/long-tran/napas-mock-server/blob/master/src/main/groovy/devatnight/napas/NapasPackager.groovy).
All the Q2 XML deployment files are [here](https://github.com/long-tran/napas-mock-server/tree/master/q2-xml).

## How do you run this?

1. Install [gradle](https://gradle.org)
2. Clone my code here: https://github.com/long-tran/napas-mock-server
3. Do a: ```gradle q2``` in your local directory
4. Play around with the scripts under ```q2-xml```
5. Enjoy your cup of coffee

## Implementation status:

1. **DONE**: Created a Napas Mock Server running on port ```8001```, using ```org.jpos.iso.channel.NACChannel``` and ```devatnight.napas.NapasPackager```.
2. **DONE**: Respond to all message with a response code (field 39) as the last 02 digits of the Trace Number (field 11). Example: you send a message with Trace Number = 0192055, then, the response will be 55, see what I did there? Cool, huh. The magic is in this [BSH file] (https://github.com/long-tran/napas-mock-server/blob/master/q2-xml/scripts/napas-simulator-server-8001-listener.bsh).
3. **DONE**: Create a script to initiate a message back to the "lastConnectedISOChannel" [here](https://github.com/long-tran/napas-mock-server/blob/master/q2-xml/80_scripts_test_mock_server_initiate.xml).
4. **NOT DONE**: Unit tests.

# Credits
This application uses Open Source components. You can find the source code of their open source projects along with license information below. We acknowledge and are grateful to these developers for their contributions to open source.

Project: jPOS, https://jpos.org, by [Alejandro Revilla](https://github.com/ar)
