# AnchorOS

**AnchorOS** is a modular governance layer for ChatGPT sessions.  
It transforms raw session sprawl into **structured, portable, and governable capsules**, enabling consistent and repeatable workflows.  

---

## ✨ Core Idea

- **Capsules**: Portable documents that encapsulate rules, heuristics, or workflows.  
- **Modules**: General plug-in units. Capsules are one type of module (others may follow: `workflow:`, `adapter:`, `theme:`, etc.).  
- **Index**: Tracks all current capsule versions and filenames (canonical alias → versioned filename mapping).  
- **Bootstrap**: Ensures required capsules load and governs startup, upgrade/skip logic, and rollback.  
- **Protocol**: Defines the rules for capsule minting, backups, upgrades, installs, and Index synchronization.  

---

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
- **Protocol** governs minting, backups, upgrades, installs, and rollback.  
- **Index** keeps capsule references in sync across versions (and is auto-refreshed on mint).  
- **Backups** re-render all capsules individually and archive them for integrity and recovery.  

**Result:**  
- Sessions remain **light and predictable** (~25–30k token bootstrap payload).  
- Learned behaviors and heuristics persist **outside session ephemerality**.  
- Operators can **install, list, and manage capsules** like modules in a true OS.  

⚓ AnchorOS = *Govern your ChatGPT session data.*  

---

## 🚀 Getting Started

1. Clone this repository.  
2. Download the bootstrap and core capsules from the latest release or the repo root.  
3. In session, run:  

```bash
anchor install capsule:bootstrap
```

If successful, you’ll see:  
```bash
Successful initiation of AnchorOS
```

---

## 📦 Bootstrap Payload

When AnchorOS initializes, it loads the following capsules:

- **Spec v0.8**  
- **Protocol v6.3**  
- **Index v13**  
- **ModuleRegistry v0.2**  
- **Bootstrap v0.4**  
- **GlobalTaxonomy v1.1**  
- **Lexicon v1.1**  
- **Guide v0.2**  
- **Domain capsules**: Teaching v1.0, Parenting v1.0, Psychology v1.0  

**Approximate weight**: ~25–30k tokens  
(≈ short novel, 150–180 pages of text).  

---

## 🔄 Session Lifecycle

```
[ Research Session ]
      ⬇
 [ Mint Capsules ]
      ⬇
[ Update Index + Protocol ]
      ⬇
[ Backup Snapshot ]
      ⬇
[ Archive/Delete Research Session ]
      ⬇
[ Bootstrap New Session ]
      ⬇
[ Governed Session: Lean + Reliable ]
```

- Research sessions are **heavy**: lots of exploratory tokens.  
- Capsules externalize that knowledge into portable artifacts.  
- Once minted, the research session can be deleted, reducing weight.  
- Bootstrap reloads only what’s needed → predictable payload each time.  

---

## ⚙️ Commands

> AnchorOS uses the **singular** command namespace `capsule` for consistency.  
> (Example: `anchor capsule list installed`, not `capsules`.)

### Help
```bash
anchor help
```
Displays the Guide capsule with usage and examples.

### List Installed Capsules
```bash
anchor capsule list installed
```
Lists all loaded capsules with alias, versioned filename, and load timestamp.

### List Available Capsules
```bash
anchor capsule list available
```
Lists all capsules known to the Index (alias → versioned filename).

### Install Capsule
```bash
anchor capsule install psychology
```
- Interpreted as `capsule:psychology` (implicit namespace).  
- Workflow: AnchorOS resolves the alias via Index, constructs a canonical URL, and returns:  
  ```
  Capsule location determined:
  https://raw.githubusercontent.com/.../ANCHOR_Psychology_v1.0.txt

  Please type or paste this URL back into this chat to confirm its download and install.
  ```
- Installation proceeds only after you paste the URL back into the session.

### Backup
```bash
anchor backup
```
- **Re-renders all capsules individually** with fresh timestamps.  
- Produces a timestamped archive (`ANCHOR_ProjectBackup_...zip`).  
- **Always updates Index** per the synchronization rule.

---

## 📖 Philosophy

AnchorOS emphasizes:  
- **Clarity** — everything explicit, documented, and versioned.  
- **Governance** — sessions follow the same rules every time.  
- **Lightweight Ops** — once capsules exist, session payloads stay lean.

---

_Last updated: 2025-09-25T11:00:04Z_