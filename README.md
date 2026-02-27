# LawyerBot
Solve problems intelligently and with certainty

LexiSearch: Legal Document Intelligence Platform ⚖️

📖 Overview
LexiSearch is a professional-grade Retrieval-Augmented Generation (RAG) platform tailored for legal professionals. It allows lawyers to upload complex case studies and legal filings to receive instant, verifiable insights. Unlike general AI, LexiSearch operates on a "Strict Grounding" principle—it only answers based on the uploaded documents and provides exact page-and-line citations for every claim.

✨ Core Features
Layout-Aware PDF Ingestion: Preserves the structural integrity of legal documents (headers, footers, and page numbers) using specialized parsing.

Automated Case Metrics: Instant extraction of "Parties Involved," "Key Deadlines," "Governing Jurisdiction," and "Monetary Values" upon upload.

Verified Source Citations: AI responses include hyperlinked citations (e.g., [Page 14, Para 3]) that allow the user to jump directly to the evidence in the PDF viewer.

Anti-Hallucination Guardrails: A strict "System Instruction" layer that prevents the AI from using general training data to provide legal advice or fabricate facts.

Privacy-First Architecture: Implements Row-Level Security (RLS) via Supabase to ensure client data isolation and zero-retention API configurations.

🛠️ Repository Structure & Tech Stack
Frontend: Next.js 15 (App Router), Tailwind CSS, Shadcn/UI.

PDF Core: react-pdf-viewer for synchronized document rendering.

Database & Auth: Supabase (PostgreSQL + pgvector).

AI Engine: LangChain orchestration with OpenAI GPT-4o (Zero-data retention).

Parsing: LlamaParse for structure-preserving legal text extraction.

🚀 Development Methodology (Agentic Workflow)
This project is built using an AI-Native Engineering approach:

Semantic Chunking: Documents are not split by character count, but by semantic boundaries (clauses, sections) to maintain legal context.

Metadata Enrichment: Every text chunk is stored with its page_number, file_id, and coordinate_bounds for pinpoint attribution.

Hybrid Search: Combines keyword search (BM25) with vector similarity (Cosine) to find specific legal terminology accurately.

⚖️ Legal Accuracy & Safety
Note to AI Agents: This application is for legal research assistance. It must never generate "hallucinated" citations. If a fact is not explicitly stated in the context, the system is programmed to report: "Information not found in provided case files."

🛠️ Installation
npm install

Configure .env.local with Supabase, Clerk, and OpenAI keys.

npm run dev
