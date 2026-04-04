# Laboratorio de Ciberseguridad

Laboratorio personal de ciberseguridad construido desde cero con el objetivo 
de practicar el ciclo completo de una prueba de penetración en un entorno 
controlado y aislado.

---

##  Objetivo

Simular un entorno real de ataque y defensa usando máquinas virtuales, 
cubriendo desde el reconocimiento inicial hasta la remediación de 
vulnerabilidades encontradas.

---

##  Entorno del laboratorio

| Componente | Detalle |
|---|---|
| **Hipervisor** | QEMU/KVM (Virt-Manager) |
| **Sistema atacante** | Kali Linux (amd64) |
| **Sistema objetivo** | Metasploitable2 |
| **Red** | NAT aislada (sin acceso a Internet) |

---

##  Herramientas utilizadas

- **Nmap** — Reconocimiento y análisis de vulnerabilidades
- **Metasploit Framework** — Explotación de vulnerabilidades
- **Wireshark** — Análisis de tráfico de red (referencia)
- **Netstat / Lsof** — Verificación de puertos y servicios

---

## 📋 Fases del laboratorio

| Fase | Archivo | Descripción |
|---|---|---|
| 🏗️ Construcción del entorno | [00_Creacion_Lab.md](00%20Creación%20de%20mi%20Lab.md) | Despliegue de VMs y verificación de conectividad |
| 🔍 Reconocimiento | [01_Reconocimiento.md](01_Reconocimiento.md) | Escaneo de puertos, versiones y vulnerabilidades con Nmap |
| 💥 Explotación | [02_Explotacion.md](02_Explotacion.md) | Explotación de backdoor vsftpd 2.3.4 con Metasploit |
| 🔒 Remediación | [03_Remediacion.md](03_Remediacion.md) | Corrección de la vulnerabilidad y verificación |

---

## 📊 Resumen de resultados

| Fase | Herramienta | Resultado |
|---|---|---|
| Reconocimiento | Nmap | 23 puertos abiertos identificados |
| Análisis | Nmap --script vuln | Backdoor vsftpd 2.3.4 confirmada |
| Explotación | Metasploit | Acceso root obtenido (uid=0) |
| Remediación | SFTP | Puerto 21 cerrado y reemplazado |

---

##  Aprendizajes clave

- La importancia de mantener servicios actualizados en producción
- Cómo el reconocimiento previo define el vector de ataque
- Que remediar una vulnerabilidad requiere ofrecer una alternativa segura
- La diferencia práctica entre FTP (inseguro) y SFTP (cifrado)
