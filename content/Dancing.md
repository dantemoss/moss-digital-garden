---
title: "Machine: Dancing"
date: 2025-12-16
tags: [htb, windows, smb, easy, starting-point]
---
> [!info] Intel
>
> * **IP:** 10.129.x.x (Completar al iniciar)
> * **OS:** Windows
> * **Difficulty:** Very Easy
> * **Goal:** Aprender a interactuar con el protocolo SMB (Server Message Block).

## 1. Reconnaissance 🕵️‍♂️

Primer contacto con el objetivo. Buscamos puertos abiertos.

```bash
nmap -p- --min-rate 5000 10.129.x.x
```
