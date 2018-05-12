# Bit-Torrent-Simulator
It's a peer to peer file sharing application similar to Bit Torrent

This project was done as a part of the course Computer Networks at University of Florida in Fall '17. 

About the Project
------------------

All operations are assumed to be implemented using reliable transport protocol (i.e TCP). 
The interactions between 2 peers is symmetrical i.e messages sent in both directions look the same. 
The protocol consists of a handshaking followed by a never-ending stream of length prefixed messages. It follows the principle of preferred neighbours where each peer chooses a certain number of peers to tranfer data to. The peers also follow the choking-unchoking principle on its preferred neighbors. Furthermore, each peer optimistically unchokes a peer after a certain interval. 

How to test it
------------------------
To simulate multiple peers running in parallel, we lauch multiple threads where each thread represents a peer process. We are running the threads in the same system using localhost address but we can run them in different systems as well and get the same behavior. 

PeerInfo.cfg is the configuration file and is of the format [peer ID] [host name] [listening port] [has file or not]. So at least, one peer process should have the file in the beginning. 
After execution all the peer processes should have it! 

common.cfg has additional configuration fuctionalities that need to be updated. This is what we currently have - 
NumberOfPreferredNeighbors 2 UnchokingInterval 5 OptimisticUnchokingInterval 15 FileName test.csv FileSize 335872 PieceSize 16794

Once the above is done, we can compile peerProcess.java
Next we need to run each peer individually using their peerId
After the every peer process has started, the files should be present in all the peers once the program finishes execution. 
