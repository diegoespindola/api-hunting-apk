# Cazando APIs en aplicaciones Android
Taller día Sabado 19 de noviembre 2022 a las 14:00 hrs via streaming por [LockDown Fest](https://www.linkedin.com/company/lockdown0x0/)
Registrate en [Eventbrite](https://www.eventbrite.cl/e/talleres-lockdown-fest-2022-techsec-tickets-436646149387)
## Prerequisitos

### Celular android
  Cualquier celular android con la apliacion que deseas analizar instalada

### Cable usb
  cable usb para conectar tu celular android al computador
  
### APPs (deben esar instaladas previamente en el computador)

#### Para obtener la apk
  1. [Android Debug Bridge (adb)](https://developer.android.com/studio/command-line/adb)
  2. [Apk Analyzer](https://play.google.com/store/apps/details?id=sk.styk.martin.apkanalyzer)
#### Para analizar la apk
  1. [Mobile Security Framework (MobSF)](https://github.com/MobSF/Mobile-Security-Framework-MobSF)
#### Para consumir la api encontrada
  1. [Advance Rest Client](https://install.advancedrestclient.com/)
#### Para analizar el trafico web de la apk
  1. [Mitmproxy](https://mitmproxy.org/)
  2. [Genymotion](https://www.genymotion.com/download/)
### Aplicaciones a analizar (instaladas en tu telefono android)
  1. [Edad por rut](https://play.google.com/store/apps/details?id=app.details.nacimientoporrut)
  2. [Rutificador Chile](https://play.google.com/store/apps/details?id=app.details.rutificadorapp)
  
## Conseguir la apk instalada en tu telefono para su analisis
  Hay 2 opciones, con ADB y con Apk Analizer

### Obtener la apk con ADB
  1. Conectar el telefono con adb
  2. listar las apk instaladas en el telefono
  3. ruta de la apk
  4. descargar apk
  
#### Pasos para conectar tu Android a ADB por WiFi (sin root)

1. Anota la dirección IP de tu Android que la puedes encontrar en Ajustes > Acerca del teléfono > Estado > Dirección IP.
2. Activa la depuración USB de tu Android.
3. Ahora conecta tu Android al PC con el cable USB.
4. Abre una ventana de comandos en el ordenador. En Windows, ve a la carpeta donde están los drivers ADB, pulsa CTRL + Shift y haz clic derecho en cualquier lugar de la misma. Luego, selecciona Abrir la ventana de PowerShell aquí.
5. Ingresa el siguiente comando: adb tcpip 5555. Si no funciona, cambia «adb» por «./adb». Deberías recibir el siguiente mensaje: restarting in TCP mode port: 5555.
6. Ahora ingresa este comando: adb connect [pon aquí la IP de tu Android]. Por ejemplo: adb connect 192.168.0.100.
7. Ya puedes desconectar el cable USB que conecta a tu Android con el PC.
8. Desde el ordenador, envía el siguiente comando: adb devices. Si todo ha salido bien, recibirás este mensaje: List of devices attached [La IP de tu Android]:5555 device.

#### Listar las apk instaladas en tu telefono
```shell
  adb shell pm list packages
```
adb shell pm list packages

#### Obtener la ruta de la apk a descargar
```shell
adb shell pm path com.example.someapp
```

#### Descargar apk
```shell
adb pull /data/app/com.example.someapp-2.apk path/to/desired/destination
```

#### Descargar apk spliteada
```shell
adb shell pm path com.example.myapp | sed 's/^package://g' | xargs -L1 adb pull 
```

#### Instalar apk
```shell
adb install com.example.someapp-2.apk 
```

#### Subir archivo (certificado) 
```shell
adb push mitmproxy-ca-cert.cer /sdcard/certs/mitmproxy-ca-cert.cer
```

#### Habilitar proxy
```shell
adb shell settings put global http_proxy 192.168.1.5:8080
```

#### Deshabilitar proxy
```shell
adb shell settings put global http_proxy :0 
```
