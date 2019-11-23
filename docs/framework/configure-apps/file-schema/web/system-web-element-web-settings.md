---
title: Elemento <system.web> (configuración web)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: 5c5c857d4494b6d78b819e56bae4213abc5e2035
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699093"
---
# <a name="systemweb-element-web-settings"></a>\<elemento System. Web > (configuración Web)
Contiene información sobre cómo el nivel de hospedaje de ASP.NET administra el comportamiento de todo el proceso.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp; **\<System. web >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.  
  
### <a name="attributes"></a>Atributos  

Ninguno.  
  
### <a name="child-elements"></a>Elemento secundario  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|Especifica los valores de configuración para los grupos de aplicaciones de IIS en un archivo Aspnet. config.|  
  
### <a name="parent-elements"></a>Elemento principal  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Especifica el elemento raíz de cada archivo de configuración usado por las aplicaciones Common Language Runtime y .NET Framework.|  
  
## <a name="remarks"></a>Comentarios  

El elemento `system.web` y su elemento `applicationPool` secundario se agregaron a la .NET Framework a partir de .NET Framework 3,5 SP1. Al ejecutar IIS 7,0 o versiones posteriores en el modo integrado, esta combinación de elementos le permite configurar el modo en que ASP.NET administra los subprocesos y cómo pone en cola las solicitudes cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS. Si ejecuta IIS 7,0 o versiones posteriores en el modo clásico o ISAPI, se omiten estos valores de configuración.  
  
## <a name="example"></a>Ejemplo  

En el ejemplo siguiente se muestra cómo configurar el comportamiento de todo el proceso de ASP.NET en el archivo Aspnet. config cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS. En el ejemplo se da por supuesto que IIS se ejecuta en modo integrado y que la aplicación está usando .NET Framework 3,5 SP1 o una versión posterior. Este comportamiento no se produce en las versiones de .NET Framework anteriores al .NET Framework 3,5 SP1. Los valores del ejemplo son los valores predeterminados.  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"   
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a>Información del elemento  
  
|||  
|-|-|  
|Espacio de nombres||  
|Nombre de esquema||  
|Archivo de validación||  
|Puede estar vacío||  
  
## <a name="see-also"></a>Vea también

- [Elemento \<applicationPool> (configuración web)](applicationpool-element-web-settings.md)
