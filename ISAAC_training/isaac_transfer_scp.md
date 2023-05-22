---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: starstuff
parent: posts
nav_order: 1
---


Please also check out the resources for ISAAC and high-performance computing at the [OIT documentation](https://oit.utk.edu/hpsc/isaac-open-enclave-new-kpb/data-transfer-new-cluster-kpb-2/) and [OIT Workshops and Training](https://oit.utk.edu/hpsc/overview/workshop-recordings/) pages

## Confirm ISAAC SSH login works
From command line (terminal), first confirm that you can [login to ISAAC](https://oit.utk.edu/hpsc/isaac-open-enclave-new-kpb/access-and-login-isaac-ng/) using ssh:

```
ssh <username>@login.isaac.utk.edu
```

This should prompt you for your password and 2FA login. If not, depending on your status as student/staff, you may also need to try:

```
ssh <username>@login.isaac.utk.edu
```

## Confirm you have access to the data directory of interest

Data on ISAAC is typically stored in a path such as /lustre/isaac/proj/UTK... where the "UTK..." field is an ISAAC project that you have access to.

If you're unsure whether you have access to a certain ISAAC account, login to the [ISAAC User Portal](https://portal.acf.tennessee.edu/accounts/login/?next=/) and see what projects your account is attached to.

List the contents of your directory of interest using the following:

```
ls </path/to/your/data/>
```

If that works for you, you should have the ability to go to the directory where you would like the files to end up, exit your ssh login to ISAAC using the following:

```
exit
```

## Copy files to local computer using SCP

then do one of the following:

...on [Windows Powershell](https://github.com/mestato/EPP622_2022/wiki/Getting-started-with-PowerShell-(Windows-users))/Linux:

```
scp -r <username>@dtn1.isaac.utk.edu:</path/to/their/files/folder/> ./
```

...on macOS:

```
scp -r '<username>@dtn1.isaac.utk.edu:</path/to/their/files/folder/>' ./
```

note:

"\<username>" is replaced by your netid

"\</path/to/their/files/folder/>" is replaced with the full path (beginning with "/") to the directory of your sequence data on ISAAC).

If all goes well, you'll be prompted to use your password and two factor authentication. The file transfer may take awhile so you'll need to be sure your computer doesn't sleep during the transfer.
