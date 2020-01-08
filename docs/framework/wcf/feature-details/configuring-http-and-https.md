---
title: Configuración de HTTP y HTTPS
ms.date: 04/08/2019
helpviewer_keywords:
- configuring HTTP [WCF]
ms.assetid: b0c29a86-bc0c-41b3-bc1e-4eb5bb5714d4
ms.openlocfilehash: f7fd2bad6ced09b638cc1bb5d539fab1b9ce7d25
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75336698"
---
# <a name="configuring-http-and-https"></a>Configuración de HTTP y HTTPS

Los servicios y clientes de WCF se pueden comunicar a través de HTTP y HTTPS, que se configuran mediante el uso de Internet Information Services (IIS) o de una herramienta de la línea de comandos. Cuando un servicio WCF se hospeda bajo IIS y necesita la configuración de HTTP o HTTPS se puede configurar en IIS (con la herramienta inetmgr.exe). Si el servicio WCF se autohospeda, la configuración de HTTP o HTTPS se configura usando una herramienta de la línea de comandos.

Como mínimo, desea configurar un registro de direcciones URL y agregar una excepción de Firewall para la dirección URL que utilizará el servicio. Puede configurar estas opciones con la herramienta netsh. exe.

## <a name="configuring-namespace-reservations"></a>Configurar reservas de espacio de nombres

La reserva de espacio de nombres asigna los derechos de una parte del espacio de nombres HTTP URL a un grupo de usuarios determinado. Una reserva concede a esos usuarios el derecho para crear servicios que escuchen en esa porción del espacio de nombre. Las reservas son prefijos de dirección URL, lo que significa que la reserva cubre todos los subtrazados de la ruta de acceso de reserva. Las reservas de espacio de nombres permiten dos maneras de utilizar los caracteres comodín. La documentación de la API del servidor HTTP describe el [orden de resolución entre notificaciones de espacios de nombres que impliquen caracteres comodín](/windows/desktop/Http/routing-incoming-requests).

Una aplicación en ejecución puede crear una solicitud similar para agregar los registros de espacio de nombres. Los registros y reservas compiten por partes del espacio de nombres. Una reserva puede tener prioridad sobre un registro según el orden de resolución dado en el [orden de resolución entre notificaciones de espacios de nombres que impliquen caracteres comodín](/windows/desktop/Http/routing-incoming-requests). En este caso, la reserva bloquea a la aplicación en ejecución la posibilidad de recibir solicitudes.

En el ejemplo siguiente se usa la herramienta netsh. exe:

```console
netsh http add urlacl url=http://+:80/MyUri user=DOMAIN\user
```

Este comando agrega una reserva de direcciones URL para el espacio de nombres de la dirección URL especificada para la cuenta Dominio\usuario. Para obtener más información sobre el uso del comando netsh, escriba `netsh http add urlacl /?` en un símbolo del sistema y presione Entrar.

## <a name="configuring-a-firewall-exception"></a>Configuración de una excepción de Firewall

Cuando se autohospeda un servicio de WCF que se comunica sobre HTTP, se debe agregar una excepción a la configuración del firewall para permitir conexiones de entrada usando una dirección URL determinada.

## <a name="configuring-ssl-certificates"></a>Configuración de certificados SSL

El protocolo SSL (Capa de sockets seguros) usa los certificados de cliente y servidor para almacenar las claves de cifrado. El servidor proporciona su certificado SSL cuando se realiza una conexión, para que el cliente pueda comprobar la identidad del servidor. El servidor también puede solicitar un certificado del cliente para proporcionar una autenticación mutua de ambos lados de la conexión.

Los certificados se almacenan en un almacén centralizado según la dirección IP y el número de puerto de la conexión. La dirección IP 0.0.0.0 especial coincide con cualquier dirección IP del equipo local. Tenga en cuenta que el almacén de certificados no distingue las direcciones URL en función de la ruta de acceso. Los servicios con la misma dirección IP y combinación de puertos deben compartir los certificados aun cuando la ruta de acceso en la dirección URL de los servicios sea diferente.

Para obtener instrucciones paso a paso, consulte [Cómo: configurar un puerto con un certificado SSL](how-to-configure-a-port-with-an-ssl-certificate.md).

## <a name="configuring-the-ip-listen-list"></a>Configuración de la lista de escuchas de IP

La API de servidor HTTP solo se enlaza una vez a una dirección IP y a un puerto, una vez que el usuario haya registrado una dirección URL. De forma predeterminada, el API de servidor HTTP se enlaza al puerto en la URL de todas las direcciones IP del equipo. Se produce un conflicto si una aplicación que no usa la API del servidor HTTP se ha enlazado previamente a esa combinación de dirección IP y puerto. La lista de escucha de IP permite que los servicios WCF coexistan con las aplicaciones que usan un puerto para algunas de las direcciones IP de la máquina. Si la lista de escucha de IP contiene cualquier entrada, el API de servidor HTTP solo se enlaza a esas direcciones IP que la lista especifica. Para modificar la lista de escuchas de IP se requieren privilegios de administrador.

Use la herramienta Netsh para modificar la lista de escucha IP, como se muestra en el ejemplo siguiente:

```console
netsh http add iplisten ipaddress=0.0.0.0:8000
```

## <a name="other-configuration-settings"></a>Otras opciones de configuración

Cuando se use la clase <xref:System.ServiceModel.WSDualHttpBinding>, la conexión de cliente utiliza valores predeterminados compatibles con reservas de espacio de nombres y el Firewall de Windows. Si elige personalizar la dirección base de cliente de una conexión dual, también debe configurar esta configuración de HTTP en el cliente para que coincida con la nueva dirección.

La API del servidor HTTP tiene algunas opciones de configuración avanzadas que no están disponibles a través de HttpCfg. Estos valores se mantienen en el Registro y se aplican a todas las aplicaciones que se ejecutan en los sistemas que utilizan los API de servidor HTTP. Para obtener información acerca de esta configuración, consulte [configuración del registro de http. sys para IIS](https://support.microsoft.com/help/820129/http-sys-registry-settings-for-windows). La mayoría de los usuarios no necesitan cambiar esta configuración.

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.WSDualHttpBinding>
- [Configuración de un puerto con un certificado SSL](how-to-configure-a-port-with-an-ssl-certificate.md)
