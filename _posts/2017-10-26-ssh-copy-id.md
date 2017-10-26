---
layout: default
status: publish
published: true
title: "Command line tapas: How to install your SSH key on a remote server"
---

## 1. Nice way

You can install an SSH key by executing

    ssh-copy-id user@servername.com

Now you can log in to the remote server with your password and ssh-copy-id will do the rest.
    
## 2. Manual way

Append your public ssh key to the `authorized_key` file on the server.

As a one-liner:

    cat ~/.ssh/id_rsa.pub | ssh user@servername.com 'cat>> ~/.ssh/authorized_keys' 

## Conclusion

Both commands pretty much do the same. The first way is way easier though.

The next time you can connect to the server using your SSH key.

    ssh user@servername.com    
