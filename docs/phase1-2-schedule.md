---
title: "Phase 1–2 Schedule"
parent: Roadmap
nav_order: 2
permalink: /roadmap/phase-1-2/
description: "The concrete week-by-week schedule for Phases 1 and 2."
---

# Phase 1–2 Week-by-Week Schedule

> Companion to the [Full Roadmap]({{ '/roadmap/full/' | relative_url }}). A concrete
> 28-week schedule covering **Phase 1 (Foundations)** and **Phase 2 (Web mastery)**, tuned for
> the depth-track targets — **red team / in-house product security / vulnerability research** —
> and for a starting point of *solid general programming, C / memory / assembly touched but not
> mastered.*

## How to read this

- **Assumed load:** ~12–15 focused hours/week. Compress the calendar if you can do more; the
  *ordering* matters more than the exact week numbers.
- **The spine is systems programming.** Because all three target roles sit on top of C, memory,
  and assembly, the first block is a deliberate ramp rather than a rush to web tooling. Don't
  skip it because the web material looks more exciting — the depth tracks live and die here.
- **Two parallel tracks each week:** a **primary** focus block and a **background** habit that
  runs continuously (PortSwigger Academy, reading, notes). The background habit is how you avoid
  finishing Phase 1 with zero web exposure.
- **Every phase ends with a gate** — an artifact or demonstrable skill, not just "time elapsed."

---

## Phase 1 — Foundations (Weeks 1–12)

**Goal:** stop being slowed down by fundamentals; make C/assembly a comfort zone, not a wall.

### Block A — Systems & C ramp (Weeks 1–5) — *the critical path*

| Week | Primary focus | Background habit | Milestone |
|---|---|---|---|
| **1** | C refresher with a debugger in hand: pointers, arrays-vs-pointers, structs, the stack frame. Write small programs, then step through them in GDB watching memory. | Set up notes/writeup system (your site repo works). | Single-step a recursive function in GDB and narrate the stack. |
| **2** | Memory model deep dive: stack vs heap, `malloc`/`free` internals at a high level, buffer layout, endianness. Deliberately write and then *observe* an out-of-bounds write. | Start **OverTheWire Bandit** (background, ~30 min/day). | Reproduce a stack buffer overflow in a toy program and see it in GDB. |
| **3** | x86-64 assembly reading: registers, calling convention (System V ABI), `call`/`ret`, prologue/epilogue. Compile C at `-O0` and read the disassembly until it's boring. | Bandit continues. | Hand-translate a small C function to/from its disassembly. |
| **4** | More assembly + intro tooling: `objdump`, `readelf`, ELF layout (sections, symbols, PLT/GOT at a glance). Begin the intro **pwn.college** modules (assembly, program interaction). | Finish **Bandit**; start light **PortSwigger Academy** (SQLi intro labs). | Complete pwn.college's early assembly module set. |
| **5** | Consolidate: pwn.college intro track, comfortable with GDB+pwndbg. Write up "what I learned about the stack" as your first public post. | PortSwigger Academy continues. | **First published technical writeup.** |

**Block A gate:** you can read `-O0` x86-64 disassembly without panic, drive GDB fluently, and
explain a stack overflow at the memory level. This is the foundation the entire depth track stands
on — do not proceed weak here.

### Block B — Networking & OS (Weeks 6–9)

| Week | Primary focus | Background habit | Milestone |
|---|---|---|---|
| **6** | TCP/IP for real: the 3-way handshake, teardown, flags, MTU/fragmentation. Capture your own traffic in Wireshark and dissect it. | pwn.college continues (a module/week, background now). | Explain a captured TCP session packet by packet. |
| **7** | TLS + DNS: the handshake (1.2 and 1.3), certificates and the trust chain, DNS resolution paths and tunneling concept. HTTP/1.1 and HTTP/2 semantics in depth. | PortSwigger Academy (auth + access-control labs). | Read a TLS handshake from a pcap and identify each message. |
| **8** | OS internals as applied theory: processes/threads, virtual memory & paging, syscalls, the user/kernel boundary, privilege rings, signals. Tie each back to why it matters offensively. | PortSwigger Academy continues. | Trace a syscall with `strace` and explain the boundary crossing. |
| **9** | Linux mastery layer: permissions & capabilities, systemd, namespaces + cgroups (container primitives), `/proc`. Leverage your Arch background here — go deeper than "it works." | PortSwigger Academy continues. | Build a minimal container from namespaces by hand. |

**Block B gate:** open an arbitrary pcap and explain what's happening; articulate the full
user→kernel path of a syscall; comfortable enough in Linux that the shell is invisible.

### Block C — Lab build & first blood (Weeks 10–12)

