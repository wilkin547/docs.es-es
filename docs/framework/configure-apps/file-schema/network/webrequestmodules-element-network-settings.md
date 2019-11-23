---
title: Elemento <webRequestModules> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: e119d9ce1f8bb6f07f8050612550db459a2f065c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697459"
---
# <a name="webrequestmodules-element-network-settings"></a>\<el elemento > webRequestModules (configuración de red)
Especifica los módulos que se van a usar para solicitar información de los hosts de red.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elemento secundario  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[add](add-element-for-webrequestmodules-network-settings.md)|Agrega un módulo de solicitud web personalizado a la aplicación.|  
|[clear](clear-element-for-webrequestmodules-network-settings.md)|Quita todos los módulos de solicitud Web registrados de la aplicación.|  
|[remove](remove-element-for-webrequestmodules-network-settings.md)|Quita un módulo de solicitud web personalizado de la aplicación.|  
  
### <a name="parent-elements"></a>Elemento principal  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[system.net](system-net-element-network-settings.md)|Contiene valores que especifican cómo se conecta .NET Framework a la red.|  
  
## <a name="remarks"></a>Comentarios  
 El elemento `webRequestModules` registra los descendientes de la clase <xref:System.Net.WebRequest> para controlar las solicitudes de información a los hosts de red. Los módulos de solicitud Web deben implementar la interfaz <xref:System.Net.IWebRequestCreate>.  
  
 El .NET Framework incluye módulos de solicitud Web para los URI que comienzan con `http://`, `https://`y `file://`. Solo puede invalidar los módulos predeterminados Si registra un módulo personalizado en el archivo de configuración.  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se registra el módulo HTTP predeterminado. Debe reemplazar los valores de version y PublicKeyToken por los valores correctos para el módulo especificado.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [Esquema de la configuración de red](index.md)
