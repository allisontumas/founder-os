# Agent roles

One markdown manifest per agent. Agnostic on purpose: the same manifest compiles to a Claude skill, a Codex AGENTS.md section, or a ChatGPT Project instruction — the role is defined once. Security model: roles load **packs**, never raw foundation files; exposed surfaces write to a queue (00-inbox/), never directly to context. Start with the two roles brand-voice unlocks; add PM/engineer-type roles per project when a project actually needs one.
