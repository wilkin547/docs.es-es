---
title: Elemento <bypasslist> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: 97e69a4978aa4700d13a994619a65312cf70aeaa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154951"
---
# <a name="bypasslist-element-network-settings"></a>\<bypasslist> Element (Configuración de red)
Proporciona un conjunto de expresiones regulares que describen direcciones que no utilizan un proxy.  

[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>de lista de derivación**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|**Elemento**|**Descripción**|  
|-----------------|---------------------|  
|[agregar](add-element-for-bypasslist-network-settings.md)|Agrega una dirección IP o un nombre DNS a la lista de omisión de proxy.|  
|[Claro](clear-element-for-bypasslist-network-settings.md)|Borra la lista de derivación.|  
|[quitar](remove-element-for-bypasslist-network-settings.md)|Quita una dirección IP o un nombre DNS de la lista de omisión de proxy.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Elemento**|**Descripción**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).|  
  
## <a name="remarks"></a>Observaciones  
 La lista de omisión contiene <xref:System.Net.WebRequest> expresiones regulares que describen los URI a los que las instancias tienen acceso directamente en lugar de a través del servidor proxy.  
  
 Debe tener cuidado al especificar una expresión regular para este elemento. La expresión regular "[a-z]+\\.contoso\\.com" coincide con cualquier host del dominio contoso.com, pero también coincide con cualquier host del dominio contoso.com.cpandl.com. Para que solo coincida con un host del dominio contoso.com, use un\\delimitador\\("$"): "[a-z]+ .contoso .com$".  
  
 Para obtener más información acerca de las expresiones regulares, consulte . [Expresiones regulares de .NET Framework](../../../../standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se agregan dos direcciones a la lista de omisión. El primero omite el proxy para todos los servidores del dominio contoso.com; el segundo omite el proxy para todos los servidores cuyas direcciones IP comienzan con 192.168.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Esquema de configuración de red](index.md)
