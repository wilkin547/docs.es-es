---
title: "Elemento &lt;assert&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#assert"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<assert> (elemento)"
  - "assert (elemento)"
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Elemento &lt;assert&gt;
Especifica si aparecerá o no un cuadro de mensaje al llamar al método <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>; también especifica el nombre del archivo donde se escriben los mensajes.  
  
## Sintaxis  
  
```  
  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`assertuienabled`|Atributo opcional.<br /><br /> Especifica si se mostrará o no un cuadro de mensaje cuando el método **Debug.Assert** se evalúe como **false**.|  
|`logfilename`|Atributo opcional.<br /><br /> Especifica el nombre del archivo donde se escribirá el mensaje si **Debug.Assert** se evalúa como **false**.|  
  
## Atributo assertuienabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`true`|Muestra el cuadro de mensaje.  Éste es el valor predeterminado.|  
|`false`|No muestra el cuadro de mensaje.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, y el nivel donde se establece un modificador de seguimiento.|  
  
## Comentarios  
 Ambos atributos en el elemento de **\<assert\>** son opcionales.  Es posible deshabilitar los cuadros de mensajes sin especificar un archivo donde se escribirán los mensajes o bien especificar un archivo en el que se escribirán los mensajes mientras los cuadros de mensajes permanecen habilitados.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo deshabilitar la presentación de cuadros de mensajes al llamar a **Debug.Assert** y escribir los mensajes en `c:\log.txt`.  
  
```  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Diagnostics.Debug>   
 [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)