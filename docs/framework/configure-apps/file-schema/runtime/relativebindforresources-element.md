---
title: <relativeBindForResources> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: cd49d424019a4e8422fee0ae16217d49cfc456b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153911"
---
# <a name="relativebindforresources-element"></a>\<relativeBindForResources> Element
Optimiza el sondeo de ensamblados satélite.  
  
[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**  
  
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
|`enabled`|Atributo necesario.<br /><br /> Especifica si Common Language Runtime optimiza el sondeo para los ensamblados satélite.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|`false`|El tiempo de ejecución no optimiza el sondeo para los ensamblados satélite. Este es el valor predeterminado.|  
|`true`|El tiempo de ejecución optimiza el sondeo para los ensamblados satélite.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Observaciones  
 En general, Resource Manager busca recursos, como se documenta en el tema [Empaquetado e implementación de recursos.](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) Esto significa que cuando Resource Manager sondea una versión localizada determinada de un recurso, puede buscar en la caché global de ensamblados, buscar <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> en una carpeta específica de la referencia cultural en la base de código de la aplicación, consultar windows Installer para ensamblados satélite y generar el evento. El `<relativeBindForResources>` elemento optimiza la forma en que Resource Manager sondea los ensamblados satélite. Puede mejorar el rendimiento al sondear recursos en las siguientes condiciones:  
  
- Cuando el ensamblado satélite se implementa en la misma ubicación que el ensamblado de código. En otras palabras, si el ensamblado de código está instalado en la caché global de ensamblados, los ensamblados satélite también deben instalarse allí. Si el ensamblado de código está instalado en la base de código de la aplicación, los ensamblados satélite también deben instalarse en una carpeta específica de la referencia cultural en la base de código.  
  
- Cuando Windows Installer no se utiliza o solo se usa raramente para la instalación a petición de ensamblados satélite.  
  
- Cuando el código de <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> la aplicación no controla el evento.  
  
 Establecer `enabled` el atributo `<relativeBindForResources>` del `true` elemento para optimizar el sondeo de Resource Manager para ensamblados satélite de la siguiente manera:  
  
- Utiliza la ubicación del ensamblado de código primario para sondear el ensamblado satélite.  
  
- No consulta windows Installer para ensamblados satélite.  
  
- No genera el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> evento.  
  
## <a name="see-also"></a>Consulte también

- [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema del archivo de configuración](../index.md)
