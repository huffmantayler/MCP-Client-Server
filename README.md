# Spring AI MCP Projects

This repository contains two Spring Boot projects that demonstrate the implementation of a Model Control Protocol (MCP) server and client using Spring AI. These projects are based on Spring AI's example projects and have been modified to work together using OpenAI's API.

## Project Origins

Both projects are derived from Spring AI's official examples:
- The MCP server is based on Spring AI's `starter-default-server` example
- The MCP client is based on Spring AI's `starter-default-client` example

The original examples have been adapted to:
- Work together in a client-server architecture
- Use OpenAI's API for natural language processing
- Implement a custom tool (DateTool) to demonstrate MCP functionality
- Configure proper communication between client and server

## Projects Overview

### 1. MCP Server (`spring-ai-mcp-server`)

The MCP server is a Spring Boot application that implements the Model Control Protocol, providing tools and endpoints for AI model interaction. It serves as the backend service that handles tool execution and model responses.

Key features:
- Tool execution framework
- RESTful API endpoints for MCP interactions
- Integration with Spring AI for model management
- Example tool implementation (DateTool)

### 2. MCP Client (`spring-ai-mcp-client`)

The MCP client is a Spring Boot application that demonstrates how to interact with the MCP server. It provides a user interface and handles the communication with the MCP server.

Key features:
- Integration with ChatGPT for natural language processing
- MCP client configuration for server communication
- RESTful API endpoints for client interactions
- Example implementation of client-server communication

## Getting Started

### Prerequisites

- Java 17 or higher
- Maven
- OpenAI API key (for ChatGPT integration)

### Configuration

1. MCP Server Configuration (`spring-ai-mcp-server/src/main/resources/application.properties`):
```properties
server.port=8080
spring.ai.openai.api-key=your-openai-api-key
```

2. MCP Client Configuration (`spring-ai-mcp-client/src/main/resources/application.properties`):
```properties
server.port=8081
spring.ai.openai.api-key=your-openai-api-key
spring.ai.mcp.server.url=http://localhost:8080
```

### Running the Applications

1. Start the MCP Server:
```bash
cd spring-ai-mcp-server
mvn spring-boot:run
```

2. Start the MCP Client:
```bash
cd spring-ai-mcp-client
mvn spring-boot:run
```

## API Endpoints

### MCP Server Endpoints

- `POST /mcp/chat`: Main endpoint for MCP interactions
- `POST /mcp/tools`: Endpoint for tool execution

### MCP Client Endpoints

- `POST /chat`: Endpoint for client-side chat interactions
- `POST /mcp/chat`: Endpoint for MCP-specific interactions

## Project Structure

### MCP Server
```
spring-ai-mcp-server/
├── src/main/java/com/example/springaimcp/
│   ├── controller/
│   │   └── McpController.java
│   ├── tool/
│   │   └── DateTool.java
│   └── SpringAiMcpApplication.java
└── src/main/resources/
    └── application.properties
```

### MCP Client
```
spring-ai-mcp-client/
├── src/main/java/com/example/springaimcpclient/
│   ├── controller/
│   │   └── ChatController.java
│   ├── config/
│   │   └── McpConfig.java
│   └── SpringAiMcpClientApplication.java
└── src/main/resources/
    └── application.properties
```

## Dependencies

Both projects use Spring Boot and Spring AI with the following key dependencies:
- `spring-boot-starter-web`
- `spring-ai-openai-spring-boot-starter`
- `spring-ai-mcp-spring-boot-starter`

## License

This project is licensed under the MIT License - see the LICENSE file for details. 