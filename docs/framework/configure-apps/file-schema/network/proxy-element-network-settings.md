---
title: '&lt;proxy&gt; Element (Network Settings)'
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
ms.openlocfilehash: 8d2e224f710a1f344623440f29c2c6e0e9bd661e
ms.sourcegitcommit: 9e18e4a18284ae9e54c515e30d019c0bbff9cd37
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2018
ms.locfileid: "37072519"
---
# <a name="ltproxygt-element-network-settings"></a>&lt;proxy&gt; Element (Network Settings)
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
|`scriptLocation`|Especifica la ubicación de la secuencia de comandos de configuración.|  
|`usesystemdefault`|Especifica si se debe usar la configuración de proxy de Internet Explorer. Si establece en `true`, los atributos subsiguientes invalidarán la configuración de proxy de Internet Explorer. El valor predeterminado es `unspecified`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).|  
  
## <a name="text-value"></a>Valor de texto  
  
## <a name="remarks"></a>Comentarios  
 El `proxy` elemento define un servidor proxy para una aplicación. Si falta este elemento en el archivo de configuración, .NET Framework utilizará la configuración del proxy en Internet Explorer.  
  
 El valor de la `proxyaddress` atributo debe ser un indicador de recursos uniforme (URI) correcto.  
  
 El `scriptLocation` atributo hace referencia a la detección automática de scripts de configuración de proxy. El <xref:System.Net.WebProxy> clase intentará encontrar un script de configuración (generalmente denominado Wpad.dat) cuando la **usar scripts de configuración automática** opción está seleccionada en el Explorador de Internet.  
  
 Use la `usesystemdefault` atributo para las aplicaciones de la versión 1.1 de .NET Framework que va a migrar a la versión 2.0.  
  
 Se produce una excepción si el `proxyaddress` atributo especifica un proxy predeterminado no válido. La propiedad <xref:System.Exception.InnerException%2A> en la excepción debería tener más información acerca de la causa del error.  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo utiliza los valores predeterminados del proxy de Internet Explorer, especifica la dirección del proxy y omite al proxy para el acceso local.  
  
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
