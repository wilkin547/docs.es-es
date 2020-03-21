---
title: Elemento <add> para webRequestModules (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
ms.openlocfilehash: f4edce948033478aab59a2aff61abadc55a327ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155029"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a>\<Agregar> Elemento para webRequestModules (Configuración de red)
Agrega un módulo de solicitud web personalizado a la aplicación.  

[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<añadir>**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<add
  prefix="URI prefix"
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|**Atributo**|**Descripción**|  
|-------------------|---------------------|  
|`prefix`|El prefijo URI para las solicitudes controladas por este módulo de solicitud web.|  
|`type`|El nombre de tipo completo <xref:System.Type.FullName%2A> (indicado por la propiedad) y <xref:System.Reflection.Assembly.FullName%2A> el nombre del ensamblado (indicado por la propiedad), separados por una coma, que implementa este módulo de solicitud web.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Elemento**|**Descripción**|  
|-----------------|---------------------|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|Especifica los módulos que se utilizarán para solicitar información de los hosts de red.|  
  
## <a name="remarks"></a>Observaciones  
 El `prefix` atributo define el prefijo URI que utiliza el módulo de solicitud web especificado. Los módulos de solicitud web se registran normalmente para controlar un protocolo específico, como HTTP o FTP, pero se pueden registrar para controlar una solicitud a un servidor o ruta de acceso específico en un servidor.  
  
 El módulo de solicitud web se crea cuando <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> se pasa un prefijo de coincidencia de URI al método.  
  
 El valor `prefix` del atributo debe ser los caracteres principales de un URI válido. Por ejemplo, `http` o `http://www.contoso.com`.
  
 El valor `type` del atributo debe ser un nombre de tipo válido y el nombre de ensamblado correspondiente, separados por una coma.
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se registra un módulo de solicitud web personalizado para HTTP. Debe reemplazar los valores de Version y PublicKeyToken por los valores correctos para el módulo especificado.  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Net.WebRequest>
- [Esquema de configuración de red](index.md)
