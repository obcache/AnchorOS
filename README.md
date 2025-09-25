# AnchorOS

**AnchorOS** is a modular governance layer for ChatGPT sessions.  
It transforms raw session sprawl into **structured, portable, and governable capsules**, enabling consistent and repeatable workflows.  

---

## ✨ Core Idea

- **Capsules**: Portable documents that encapsulate rules, heuristics, or workflows.  
- **Modules**: General plug-in units. Capsules are one type of module (others may follow: `workflow:`, `adapter:`, `theme:`, etc.).  
- **Index**: Tracks all current capsule versions and filenames.  
- **Bootstrap**: Ensures required capsules load and governs startup/rollback.  
- **Protocol**: Defines the rules for capsule minting, backups, upgrades, and installs.  

---

## 🚀 Getting Started

1. Clone this repository.  
2. Download the bootstrap and core capsules from the latest release or the `capsules/` directory.  
3. In session, issue:  

```bash
anchor install capsule:bootstrap
```

If successful, you’ll see:  
```bash
Bootstrap initiation successful: AnchorOS is now active.
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

### Installed Capsules
```bash
anchor capsules list
```
→ Lists all installed capsules with version and load timestamp.  

### Available Capsules
```bash
anchor capsules list available
```
→ Lists all capsules available per the Index.  

### Install Capsule
```bash
anchor install capsule:psychology
```
- If no namespace is provided, `capsule:` is assumed.  
- AnchorOS provides the capsule URL and requires you to paste it back to confirm download.  

### Backup
```bash
anchor backup
```
- Re-renders all capsules individually.  
- Produces a timestamped archive (`ANCHOR_ProjectBackup_...zip`).  
- Always updates the Index.  

---

## 📖 Philosophy

AnchorOS emphasizes:  
- **Clarity**: everything is explicit, documented, and versioned.  
- **Governance**: sessions follow the same rules every time.  
- **Lightweight ops**: once capsules exist, session payloads remain lean.  

---

⚓ AnchorOS = Govern your ChatGPT session data.  
