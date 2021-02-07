---
description: 'Más información acerca de: <relativeBindForResources> elemento'
title: <relativeBindForResources> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: f08d8f8a8fc4bb14d28762254dca99788d44a858
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712927"
---
# <a name="relativebindforresources-element"></a>\<relativeBindForResources> (Elemento)

Optimiza el sondeo de ensamblados satélite.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
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
|`enabled`|Atributo necesario.<br /><br /> Especifica si el Common Language Runtime optimiza el sondeo para los ensamblados satélite.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|`false`|El motor en tiempo de ejecución no optimiza el sondeo de ensamblados satélite. Este es el valor predeterminado.|  
|`true`|El motor en tiempo de ejecución optimiza el sondeo de los ensamblados satélite.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Observaciones  

 En general, Administrador de recursos sondea los recursos, tal como se documenta en el tema [empaquetar e implementar recursos](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) . Esto significa que, cuando Administrador de recursos sondea una versión localizada determinada de un recurso, puede buscar en la caché global de ensamblados, buscar una carpeta específica de la referencia cultural en la base de código de la aplicación, Windows Installer de consulta para los ensamblados satélite y generar el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> evento. El `<relativeBindForResources>` elemento optimiza la manera en que administrador de recursos sondea para los ensamblados satélite. Puede mejorar el rendimiento al buscar recursos en las siguientes condiciones:  
  
- Cuando el ensamblado satélite se implementa en la misma ubicación que el ensamblado de código. En otras palabras, si el ensamblado de código está instalado en la caché global de ensamblados, los ensamblados satélite también se deben instalar allí. Si el ensamblado de código está instalado en la base de código de la aplicación, los ensamblados satélite también se deben instalar en una carpeta específica de la referencia cultural en el código base.  
  
- Cuando Windows Installer no se usa o solo se usa con poca frecuencia para la instalación a petición de ensamblados satélite.  
  
- Cuando el código de aplicación no controla el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> evento.  
  
 Establecer el `enabled` atributo del `<relativeBindForResources>` elemento para `true` optimizar el sondeo de administrador de recursos para los ensamblados satélite de la manera siguiente:  
  
- Utiliza la ubicación del ensamblado de código primario para sondear el ensamblado satélite.  
  
- No consulta Windows Installer para los ensamblados satélite.  
  
- No genera el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> evento.  
  
## <a name="see-also"></a>Vea también

- [Empaquetar e implementar recursos](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
