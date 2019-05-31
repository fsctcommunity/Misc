# Using the FSTOOL Command

## Non CLIADMIN usage
Usage of the fstool command is through the "root" user and not for using the cliadmin user in 8.1 or higher.

## About this document
This covers using the "fstool" comand and all of the syntax with fstool
- fstool va_test -h <ip address> -c manage
    - Shows if the host is manageable
- fstool va_test -h <ip address> 
    - Shows if manageable plus misc test results and open ports
- fstool va_test -h <ip address> -v > /tmp/va_test-host1.txt
    - Shows all of the processes, services, apps on a host and then saves it to a file
- fstool va_test -h <ip address> -c manage -v > /tmp/va_test-host1.txt
    - Shows all of the process, services, apps on host, managability and outputs it to a file
- fstool va_test -h <ip address> -c nmap  > /tmp/nmaphost1.txt
    - Nmap test and other misc information
- fstool va_test -h <ip address> -c nmapf  > /tmp/nmapfhost1.txt
    - Nmap test and misc information plus fingerprinting and outputs it to a text file
- fstool hostinfo <ip address> > /tmp/hostinfohost1.txt
    - Shows a view of what has been learned and is present in the database, this information is used in the GUI to display various property details
- fstool fingerprint -v nmap analyse <ip address>  > /tmp/analysehost1.txt   
    - Realtime analysis runs until you cntrl c out of the command
- fstool va_test -h <host ip> -c script -r ipconfig –a (or put any script name in the command where ipconfig is)
    - Test running a command or script on the host
