# Configuración Básica de Routers Cisco

### Accesar en modo de Consola del Router y habilitar el modo EXEC Privilegiado.

```cisco
router> enable
```

### Accesar el modo de configuración global.

```cisco
router# config terminal
```

### Asignar un nombre al Router.

```cisco
router(config)# hostname R1
```

### Configurar un nombre de dominio para el Router (ccna-lab.net).

```cisco
R1(config)# ip domain name ccna-lab.net
```

### Deshabilitar la búsqueda DNS para prevenir que el Router intenta traducir entradas de comando incorrectos como si fuera nombres de dispositivos.

```cisco
R1(config)# no ip domain lookup
```

### Activar el cifrado de las contraseñas en texto plano

```cisco
R1(config)# service password-encryption
```

### Configurar el Router para que requiera una contraseña mínima de 12 carácter.

```cisco
R1(config)# security passwords min-length 12
```

### Establecer el nombre de usuario como AdminR y una contraseña cifrado de 4dM!nr-#2025.

```cisco
R1(config)# username AdminR secret 4dM!nr-#2025
```

### Generar las claves criptográficas con un modulo de 1024 bits.

```cisco
R1(config)# crypto key generate rsa general-keys modulus 1024
```

### Asignar contraseña al modo de EXEC Privilegiado.

```cisco
R1(config)# enable secret c!$c0*P7iv-M
```

### Asignar contraseña a la consola y configure la sesión para que se desconecta después de 5 minutos de inactividad y habilitar el login.

```cisco
R1(config)# line console 0
R1(config-line)# password c!$c0*C0n2-L
R1(config-line)# exec-timeout 5 0
R1(config-line)# login
```

### Configurar la linea vty para aceptar unicamente sesiones SSH agregare le contraseña y configurar la sesión para que se desconecta después de 5 minutos de inactividad, habilitar también el login utilizando la base de datos local.

```cisco
R1(config)# line vty 0 4
R1(config-line)# password c!$c0*V7ys-L
R1(config-line)# exec-timeout 5 0
R1(config-line)# transport input ssh
R1(config-line)# login local
```

### Crear un mensaje del día (MOTD Banner) para advertir a cualquiera que accede al dispositivo de su acceso.

```cisco
R1(config)# banner motd $
R1(config)# Authorized Users Only! $
```

### Agregar un descripción a cada interfaz en el Router.

```cisco
R1(config)# interface g0/0
R1(config-if)# description Connection to LAN-1
```

### Configuración de las interfaces con IPv4 y IPv6 activadas, descripción y en estado activado.

```cisco
```

### Configurar el Router para no permitir el login al vty por 2 minutos si 3 intentos fallidos ocurrió en los últimos 60 segundos.

```cisco
R1(config)# login block-for 120 attempts 3 within 60
R1(config)# exit
```

### Configuración del reloj.

```cisco
R1# clock set hh:mm:ss day month year
```

### Guardar las configuraciones.

```cisco
R1# copy running-config startup-config
o
R1# wr
```
