---
title: '&lt;proxy&gt; elemento (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5fba4bfa14642092dbb7c0153bcd92160a62b12b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43451576"
---
# <a name="ltproxygt-element-network-settings"></a>&lt;proxy&gt; elemento (configuración de red)
Define un servidor proxy.  
  
 \<configuration>  
\<System.NET >  
\<defaultProxy >  
\<proxy >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|**Attribute**|**Descripción**|  
|-------------------|---------------------|  
|`autoDetect`|Especifica si el proxy se detecta automáticamente. El valor predeterminado es `unspecified`.|  
|`bypassonlocal`|Especifica si se omite el proxy para los recursos locales. Los recursos locales incluyen el servidor local (`http://localhost`, `http://loopback`, o `http://127.0.0.1`) y un URI sin un punto (`http://webserver`). El valor predeterminado es `unspecified`.|  
|`proxyaddress`|Especifica al proxy de URI que se utiliza.|  
|`scriptLocation`|Especifica la ubicación del script de configuración. No utilice el `bypassonlocal` atributo con este atributo. |  
|`usesystemdefault`|Especifica si se debe usar la configuración de proxy de Internet Explorer. Si establece en `true`, atributos subsiguientes invalidarán la configuración de proxy de Internet Explorer. El valor predeterminado es `unspecified`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).|  
  
## <a name="text-value"></a>Valor de texto  
  
## <a name="remarks"></a>Comentarios  
 El `proxy` elemento define un servidor proxy para una aplicación. Si este elemento no aparece en el archivo de configuración, .NET Framework usará la configuración de proxy en Internet Explorer.  
  
 El valor de la `proxyaddress` atributo debe ser un indicador de recursos uniforme (URI) tiene el formato correcto.  
  
 El `scriptLocation` atributo hace referencia a la detección automática de scripts de configuración de proxy. El <xref:System.Net.WebProxy> clase intentará encontrar un script de configuración (normalmente con nombre Wpad.dat) cuando el **usar scripts de configuración automática** está seleccionada en el Explorador de Internet. Si `bypassonlocal` se establece en cualquier valor, `scriptLocation` se omite.
  
 Use el `usesystemdefault` atributo para las aplicaciones de la versión 1.1 de .NET Framework que se va a migrar a la versión 2.0.  
  
 Se produce una excepción si el `proxyaddress` atributo especifica un proxy predeterminado no válido. La propiedad <xref:System.Exception.InnerException%2A> en la excepción debería tener más información acerca de la causa del error.  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente utiliza los valores predeterminados desde el proxy de Internet Explorer, especifica la dirección del proxy y omite al proxy para el acceso local.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
