# Cazando APIs en aplicaciones mobiles

## Prerequisitos

### Celular android
  Cualquier celular android con la apliacion que deseas analizar instalada
  
### APPs
#### Para obtener la apk
  1. [Android Debug Bridge (adb)](https://developer.android.com/studio/command-line/adb)
  2. [Apk Analyzer](https://play.google.com/store/apps/details?id=sk.styk.martin.apkanalyzer)
#### Para analizar la apk
  1. [Mobile Security Framework (MobSF)](https://github.com/MobSF/Mobile-Security-Framework-MobSF)
### Para consumir la api encontrada
  1. [Advance Rest Client](https://install.advancedrestclient.com/)
  

### Aplicaciones a analizar
  1. [Edad por rut](https://play.google.com/store/apps/details?id=app.details.nacimientoporrut)

## Conseguir la apk instalada en tu telefono para su analisis
  Hay 2 opciones, con ADB y con Apk Analizer


### Pasos para conectar tu Android a ADB por WiFi (sin root)

1. Anota la dirección IP de tu Android que la puedes encontrar en Ajustes > Acerca del teléfono > Estado > Dirección IP.
2. Activa la depuración USB de tu Android.
3. Ahora conecta tu Android al PC con el cable USB.
4. Abre una ventana de comandos en el ordenador. En Windows, ve a la carpeta donde están los drivers ADB, pulsa CTRL + Shift y haz clic derecho en cualquier lugar de la misma. Luego, selecciona Abrir la ventana de PowerShell aquí.
5. Ingresa el siguiente comando: adb tcpip 5555. Si no funciona, cambia «adb» por «./adb». Deberías recibir el siguiente mensaje: restarting in TCP mode port: 5555.
6. Ahora ingresa este comando: adb connect [pon aquí la IP de tu Android]. Por ejemplo: adb connect 192.168.0.100.
7. Ya puedes desconectar el cable USB que conecta a tu Android con el PC.
8. Desde el ordenador, envía el siguiente comando: adb devices. Si todo ha salido bien, recibirás este mensaje: List of devices attached [La IP de tu Android]:5555 device.

