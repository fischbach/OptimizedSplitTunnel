# OptimizedSplitTunnel
GP - Split tunnel of media AppIDs


GP agent will know the video traffic based on the app ID. Firewall sends a redirect message to the GP App as soon as it identifies the video traffic based on the app-id .
 
Step 1 : Users plays a youtube video on a GP connected machine.

Step 2: GP sends all the youtube video streaming traffic destined to youtube to firewall

Step 3: Firewall decrypts the packet ( ssl decryption must be allowed ) and identifies the traffic as a video traffic based on the app-id

Step 4: Firewall sends a video redirect message to GP App / GP Agent.

Step 5: GP agent disconnects the youtube session from the tunnel and add that ip to the exclude ip list.

Step 6: GP agent establishes a new session to that youtube ip on the physical adapter.
