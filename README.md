# OptimizedSplitTunnel
Configure a split tunnel to exclude video streaming traffic

Software Support: Starting with GlobalProtect™ App 4.1 and with PAN-OS® 8.1 and later releases
OS Support:       Windows 7 Service Pack 2 and later releases and macOS 10.10 and later releases
In addition to route-based split tunneling, the GlobalProtect app for Windows and macOS endpoints now supports split tunneling based on destination domain, client process, and HTTP/HTTPS video streaming application.

GP agent will know the video traffic based on the app ID. Firewall sends a redirect message to the GP App as soon as it identifies the video traffic based on the app-id .
 
Step 1 : Users plays a youtube video on a GP connected machine.

Step 2: GP sends all the youtube video streaming traffic destined to youtube to firewall

Step 3: Firewall decrypts the packet ( ssl decryption must be allowed ) and identifies the traffic as a video traffic based on the app-id

Step 4: Firewall sends a video redirect message to GP App / GP Agent.

Step 5: GP agent disconnects the youtube session from the tunnel and add that ip to the exclude ip list.

Step 6: GP agent establishes a new session to that youtube ip on the physical adapter.

Repeat the skillet to add additional media App-IDs.
