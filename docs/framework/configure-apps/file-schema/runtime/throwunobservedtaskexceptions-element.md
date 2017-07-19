---
title: "&lt;ThrowUnobservedTaskExceptions&gt; (elemento) | Microsoft Docs"
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
  - "<ThrowUnobservedTaskExceptions> (elemento)"
  - "ThrowUnobservedTaskExceptions (elemento)"
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# &lt;ThrowUnobservedTaskExceptions&gt; (elemento)
Especifica si las excepciones no controladas de tarea deben finalizar un proceso en ejecución.  
  
## Sintaxis  
  
```vb  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si las excepciones no controladas de tarea deben finalizar el proceso en ejecución.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|No termina el proceso en ejecución para una excepción no controlada de la tarea.  Éste es el valor predeterminado.|  
|`true`|Finaliza el proceso en ejecución para una excepción no controlada de la tarea.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
|||  
  
## Comentarios  
 Si una excepción asociada a <xref:System.Threading.Tasks.Task> no se ha aplicado, no hay ninguna operación de <xref:System.Threading.Tasks.Task.Wait%2A> , no está asociado al elemento primario, y la propiedad de <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=fullName> no era la excepción de la tarea se consideren como involuntarios.  
  
 En [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], de forma predeterminada, si <xref:System.Threading.Tasks.Task> que tiene una excepción inadvertida es la recolectan, el finalizador inicia una excepción y finaliza el proceso.  Finalización del proceso está determinada por el control de tiempo de la recolección de elementos no utilizados y finalización.  
  
 Para facilitar la para que los desarrolladores escriban código asincrónico basado en tareas, [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] cambia este comportamiento predeterminado para las excepciones inadvertidas.  Las excepciones inadvertidas además produzcan el evento de <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> que se inicia, pero de forma predeterminada, el proceso no termina.  En su lugar, la excepción se omite después de que se produzca el evento, independientemente de si un controlador de eventos sigue la excepción.  
  
 En [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], puede utilizar [\<ThrowUnobservedTaskExceptions\> elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) en un archivo de configuración de la aplicación para habilitar el comportamiento de [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] de producir una excepción.  
  
 También puede especificar el comportamiento de excepción en una de las siguientes maneras:  
  
-   Estableciendo la variable de entorno `COMPlus_ThrowUnobservedTaskExceptions` \(`set COMPlus_ThrowUnobservedTaskExceptions=1`\).  
  
-   Estableciendo el valor DWORD ThrowUnobservedTaskExceptions de registro \= 1 en la clave de HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework .  
  
## Ejemplo  
 El ejemplo siguiente se muestra cómo habilitar producir de excepciones en tareas mediante un archivo de configuración de la aplicación.  
  
```  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
  
```  
  
## Ejemplo  
 El ejemplo siguiente se muestra cómo una excepción inadvertida se produce de una tarea.  El código se debe ejecutar como programa lanza para funcionar correctamente.  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)