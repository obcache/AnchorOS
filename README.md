# AnchorOS

## Core Idea
AnchorOS provides a governed capsule-based system for persisting, managing, and orchestrating ChatGPT session data.

## 🧩 The Problem & Why AnchorOS

Modern ChatGPT sessions are powerful, but they suffer from three persistent issues:

1. **Session Ephemerality**  
   - Each new conversation begins as a blank slate.  
   - Hard-won heuristics, context, and conventions are lost unless manually restated.  

2. **Unbounded Growth**  
   - Research sessions become extremely heavy in tokens.  
   - Exploratory context lingers long after it is needed, bloating session state.  

3. **Lack of Governance**  
   - No shared protocol for how to structure, load, or manage custom instructions.  
   - Each session is an ad-hoc experiment rather than an operational system.  

---

## ✅ The AnchorOS Solution

AnchorOS introduces a **governed, modular layer** on top of ChatGPT:

- **Capsules** externalize knowledge → portable, versioned, and lightweight.  
- **Bootstrap** ensures critical capsules always load consistently at startup.  
- **Protocol** governs minting, backups, upgrades, and rollback.  
- **Index** keeps capsule references in sync across versions.  
- **Backups** ensure all capsules are re-rendered and archived for consistency.  

**Result:**  
- Sessions remain **light and predictable** (~25–30k token bootstrap payload).  
- Learned behaviors and heuristics persist **outside session ephemerality**.  
- Operators can **install, list, and manage capsules** like modules in a true OS.  

⚓ AnchorOS = *Govern your ChatGPT session data.*  

## Getting Started
Clone the repository and load the bootstrap capsules into your session.
