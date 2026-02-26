# Lesson 5: Workflows with Model Context Protocol (MCP)

## What is Model Context Protocol (MCP)?

MCP is an open standard enabling AI agents to interact with external tools, APIs, and data. MCP allows you to extend Gemini CLI's capabilities by providing access to hundreds of MCP servers for your favorite tools.

### Types of MCP Servers
- **Local** - Run on your machine
- **Remote** - Hosted externally, often requiring authentication

### Popular MCP Servers
- Canva
- Figma
- Stripe
- GitHub
- Notion

## Configuring MCP Servers

### Adding an MCP Server
```bash
gemini mcp add -t http canva https://mcp.canva.com/mcp
```

### MCP Commands

| Command | Description |
|---------|-------------|
| `/mcp` | View configured MCP servers |
| `/mcp auth <server_name>` | Authenticate with a remote MCP server |
| `/mcp desc` | See detailed description of all configured tools |

### Authentication Example
```
/mcp auth canva
```
> This kicks off the authentication flow for remote servers that require it.

## Prompts

> [!NOTE]
> Make a copy of the "TechStack Brand Kit" Canva design in order to follow along with this lesson.
> 
> Here is the link: [TechStack Canva Template](https://www.canva.com/design/DAG--ZeGG9A/KTvs7EXJ2-wYAmOzm3J36g/view?mode=preview)

### Prompt 1: List Designs
```
내가 가장 최근에 만든 디자인을 나열해줄 수 있어? (Can you list my most recent design?)
```

### Prompt 2: Create Social Kit Page
```
그 디자인의 내용을 읽고, @public/logo.svg를 사용한 소셜 키트(로고, 폰트, 색상, 소셜 태그 포함)가 있는 웹사이트의 /socials 페이지를 만들어줘. 그리고 웹사이트 푸터에 소셜 키트로 가는 링크를 추가해줘. (Read the design's content and use it to create a /socials page for the website that has a social kit using @public/logo.svg as well as font, colors and social tag. Add a link to the social kit in the footer of the website.)
```

## Optimizing MCP Usage

> **Important:** All MCP tool names and descriptions are sent to the model as context and consume input tokens. Only add MCP servers and tools you frequently use to avoid unnecessary token costs.

### Restricting Tools
You can limit which tools are enabled for an MCP server:

```bash
gemini mcp add -t http --allowed-tools get-design canva https://mcp.canva.com/mcp
```

This adds the Canva MCP server but only enables the `get-design` tool.

**Benefits:**
- **Token savings** - Fewer tool descriptions sent to the model
- **Security** - Restricts which actions the agent can perform
