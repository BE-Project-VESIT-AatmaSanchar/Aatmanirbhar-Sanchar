
# Aatmanirbhar Sanchar - Self-Sufficient Communications

"Aatmanirbhar Sanchar" aims at providing the users a real time off the grid, secure and anonymous messaging service. We have fulfilled these claims by not incorporating any third-party APIs or other services. Our application is a cross-platform ephemeral anonymous messaging service providing End to End encryption while also enabling secure transmission of any kind of data files including but not limited to images, videos, and documents. The most unique feature of our product would be the use of our very own indigenous private server and database system without the inclusion of any third-party cloud servers.


## Deployment

To deploy this project please refer the following link which contains the instructions for 
    UBUNTU OS
    CENTOS
    WINDOWS 

[Deployment Cookbook](https://docs.google.com/document/d/1fSwpv6ZCRhyami0U6lCNLExHZtTIIsLdNf6ZaCJpGYY/edit#heading=h.ps3q5wgkiq74)



## Documentation

### Joining a chat room

When a user visits the web application at http://aatmanirbhar-sanchar.live/ hosted at our own private servers at VESIT, he is greeted with the homepage asking for a Username along with a Room key (RK)

![test](https://github.com/BE-Project-VESIT-AatmaSanchar/Aatmanirbhar-Sanchar/blob/master/screenshots/image14.png)

The entered username will act as the main identity of that particular user for the ongoing session. The room key is the most significant aspect of the chat application. This key serves a dual purpose:
    
    1) The hash of the key acts as the identity of a particular group chat created using the same. 
    2) The key itself is used in the encoding and decoding process of the incoming and outgoing messages.


### The Ephemeral Chat Room

When a user joins a chat room using the shared RK, the active user counter is incremented and their encrypted username is broadcasted to all the users active in the room utilizing which a greeting message is displayed

![test](https://github.com/BE-Project-VESIT-AatmaSanchar/Aatmanirbhar-Sanchar/blob/master/screenshots/image12.png)

Now every user is subscribed to the following events:

    Join Response: Handles a new incoming user.
    Chat Response: Handles incoming text messages.
    File Response: Handles incoming files.  
    Leave Response: Handles a user leaving.

When a user joins a chat room using the shared RK, the active user counter is incremented.

### Encryption Process

We use a double layered encryption process for achieving enhanced security. 
The first layer constitutes of our self-developed XOR encryption process:
    
    This encryption system is based on the concept that if an object is XOR’ed by the same key twice it will revert to its original state. To make this viable in this innovative era of cybercriminals vs cybersecurity we have added multiple iterations of permutations and combinations of the original entity. 
    To put it simply, a text message is first converted to its binary format in the shape of matrices. 
    These matrices are then shuffled and reshuffled to increase protection followed with it getting XOR’d by the room key. 
This encryption layer is followed by the Advance Encryption Standard (AES-256) algorithm to ensure privacy.

Finally, to ensure the integrity and authenticity of the transmitted message, the process of HMAC (hash-based message authentication code) verification is also practiced which guarantees tamper-proof messaging .

### Transmitting a message

The users can either directly type and send a text message using the provided chat box, else a user can also attach files up to the 50 MB limit to be transmitted. 

![test](https://github.com/BE-Project-VESIT-AatmaSanchar/Aatmanirbhar-Sanchar/blob/master/screenshots/image8.png)
![test](https://github.com/BE-Project-VESIT-AatmaSanchar/Aatmanirbhar-Sanchar/blob/master/screenshots/image21.png)
![test](https://github.com/BE-Project-VESIT-AatmaSanchar/Aatmanirbhar-Sanchar/blob/master/screenshots/image13.png)

### Leaving the chat room

A user can press the “leave” button to securely exit the chat room. 

Once pressed, the client is unsubscribed from all the live-time events and finally emits an encoded dictionary consisting of the hashed room key and the encrypted user name. 

This username is then broadcasted to every active user with a message indicating that this person left the chat room.

Once left, the user can not access the chat history and for enhanced security the chats are never stored on the local device. If every user leaves a particular chat room, the session is destroyed instantly.




## Algorithms for the respective modules developed

    Block Diagram
![test](https://github.com/BE-Project-VESIT-AatmaSanchar/Aatmanirbhar-Sanchar/blob/master/screenshots/image16.png)

    Joining Process
![test](https://github.com/BE-Project-VESIT-AatmaSanchar/Aatmanirbhar-Sanchar/blob/master/screenshots/image30.png)

    Sending a Text Message
![test](https://github.com/BE-Project-VESIT-AatmaSanchar/Aatmanirbhar-Sanchar/blob/master/screenshots/image10.png)

    File Transfer Process
![test](https://github.com/BE-Project-VESIT-AatmaSanchar/Aatmanirbhar-Sanchar/blob/master/screenshots/image1.png)



## Mobile Application

We have also developed a Mobile Application of the above stated web Application

Code for the same is there in this particular [Repository](https://github.com/BE-Project-VESIT-AatmaSanchar/Aatmanirbhar-Sanchar-App)

