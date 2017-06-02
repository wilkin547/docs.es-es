---
title: "How to: Prevent a Child Task from Attaching to its Parent | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "tasks, preventing attachments"
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# How to: Prevent a Child Task from Attaching to its Parent
En este documento se muestra cómo evitar que una tarea secundaria adjunta a la tarea primaria.  Evitar que una tarea secundaria adjunta a su elemento primario es útil cuando se llama a un componente escrito por terceros y que también utilice tareas.  Por ejemplo, un componente de terceros que utiliza la opción de <xref:System.Threading.Tasks.TaskCreationOptions?displayProperty=fullName> de crear un objeto de <xref:System.Threading.Tasks.Task> o de <xref:System.Threading.Tasks.Task%601> puede producir problemas en el código si es de ejecución prolongada o produce una excepción no controlada.  
  
## Ejemplo  
 El ejemplo siguiente se comparan los efectos de utilizar opciones predeterminadas a los efectos de evitar que una tarea secundaria adjunta al elemento primario.  El ejemplo crea un objeto de <xref:System.Threading.Tasks.Task> que llama a una biblioteca de terceros que también utilice un objeto de <xref:System.Threading.Tasks.Task> .  La biblioteca de otro fabricante utiliza la opción de <xref:System.Threading.Tasks.TaskCreationOptions> de crear el objeto de <xref:System.Threading.Tasks.Task> .  La aplicación utiliza la opción de <xref:System.Threading.Tasks.TaskCreationOptions?displayProperty=fullName> de crear la tarea primaria.  Esta opción indica al tiempo de ejecución para quitar la especificación de <xref:System.Threading.Tasks.TaskCreationOptions> en tareas secundarias.  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 Dado que una tarea primaria no finaliza hasta que todo el final secundario de tareas, una tarea secundaria de ejecución prolongada puede provocar la aplicación total para ejecutarse mal.  En este ejemplo, cuando la aplicación utiliza las opciones predeterminadas de crear la tarea primaria, la tarea secundaria debe finalizar antes de que la tarea primaria finaliza.  Cuando la aplicación utiliza la opción de <xref:System.Threading.Tasks.TaskCreationOptions?displayProperty=fullName> , no está asociado al elemento secundario al elemento primario.  Por consiguiente, la aplicación puede realizar el trabajo adicional después de que la tarea primaria finaliza y antes de que debe esperar la tarea secundaria finalice.  
  
## Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio, o péguelo en un archivo denominado `DenyChildAttach.cs` \(`DenyChildAttach.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), y ejecutar el siguiente comando en una ventana de símbolo del sistema de Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe DenyChildAttach.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe DenyChildAttach.vb**  
  
## Programación eficaz  
  
## Vea también  
 [Task Parallelism](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)