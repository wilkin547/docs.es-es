---
title: Elemento <proxy> (configuración de red)
description: El <proxy> elemento de configuración de red define las opciones del servidor proxy en el .NET Framework. En este artículo se incluye un ejemplo.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 54b324dcd27d5827159bc2d773365e388a367d26
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190220"
---
# <a name="proxy-element-network-settings"></a>Elemento \<proxy> (configuración de red)

Define un servidor proxy.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<proxy
  autoDetect="True|False|Unspecified"
  bypassonlocal="True|False|Unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="True|False|Unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|**Atributo**|**Descripción**|  
|-------------------|---------------------|  
|`autoDetect`|Especifica si el servidor proxy se detecta automáticamente. El valor predeterminado es `Unspecified`.|  
|`bypassonlocal`|Especifica si el servidor proxy se omite para los recursos locales. Los recursos locales incluyen el servidor local ( `http://localhost` , `http://loopback` o `http://127.0.0.1` ) y un URI sin punto ( `http://webserver` ). El valor predeterminado es `Unspecified`.|  
|`proxyaddress`|Especifica el URI del proxy que se va a usar.|  
|`scriptLocation`|Especifica la ubicación del script de configuración. No utilice el `bypassonlocal` atributo con este atributo. |  
|`usesystemdefault`|Especifica si se va a usar la configuración de proxy de Internet Explorer. Si se establece en `True` , los atributos subsiguientes invalidarán la configuración de proxy de Internet Explorer. El valor predeterminado es `Unspecified`.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).|  
  
## <a name="text-value"></a>Valor de texto  
  
## <a name="remarks"></a>Observaciones  

 El `proxy` elemento define un servidor proxy para una aplicación. Si este elemento no se encuentra en el archivo de configuración, el .NET Framework utilizará la configuración de proxy en Internet Explorer.  
  
 El valor del `proxyaddress` atributo debe ser un indicador uniforme de recursos (URI) correcto.  
  
 El `scriptLocation` atributo hace referencia a la detección automática de scripts de configuración de proxy. La <xref:System.Net.WebProxy> clase intentará localizar un script de configuración (normalmente denominado WPAD. dat) cuando se selecciona la opción **usar script de configuración automática** en Internet Explorer. Si `bypassonlocal` se establece en cualquier valor, `scriptLocation` se omite.
  
 Use el `usesystemdefault` atributo para las aplicaciones de .NET Framework versión 1,1 que migran a la versión 2,0.  
  
 Se produce una excepción si el `proxyaddress` atributo especifica un proxy predeterminado no válido. La propiedad <xref:System.Exception.InnerException%2A> en la excepción debería tener más información acerca de la causa principal del error.  
  
## <a name="configuration-files"></a>Archivos de configuración  

 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usan los valores predeterminados del proxy de Internet Explorer, se especifica la dirección del proxy y se omite el proxy para el acceso local.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="True"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="True"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Esquema de la configuración de red](index.md)
