# Team members:  

King Long Tang | tangkl@seas.upenn.edu

Jingqi Yao | jingqiy@seas.upenn.edu

Ruiwen Yang | ruiweny@seas.upenn.edu

Richard Zhang | zhank24@seas.upenn.edu

---

# PennCloud Distributed Key-Value Store System

This project implements a distributed cloud platform with a key-value store backend, similar to Google Apps with Gmail and Drive functionality.

## System Components

- **Backend Key-Value Store**: Distributed, replicated storage system
- **Frontend Web Servers**: Web interface for email and file storage
- **Frontend Load Balancer**
- **Master Node**: Coordinates backend nodes and tablet distribution
- **Admin Console**: Web interface for system monitoring and management

## Running the System

To run the entire system at once (master, backend nodes, frontend servers, and load balancer):

```bash
# Make the script executable (first time only)
chmod +x run_all.sh

# Start all system components
./run_all.sh
```

This will start:
- 1 master node
- 9 backend KV store nodes
- Multiple frontend web servers
- 1 load balancer
- Admin console

## Accessing the System

- **Web Interface**: http://localhost:8888/
- **Admin Console**: http://localhost:9000/admin

## Testing and Demonstration

For detailed testing instructions and demonstration scenarios:
- See [backend/README.md](backend/README.md) for KV store testing
- See [admin_console/README.md](admin_console/README.md) for admin console usage
- See [frontend/README.md](frontend/README.md) for frontend functionality

## Fault Tolerance

1. Each tablet is replicated across multiple nodes
2. Primary-based replication ensures data consistency
3. Automatic failover when primary nodes fail
4. Recovery mechanisms to restore failed nodes

You can test fault tolerance by stopping nodes through the admin console or via terminal commands.
