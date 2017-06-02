---
title: "Elemento &lt;switches&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#switches"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<switches> (elemento)"
  - "switches (elemento)"
  - "modificadores de seguimiento, <switches> (elemento)"
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Elemento &lt;switches&gt;
Contiene modificadores de seguimiento y el nivel donde éstos se establecen.  
  
## Sintaxis  
  
```  
  
      <switches>   
</switches>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<agregar\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|Especifica el nivel donde se establece un modificador de seguimiento.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`System.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, y el nivel donde se establece un modificador de seguimiento.|  
  
## Comentarios  
 Puede cambiar el nivel de un modificador de seguimiento si lo pone en un archivo de configuración.  Si el modificador es un <xref:System.Diagnostics.BooleanSwitch>, es posible activarlo y desactivarlo.  Si el modificador es un <xref:System.Diagnostics.TraceSwitch>, es posible asignarle distintos niveles para especificar los tipos de mensajes de seguimiento o de depuración que genera la aplicación.  
  
## Ejemplo  
 El ejemplo siguiente se muestra cómo utilizar el elemento de **\<modificador\>** para establecer el modificador de traza de `General` al nivel de [TraceLevel.Error](frlrfSystemDiagnosticsTraceLevelClassTopic) , y habilitar el modificador TRACE booleano de `Data` .  
  
```  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Diagnostics.Switch>   
 <xref:System.Diagnostics.TraceSwitch>   
 <xref:System.Diagnostics.BooleanSwitch>   
 [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)