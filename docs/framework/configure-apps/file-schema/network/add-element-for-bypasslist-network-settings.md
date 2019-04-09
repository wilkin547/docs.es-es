---
title: <add> Elemento para bypasslist (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
ms.openlocfilehash: 904c8e23f7a09a975a6f3b9322ed6bc4148d9ba4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098291"
---
# <a name="add-element-for-bypasslist-network-settings"></a>\<Agregar > elemento para bypasslist (configuración de red)
Agrega una dirección IP o nombre DNS a la lista de omisión de proxy.  
  
 \<configuration>  
\<system.net>  
\<defaultProxy>  
\<bypasslist>  
\<add>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|**Atributo**|**Descripción**|  
|-------------------|---------------------|  
|**dirección**|Una expresión regular que describe una dirección IP o nombre DNS.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Elemento**|**Descripción**|  
|-----------------|---------------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Proporciona un conjunto de expresiones regulares que describen direcciones que no se usa a un proxy.|  
  
## <a name="remarks"></a>Comentarios  
 El `add` elemento inserta expresiones regulares que describen direcciones IP o nombres de los servidores DNS a la lista de direcciones que omitir un servidor proxy.  
  
 El valor de la `address` atributo debe ser una expresión regular que describe un conjunto de direcciones IP o nombres de host.  
  
 Se debe tener cuidado al especificar una expresión regular para este elemento. La expresión regular "[a-z] +\\.contoso\\.com" coincide con cualquier host en el dominio contoso.com, pero también coincide con cualquier host del dominio contoso.com.cpandl.com. Para que coincida con un host en el dominio contoso.com, use un delimitador ("$"): "[a-z] +\\.contoso\\.com$".  
  
 Para obtener más información sobre las expresiones regulares, vea. [Expresiones regulares de .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente agrega dos direcciones a la lista de omisión. La primera omite al proxy para todos los servidores en el dominio contoso.com; la segunda omite al proxy para todos los servidores cuya dirección IP comienza con 192.168.  
  
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
