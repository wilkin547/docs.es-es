---
title: "Cómo: Evitar que una tarea secundaria se adjunte a su elemento primario"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, preventing attachments
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4717e3a077648d9db51fe39228209617b384bd0c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-prevent-a-child-task-from-attaching-to-its-parent"></a>Cómo: Evitar que una tarea secundaria se adjunte a su elemento primario
Este documento muestra cómo evitar que una tarea secundaria se adjunte a la tarea primaria. Impedir que una tarea secundaria se adjunte a su elemento primario es útil cuando se llama a un componente que está escrito por un tercero y que también usa las tareas. Por ejemplo, un componente de terceros que utiliza el <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> opción para crear un <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> objeto puede causar problemas en el código si es de larga duración o produce una excepción no controlada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se comparan los efectos del uso de las opciones predeterminadas a los efectos de impedir que una tarea secundaria se adjunte al elemento primario. El ejemplo se crea un <xref:System.Threading.Tasks.Task> objeto que llama a una biblioteca de terceros que también se usa un <xref:System.Threading.Tasks.Task> objeto. La biblioteca de otro fabricante utiliza la <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> opción para crear el <xref:System.Threading.Tasks.Task> objeto. La aplicación utiliza el <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> opción para crear la tarea primaria. Esta opción indica el tiempo de ejecución para quitar el <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> especificación de las tareas secundarias.  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 Dado que una tarea primaria no finaliza hasta que finalicen todas las tareas secundarias, una tarea secundaria de ejecución prolongada puede hacer la aplicación global mediocre. En este ejemplo, cuando la aplicación usa las opciones predeterminadas para crear la tarea primaria, la tarea secundaria debe finalizar antes de que finalice la tarea primaria. Cuando la aplicación utiliza el <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> opción, el elemento secundario no está asociado al elemento primario. Por lo tanto, la aplicación puede realizar un trabajo adicional después de que finalice la tarea primaria y antes de que debe esperar a que finalice la tarea secundaria.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o en un archivo denominado `DenyChildAttach.cs` (`DenyChildAttach.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) y, a continuación, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe DenyChildAttach.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe DenyChildAttach.vb**  
  
## <a name="robust-programming"></a>Programación sólida  
  
## <a name="see-also"></a>Vea también  
 [Programación asincrónica basada en tareas](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
