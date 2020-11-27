---
title: Interpretar códigos de error devueltos por wsatConfig.exe
ms.date: 03/30/2017
ms.assetid: ab65f22b-0d69-4c21-9aaf-74acef0ca102
ms.openlocfilehash: c5f423f5054a3a80bc0c730444ca9e90c203e288
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262754"
---
# <a name="interpreting-error-codes-returned-by-wsatconfigexe"></a>Interpretar códigos de error devueltos por wsatConfig.exe

En este tema se hace una lista de todos los códigos de error generados por la utilidad de configuración de WS-AtomicTransaction (wsatConfig.exe) y acciones recomendadas que se van a tomar.  
  
## <a name="list-of-error-codes"></a>Lista de códigos de error  
  
|Código de error|Descripción|Acción que se recomienda realizar|  
|----------------|-----------------|------------------------------------|  
|0|Operación realizada correctamente|None|  
|1|Error inesperado|Contacto con Microsoft|  
|2|Se ha producido un error inesperado al intentar ponerse en contacto con MSDTC para recuperar su configuración de seguridad.|Asegúrese de que el servicio de MSDTC no está deshabilitado, y resuelva todos los problemas enumerados en la excepción devuelta.|  
|3|La cuenta bajo la que se ejecutó WsatConfig.exe no tenía los permisos necesarios para leer los valores de seguridad de red.|Ejecute WsatConfig.exe con una cuenta de usuario Administrador.|  
|4|Permita "Acceso DTC a red" para MSDTC antes de intentar habilitar la compatibilidad WS-AT.|Permita “Acceso DTC a red” para MSDTC y vuelva a ejecutar la utilidad.|  
|5|El puerto indicado estaba fuera del intervalo. El valor de debe estar entre 1 y 65535|Corrija `-port:<portNum>`<br /><br /> opción de línea de comandos como se indica en el mensaje de error.|  
|6|Se ha especificado un certificado del punto de conexión no válido en la línea de comandos.  No se ha podido encontrar el certificado o éste no ha superado la comprobación.|Corrija la opción de la línea de comandos `-endpointCert`. Asegúrese de que el certificado tiene una clave privada, se va a utilizar para ClientAuthentication y ServerAuthentication, está instalado en el almacén de certificados de LocalMachine\MY y es de plena confianza.|  
|7|Se ha especificado un certificado de cuentas no válido en la línea de comandos.|Corrija la opción de la línea de comandos `-accountsCerts`. El certificado especificado no estaba correctamente especificado o no se pudo encontrar.|  
|8|Se especificó un tiempo de espera predeterminado fuera del intervalo de 1 a 3600 segundos.|Escriba un valor de tiempo de espera predeterminado correcto tal y como se indica.|  
|10|Se ha producido un error inesperado mientras se intentaba tener acceso al registro.|Comprobar si hay elementos procesables en el mensaje de error y código de error|  
|11|No puede escribir en el registro.|Asegurarse que la clave enumerada en el mensaje de error es capaz de admitir el acceso al registro desde la cuenta bajo la cual se ejecutó WsatConfig.exe.|  
|12|Se ha producido un error inesperado mientras se intentaba tener acceso al almacén de certificados.|Utilice el código de error devuelto para realizar la asignación al error de sistema adecuado.|  
|13|Error de configuración de http.sys. No puede crear una nueva reserva de puerto HTTPS para MSDTC.|Utilice el código de error devuelto para realizar la asignación al error de sistema adecuado.|  
|14|Error de configuración de http.sys. No puede quitar una reserva del puerto HTTPS para MSDTC anterior.|Utilice el código de error devuelto para realizar la asignación al error de sistema adecuado.|  
|15|Error de configuración de http.sys. Ya hay una reserva de puerto HTTPS anterior para el puerto especificado.|Otra aplicación ya ha obtenido la propiedad del puerto concreto. Cambie la aplicación actual a un puerto diferente, desinstálela o vuelva a configurarla.|  
|16|Error de configuración de http.sys. No se puede enlazar el certificado especificado al puerto.|Utilice el código de error devuelto en el mensaje de error para realizar la asignación al error de sistema adecuado.|  
|17|Error de configuración de http.sys. No puede desenlazar el certificado SSL del puerto anterior.|Utilice el código de error devuelto en el mensaje de error para realizar la asignación al error de sistema adecuado. Si es necesario, utilice httpcfg.exe o netsh.exe para quitar las reservas de puerto incorrectas.|  
|18|Error de configuración de http.sys. No se puede enlazar el certificado especificado al puerto porque ya existe un enlace de SSL anterior.|Otra aplicación ya ha obtenido la propiedad del puerto concreto. Cambie la aplicación actual a un puerto diferente, desinstálela o vuelva a configurarla.|  
|19|No se ha podido reiniciar MSDTC|Si es necesario, reinicie MSDTC de forma manual. Si el problema continúa, póngase en contacto con Microsoft.|  
|20|WinFX no está instalado en el equipo remoto o no se ha instalado correctamente.|Instale WinFX en la máquina.|  
|21|Se ha producido un error en la configuración remota porque la operación ha expirado.|La llamada para configurar WS-AT en el equipo remoto debería llevar mucho más tiempo que 90 segundos.|  
|22|WinFX no está instalado en el equipo remoto o no se ha instalado correctamente.|Instale WinFX en la máquina.|  
|23|Se ha producido un error en la configuración remota debido a una excepción en el equipo remoto.|Comprobar si hay elementos procesables en el mensaje de error|  
|26|Se ha pasado un argumento no válido a WsatConfig.exe.|Compruebe si hay errores en la línea de comandos.|  
|27|La opción de línea de comandos `-accounts` no es válida.|Corrija la opción de línea de comandos -`accounts` para especificar correctamente una cuenta de usuario.|  
|28|La opción de línea de comandos `-network` no es válida.|Corrija la opción de línea de comandos `-network` para especificar correctamente "habilitar" o "deshabilitar".|  
|29|La opción de línea de comandos `-maxTimeout` no es válida.|Corrija la opción de línea de comandos `-maxTimeout` como se indica.|  
|30|La opción de línea de comandos `-timeout` no es válida.|Corrija la opción de línea de comandos `-timeout` como se indica.|  
|31|La opción de línea de comandos `-traceLevel` no es válida.|Corrija la opción de línea de comandos `-traceLevel` para especificar un valor válido de lo siguientes<br /><br /> -OFF<br />-   Error<br />-   Critical<br />-   Warning<br />-Información<br />-Verbose<br />-Todo|  
|32|La opción de línea de comandos `-traceActivity` no es válida.|Corrija la opción de línea de comandos `-traceActivity` especificando "habilitar" o "deshabilitar".|  
|33|La opción de línea de comandos `-traceProp` no es válida.|Corrija la opción de línea de comandos `-traceProp` especificando "habilitar" o "deshabilitar".|  
|34|La opción de línea de comandos `-tracePII` no es válida.|Corrija la opción de línea de comandos `-tracePII` especificando "habilitar" o "deshabilitar".|  
|37|WsatConfig.exe no pudo determinar el certificado de equipo exacto. Esto puede pasar cuando hay más de un candidato o cuando no existe ninguno.|Especifique una huella digital del certificado o un par Issuer\SubjectName para identificar correctamente el certificado exacto para configurar.|  
|38|El proceso o el usuario no tienen los permisos necesarios para cambiar la configuración del firewall.|Ejecute WsatConfig.exe con una cuenta de usuario Administrador.|  
|39|WsatConfig.exe ha encontrado un error actualizando la configuración del firewall.|Comprobar si hay elementos procesables en el mensaje de error.|  
|40|WsatConfig.exe no puede dar acceso de lectura MSDTC al archivo de clave privada del certificado|Ejecute WsatConfig.exe con una cuenta de usuario Administrador.|  
|41|No se encontró ninguna instalación de WinFX o la versión encontrada no coincide con lo que la herramienta es capaz de configurar.|Asegúrese de que WinFX está instalado correctamente y use la herramienta de WsatConfig.exe que se incluye con esa versión de WinFX para configurar WS-AT.|  
|42|Se ha especificado un argumento más de una vez en la línea de comandos.|Especifique cada argumento sólo una vez al ejecutar WsatConfig.exe.|  
|43|WsatConfig.exe no puede actualizar los valores WS-AT si WS-AT no está habilitado.|Especifique `-network:enable` como argumento de la línea de comandos adicional.|  
|44|Falta una revisión necesaria y no se puede configurar WS-AT hasta que se instale la revisión.|Vea las notas de la versión de WinFX para obtener instrucciones sobre cómo instalar la revisión necesaria.|  
|45|La opción de línea de comandos `-virtualServer` no es válida.|Corrija la opción de línea de comandos `-virtualServer` especificando el nombre de red del recurso del clúster en el se debe configurar.|  
|46|Error inesperado al intentar iniciar la sesión de seguimiento ETW.|Utilice el código de error devuelto para realizar la asignación al error de sistema adecuado.|  
|47|El proceso o el usuario no tiene los permisos necesarios para habilitar la sesión de seguimiento ETW.|Ejecute WsatConfig.exe con una cuenta de usuario Administrador.|  
|48|Error inesperado al intentar iniciar la sesión de seguimiento ETW.|Póngase en contacto con Microsoft.|  
|49|No puede crear un nuevo archivo de registro debido al espacio insuficiente en %systemdrive%|Asegúrese de que su %systemdrive% tiene espacio adecuado para el archivo de registro.|  
|51|Error inesperado al intentar iniciar la sesión de seguimiento ETW.|Póngase en contacto con Microsoft.|  
|52|Error inesperado al intentar iniciar la sesión de seguimiento ETW.|Póngase en contacto con Microsoft.|  
|53|La copia de seguridad del archivo de registro de sesión de ETW anterior no se ha realizado correctamente.|Asegurarse que su %systemdrive% tiene espacio adecuado para el archivo de registro y la copia de seguridad del archivo de registro anterior (si existe). Quite manualmente el archivo de registro anterior si es necesario.|  
|55|Error inesperado al intentar iniciar la sesión de seguimiento ETW.|Póngase en contacto con Microsoft.|  
|56|Error inesperado al intentar iniciar la sesión de seguimiento ETW.|Póngase en contacto con Microsoft.|  
  
## <a name="see-also"></a>Vea también

- [Utilidad de configuración de WS-AtomicTransaction (wsatConfig.exe)](ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
