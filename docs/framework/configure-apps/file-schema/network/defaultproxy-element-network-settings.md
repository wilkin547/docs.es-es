---
title: Elemento <defaultProxy> (configuración de red)
description: El <defaultProxy> elemento de configuración de red configura el servidor proxy del Protocolo de transferencia de hipertexto (http) en el .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
ms.openlocfilehash: 85004d49ce7605b050709a3019592ec696a7bada
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141636"
---
# <a name="defaultproxy-element-network-settings"></a>Elemento \<defaultProxy> (configuración de red)
Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultProxy>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<defaultProxy  
  enabled="True|False"  
  useDefaultCredentials="True|False">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|`enabled`|Especifica si se usa un proxy web. El valor predeterminado es `True`.|  
|`useDefaultCredentials`|Especifica si se usan las credenciales predeterminadas de este host para tener acceso al proxy web. El valor predeterminado es `False`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[bypasslist](bypasslist-element-network-settings.md)|Proporciona un conjunto de expresiones regulares que describen direcciones que no usan el proxy.|  
|[destina](module-element-network-settings.md)|Agrega un nuevo módulo proxy a la aplicación.|  
|[proxi](proxy-element-network-settings.md)|Define un servidor proxy.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[system.net](system-net-element-network-settings.md)|Contiene valores que especifican cómo se conecta .NET Framework a la red.|  
  
## <a name="remarks"></a>Comentarios  
 Si el elemento defaultProxy está vacío, se usará la configuración de proxy de Internet Explorer. Este comportamiento es diferente de la versión 1.1 de .NET Framework.  
  
 Se produce una excepción si el elemento [Module](module-element-network-settings.md) especifica un tipo no público, el tipo no se deriva de la <xref:System.Net.IWebProxy> clase, se produjo una excepción del constructor sin parámetros de este objeto o se produjo una excepción al recuperar el proxy predeterminado especificado por el sistema. La propiedad <xref:System.Exception.InnerException%2A> en la excepción debería tener más información acerca de la causa principal del error.  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usan los valores predeterminados del proxy de Internet Explorer, se especifica la dirección del proxy y se omite el proxy para el acceso local y contoso.com.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="True"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="True"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también:

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Esquema de la configuración de red](index.md)
