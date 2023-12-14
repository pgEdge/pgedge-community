
# pgEdge Community Lab

We build our secure and statically linked binaries on Rocky Linux 8 & 9 for *x86_64* & and on Rocky Linux 9 for *arm64*.   Our binaries run on nicely, in bare metal, vm's, & containers.  We are tested to run on EL8, EL9, SLES-15 & AWS Linux 2023, and Ubuntu 22.04.

## To install our CLI:

```python3 -c "$(curl -fsSL https://pgedge-upstream.s3.amazonaws.com/REPO/install24.py)```

```python3 -c "$(curl -fsSL https://pgedge-download.s3.amazonaws.com/REPO/install.py)```

## Useful Notes:
- Interested in our [CHANGELOG] (https://github.com/pgEdge/nodectl/blob/REL24_STABLE/CHANGELOG.md)

- Install as a non-root user from your `$HOME` directory

- configure [password-less sudo] (https://blog.pgedge.org/index.php/2023/04/07/passwordless-sudo/) for easier testing of advanced commands

- set up [password-less ssh to localhost] (https://blog.pgedge.org/index.php/2023/06/07/passwordless-ssh-to-localhost-2) for using `cluster localhost` commands

- Tested with Python 3.9 on EL8, EL9, SLE-15, & Amazon inux 2023

- Tested with Python 3.10 on Ubuntu 22.04

- Learn about running [pgEdge Platform] (https://www.pgedge.com/products/pgedge-platform) in production and/or for professional grade support

- Denis' [Cheatsheet] (https://blog.pgedge.org)

- pgedge [Community License] (https://www.pgedge.com/communitylicense>pgEdge Community License 1.0)



## Usage Samples:

Sandbox with latest *Postgres 16* & *Spock* installed into default *postgres* db<br>
```
pgedge/ctl install pg16 --start : install spock
```

<p>Create database *db1* owned by *denis* installing\configuring *pgedge* core components into *pg16* on *db1* database

```
./ctl install pgedge -U denis -P secret -d db1 --pg 16
```


<p>Create a cluster `cl1` on localhost with two nodes, then install `northwind` app into `cl1`

```
./ctl cluster localhost-create cl1 2 : cluster app-install cl1 northwind
```

<p>Create cluster 'clc' in docker compose with three nodes (*Coming Soon!*)<br>
```
./ctl cluster container-create clc 3 : cluster app-install clc pgbench
```

<p>Authenticate withe pgEdge Cloud credentials, then list your clusters<br>
```
./ctl secure login : secure cluster-list
```

<p>Create virtual machine 'n1' on **AWS** and virtual machine 'n2' on **Equinix Metal**<br>
```
./ctl machine create aws n1 : machine create eqnx n2
```

<p>Create a multi-cloud cluster 'mach1' (*Coming Soon!*)<br>
```
./ctl machine cluster-create mach1 aws-n1 eqnx-n2
```


