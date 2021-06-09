# Application-Failed-to-Start


It sometimes happen even when we stop running processes in IDE with help of Red button , we continue to get same error.

It was resolved with following steps,

Check what processes are running at available ports

**netstat -ao |find /i "listening"**

We get following

TCP    0.0.0.0:7981           machinename:0        LISTENING       2428
TCP    0.0.0.0:7982           machinename:0        LISTENING       2428
TCP    0.0.0.0:8080           machinename:0        LISTENING       12704
TCP    0.0.0.0:8500           machinename:0        LISTENING       2428

i.e. Port Numbers and what Process Id they are listening to

Stop process running at your port number(In this case it is 8080 & Process Id is 12704)

**Taskkill /F /IM 12704**

(Note: Mention correct Process Id)
