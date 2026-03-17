# DBETA AIDI Specification
### AI Digital Interface (AIDI) – Open Standard for Machine-Legible Web Systems

---

## Overview

The **AI Digital Interface (AIDI)** is a structured data layer designed to make websites fully interpretable by machines, including AI systems, search engines, and automated agents.

It moves beyond traditional SEO by providing explicit, structured, and connected data outputs that represent a website as a system — not just a collection of pages.

AIDI enables:
- Machine-readable content
- Clear entity relationships
- Predictable data structures
- Scalable digital architecture

---

## Why Machine Legibility Matters

Modern discovery is shifting from:
- keyword-based search  
→ to  
- AI-driven understanding  

Traditional websites are built for:
- human reading  
- visual interaction  

But AI systems require:
- structured outputs  
- clear relationships  
- consistent schemas  

Without this, websites become:
- partially understood  
- incorrectly interpreted  
- underutilised in AI-driven environments  

AIDI ensures your digital presence is:
- readable by AI  
- indexable as structured data  
- usable across future systems  

---

## The Problem with Traditional SEO

Traditional SEO focuses on:
- keywords
- metadata
- backlinks
- page optimisation

Limitations:
- Content is unstructured
- Relationships between pages are unclear
- Context must be inferred (often incorrectly)
- No standard way to expose full site data

AIDI replaces inference with clarity.

---

## Core Concept

AIDI introduces a parallel structured layer alongside the website.

Instead of:

Page → HTML → Interpretation

We provide:

System → Structured JSON → Direct Understanding

---

## File Structure

Recommended implementation structure:

/aidi/
  ├── index.json
  ├── services.json
  ├── articles.json
  ├── cases.json

Each file represents a collection of entities of a specific type.

---

## Endpoint Standard

All AIDI data should be accessible via:

https://example.com/aidi/

Requirements:
- Publicly accessible
- Returns valid JSON
- Updated regularly
- No authentication required
- Fast response time

---

## Schema Definition

### Service Entity

| Field        | Type     | Required | Description |
|--------------|----------|----------|-------------|
| id           | string   | Yes      | Unique identifier |
| name         | string   | Yes      | Human-readable name |
| description  | string   | Yes      | Summary |
| category     | string   | Yes      | Classification |
| related      | array    | No       | Linked entities |
| url          | string   | Yes      | Canonical URL |
| lastUpdated  | date     | Yes      | ISO format (YYYY-MM-DD) |

---

### Article Entity

| Field             | Type   | Required | Description |
|------------------|--------|----------|-------------|
| id               | string | Yes      | Unique identifier |
| title            | string | Yes      | Article title |
| category         | string | Yes      | Topic classification |
| relatedServices  | array  | No       | Linked services |
| author           | string | Yes      | Author or organisation |
| published        | date   | Yes      | ISO format |

---

## Example JSON

### Service

```json
{
  "type": "service",
  "id": "web-design",
  "name": "Web Design",
  "description": "Custom website design focused on performance, scalability, and user experience.",
  "category": "digital-services",
  "related": ["web-development", "seo"],
  "url": "/services/web-design",
  "lastUpdated": "2026-01-01"
}
{
  "type": "article",
  "id": "website-strategy-guide",
  "title": "Website Strategy: The Complete Guide",
  "category": "strategy",
  "relatedServices": ["web-design", "consulting"],
  "author": "DBETA",
  "published": "2026-01-10"
}