| Week | Primary focus | Background habit | Milestone |
|---|---|---|---|
| **10** | Stand up the [home lab](/roadmap/full/#7-home-lab): hypervisor, attack box (Arch/Kali), a Linux target, snapshotting discipline. Isolate the network. | PortSwigger Academy continues. | Lab reachable, snapshotted, isolated. |
| **11** | Build the **Windows Server + AD** starter domain (one DC, one workstation). Automate the build so teardown/rebuild is cheap — you'll break it repeatedly later. | PortSwigger Academy continues. | Domain up; you can rebuild it from a script. |
| **12** | Consolidation week: finish outstanding pwn.college intro modules, tidy notes, publish a "Phase 1 retro" post. Light HTB/THM starter box to feel end-to-end flow. | — | **Phase 1 retro published; foundations gate cleared.** |

**Phase 1 exit criteria:** read a TLS handshake from capture; drop into a shell without thinking;
read simple disassembly; lab (incl. AD + isolation) standing; one or two public writeups done.

---

## Phase 2 — Web Mastery (Weeks 13–28)

**Goal:** become genuinely dangerous on web/API — the highest-volume employable skill and, via
source-code review, the on-ramp to product security. You've been trickling through PortSwigger
Academy since Week 4; now it becomes the primary focus and you finish *all* of it.

### Block D — Academy core (Weeks 13–18)

| Week | Focus | Milestone |
|---|---|---|
| **13** | SQL injection (all variants) + authentication vulns — complete these Academy tracks properly, not just for the flag. | SQLi + auth tracks done. |
| **14** | Access control / IDOR / broken object-level authorization — the *real* skill. Plus business-logic flaws. | Authz + logic tracks done. |
| **15** | SSRF (deeply — it's a top-tier finding) + XXE + file-path/upload issues. | SSRF + XXE tracks done. |
| **16** | XSS end to end (reflected/stored/DOM), CSRF, CORS, `postMessage`, clickjacking. | Client-side tracks done. |
| **17** | Injection breadth: OS command injection, SSTI, and an intro to insecure deserialization. | Injection + SSTI tracks done. |
| **18** | Identity: OAuth 2.0, OIDC, SAML flow abuse; JWT attacks (`alg` confusion, weak keys). | Identity tracks done. |

### Block E — Modern surface + tooling (Weeks 19–23)

| Week | Focus | Milestone |
|---|---|---|
| **19** | Advanced deserialization (Java/Python/PHP/.NET gadget concepts) + prototype pollution. | Deserialization + protopoll tracks done. |
| **20** | HTTP request smuggling + web cache poisoning/deception — the Academy's expert-tier material. | Smuggling + cache tracks done. |
| **21** | GraphQL, API-specific testing, and any remaining Academy topics. **Finish 100% of PortSwigger Academy, including all expert labs.** | **Academy complete.** |
| **22** | Write a **Burp Suite extension** — your first offensive web tool. Pick a real annoyance and automate it. | Extension working. |
| **23** | Polish + publish the extension (repo + writeup). This is a portfolio artifact, not homework. | **Burp extension published.** |

### Block F — Real targets + BSCP (Weeks 24–28)

| Week | Focus | Milestone |
|---|---|---|
| **24** | Start **bug bounty on a VDP** (no-bounty disclosure program). Goal is reps and *report writing*, not money. Pick one program, map it thoroughly. | Target mapped; recon notes written. |
| **25** | Hunt + write your first real vulnerability report against a live target. Focus on report quality — impact, repro, remediation. | **First real report submitted.** |
| **26** | Continue hunting; deliberately practice authorization-logic and SSRF findings (your highest-value classes). | Second report or strong near-miss documented. |
| **27** | **BSCP** exam prep + sit the exam. The Academy *was* the prep; this week is timed practice and the attempt. | **BSCP passed.** |
| **28** | Phase 2 retro: publish a "web mastery" writeup, update the roadmap checklist, and choose your provisional Phase 3–4 emphasis (AD-heavy for red team vs. code-review-heavy for product sec/VR). | **Phase 2 gate cleared; direction chosen.** |

**Phase 2 exit criteria:** walk into an unfamiliar web app and methodically attack its
authorization logic; PortSwigger Academy 100% complete; a published Burp extension; at least one
real vulnerability report on a live target; **BSCP** passed.

---

## What comes next

Phase 3 (Active Directory + OSCP) and Phase 4 (the CS differentiator — fuzzing, reversing,
code review, first CVE) are described at the phase level in the
[main roadmap](/roadmap/full/#6-the-pathway-phase-by-phase). Build their
week-by-week schedules once Phase 2's Week 28 retro tells you which branch (red team / product sec
/ VR) is pulling hardest — the emphasis differs enough that it's worth deciding on real evidence
rather than guessing now.

**A note on pace:** the week numbers are a scaffold, not a contract. If a topic hasn't clicked,
stay on it — depth here is the entire point of the depth track. If you're flying, compress. The
gates are what matter; the calendar is just a default.

---

*Living document — revise as reality diverges from the plan.*
