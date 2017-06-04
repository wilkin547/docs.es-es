---
title: "&lt;etwEnable&gt; (Elemento) | Microsoft Docs"
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
  - "<etwEnable> (elemento)"
  - "etwEnable (elemento)"
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;etwEnable&gt; (Elemento)
Especifica si permitir el seguimiento de eventos para Windows \(ETW\) para los eventos de Common Language Runtime.  
  
## Sintaxis  
  
```  
<etwEnable enabled="true|false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si ETW debería estar habilitado.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|true|Enable ETW.  Este es el valor predeterminado de las versiones de Windows a partir de los sistemas operativos Windows Vista y Windows Server 2008.|  
|false|Deshabilitar ETW.  Este es el valor predeterminado de las versiones anteriores de Windows.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 Comenzando con Windows Vista, ETW está habilitado de forma predeterminada.  Use este elemento para deshabilitar ETW para una aplicación.  En versiones anteriores de Windows, use este elemento para habilitar ETW para una aplicación.  
  
> [!NOTE]
>  ETW puede estar habilitado o deshabilitado globalmente en un servidor usando un valor del Registro.  Vea [Controlling .NET Framework Logging](../../../../../docs/framework/performance/controlling-logging.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo habilitar la traza de ETW para una aplicación.  
  
```  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Controlling .NET Framework Logging](../../../../../docs/framework/performance/controlling-logging.md)