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
ms.openlocfilehash: ec2c8388411e24940041dc9dcb7f6a6755e89805
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697588"
---
# <a name="socket-element-network-settings"></a>\<socket (elemento >) (configuración de red)
Especifica si las operaciones de socket utilizan puertos de finalización.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **@no__t -4System. net >** ](system-net-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<settings >** ](settings-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<socket >**  
  
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
|`alwaysUseCompletionPortsForAccept`|Indica si el socket siempre debe utilizar los puertos de finalización para las llamadas al método Accept. El valor predeterminado es `false`.|  
|`alwaysUseCompletionPortsForConnect`|Indica si el socket siempre debe utilizar los puertos de finalización para las llamadas al método Connect. El valor predeterminado es `false`.|  
|`ipProtectionLevel`|Especifica el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> que se va a usar para un socket. El valor predeterminado depende de la versión de Windows.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[Configuración](settings-element-network-settings.md)|Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## <a name="remarks"></a>Comentarios  
 Los atributos `alwaysUseCompletionPortsForAccept` y `alwaysUseCompletionPortsForConnect` se utilizan para especificar el comportamiento predeterminado relacionado con el uso de los puertos de finalización por las clases de la @no__t -2. Namespace. Los puertos de finalización se recomiendan para las aplicaciones de servidor de alto rendimiento.  
  
 El valor predeterminado de los atributos `alwaysUseCompletionPortsForAccept` y `alwaysUseCompletionPortsForConnect` es **false**.  
  
 Se puede usar <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> para obtener el valor actual del atributo `alwaysUseCompletionPortsForAccept` de los archivos de configuración aplicables. Se puede usar <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> para obtener el valor actual del atributo `alwaysUseCompletionPortsForConnect` de los archivos de configuración aplicables.  
  
 El atributo `ipProtectionLevel` especifica el @no__t predeterminado-1 que se va a usar para un socket. La propiedad <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> permite configurar una restricción para un socket IPv6 a un ámbito especificado, como direcciones con el mismo prefijo local de vínculo o sitio. Esta opción permite a las aplicaciones colocar restricciones de acceso en sockets IPv6. Estas restricciones permiten que una aplicación que se ejecuta en una LAN privada se fortalezca de forma sencilla frente a ataques externos. Esta opción amplía o reduce el ámbito de un socket de escucha, lo que permite el acceso no restringido de usuarios públicos y privados cuando sea adecuado, o restringiendo el acceso únicamente al mismo sitio, según sea necesario.  
  
 Este valor de atributo `ipProtectionLevel` solo afecta al tráfico entrante inicial:  
  
- Un servidor TCP que escucha las conexiones entrantes en un socket.  
  
- Aplicación UDP que recibe un paquete en un socket.  
  
 Esta opción de configuración no afecta a las conexiones TCP ya establecidas (el tráfico no está restringido en ambas direcciones) y no afecta a una aplicación que envía paquetes UDP.  
  
 Los valores posibles para el valor del atributo `ipProtectionLevel` se corresponden con los niveles de protección definidos en la enumeración <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> como se indica a continuación:  
  
|**Valor de atributo**|**Descripción**|  
|-|-|  
|EdgeRestricted|El nivel de protección de IP tiene restricción perimetral. Este valor lo usan las aplicaciones diseñadas para funcionar a través de Internet. Esta configuración no permite la exploración transversal de la traducción de direcciones de red (NAT) mediante la implementación de Teredo de Windows. Estas aplicaciones pueden eludir los firewalls IPv4, por lo que las aplicaciones deben protegerse frente a ataques por Internet dirigidos al puerto abierto. En Windows Server 2003 y Windows XP, el valor predeterminado para el nivel de protección de IP en un socket es el restringido perimetral.|  
|Restringido|El nivel de protección de IP está restringido. Este valor lo usan las aplicaciones de intranet que no implementan escenarios de Internet. Normalmente, estas aplicaciones no se comprueban ni protegen frente a ataques de tipo Internet. Esta configuración limitará el tráfico recibido solo a vínculo local.|  
|Sin restricción|El nivel de protección de IP no está restringido. Este valor lo usan las aplicaciones diseñadas para funcionar a través de Internet, incluidas las aplicaciones que aprovechan las capacidades de NAT transversal de IPv6 integradas en Windows (por ejemplo, Teredo). Estas aplicaciones pueden eludir los firewalls IPv4, por lo que las aplicaciones deben protegerse frente a ataques por Internet dirigidos al puerto abierto. En Windows Server 2008 R2 y Windows Vista, el valor predeterminado para el nivel de protección de IP en un socket es Unrestricted.|  
|Sin especificar|El nivel de protección de IP no está especificado. En Windows 7 y Windows Server 2008 R2, no se especifica el valor predeterminado para el nivel de protección de IP en un socket.|  
  
 No se **especifica**el valor predeterminado del atributo `ipProtectionLevel`.  
  
 Se puede usar la propiedad <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> para obtener el valor actual del atributo `ipProtectionLevel` de los archivos de configuración aplicables.  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que se deben usar los puertos de finalización y que el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> debe ser Unrestricted.  
  
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
- [Esquema de la configuración de red](index.md)
