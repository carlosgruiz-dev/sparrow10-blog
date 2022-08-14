---
title: "SSH Port Forwarding"
date: 2022-08-13T13:40:57Z
draft: false
tags: ["ssh", "bash", "gist"]
---

Something I do regulary is accessing a port from a server from my local machine. For this we use
[SSH Tunneling][1] and the technique called port forwarding. The structure of the command is as
follows:

```text
ssh -L [REMOTE_PORT]:LOCAL_ADDRESS:LOCAL_PORT USER@REMOTE_ADDRESS
```

To avoid login a session on the server, and send this task to process on background, we can add this
flags:

```text
ssh -L [REMOTE_PORT]:LOCAL_ADDRESS:LOCAL_PORT -Nf USER@REMOTE_ADDRESS
```

And if you want to create a shortcut for this using a shell script, you can use this gist as a
template.

{{< gist carlosgruiz-dev 5bde0ea77a76dee2864d19f33b1a884a port_forward.sh >}}

And now you can type in your termnal this to foward server ports to your local machine.

```bash
# port_forward.sh <port> <username> <server>
port_forward.sh 8080 carlos 192.168.0.15
```

Hope you find this helpful. See you next time.

[1]: https://www.ssh.com/academy/ssh/tunneling-example

