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
# <a name="how-to-prevent-a-child-task-from-attaching-to-its-parent"></a><span data-ttu-id="d5039-102">Cómo: Evitar que una tarea secundaria se adjunte a su elemento primario</span><span class="sxs-lookup"><span data-stu-id="d5039-102">How to: Prevent a Child Task from Attaching to its Parent</span></span>
<span data-ttu-id="d5039-103">Este documento muestra cómo evitar que una tarea secundaria se adjunte a la tarea primaria.</span><span class="sxs-lookup"><span data-stu-id="d5039-103">This document demonstrates how to prevent a child task from attaching to the parent task.</span></span> <span data-ttu-id="d5039-104">Impedir que una tarea secundaria se adjunte a su elemento primario es útil cuando se llama a un componente que está escrito por un tercero y que también usa las tareas.</span><span class="sxs-lookup"><span data-stu-id="d5039-104">Preventing a child task from attaching to its parent is useful when you call a component that is written by a third party and that also uses tasks.</span></span> <span data-ttu-id="d5039-105">Por ejemplo, un componente de terceros que utiliza el <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> opción para crear un <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> objeto puede causar problemas en el código si es de larga duración o produce una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="d5039-105">For example, a third-party component that uses the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> option to create a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> object can cause problems in your code if it is long-running or throws an unhandled exception.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5039-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5039-106">Example</span></span>  
 <span data-ttu-id="d5039-107">En el ejemplo siguiente se comparan los efectos del uso de las opciones predeterminadas a los efectos de impedir que una tarea secundaria se adjunte al elemento primario.</span><span class="sxs-lookup"><span data-stu-id="d5039-107">The following example compares the effects of using the default options to the effects of preventing a child task from attaching to the parent.</span></span> <span data-ttu-id="d5039-108">El ejemplo se crea un <xref:System.Threading.Tasks.Task> objeto que llama a una biblioteca de terceros que también se usa un <xref:System.Threading.Tasks.Task> objeto.</span><span class="sxs-lookup"><span data-stu-id="d5039-108">The example creates a <xref:System.Threading.Tasks.Task> object that calls into a third-party library that also uses a <xref:System.Threading.Tasks.Task> object.</span></span> <span data-ttu-id="d5039-109">La biblioteca de otro fabricante utiliza la <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> opción para crear el <xref:System.Threading.Tasks.Task> objeto.</span><span class="sxs-lookup"><span data-stu-id="d5039-109">The third-party library uses the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> option to create the <xref:System.Threading.Tasks.Task> object.</span></span> <span data-ttu-id="d5039-110">La aplicación utiliza el <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> opción para crear la tarea primaria.</span><span class="sxs-lookup"><span data-stu-id="d5039-110">The application uses the <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> option to create the parent task.</span></span> <span data-ttu-id="d5039-111">Esta opción indica el tiempo de ejecución para quitar el <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> especificación de las tareas secundarias.</span><span class="sxs-lookup"><span data-stu-id="d5039-111">This option instructs the runtime to remove the <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> specification in child tasks.</span></span>  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 <span data-ttu-id="d5039-112">Dado que una tarea primaria no finaliza hasta que finalicen todas las tareas secundarias, una tarea secundaria de ejecución prolongada puede hacer la aplicación global mediocre.</span><span class="sxs-lookup"><span data-stu-id="d5039-112">Because a parent task does not finish until all child tasks finish, a long-running child task can cause the overall application to perform poorly.</span></span> <span data-ttu-id="d5039-113">En este ejemplo, cuando la aplicación usa las opciones predeterminadas para crear la tarea primaria, la tarea secundaria debe finalizar antes de que finalice la tarea primaria.</span><span class="sxs-lookup"><span data-stu-id="d5039-113">In this example, when the application uses the default options to create the parent task, the child task must finish before the parent task finishes.</span></span> <span data-ttu-id="d5039-114">Cuando la aplicación utiliza el <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> opción, el elemento secundario no está asociado al elemento primario.</span><span class="sxs-lookup"><span data-stu-id="d5039-114">When the application uses the <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> option, the child is not attached to the parent.</span></span> <span data-ttu-id="d5039-115">Por lo tanto, la aplicación puede realizar un trabajo adicional después de que finalice la tarea primaria y antes de que debe esperar a que finalice la tarea secundaria.</span><span class="sxs-lookup"><span data-stu-id="d5039-115">Therefore, the application can perform additional work after the parent task finishes and before it must wait for the child task to finish.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d5039-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d5039-116">Compiling the Code</span></span>  
 <span data-ttu-id="d5039-117">Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o en un archivo denominado `DenyChildAttach.cs` (`DenyChildAttach.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) y, a continuación, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d5039-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DenyChildAttach.cs` (`DenyChildAttach.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="d5039-118">**csc.exe DenyChildAttach.cs**</span><span class="sxs-lookup"><span data-stu-id="d5039-118">**csc.exe DenyChildAttach.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="d5039-119">**vbc.exe DenyChildAttach.vb**</span><span class="sxs-lookup"><span data-stu-id="d5039-119">**vbc.exe DenyChildAttach.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d5039-120">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="d5039-120">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5039-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5039-121">See Also</span></span>  
 [<span data-ttu-id="d5039-122">Programación asincrónica basada en tareas</span><span class="sxs-lookup"><span data-stu-id="d5039-122">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
