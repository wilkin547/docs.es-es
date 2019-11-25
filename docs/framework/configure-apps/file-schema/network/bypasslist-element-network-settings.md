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
ms.openlocfilehash: 7a6c1282c9ca8381d2dbb21ffdc82f95732c42b3
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087523"
---
# <a name="bypasslist-element-network-settings"></a>\<BypassList > elemento (configuración de red)
Proporciona un conjunto de expresiones regulares que describen las direcciones que no utilizan un proxy.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<bypasslist >**

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
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[add](add-element-for-bypasslist-network-settings.md)|Agrega una dirección IP o un nombre DNS a la lista de omisión de proxy.|  
|[clear](clear-element-for-bypasslist-network-settings.md)|Borra la lista de omisiones.|  
|[remove](remove-element-for-bypasslist-network-settings.md)|Quita una dirección IP o un nombre DNS de la lista de omisión de proxy.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).|  
  
## <a name="remarks"></a>Comentarios  
 La lista de omisión contiene expresiones regulares que describen los URI que <xref:System.Net.WebRequest> instancias acceden directamente en lugar de a través del servidor proxy.  
  
 Debe tener precaución al especificar una expresión regular para este elemento. La expresión regular "[a-z] +\\. contoso\\. com" coincide con cualquier host del dominio contoso.com, pero también coincide con cualquier host del dominio contoso.com.cpandl.com. Para que solo coincida con un host del dominio contoso.com, use un delimitador ("$"): "[a-z] +\\. contoso\\. com $".  
  
 Para obtener más información acerca de las expresiones regulares, vea. [.NET Framework expresiones regulares](../../../../standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se agregan dos direcciones a la lista de omisiones. El primero omite el proxy para todos los servidores del dominio contoso.com; la segunda omite el proxy para todos los servidores cuyas direcciones IP comienzan con 192,168.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Esquema de la configuración de red](index.md)
