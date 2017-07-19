---
title: "&lt;UseSmallInternalThreadStacks&gt; (Elemento) | Microsoft Docs"
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
  - "<UseSmallInternalThreadStacks> (elemento)"
  - "UseSmallInternalThreadStacks (elemento)"
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# &lt;UseSmallInternalThreadStacks&gt; (Elemento)
Solicita que Common Language Runtime \(CLR\) reduzca el uso de memoria especificando tamaños de pila explícitos cuando crea ciertos subprocesos que utiliza internamente, en lugar de utilizar el tamaño de pila predeterminado para esos subprocesos.  
  
## Sintaxis  
  
```  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si se solicita que CLR use tamaños de pila explícitos en lugar del tamaño de pila predeterminado cuando crea ciertos subprocesos que utiliza internamente.  Los tamaños de pila explícitos son menores que el tamaño de pila predeterminado de 1 MB.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|true|Solicitar tamaños de pila explícitos.|  
|false|Use el tamaño de pila predeterminado.  Este es el valor predeterminado de [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 Este elemento de configuración se utiliza para solicitar un menor uso de la memoria virtual en un proceso, porque los tamaños de subproceso explícitos que usa CLR para sus subprocesos internos, si se admite la solicitud, son menores que el tamaño predeterminado.  
  
> [!IMPORTANT]
>  Este elemento de configuración es una solicitud a CLR en lugar de un requisito absoluto.  En [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], la solicitud solo se admite para la arquitectura x86.  Este elemento se podría omitir completamente en versiones futuras de CLR o reemplazar por tamaños de pila explícitos que se utilicen siempre para los subprocesos internos seleccionados.  
  
 Al especificar este elemento de configuración, se reduce la confiabilidad pero también el uso de la memoria virtual si el CLR admite la solicitud, porque un tamaño de pila menor podría provocar desbordamientos de pila con mayor probabilidad.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo solicitar que CLR use tamaños de pila explícitos para ciertos subprocesos que utiliza internamente.  
  
```  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)