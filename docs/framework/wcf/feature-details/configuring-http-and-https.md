---
title: Configuración de HTTP y HTTPS
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring HTTP [WCF]
ms.assetid: b0c29a86-bc0c-41b3-bc1e-4eb5bb5714d4
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8d3317cd4bba7c9935bd7555f16599dc94725fbd
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="configuring-http-and-https"></a>Configuración de HTTP y HTTPS
Los servicios y clientes de WCF se pueden comunicar a través de HTTP y HTTPS, que se configuran mediante el uso de Internet Information Services (IIS) o de una herramienta de la línea de comandos. Cuando un servicio WCF se hospeda bajo IIS y necesita la configuración de HTTP o HTTPS se puede configurar en IIS (con la herramienta inetmgr.exe). Si el servicio WCF se autohospeda, la configuración de HTTP o HTTPS se configura usando una herramienta de la línea de comandos.  
  
 Como mínimo deseará configurar un registro de direcciones URL, y agregar una excepción de Firewall para la dirección URL que el servicio usará.  
  
 La herramienta que se usa para definir la configuración de HTTP depende del sistema operativo que el equipo esté ejecutando.  
  
 Cuando se ejecuta [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use la herramienta HttpCfg.exe. [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] instala automáticamente esta herramienta. Cuando se ejecuta [!INCLUDE[wxp](../../../../includes/wxp-md.md)], puede descargar la herramienta en [herramientas de soporte técnico de Windows XP Service Pack 2](http://go.microsoft.com/fwlink/?LinkId=88606). Para obtener más información, consulte [general de Httpcfg](http://go.microsoft.com/fwlink/?LinkId=88605).  
  
 Cuando se ejecute [!INCLUDE[wv](../../../../includes/wv-md.md)]o Windows 7, configúrelo con la herramienta Netsh.exe.  
  
## <a name="configuring-namespace-reservations"></a>Configuración de las reservas de espacios de nombres  
 La reserva de espacio de nombres asigna los derechos de una parte del espacio de nombres HTTP URL a un grupo de usuarios determinado. Una reserva da derecho a esos usuarios para crear servicios que escuchen en esa parte del espacio de nombres. Las reservas son prefijos URL, lo que significa que la reserva cubre todas las rutas de acceso secundarias de la ruta de acceso de la reserva. Las reservas de espacio de nombres permiten dos maneras de utilizar los caracteres comodín. La documentación de API de servidor HTTP describe el [orden de resolución entre notificaciones de espacio de nombres que impliquen caracteres comodín](http://go.microsoft.com/fwlink/?LinkId=94841).  
  
 Una aplicación en ejecución puede crear una solicitud similar para agregar los registros de espacio de nombres. Los registros y reservas compiten por partes del espacio de nombres. Una reserva puede tener prioridad sobre un registro según el orden de resolución dado en el [orden de resolución entre notificaciones de espacio de nombres que impliquen caracteres comodín](http://go.microsoft.com/fwlink/?LinkId=94841). En este caso, la reserva bloquea a la aplicación en ejecución la posibilidad de recibir solicitudes.  
  
### <a name="running-windows-xp-or-server-2003"></a>Ejecución de Windows XP o Windows Server 2003  
 Use la `httpcfg.exe set urlacl` comando para cambiar las reservas de espacio de nombres. El [Httpcfg](http://go.microsoft.com/fwlink/?LinkId=94840) explica la sintaxis de la herramienta Httpcfg.exe. Para modificar los derechos de la reserva para una parte del espacio de nombres, se requieren privilegios de administrador o propiedad sobre esa parte del espacio de nombres. Inicialmente, el espacio de nombres HTTP completo pertenece al administrador local.  
  
 A continuación, se muestra la sintaxis del comando Httpcfg con la opción `set urlacl`  
  
```  
httpcfg set urlacl /u {http://URL:Port/ | https://URL:Port/} /aACL  
```  
  
 El parámetro `/u` es necesario al usar `set urlacl`. Toma una cadena que contiene una dirección URL completa que actúa como clave de registro para la reserva que se está realizando.  
  
 El parámetro `/a` también es necesario al utilizar `set urlacl`. Toma una cadena que contiene una lista de control de acceso (ACL) en forma de cadena de lenguaje de definición de descriptor de seguridad (SDDL).  
  
 A continuación se muestra un ejemplo del uso de este comando.  
  
```  
httpcfg.exe set urlacl /u http://myhost:8000/ /a "O:AOG:DAD:(A;;RPWPCCDCLCSWRCWDWOGA;;;S-1-0-0)"  
```  
  
### <a name="running-windows-vista-windows-server-2008-r2-or-windows-7"></a>Ejecución de Windows Vista, Windows Server 2008 R2 o Windows 7  
 Si ejecuta [!INCLUDE[wv](../../../../includes/wv-md.md)], Windows Server 2008 R2 o Windows 7, use la herramienta Netsh.exe. A continuación se muestra un ejemplo del uso de este comando.  
  
```  
netsh http add urlacl url=http://+:80/MyUri user=DOMAIN\user  
```  
  
 Este comando agrega una reserva de dirección URL para el espacio de nombres URL especificado para la cuenta DOMAIN\user.  Para obtener más información sobre el uso del comando netsh escriba "netsh http add urlacl" en un símbolo del sistema y presione escriba.  
  
## <a name="configuring-a-firewall-exception"></a>Configurar una excepción de firewall  
 Cuando se autohospeda un servicio de WCF que se comunica sobre HTTP, se debe agregar una excepción a la configuración del firewall para permitir conexiones de entrada usando una dirección URL determinada. Para obtener más información, vea [abrir un puerto en Firewall de Windows (Windows 7)](http://go.microsoft.com/fwlink/?LinkId=239961)  
  
## <a name="configuring-ssl-certificates"></a>Configuración de certificados SSL  
 El protocolo SSL (Capa de sockets seguros) usa los certificados de cliente y servidor para almacenar las claves de cifrado. El servidor proporciona su certificado SSL cuando se realiza una conexión, para que el cliente pueda comprobar la identidad del servidor. El servidor también puede solicitar un certificado del cliente para proporcionar una autenticación mutua de ambos lados de la conexión.  
  
 Los certificados se almacenan en un almacén centralizado según la dirección IP y el número de puerto de la conexión. La dirección IP 0.0.0.0 especial coincide con cualquier dirección IP del equipo local. Observe que el almacén de certificados no distingue direcciones URL basadas en la ruta de acceso. Los servicios con la misma dirección IP y combinación de puertos deben compartir los certificados aun cuando la ruta de acceso en la dirección URL de los servicios sea diferente.  
  
 Para obtener instrucciones detalladas, consulte [Cómo: configurar un puerto con un certificado SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).  
  
## <a name="configuring-the-ip-listen-list"></a>Configuración de la lista de escuchas de IP  
 La API de servidor HTTP solo se enlaza una vez a una dirección IP y a un puerto, una vez que el usuario haya registrado una dirección URL. De forma predeterminada, el API de servidor HTTP se enlaza al puerto en la URL de todas las direcciones IP del equipo. Se produce un conflicto si una aplicación que no usa la API de servidor HTTP se ha enlazado previamente a esa combinación de dirección IP y puerto. La lista de escucha de IP permite que los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] coexistan con aplicaciones que utilizan un puerto para algunas de las direcciones IP del equipo. Si la lista de escucha de IP contiene cualquier entrada, el API de servidor HTTP solo se enlaza a esas direcciones IP que la lista especifica. Para modificar la lista de escuchas de IP se requieren privilegios de administrador.  
  
### <a name="running-windows-xp-or-server-2003"></a>Ejecución de Windows XP o Windows Server 2003  
 Use la herramienta httpcfg para modificar la lista de escucha IP, como se muestra en el ejemplo siguiente. El [Httpcfg](http://go.microsoft.com/fwlink/?LinkId=94840) explica la sintaxis de la herramienta httpcfg.exe.  
  
```  
httpcfg.exe set iplisten -i 0.0.0.0:8000  
```  
  
### <a name="running-windows-vista-or-windows-7"></a>Ejecución de Windows Vista o Windows 7  
 Use la herramienta netsh para modificar la lista de escucha IP, como se muestra en el ejemplo siguiente.  
  
```  
netsh http add iplisten ipaddress=0.0.0.0:8000  
```  
  
## <a name="other-configuration-settings"></a>Otras opciones de configuración  
 Cuando se use la clase <xref:System.ServiceModel.WSDualHttpBinding>, la conexión de cliente utiliza valores predeterminados compatibles con reservas de espacio de nombres y el Firewall de Windows. Si elige personalizar la dirección base de cliente de una conexión dual, también debe configurar esta configuración de HTTP en el cliente para que coincida con la nueva dirección.  
  
 El API de servidor HTTP tiene algunos valores de configuración avanzados que no están disponibles a través de HttpCfg. Estos valores se mantienen en el Registro y se aplican a todas las aplicaciones que se ejecutan en los sistemas que utilizan los API de servidor HTTP. Para obtener información acerca de estas opciones, consulte [configuración del registro de Http.sys para IIS](http://go.microsoft.com/fwlink/?LinkId=94843). La mayoría de usuarios no deberían necesitar cambiar estos valores.  
  
## <a name="issues-specific-to-windows-xp"></a>Problemas específicos de Windows XP  
 IIS no admite el uso compartido de puertos en [!INCLUDE[wxp](../../../../includes/wxp-md.md)]. Si IIS se está ejecutando y un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] intenta utilizar un espacio de nombres con el mismo puerto, el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no puede iniciarse. De forma predeterminada, IIS y [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usan el puerto 80. Cambie la asignación de puertos para uno de los servicios o use la lista de escucha de IP para asignar el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] a un adaptador de red no usado por IIS. IIS 6.0 y sus versiones posteriores se han rediseñado para utilizar los API de servidor HTTP.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.WSDualHttpBinding>  
 [Configuración de un puerto con un certificado SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
