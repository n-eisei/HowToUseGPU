1. copy "gpususer.pem" and "config" files in .ssh folder to  your %HOME%/.ssh folder
2. execute the following command
 ```
  $> ssh <your_username>@gpu-server -p <your_port>
 ```
3. input <your_password> 

* please ask for <your_username> and <your_password> to administrator.
* <your_port> is setup for different cuda versions:
   -   cuda 11.3   -- <your_port> is 2113
   -   cuda 11.6   -- <your_port> is 2116
   -   cuda 11.8   -- <your_port> is 2118

 

