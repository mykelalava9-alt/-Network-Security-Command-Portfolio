# -Network-Security-Command-Portfolio
# 🌐 Network & Security Command Portfolio

---

# 📚 Command Dictionary

## 🔎 1. Network Scanning & Diagnostics

| **Comando** | **Viene de** | **💡 Idea para recordarlo** |
|---|---|---|
| `nmap` | **Network Mapper** | 🗺️ Mapear puertos y servicios |
| `ss` | **Socket Statistics** | 🔌 Consultar conexiones y sockets |
| `netstat` | **Network Statistics** | 📊 Consultar estadísticas de red |

---

## 🔌 2. Network Communication

| **Comando** | **Viene de** | **💡 Idea para recordarlo** |
|---|---|---|
| `nc` | **Netcat** | 🔗 Conectar e intercambiar datos |
| `ncat` | **Ncat (Network utility)** | 🔗 Comunicar sistemas por la red |
| `telnet` | **TELecommunication NETwork** | 💬 Conectarse a servicios de red |
| `socat` | **SOcket CAT** | 🔀 Conectar dos extremos de comunicación |
| `ssh` | **Secure Shell** | 🔐 Acceder remotamente de forma segura |

---

## 🔐 3. Cryptography & TLS

| **Comando** | **Viene de** | **💡 Idea para recordarlo** |
|---|---|---|
| `openssl` | **OpenSSL** | 🔑 Herramientas de criptografía y seguridad |
| `s_client` | **SSL/TLS client** | 🤝 Probar conexiones TLS con servidores |

---

## 🛡️ 4. Protocols & Security Concepts

| **Concepto** | **Viene de** | **💡 Idea para recordarlo** |
|---|---|---|
| `TCP` | **Transmission Control Protocol** | 📦 Comunicación fiable y orientada a conexión |
| `UDP` | **User Datagram Protocol** | ⚡ Enviar datagramas sin conexión previa |
| `IP` | **Internet Protocol** | 🧭 Direccionar y transportar paquetes |
| `TLS` | **Transport Layer Security** | 🔒 Proteger las comunicaciones |
| `SSL` | **Secure Sockets Layer** | 🕰️ Protocolo antiguo, reemplazado por TLS |
| `SSH` | **Secure Shell** | 🖥️ Administrar sistemas remotamente |

---

## 🧠 Quick Memory Guide

- `nmap` → Descubrir puertos y servicios.
- `ss` / `netstat` → Observar conexiones y sockets locales.
- `nc` / `ncat` → Enviar y recibir datos.
- `telnet` → Interactuar con servicios TCP.
- `socat` → Unir o retransmitir datos entre extremos.
- `openssl` → Trabajar con criptografía y certificados.
- `s_client` → Inspeccionar conexiones SSL/TLS.
- `ssh` → Acceder de forma segura a otro sistema.

---









# 🌐 Network & Security Command Portfolio

---

# ⚙️ Command Syntax Dictionary

## 🔎 1. Network Scanning & Diagnostics

### `nmap` — Network Mapper

**Estructura:**
```bash
nmap [opciones] [objetivo]
```

**Ejemplos:**
```bash
nmap 127.0.0.1
nmap -p 80,443 127.0.0.1
nmap -sV 127.0.0.1
```

- `-p`: especifica los puertos que quieres examinar.
- `-sV`: intenta identificar los servicios y sus versiones.
- `127.0.0.1`: dirección IP de loopback, que representa tu propio equipo.

### `ss` — Socket Statistics

**Estructura:**
```bash
ss [opciones]
```

**Ejemplos:**
```bash
ss -tuln
ss -tun
```

- `-t`: conexiones TCP.
- `-u`: conexiones UDP.
- `-l`: sockets en escucha.
- `-n`: muestra direcciones y puertos numéricos.

### `netstat` — Network Statistics

**Estructura:**
```bash
netstat [opciones]
```

**Ejemplos:**
```bash
netstat -tuln
netstat -an
```

- `-t`: conexiones TCP.
- `-u`: conexiones UDP.
- `-l`: sockets en escucha.
- `-n`: evita resolver nombres de servicios y direcciones.
- `-a`: muestra conexiones y sockets en escucha.

---

## 🔌 2. Network Communication

