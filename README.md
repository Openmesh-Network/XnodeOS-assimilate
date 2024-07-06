# XnodeOS-assimilate

This script/utility is meant to execute only on newly provisioned systems. It will destroy all data on your system.

## What is this?
A script to install XnodeOS on non-XnodeOS hosts.

Use with extreme caution and only on newly provisioned systems.

## How do I use it?

0) **Read and understand the [the script](./xnodeos-assimilate)**
1) Deploy any custom configuration you want on your host
2) Deploy your host as non-Nix Operating System.
3) Deploy an SSH key for the root user.

> *NB:* This step is important.
> The root user will not have a password when xnodeos-assimilate runs to completion.
> To enable root login, you *must* have an SSH key configured.

4) run the script with (replace main with whichever reference (dev, commitish, etc) you wish to deploy from):
```
  curl https://raw.githubusercontent.com/openmesh-network/XnodeOS-assimilate/main/xnodeos-assimilate | NIX_CHANNEL=XnodeOS-dev bash -x
```

*NB*: This script wipes out the targeted host's root filesystem when it runs to completion.
Any errors halt execution.
A failure will leave the system in an inconsistent state,
and so it is advised to run with `bash -x`.
