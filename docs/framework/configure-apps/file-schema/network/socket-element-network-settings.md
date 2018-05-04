---
title: '&lt;socket&gt; Element (Network Settings)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 995a89dd67664fd6a408f88f20f6837d2dbaaad4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltsocketgt-element-network-settings"></a>&lt;socket&gt; Element (Network Settings)
Especifica si las operaciones de socket utilizan puertos de terminación.  
  
 \<configuration>  
\<System.NET >  
\<Configuración >  
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
|`alwaysUseCompletionPortsForAccept`|Indica si el socket siempre debería utilizar los puertos de terminación para llamadas al método Accept. El valor predeterminado es `false`.|  
|`alwaysUseCompletionPortsForConnect`|Indica si el socket siempre debería utilizar los puertos de terminación para llamadas al método Connect. El valor predeterminado es `false`.|  
|`ipProtectionLevel`|Especifica el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> debe utilizar para un socket. El valor predeterminado depende de la versión de Windows.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[Configuración](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## <a name="remarks"></a>Comentarios  
 El `alwaysUseCompletionPortsForAccept` y `alwaysUseCompletionPortsForConnect` atributos se usan para especificar el comportamiento predeterminado con respecto al uso de puertos de terminación de las clases en el <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace. Los puertos de terminación se recomiendan para aplicaciones de servidor de alto rendimiento.  
  
 El valor predeterminado para la `alwaysUseCompletionPortsForAccept` y `alwaysUseCompletionPortsForConnect` atributos **false**.  
  
 El <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> puede utilizarse para obtener el valor actual de la `alwaysUseCompletionPortsForAccept` atributos de archivos de configuración aplicables. El <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> puede utilizarse para obtener el valor actual de la `alwaysUseCompletionPortsForConnect` atributos de archivos de configuración aplicables.  
  
 El `ipProtectionLevel` atributo especifica el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> debe utilizar para un socket. El <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> propiedad permite la configuración de una restricción para un socket IPv6 a un ámbito especificado, como direcciones con el mismo vínculo locales o prefijo local del sitio. Esta opción permite a las aplicaciones colocar restricciones de acceso en sockets IPv6. Estas restricciones permiten que una aplicación que se ejecuta en una LAN privada se fortalezca de forma sencilla frente a ataques externos. Esta opción amplía o reduce el ámbito de un socket de escucha, lo que permite el acceso no restringido de usuarios públicos y privados cuando sea adecuado o restringe el acceso únicamente al mismo sitio, según sea necesario.  
  
 Esto `ipProtectionLevel` afecta a la configuración del atributo solamente el tráfico entrante inicial:  
  
-   Un servidor TCP escuchar las conexiones entrantes en un socket.  
  
-   Una aplicación de UDP recibir un paquete en un socket.  
  
 Esta opción de configuración no afecta a las conexiones TCP ya se ha establecido (tráfico no tiene restricciones en ambas direcciones) y no afecta a ninguna aplicación que envíe paquetes UDP.  
  
 Los valores posibles de la `ipProtectionLevel` configuración del atributo se corresponden con los niveles de protección definidos especificados en la <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeración como se indica a continuación:  
  
|**Valor de atributo**|**Descripción**|  
|-|-|  
|EdgeRestricted|El nivel de protección de IP tiene una restricción perimetral. Este valor se usaría por aplicaciones diseñadas para funcionar a través de Internet. Esta configuración no permitir cruce seguro de traducción de direcciones de red (NAT) mediante la implementación de Windows Teredo. Estas aplicaciones pueden eludir los firewalls de IPv4, por lo que se deben reforzar las aplicaciones frente a ataques de Internet que se dirigen al puerto abierto. En Windows Server 2003 y Windows XP, el valor predeterminado para el nivel de protección de IP en un socket es borde restringido.|  
|Restringido|El nivel de protección de IP está restringido. Este valor se usaría las aplicaciones de intranet que no implementan escenarios de Internet. Estas aplicaciones son generalmente no probadas o protege frente a ataques de estilo de Internet. Esta opción limitará el tráfico recibido a las direcciones locales de vínculo.|  
|Sin restricción|El nivel de protección de IP no está restringido. Este valor se usaría por aplicaciones diseñadas para funcionar a través de Internet, incluidas las aplicaciones de sacar partido de las funciones de cruce seguro de NAT de IPv6 integradas en Windows (por ejemplo, Teredo). Estas aplicaciones pueden eludir los firewalls de IPv4, por lo que se deben reforzar las aplicaciones frente a ataques de Internet que se dirigen al puerto abierto. En Windows Server 2008 R2 y Windows Vista, el valor predeterminado para el nivel de protección de IP en un socket no está restringido.|  
|Sin especificar|El nivel de protección de IP no está especificado. En Windows 7 y Windows Server 2008 R2, el valor predeterminado para el nivel de protección de IP en un socket no está especificado.|  
  
 El valor predeterminado para la `ipProtectionLevel` atributo es **Unspecified**.  
  
 El <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> propiedad puede utilizarse para obtener el valor actual de la `ipProtectionLevel` atributos de archivos de configuración aplicables.  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que se deben usar los puertos de terminación y que el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> debe ser sin restricciones.  
  
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
 <xref:System.Net?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>  
 <xref:System.Net.Sockets?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>  
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
