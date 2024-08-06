# ew-websocket
experiments with websocket

## CRUD Operations
As a developer\
I want to have implementation WebSocket-based communication between the back-end and front-end to handle CRUD operations efficiently\
So that a fron-end will be more interactive.
### System Overview
- **Back-end (WebSocket server)**: Manages and maintains the data.
- **Front-end (WebSocket client)**: Holds a partial copy of the back-end data.
### Workflow
1. **Initial Connection**:
	- Upon connection, the front-end sends a request to retrieve the necessary data and subscribes to updates for that data.
2. **Data Updates**:
	- Whenever there are changes in the back-end data, the server sends a message to all subscribed clients with the necessary information to update their local data.
3. **CRUD Operations**:
	- The front-end performs CRUD operations and sends WebSocket messages to manage data on the back-end.
4. **Message Integrity**:
	- Each message from the back-end to the front-end includes the last message ID for the current connection to ensure data integrity.
### Message Format and Standards
To ensure a well-structured message format, consider the following standards and patterns:
- **WAMP (Web Application Messaging Protocol)**:
	- Provides a standardized way for WebSocket communication with support for RPC (Remote Procedure Call) and PubSub (Publish-Subscribe) patterns.
    - [WAMP Documentation](https://wamp-proto.org/)
- **JSON-RPC**:
	- A protocol for remote procedure calls encoded in JSON. While not specific to WebSockets, it can be adapted for WebSocket communication.
    - [JSON-RPC Specification](https://www.jsonrpc.org/)
### HTTP Method Naming for Data Manipulation
Consider using HTTP method names to represent operations form back-end to front-ends:
- `PUT`: Replace the entire resource identified by a key.
- `PATCH`: Update parts of the resource identified by a key.
- `DELETE`: Remove the resource identified by a key.

**Handling Partial Resource Deletion**:
- For deleting a part of a resource, consider using `PATCH` or `DELETE`.
### Additional Considerations
- **GraphQL**:
    - Explore GraphQL for data subscriptions, as it provides a flexible and efficient way to manage and query data with real-time updates.
    - [GraphQL Documentation](https://graphql.org/)
