---
title: "Getting Started with GitHub Webhooks in C#"
slug: "github-webhooks-csharp"
date: "2025-07-06"
tags:
  - GitHub
  - Webhooks
  - C#
  - ASP.NET Core
---

# Handling GitHub Webhooks in C

GitHub webhooks let you trigger actions when events happen in a repository, like when someone pushes a commit.

To start, you'll need to:

1. Set up a GitHub webhook.
2. Configure your server to receive the payload.
3. Validate the webhook using a shared secret.

## 🚀 Setting Up the Webhook

In your GitHub repository:

- Go to `Settings` → `Webhooks`
- Click **"Add webhook"**
- Set the **payload URL** to your endpoint (e.g., `https://example.com/webhook`)
- Choose content type: `application/json`
- Set a **secret** (you'll need this to validate the webhook)

## 🛠️ Validating the Webhook in C

To verify the webhook, GitHub sends a signature in the header:

```http
X-Hub-Signature-256: sha256=abcdef123456...

```
