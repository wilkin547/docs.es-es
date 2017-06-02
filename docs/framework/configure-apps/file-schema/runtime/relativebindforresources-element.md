---
title: "Elemento &lt;relativeBindForResources&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<relativeBindForResources> (elemento)"
  - "RelativeBindForResources (elemento)"
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Elemento &lt;relativeBindForResources&gt;
Optimiza el buscar ensamblados satélite.  
  
## Sintaxis  
  
```vb  
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si Common Language Runtime optimiza el buscar ensamblados satélite.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|El runtime no optimiza el buscar ensamblados satélite.  Este es el valor predeterminado.|  
|`true`|El tiempo de ejecución optimiza el buscar ensamblados satélite.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## Comentarios  
 Normalmente comprobaciones del administrador de recursos para los recursos, como se documenta en el tema de [Empaquetar e implementar recursos](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) .  Esto significa que cuando el motor del administrador de recursos para una versión localizada determinada de un recurso, puede buscar en la caché global de ensamblados, buscar en una carpeta cultura\- concreta en la base de código de aplicación, ver Windows Installer para los ensamblados satélite, y generar el evento de <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> .  El elemento de `<relativeBindForResources>` optimiza la manera en que los métodos del administrador de recursos para los ensamblados satélite.  Puede mejorar el rendimiento al buscar para los recursos en las condiciones siguientes:  
  
-   Cuando se implementan en el ensamblado satélite en la misma ubicación que el ensamblado del código.  Es decir si el ensamblado de código está instalado en la caché global de ensamblados, los ensamblados satélite también deben instalarse allí.  Si el ensamblado del código se instala en la base de código de aplicación, ensamblados satélite también deben instalarse en una carpeta cultura\- concreta en la base de código.  
  
-   Cuando Windows Installer no se utiliza o se utiliza sólo raramente para instalación a petición de ensamblados satélite.  
  
-   Cuando el código de aplicación no controla el evento de <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> .  
  
 Estableciendo el atributo de `enabled` de elemento de `<relativeBindForResources>` a `true` optimiza el sondeo del administrador de recursos para los ensamblados satélite como sigue:  
  
-   Utiliza la ubicación del ensamblado de código principal debe buscar el ensamblado satélite.  
  
-   No consulta Windows Installer para los ensamblados satélite.  
  
-   No provoca el evento de <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> .  
  
## Vea también  
 [Empaquetar e implementar recursos](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)   
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)