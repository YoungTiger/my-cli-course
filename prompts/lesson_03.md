# Lesson 3: A Tour of Gemini CLI

## Getting Started

### Installation

```bash
npm install -g @google/gemini-cli
```

## Important Slash Commands

| Command | Description |
|---------|-------------|
| `/auth` | View authentication methods and login (e.g., Google auth) |
| `/help` | View a list of all built-in commands and shortcuts |
| `/theme` | Customize the look and feel of Gemini CLI |
| `/settings` | See all the different areas of Gemini CLI you can customize |
| `/model` | Change different modes and models for your requests |
| `/clear` | Wipe history and reset conversation |
| `/stats` | Track model calls and token usage |
| `/docs` | View the documentation |
| `/quit` or `/exit` | Exit Gemini CLI |

**Tip:** Double escape to clear input prompt.

## Prompts

### Prompt 1: Reading Suggestions
```
작년 2025 TechStack 컨퍼런스의 주최자들이 몇 가지 제안을 남겨뒀는데, @suggestions.md에서 그 내용을 읽어서 나에게 말해줄래? (Last year's organizers of the 2025 TechStack conference left some suggestions, can you read them to me from @suggestions.md)
```

### Prompt 2: Research Best Practices
```
이 내용이 온라인에서 알려진 기술 컨퍼런스 운영의 모범 사례(best practices)와 일치하는지 확인해줄래? (Can you see if this matches with online best practices for organizing a tech conference?)
```

### Prompt 3: Update Documentation
```
새로 발견한 내용을 우리 제안 문서(suggestions doc)에 추가해줘. (Add the new findings to our suggestions doc.)
```

> **Note:** This prompt will show tool call and requirement to accept writing/editing to files.
