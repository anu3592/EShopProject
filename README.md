# EShopCopilot — Agentic Coding with GitHub Copilot

> **The companion repository for the Udemy course:**
> ### 🚀 [Agentic Coding with GitHub Copilot: Skills, Agents and MCP](https://www.udemy.com/course/agentic-coding-with-github-copilot-skills-agents-and-mcp/?couponCode=LAUNCH)
> *Master Agentic Coding using Context, Instructions, Skills, and SubAgents with The Explore – Plan – Code – Review Process*

---

## About This Repository

This is the **hands-on project** built throughout the course. You will watch—step by step—how a full-stack, distributed e-commerce application (**EShop**) is designed, scaffolded, and built from scratch using **GitHub Copilot CLI** agentic workflows, without writing every line manually.

You act as the **AI Architect**: you define the intent, design the agents, and let Copilot do the heavy lifting under your direction.

---

## About the Course

In this comprehensive masterclass, you will transition from traditional prompt engineering to **orchestrating terminal-native AI agents**. Using the **GitHub Copilot CLI**, you will:

- Design and scaffold a **full-stack, distributed e-commerce architecture**
- Use **plan modes**, **context management**, and **custom agent `.md` files** to instruct Copilot CLI to scaffold, build, review, and refactor the application
- Learn the **Explore → Plan → Code → Review** agentic workflow process
- Build **Skills** and **SubAgents** that automate entire feature slices
- Integrate with **MCP (Model Context Protocol)** for extended AI capabilities

> 🎓 **Enroll now with a launch discount:**
> **[https://www.udemy.com/course/agentic-coding-with-github-copilot-skills-agents-and-mcp/?couponCode=LAUNCH](https://www.udemy.com/course/agentic-coding-with-github-copilot-skills-agents-and-mcp/?couponCode=LAUNCH)**

---

## Tech Stack

| Layer | Technology |
|---|---|
| Runtime | .NET 10 / C# 12 |
| Orchestration | .NET Aspire 13 |
| Backend | ASP.NET Core Minimal APIs |
| Frontend | Blazor Server (Interactive Server) |
| AI Tooling | GitHub Copilot CLI (Skills, Agents, MCP) |

---

## Solution Structure

```
EShopCopilot/
├── src/
│   ├── EShop.AppHost/          # Aspire orchestrator — wires all services
│   ├── EShop.ApiService/       # Minimal API backend
│   │   ├── Models/             # Domain models (Product, Order, Customer, Cart)
│   │   ├── Services/           # In-memory CRUD services (Singleton)
│   │   └── Endpoints/          # Minimal API route groups
│   ├── EShop.Web/              # Blazor Server frontend
│   │   ├── Components/Pages/   # Products, Customers, Cart, Orders pages
│   │   └── Services/           # Typed HTTP clients
│   └── EShop.ServiceDefaults/  # Shared OTel, health checks, resilience
│
└── .github/
    ├── copilot-instructions.md # Global Copilot context for this repo
    ├── skills/
    │   ├── minimal-api-feature/    # Skill: scaffold a full backend feature
    │   └── blazor-crud-component/  # Skill: scaffold a Blazor UI component
    └── agents/
        ├── dotnet-architect.agent.md              # Architecture review agent
        └── eshop-integration-orchestrator.agent.md # E2E integration test agent
```

---

## Domain Features

The EShop application implements four core domains, each with full CRUD via Minimal APIs and a Blazor UI:

| Domain | API Route | Description |
|---|---|---|
| Products | `/api/products` | Product catalog management |
| Customers | `/api/customers` | Customer management |
| Shopping Cart | `/api/cart` | Add/remove items, view cart |
| Orders | `/api/orders` | Place and track orders |

---

## Agentic Copilot Assets

A key learning outcome of the course is building **reusable AI assets** that live alongside your code:

### `.github/copilot-instructions.md`
The global context file that teaches Copilot about this codebase's architecture, conventions, and patterns — so every agentic command follows the project rules automatically.

### Skills (`/.github/skills/`)
Self-contained agentic workflows invocable from the Copilot CLI:

| Skill | Purpose |
|---|---|
| `minimal-api-feature` | Scaffolds a complete backend domain feature (Model + Service + Endpoints) |
| `blazor-crud-component` | Generates a Blazor page + typed HTTP client for a domain entity |

### Custom Agents (`/.github/agents/`)
Specialized review and test agents:

| Agent | Purpose |
|---|---|
| `dotnet-architect` | Reviews code changes for architectural integrity and clean architecture compliance |
| `eshop-integration-orchestrator` | Designs and generates end-to-end integration tests across multiple services |

---

## Getting Started

### Prerequisites

- [.NET 10 SDK](https://dotnet.microsoft.com/download)
- [Aspire CLI](https://learn.microsoft.com/en-us/dotnet/aspire/fundamentals/setup-tooling)
- [GitHub Copilot CLI](https://githubnext.com/projects/copilot-cli)

### Run the Application

```bash
# Clone the repo
git clone https://github.com/mehmetozkaya/EShopCopilot.git
cd EShopCopilot

# Run via Aspire (recommended — starts dashboard + all services)
aspire run --project src/EShop.AppHost

# Or use dotnet run on the AppHost
dotnet run --project src/EShop.AppHost
```

Once running, the **Aspire Dashboard** will display all service endpoints, health checks, logs, and traces.

### Build Only

```bash
dotnet build src/EShop.sln
```

---

## Why Agentic Coding?

Traditional AI-assisted coding is reactive — you ask, it answers, you copy-paste. **Agentic Coding** is different:

- You define **goals**, not prompts
- Copilot **plans and executes** multi-step tasks autonomously
- **Skills** encode your team's patterns once and reuse them across every feature
- **Custom agents** enforce architecture, generate tests, and review PRs automatically
- You stay in the **architect role** — the AI handles implementation details

---

## 🎓 Enroll in the Course

**[Agentic Coding with GitHub Copilot: Skills, Agents and MCP](https://www.udemy.com/course/agentic-coding-with-github-copilot-skills-agents-and-mcp/?couponCode=LAUNCH)**

Use coupon code **`LAUNCH`** for a special launch discount.

> Build real enterprise-grade applications faster, with higher quality, and with less manual effort — by mastering the future of AI-assisted software development.

---

## License

This project is provided for educational purposes as part of the Udemy course.