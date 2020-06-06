---
title: Elemento <ipv6> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
ms.openlocfilehash: c16949171d082bd02abb0a02db83c2e71c2f17df
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088131"
---
# <a name="ipv6-element-network-settings"></a>Elemento \<ipv6> (configuración de red)
Habilita las respuestas del Protocolo de Internet versión 6 (IPv6) de los miembros obsoletos de la <xref:System.Net.Dns> clase.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ipv6>**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|**Attribute**|**Descripción**|  
|-------------------|---------------------|  
|`enabled`|Especifica si los miembros de la <xref:System.Net.Dns> clase devuelven direcciones del Protocolo de Internet versión 6 (IPv6). El valor predeterminado es `false`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[settings](settings-element-network-settings.md)|Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## <a name="remarks"></a>Comentarios  
 Esta configuración habilita la compatibilidad con IPv6 para los miembros obsoletos de la <xref:System.Net.Dns> clase: <xref:System.Net.Dns.BeginGetHostByName%2A> , <xref:System.Net.Dns.BeginResolve%2A> , <xref:System.Net.Dns.EndGetHostByName%2A> , <xref:System.Net.Dns.EndResolve%2A> , <xref:System.Net.Dns.GetHostByAddress%2A> , <xref:System.Net.Dns.GetHostByName%2A> y <xref:System.Net.Dns.Resolve%2A> . Para otros miembros del <xref:System.Net?displayProperty=nameWithType> espacio de nombres, es posible que se devuelvan direcciones IPv6 si IPv6 está habilitado en el sistema operativo.  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo habilitar la compatibilidad con IPv6 para la <xref:System.Net.Dns> clase.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [Esquema de la configuración de red](index.md)
