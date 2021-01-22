# Base lab

Basic lab to test simple topology (1 hub, 2 leafs)

## Usage

Launch the routers:

```
$ docker-compose build
$ docker-compose up
```

Launch the clients (from the qpid-proton examples):

```
# The receiver
$ python simple_recv.py -a localhost:5672/examples -m 15
# The sender
$ python simple_send.py -a localhost:5673/examples -m 5
```

## Beyond the standard usage

Simulate the failover:

```
$ docker stop qdr-multi-routers_router-node-1_1 # localhost:5673
```

Normally message will be sent through localhost:5674
