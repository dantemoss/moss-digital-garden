---
title: "Writeup: DANCING (Starting Point)"
date: 2025-12-16
tags: [htb, starting-point, windows, smb, very-easy]
---
> [!quote] La Verdad de la Milanesa
> *"A veces no necesitás ser un genio de la encriptación para entrar. A veces, el administrador simplemente se olvidó de ponerle llave a la puerta de atrás."*

Si REDEEMER fue prender la luz, **DANCING** es aprender a abrir puertas. Acá nos olvidamos de la terminal de Linux por un rato y jugamos de local: vamos a usar el propio Windows para atacar a otro Windows. El objetivo es entender **SMB** y por qué dejar el usuario "Invitado" activo es un tiro en el pie.

## ⚙️ El Objetivo: SMB (Server Message Block)

Acá es donde vive la acción. No estamos buscando vulnerabilidades complejas de código, estamos buscando **malas configuraciones**.

### 🟢 ¿Qué es SMB?
Es el protocolo que usan las computadoras (especialmente Windows) para compartir archivos e impresoras en una red.
* **Puerto:** `445` (TCP).
* **Servicio:** `microsoft-ds`.
* **El Error:** Permitir que cualquiera entre sin contraseña (Anonymous/Guest Access).

> [!danger] El Concepto de "Guest"
> En muchas redes corporativas, los admins habilitan la cuenta `Guest` para facilitar las cosas (compartir carpetas rápido).
> **¿Qué significa esto para nosotros?** Que podemos entrar, listar carpetas y robar archivos sin saber ninguna contraseña. Es literalmente entrar saludando.

## 🏆 Cuestionario Táctico (Tasks)

Antes de romper la máquina, HTB nos pide entender la teoría. Acá tenés el machete con la explicación técnica para que no seas un script kiddie.

| Task | Pregunta Clave | Respuesta | Por qué (La Lógica) |
| :--- | :--- | :---: | :--- |
| **1** | ¿Qué significa SMB? | `Server Message Block` | Es el estándar de la industria para compartir recursos. |
| **2** | ¿En qué puerto opera? | `445` | El SMB moderno corre directo sobre TCP 445 (el viejo usaba el 139). |
| **3** | ¿Nombre del servicio en Nmap? | `microsoft-ds` | "Microsoft Directory Services". Así lo etiqueta Nmap. |
| **4** | ¿Flag para listar shares? | `-L` | En Linux (`smbclient`), `-L` es para *Listar* antes de conectar. |
| **5** | ¿Cuántos shares hay? | `4` | Usualmente `ADMIN$`, `C$`, `IPC$` y nuestro objetivo `WorkShares`. |
| **6** | ¿A cuál entramos sin pass? | `WorkShares` | Es la carpeta mal configurada que permite `Guest`. |
| **7** | ¿Comando para bajar archivos? | `get` | La consola SMB funciona igual que un FTP. `get` descarga. |

## 🧮 La Estrategia (Living off the Land)

En vez de instalar herramientas raras, usamos lo que ya tenemos.

$$
\text{Target} = \text{\\IP\_VICTIMA} + \text{Credenciales Nulas}
$$

> [!tip] Traducción al Criollo
> No hace falta Kali Linux siempre. Si tenés Windows, usá el Explorador de Archivos. Es tráfico nativo y levanta menos sospechas (a veces).

### Procedimiento de Ataque

1. **Conexión:** Abrimos el explorador de archivos y escribimos la IP (`\\10.129.x.x`).
2. **Autenticación:** Nos pide usuario. Ponemos `guest` y dejamos la contraseña vacía.
3. **Enumeración:** Vemos las carpetas. Entramos a `WorkShares`.
4. **Extracción:** Navegamos a `James.P` (el usuario descuidado) y encontramos `flag.txt`.

## 🚩 Root Flag

La prueba del delito. Copiar, pegar y a cobrar esos puntos.

```text
5f61c10dffbc77a704d76016a22f1664