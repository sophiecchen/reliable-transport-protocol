# Reliable Transport Protocol

This is a reliable transport protocol, called WTP, built on UDP and implemented in C++. WTP provides inorder, reliable delivery of UDP datagrams despite possible packet loss, delay, corruption, etc. This implementation that there is only one sender and one receiver communicating.

`wSender` is responsible for sending datagrams and can be invoked as follows:

`$ ./wSender -h 127.0.0.1 -p 8000 -w 10 -i input.in -o sender.out`

* `-h | --hostname`: The IP address of the host that `wReceiver` is running on
* `-p | --port`: The port number `wReceiver` is listening on
* `-w | --window-size`: The maximum number of outstanding packets in the current window
* `-i | --input-file`: The file that wSender will send
* `-o | --output-log`: The file that will hold the logging information of `wSender`

`wReceiver` is responsible for receiving datagrams and can be invoked as follows:

`$ ./wReceiver -p 8000 -w 10 -d /tmp -o receiver.out`

* `-p | --port` The port number on which `wReceiver` is listening for data
* `-w | --window-size` The maximum number of outstanding packets
* `-d | --output-dir` The directory that the `wReceiver` will store the received files in
* `-o | --output-log` The file that will hold the logging information of `wReceiver`

`wSenderOpt` and `wReceiverOpt` are the optimized counterparts to `wSender` and `wReceiver`. They can be invoked with the same respective command-line arguments as above.

The information above was taken from the full spec, written by EECS 489 instructors.

*This project was completed for my network class and is stored in a private repo as per my university's honor code. If you are a involved in recruitment or hiring and would like details on this project, please contact me.*