### `nc` — Netcat

**Estructura:**
```bash
nc [opciones] [host] [puerto]
```

**Ejemplos:**
```bash
nc 127.0.0.1 8080
nc -lv 8080
```

- `host`: equipo al que deseas conectarte.
- `puerto`: puerto del servicio.
- `-l`: modo de escucha.
- `-v`: muestra información adicional de la conexión.

*Nota:* las opciones disponibles pueden variar según la implementación de Netcat.

### `ncat`

**Estructura:**
```bash
ncat [opciones] [host] [puerto]
```

**Ejemplos:**
```bash
ncat 127.0.0.1 8080
ncat -lv 8080
```

- `-l`: escucha conexiones entrantes.
- `-v`: muestra información adicional.
- `host` y `puerto`: identifican el destino de la conexión.

### `telnet`

**Estructura:**
```bash
telnet [host] [puerto]
```

**Ejemplo:**
```bash
telnet 127.0.0.1 8080
```

- `host`: equipo de destino.
- `puerto`: puerto al que deseas conectarte.

*Nota:* Telnet transmite los datos sin cifrado por defecto. Úsalo en laboratorios o para probar servicios compatibles, no para enviar credenciales sensibles.

### `socat` — Socket CAT

**Estructura:**
```bash
socat [opciones] <direccion1> <direccion2>
```

**Ejemplos:**
```bash
socat - TCP:127.0.0.1:8080
socat -V
```

- `-`: representa la entrada y salida estándar.
- `TCP:127.0.0.1:8080`: especifica un extremo TCP.
- `-V`: muestra la versión del programa.

*Nota:* Socat necesita dos direcciones de comunicación, aunque la forma exacta depende del tipo de conexión.

### `ssh` — Secure Shell

**Estructura:**
```bash
ssh [opciones] usuario@host
```

**Ejemplos:**
```bash
ssh usuario@192.168.1.10
ssh -p 2222 usuario@192.168.1.10
```

- `usuario`: cuenta con la que te autenticas.
- `host`: nombre o dirección del servidor.
- `-p`: puerto SSH del servidor.

---

## 🔐 3. Cryptography & TLS

### `openssl`

**Estructura general:**
```bash
openssl <subcomando> [opciones] [argumentos]
```

**Ejemplos:**
```bash
openssl version
openssl help
openssl s_client -help
```

- `version`: muestra la versión instalada.
- `help`: muestra información de ayuda.
- `s_client`: inicia una sesión de cliente SSL/TLS.

OpenSSL es una colección de herramientas; su sintaxis depende del subcomando utilizado.

### `openssl s_client`

**Estructura:**
```bash
openssl s_client -connect <host>:<puerto> [opciones]
```

**Ejemplo de laboratorio:**
```bash
openssl s_client -connect example.com:443
```

- `s_client`: activa el cliente de diagnóstico SSL/TLS.
- `-connect`: especifica el servidor y el puerto.
- `<host>`: nombre DNS o dirección IP del servidor.
- `<puerto>`: puerto del servicio TLS.
- `-servername <nombre>`: envía el nombre SNI cuando es necesario para seleccionar el certificado correcto.

**Conceptos importantes:**
- Handshake: negociación inicial de la conexión TLS.
- Certificado: documento digital asociado a una identidad.
- Cipher suite: conjunto de algoritmos negociados para proteger la comunicación.
- `CONNECTED`, `DONE`, `RENEGOTIATING` y `KEYUPDATE`: mensajes que pueden aparecer durante la sesión; su significado depende del contexto.

---

## 🧠 4. Estructura universal de un comando

```bash
comando [opciones] [argumentos]
```

| Parte | Función | Ejemplo |
|---|---|---|
| Comando | Programa que ejecutas | `nmap` |
| Opción | Modifica su comportamiento | `-p` |
| Argumento | Valor que recibe una opción | `80,443` |
| Objetivo | Equipo o recurso sobre el que actúa | `127.0.0.1` |

Los elementos entre corchetes `[]` son opcionales en estas representaciones. Los símbolos `< >` indican un valor que debes sustituir, no escribir literalmente.




**⚠️ Importante:** SSL está obsoleto. TLS es el protocolo moderno utilizado para proteger las comunicaciones.
