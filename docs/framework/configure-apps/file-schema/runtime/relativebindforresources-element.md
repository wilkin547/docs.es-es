---
title: <relativeBindForResources> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c98914f57c24dc51625564e266157731ff173337
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704575"
---
# <a name="relativebindforresources-element"></a>\<relativeBindForResources > elemento
Optimiza el sondeo de ensamblados satélite.  
  
 \<Configuración > elemento  
\<en tiempo de ejecución > elemento  
\<relativeBindForResources > elemento  
  
## <a name="syntax"></a>Sintaxis  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si common language runtime optimiza el sondeo de ensamblados satélite.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|El tiempo de ejecución no optimiza el sondeo de los ensamblados satélite. Este es el valor predeterminado.|  
|`true`|El tiempo de ejecución optimiza el sondeo de ensamblados satélite.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 En general, Resource Manager sondea los recursos, como se documenta en el [empaquetar e implementar recursos](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) tema. Esto significa que cuando los sondeos de administrador de recursos para una determinada versión localizada de un recurso, puede buscar en la caché global de ensamblados, busque los ensamblados satélite en una carpeta específica de la referencia cultural en la consulta de base, de código de la aplicación Windows Installer y generar el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> eventos. El `<relativeBindForResources>` elemento optimiza la manera en que Resource Manager sondea los ensamblados satélite. Puede mejorar el rendimiento cuando el sondeo para los recursos en las siguientes condiciones:  
  
- Cuando se implementa el ensamblado satélite en la misma ubicación que el ensamblado de código. En otras palabras, si el ensamblado de código está instalado en la caché global de ensamblados, los ensamblados satélite también deben instalarse allí. Si el ensamblado de código está instalado en la base de código de la aplicación, los ensamblados satélite también deben instalarse en una carpeta específica de la referencia cultural de la base de código.  
  
- Cuando Windows Installer no se usa o se usa solo en raras ocasiones para la instalación y a petición de ensamblados satélite.  
  
- Cuando el código de aplicación no controla el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> eventos.  
  
 Establecer el `enabled` atributo de la `<relativeBindForResources>` elemento `true` optimiza el sondeo del Administrador de recursos de los ensamblados satélite como sigue:  
  
- La ubicación del ensamblado de código principal usa para sondear el ensamblado satélite.  
  
- No consulta a Windows Installer para los ensamblados satélite.  
  
- No provoca la <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> eventos.  
  
## <a name="see-also"></a>Vea también

- [Empaquetar e implementar recursos](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
