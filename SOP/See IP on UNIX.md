To see your IP address on a UNIX system, you can use the following commands in the terminal:

- To display all network interfaces and their IP addresses, use:
    
    ```
    ifconfig -a
    ```
    
    or
    
    ```
    ip addr
    hostname -I
    
    ```



- To find out your public IP address, you can use the `curl` command with an external service:
    
    ```
    curl ifconfig.me
    ```
    

[These commands will provide you with the private IP addresses for all network interfaces and the public IP address that is visible on the internet](https://www.howtouselinux.com/post/check-ip-address-in-linux)[1](https://www.howtouselinux.com/post/check-ip-address-in-linux)[2](https://linuxize.com/post/how-to-find-ip-address-linux/). [Remember that some UNIX systems may require you to specify the full path to `ifconfig`, such as `/sbin/ifconfig -a` or `/etc/ifconfig -a`, especially if you’re not logged in as root](https://superuser.com/questions/347408/how-to-get-the-ip-address-of-a-unix-machine)[3](https://superuser.com/questions/347408/how-to-get-the-ip-address-of-a-unix-machine).