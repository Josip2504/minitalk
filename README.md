# Minitalk

## Overview

Minitalk is a small data exchange program that communicates between a client and a server using UNIX signals (`SIGUSR1`  and  `SIGUSR2`). The server receives messages from clients and prints them in real-time.

----------

## Features

-   **Server**:
    
    -   Prints its PID upon launch.
        
    -   Receives strings from clients and displays them instantly.
        
    -   Handles multiple clients sequentially without restarting.
        
-   **Client**:
    
    -   Takes the server PID and a string as arguments.
        
    -   Sends the string to the server using signals.
        
-   **Performance**:
    
    -   Optimized to avoid delays (e.g., 100 characters must transmit in under 1 second).
        

----------

## Usage

1.  **Compile**: Run  `make`  to produce two executables:  `server`  and  `client`.
    
2.  **Run the Server**: Launch  `./server`  and note the displayed PID.
    
3.  **Run the Client**: Send messages with  `./client <SERVER_PID> "Your message"`.
    

----------

## Technical Details

-   **Signals**: Only  `SIGUSR1`  and  `SIGUSR2`  are used.
    
-   **Global Variables**: One allowed per program (client/server).
    
