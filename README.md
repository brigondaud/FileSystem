## Getting Started

### Prerequisites

Install [Apache Ant](https://ant.apache.org/).

### Installing

To compile the project and the executables to run the authentication server, the file server and the client:
```
ant
```

## Running the tests

To execute the tests:
```
ant test
```

## Deployment

Before running the servers, launch Java RMI:
```
registry -J-Djava.rmi.server.codebase=file:shared.jar &
```

Launch the authentication server first:
```
./authentication.sh
```

Then launch the file server:
```
./server.sh
```

Use the client:
```
./client.sh <command> [options...]
```

### Generated directories and files

The authentication server generates a metadata file to save the client's credentials:

    .
    ├── authFiles
    │   ├── auth.metadata   # Clients credentials

The file server generates a metadata file to save file locks, with a directory for the file system:

    .
    ├── server.metadata
    ├── serverFiles
    │   ├── ...     # Files are stored here

The client generates a metadata file to store its credentials, with a directory for the file system:

    .
    ├── .credentials    # Client credentials
    ├── clientFiles
    │   ├── ...         # Files are stored here

## Built With

* [Apache Ant](https://ant.apache.org/)
* [JUnit](https://junit.org/junit4/)

## Authors

* **Baptiste Rigondaud**
* **Loïc Poncet**

