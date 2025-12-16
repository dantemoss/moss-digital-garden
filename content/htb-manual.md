---
title: "Manual de Supervivencia: El Sistema de Rangos de HTB"
date: 2025-12-15
tags: [htb, guide, strategy, rank]
---
> [!quote] La Verdad de la Milanesa
> *"En Hack The Box no subís por ser un genio. Subís por ser constante. El sistema está diseñado para que te caigas si te quedás quieto."*

Si estás leyendo esto es porque querés entender cómo carajo funciona el ranking y por qué, aunque rompés máquinas, a veces sentís que no avanzás. Acá te explico la matemática detrás de la locura y cómo vamos a llegar al **Top 1000**.

## ⚙️ La Trampa: Active vs. Retired

Acá es donde muere el 90% de los usuarios. Tenés que entender la diferencia entre estas dos categorías o vas a estar pedaleando en el aire.

### 🟢 Active Machines (La Mina de Oro)

Son las máquinas que salieron hace poco y **NO tienen solución publicada**.

* **Puntos:** TE DAN PUNTOS PARA EL RANKING.
* **Porcentaje:** Te suben el % para cambiar de Rango (ej: de *Hacker* a *Pro Hacker*).
* **Writeups:** Prohibido publicar soluciones (te banean si lo hacés).

### 🔴 Retired Machines (El Cementerio)

Son las máquinas viejas. Ya hay soluciones en YouTube y Google.

* **Puntos:** **CERO.** No suman nada para el ranking global (a menos que seas VIP, y aun así es casi nada).
* **Utilidad:** Sirven para aprender sin presión. Son para entrenar la memoria muscular.

> [!danger] El "Drenaje" Semanal (The Grind)
> Hack The Box es una cinta de correr.
> Cada sábado, una máquina *Active* se jubila y pasa a *Retired*.
> Si vos habías hackeado esa máquina, **PERDÉS ESOS PUNTOS**.
>
> **¿Qué significa esto?** Que si no hackeás la máquina nueva de la semana, tu puntaje **BAJA** automáticamente. Para mantenerte en el Top, tenés que hackear al mismo ritmo que ellos publican.

## 🏆 La Escalera de Rangos (Titles)

Tu "título" (ese badge verde que dice *Hacker*) depende de tu **Ownership %** de lo que está ACTIVO hoy.

| Rango                   | Requisito (% de Activos) | Estado Mental                                            |
| :---------------------- | :----------------------: | :------------------------------------------------------- |
| **Noob**          |            0%            | *"Instalé Kali y me siento Elliot Alderson"*          |
| **Script Kiddie** |           > 5%           | *"Sé tirar nmap pero no entiendo el output"*          |
| **Hacker**        |          > 20%          | **(Estamos Acá)** Empezás a entender la lógica. |
| **Pro Hacker**    |          > 45%          | Ya no copiás, adaptás.                                 |
| **Elite Hacker**  |          > 70%          | Vivís en la terminal. Tu familia te extraña.           |
| **Guru**          |          > 90%          | Soñás en hexadecimal.                                  |
| **Omniscient**    |           100%           | Dios.                                                    |

## 🧮 La Fórmula Matemática (Para Nerds)

No te asustes, pero así calcula HTB tu puntaje global (ese con el que queremos entrar al Top 1000):

$$
\text{Points} = (\text{User} + \text{Root} + \text{Challenge} + \text{Blood}) \times \text{Ownership \%}
$$

> [!tip] Traducción al Criollo
> Tu puntaje total se multiplica por tu porcentaje de completado actual.
> Si tenés 1000 puntos pero dejaste de hackear un mes y tu % baja a 0... **TUS PUNTOS VALEN CERO.**

### ¿Qué da más puntos?

1. **Challenges:** (Crypto, Reversing, Pwn). Son difíciles pero suman banda y tardan más en rotar.
2. **Blood (Sangre):** Ser el primero en hackear una máquina apenas sale. (Esto es para enfermos, todavía no estamos ahí).
3. **Máquinas Hard/Insane:** Dan más puntos que las Easy, obvio.

## 🗺️ Estrategia "Dante Top 1000"

Para entrar en ese 1% y dejar de ser un turista, el plan es este:

1. **Ritmo Semanal:** Los sábados sale máquina nueva. El fin de semana es sagrado para romperla.
2. **No descuidar Challenges:** Cuando me trabe con una máquina, voy a los *Challenges* de Forensics o Stego para sumar puntitos "fáciles" que no caducan tan rápido.
3. **Documentar TODO:** Si no está escrito, no aprendí nada.

> [!info] Próximo Paso
> Revisar el calendario de *Release* y preparar el café. La disciplina le gana al talento.

---

*Referencia: Datos cruzados con la documentación oficial de HTB Help Center (2025) y la experiencia de dolor propia.*
