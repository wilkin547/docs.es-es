---
title: 'Cómo: Evitar que una tarea secundaria se adjunte a su elemento primario'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, preventing attachments
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
ms.openlocfilehash: 5ff181344e6437179fa77f11872ae9a47745be93
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288165"
---
# <a name="how-to-prevent-a-child-task-from-attaching-to-its-parent"></a>Cómo: Evitar que una tarea secundaria se adjunte a su elemento primario
En este documento se explica cómo evitar que una tarea secundaria se adjunte a la tarea principal. Impedir que una tarea secundaria se adjunte a su elemento principal es útil cuando se llama a un componente que está escrito por un tercero y que también usa las tareas. Por ejemplo, un componente de terceros que utiliza la opción <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> para crear un objeto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> puede causar problemas en el código si es de larga duración o produce una excepción no controlada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se comparan los efectos del uso de las opciones predeterminadas con los efectos de impedir que una tarea secundaria se adjunte al elemento principal. En el ejemplo se crea un objeto <xref:System.Threading.Tasks.Task> que llama a una biblioteca de terceros que también usa un objeto <xref:System.Threading.Tasks.Task>. La biblioteca de otro fabricante utiliza la opción <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> para crear el objeto <xref:System.Threading.Tasks.Task>. La aplicación utiliza la opción <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> para crear la tarea principal. Esta opción indica el tiempo de ejecución para quitar la especificación <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> de las tareas secundarias.  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 Dado que una tarea primaria no finaliza hasta que finalizan todas las tareas secundarias, una tarea secundaria que se ejecute durante mucho tiempo puede provocar que el rendimiento general de la aplicación sea bajo. En este ejemplo, cuando la aplicación usa las opciones predeterminadas para crear la tarea principal, la tarea secundaria debe finalizar antes de que finalice la principal. Cuando la aplicación utiliza la opción <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType>, el elemento secundario no está asociado al principal. Por lo tanto, la aplicación puede realizar un trabajo adicional después de que finalice la tarea principal y antes debe esperar a que finalice la tarea secundaria.  
  
## <a name="see-also"></a>Vea también

- [Programación asincrónica basada en tareas](task-based-asynchronous-programming.md)
