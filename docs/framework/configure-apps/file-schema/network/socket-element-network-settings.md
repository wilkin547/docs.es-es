---
title: Elemento <socket> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
ms.openlocfilehash: 5e8ec13a0bb991accff080db502552e46913c66d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607509"
---
# <a name="socket-element-network-settings"></a>\<Socket > elemento (configuración de red)
Especifica si las operaciones de socket utilizan puertos de terminación.  
  
 \<configuration>  
\<system.net>  
\<settings>  
\<Socket >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|**Attribute**|**Descripción**|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|Indica si el socket siempre debería utilizar los puertos de terminación para llamadas al método de aceptación. El valor predeterminado es `false`.|  
|`alwaysUseCompletionPortsForConnect`|Indica si el socket siempre debería utilizar los puertos de terminación para llamadas al método Connect. El valor predeterminado es `false`.|  
|`ipProtectionLevel`|Especifica el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> a utilizar para un socket. El valor predeterminado depende de la versión de Windows.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## <a name="remarks"></a>Comentarios  
 El `alwaysUseCompletionPortsForAccept` y `alwaysUseCompletionPortsForConnect` atributos se usan para especificar el comportamiento predeterminado con respecto al uso de puertos de terminación de las clases en el <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace. Se recomiendan los puertos de finalización para las aplicaciones de servidor de alto rendimiento.  
  
 El valor predeterminado para el `alwaysUseCompletionPortsForAccept` y `alwaysUseCompletionPortsForConnect` atributos **false**.  
  
 El <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> puede usarse para obtener el valor actual de la `alwaysUseCompletionPortsForAccept` atributo desde archivos de configuración aplicables. El <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> puede usarse para obtener el valor actual de la `alwaysUseCompletionPortsForConnect` atributo desde archivos de configuración aplicables.  
  
 El `ipProtectionLevel` atributo especifica el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> a utilizar para un socket. El <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> propiedad habilita la configuración de una restricción para un socket IPv6 a un ámbito especificado, como direcciones con el mismo vínculo o sitio prefijo local. Esta opción permite a las aplicaciones colocar restricciones de acceso en sockets IPv6. Estas restricciones permiten que una aplicación que se ejecuta en una LAN privada se fortalezca de forma sencilla frente a ataques externos. Esta opción se amplía o reduce el ámbito de un socket de escucha, permite el acceso no restringido de usuarios públicos y privados cuando sea adecuado o restringir el acceso únicamente al mismo sitio, según sea necesario.  
  
 Esto `ipProtectionLevel` sólo tráfico inicial entrante afecta a la configuración del atributo:  
  
- Un servidor de TCP escucha las conexiones entrantes en un socket.  
  
- Una aplicación de UDP recibir un paquete en un socket.  
  
 Esta opción de configuración no afecta a las conexiones ya se ha establecido de TCP (tráfico no tiene restricciones en ambas direcciones) y no afecta a una aplicación que envía paquetes UDP.  
  
 Los valores posibles de la `ipProtectionLevel` configuración del atributo se corresponden con los niveles de protección especificados en la <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeración como sigue:  
  
|**Valor de atributo**|**Descripción**|  
|-|-|  
|EdgeRestricted|El nivel de protección de IP tiene una restricción perimetral. Este valor lo usan las aplicaciones diseñadas para funcionar a través de Internet. Esta configuración no permite la exploración transversal de traducción de direcciones de red (NAT) mediante la implementación de Teredo de Windows. Estas aplicaciones pueden eludir los firewalls de IPv4, por lo que las aplicaciones deben protegerse frente a ataques de Internet dirigidos al puerto abierto. En Windows Server 2003 y Windows XP, el valor predeterminado para el nivel de protección de IP en un socket es la restricción perimetral.|  
|Restringido|El nivel de protección de IP está restringido. Este valor lo usan las aplicaciones de intranet que no implementan escenarios de Internet. Estas aplicaciones son por lo general no probadas o protegidas contra ataques por Internet. Este valor limitará el tráfico recibido a las direcciones locales de vínculo.|  
|Sin restricción|El nivel de protección IP no está restringido. Este valor lo usan las aplicaciones diseñadas para funcionar a través de Internet, incluidas las aplicaciones aprovechar las capacidades de cruce seguro de NAT de IPv6 integradas en Windows (por ejemplo, Teredo). Estas aplicaciones pueden eludir los firewalls de IPv4, por lo que las aplicaciones deben protegerse frente a ataques de Internet dirigidos al puerto abierto. En Windows Server 2008 R2 y Windows Vista, el valor predeterminado para el nivel de protección de IP en un socket no está restringido.|  
|Sin especificar|El nivel de protección IP no está especificado. En Windows 7 y Windows Server 2008 R2, el valor predeterminado para el nivel de protección de IP en un socket no está especificado.|  
  
 El valor predeterminado para el `ipProtectionLevel` atributo es **Unspecified**.  
  
 El <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> propiedad puede usarse para obtener el valor actual de la `ipProtectionLevel` atributo desde archivos de configuración aplicables.  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo especificar que se deben usar puertos de terminación y que el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> debe ser sin restricciones.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <socket  
        alwaysUseCompletionPortsForAccept="true"  
        alwaysUseCompletionPortsForConnect="true"  
        ipProtectionLevel="Unrestricted"  
       />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
