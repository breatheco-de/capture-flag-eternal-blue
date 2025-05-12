# ETERNAL BLUE - Acceso Remoto en Windows 7

En este laboratorio deberás analizar un sistema Windows 7 vulnerable al famoso exploit **EternalBlue**, utilizado históricamente en ataques reales. Tu objetivo será explotar la vulnerabilidad, acceder remotamente al sistema y obtener una flag desde el escritorio del usuario.

En este laboratorio aprenderás:

- Detección de vulnerabilidades en servicios SMB
- Escaneo de puertos y explotación con `nmap` y `Metasploit`
- Uso del módulo `ms17_010_eternalblue`
- Obtención de acceso remoto a sistemas Windows
- Lectura de flags como usuario comprometido

<how-to-start>

## 🌱 Cómo iniciar este laboratorio

Sigue las siguientes instrucciones para comenzar:

1. **Descarga la máquina virtual** desde este [enlace]().
2. **Importa la máquina** en tu gestor de virtualización preferido (VirtualBox, VMware, etc.).
3. La máquina simula un entorno de usuario común (fondo personalizado, nombre de usuario cambiado).
4. Una vez iniciada la máquina, ¡ya puedes comenzar con el laboratorio!

</how-to-start>

## 📄 Instrucciones

Estás frente a un sistema Windows vulnerable. Tu tarea es explotar la vulnerabilidad EternalBlue (MS17-010) para obtener una shell remota y encontrar la flag.

1. **Descubre la dirección IP de la máquina Windows.**  
   - Usa herramientas como `nmap`, `netdiscover` o `arp-scan` para identificar su IP en la red.

2. **Escanea los puertos y busca servicios vulnerables.** 

3. **Lanza el exploit con Metasploit.**  
   - Usa el módulo:
     ```
     use exploit/windows/smb/ms17_010_eternalblue
     ```
   - Configura `RHOSTS`, `LHOST` y selecciona un payload como `windows/x64/meterpreter/reverse_tcp`.

4. **Accede al sistema.**  
   - Una vez obtenida la shell, navega al escritorio del usuario.

5. **Lee la flag.**: La flag debe estar en un archivo `.txt`.

**Recuerda:** este tipo de vulnerabilidades cambió la historia de la ciberseguridad. ¡Aprovéchala con responsabilidad!

¡Feliz hackeo!
