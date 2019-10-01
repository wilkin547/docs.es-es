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
ms.openlocfilehash: 94858f141e7d540454fca9c151c760c37f9ebbb0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697943"
---
# <a name="proxy-element-network-settings"></a>\<proxy (elemento >) (configuración de red)
Define un servidor proxy.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **@no__t -4System. net >** ](system-net-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<proxy >**  
  
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
|`bypassonlocal`|Especifica si el proxy se omite para los recursos locales. Los recursos locales incluyen el servidor local (`http://localhost`, `http://loopback` o `http://127.0.0.1`) y un URI sin punto (`http://webserver`). El valor predeterminado es `unspecified`.|  
|`proxyaddress`|Especifica el URI del proxy que se va a usar.|  
|`scriptLocation`|Especifica la ubicación del script de configuración. No utilice el atributo `bypassonlocal` con este atributo. |  
|`usesystemdefault`|Especifica si se va a usar la configuración de proxy de Internet Explorer. Si se establece en `true`, los atributos subsiguientes invalidarán la configuración de proxy de Internet Explorer. El valor predeterminado es `unspecified`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).|  
  
## <a name="text-value"></a>Valor de texto  
  
## <a name="remarks"></a>Comentarios  
 El elemento `proxy` define un servidor proxy para una aplicación. Si este elemento no se encuentra en el archivo de configuración, el .NET Framework utilizará la configuración de proxy en Internet Explorer.  
  
 El valor del atributo `proxyaddress` debe ser un indicador uniforme de recursos (URI) correcto.  
  
 El atributo `scriptLocation` hace referencia a la detección automática de scripts de configuración de proxy. La clase <xref:System.Net.WebProxy> intentará localizar un script de configuración (normalmente denominado WPAD. dat) cuando se selecciona la opción **usar script de configuración automática** en Internet Explorer. Si `bypassonlocal` se establece en cualquier valor, se omite `scriptLocation`.
  
 Use el atributo `usesystemdefault` para las aplicaciones de .NET Framework versión 1,1 que migran a la versión 2,0.  
  
 Se produce una excepción si el atributo `proxyaddress` especifica un proxy predeterminado no válido. La propiedad <xref:System.Exception.InnerException%2A> en la excepción debería tener más información acerca de la causa principal del error.  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usan los valores predeterminados del proxy de Internet Explorer, se especifica la dirección del proxy y se omite el proxy para el acceso local.  
  
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

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Esquema de la configuración de red](index.md)
