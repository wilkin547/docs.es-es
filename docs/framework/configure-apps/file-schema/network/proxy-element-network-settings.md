---
title: Elemento <proxy> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 590ea747c2fa9e5e85e5e9d05f6fb80fe60251d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154795"
---
# <a name="proxy-element-network-settings"></a>\<Elemento de> proxy (Configuración de red)
Define un servidor proxy.  

[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**

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
  
|**Atributo**|**Descripción**|  
|-------------------|---------------------|  
|`autoDetect`|Especifica si el servidor proxy se detecta automáticamente. El valor predeterminado es `unspecified`.|  
|`bypassonlocal`|Especifica si el servidor proxy se omite para los recursos locales. Los recursos locales`http://localhost`incluyen `http://loopback`el `http://127.0.0.1`servidor local ( ,`http://webserver`, o ) y un URI sin un punto ( ). El valor predeterminado es `unspecified`.|  
|`proxyaddress`|Especifica el URI de proxy que se va a usar.|  
|`scriptLocation`|Especifica la ubicación del script de configuración. No utilice `bypassonlocal` el atributo con este atributo. |  
|`usesystemdefault`|Especifica si se debe utilizar la configuración de proxy de Internet Explorer. Si se `true`establece en , los atributos subsiguientes invalidarán la configuración del proxy de Internet Explorer. El valor predeterminado es `unspecified`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Elemento**|**Descripción**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).|  
  
## <a name="text-value"></a>Valor de texto  
  
## <a name="remarks"></a>Observaciones  
 El `proxy` elemento define un servidor proxy para una aplicación. Si falta este elemento en el archivo de configuración, .NET Framework usará la configuración de proxy en Internet Explorer.  
  
 El valor `proxyaddress` del atributo debe ser un indicador uniforme de recursos (URI) bien formado.  
  
 El `scriptLocation` atributo hace referencia a la detección automática de scripts de configuración de proxy. La <xref:System.Net.WebProxy> clase intentará localizar un script de configuración (normalmente denominado Wpad.dat) cuando se seleccione la opción Usar script de **configuración automática** en Internet Explorer. Si `bypassonlocal` se establece en `scriptLocation` cualquier valor, se omite.
  
 Use `usesystemdefault` el atributo para las aplicaciones de .NET Framework versión 1.1 que se migran a la versión 2.0.  
  
 Se produce una excepción si el `proxyaddress` atributo especifica un proxy predeterminado no válido. La propiedad <xref:System.Exception.InnerException%2A> en la excepción debería tener más información acerca de la causa principal del error.  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usan los valores predeterminados del proxy de Internet Explorer, se especifica la dirección proxy y se omite el proxy para el acceso local.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Esquema de configuración de red](index.md)
