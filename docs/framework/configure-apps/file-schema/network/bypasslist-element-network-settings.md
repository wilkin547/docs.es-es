---
title: <bypasslist> (Elemento, Configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: db975d44db96f605767d7320737ff3c162bbc8a5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55282963"
---
# <a name="bypasslist-element-network-settings"></a>\<bypasslist > elemento (configuración de red)
Proporciona un conjunto de expresiones regulares que describen direcciones que no se usa a un proxy.  
  
 \<configuration>  
\<system.net>  
\<defaultProxy>  
\<bypasslist>  
  
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
|[add](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|Agrega una dirección IP o nombre DNS a la lista de omisión de proxy.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|Borra la lista de omisión.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|Quita una dirección IP o nombre DNS de la lista de omisión de proxy.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).|  
  
## <a name="remarks"></a>Comentarios  
 La lista de omisión contiene expresiones regulares que describen las direcciones URI que <xref:System.Net.WebRequest> instancias directamente en lugar de tener acceso a través del servidor proxy.  
  
 Se debe tener cuidado al especificar una expresión regular para este elemento. La expresión regular "[a-z] +\\.contoso\\.com" coincide con cualquier host en el dominio contoso.com, pero también coincide con cualquier host del dominio contoso.com.cpandl.com. Para que coincida con un host en el dominio contoso.com, use un delimitador ("$"): "[a-z] +\\.contoso\\.com$".  
  
 Para obtener más información sobre las expresiones regulares, vea. [Expresiones regulares de .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente agrega dos direcciones a la lista de omisión. La primera omite al proxy para todos los servidores en el dominio contoso.com; la segunda omite al proxy para todos los servidores cuyas direcciones IP comienzan con 192.168.  
  
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
- [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
