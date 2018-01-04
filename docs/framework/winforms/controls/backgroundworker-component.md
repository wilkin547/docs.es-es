---
title: BackgroundWorker (Componente)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: bef7b0ab-ce57-475a-a2d6-fb8a702a9417
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6d83ff69053a71626d0bf9a844d9e94235080d78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="backgroundworker-component"></a><span data-ttu-id="05184-102">BackgroundWorker (Componente)</span><span class="sxs-lookup"><span data-stu-id="05184-102">BackgroundWorker Component</span></span>
<span data-ttu-id="05184-103">El `BackgroundWorker` componente permite que el formulario o control para ejecutar una operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="05184-103">The `BackgroundWorker` component enables your form or control to run an operation asynchronously.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="05184-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="05184-104">In This Section</span></span>  
 [<span data-ttu-id="05184-105">Información general sobre el componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="05184-105">BackgroundWorker Component Overview</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 <span data-ttu-id="05184-106">Describe el `BackgroundWorker` componente, que le ofrece la capacidad de ejecutar operaciones prolongadas de forma asincrónica ("en segundo plano"), en un subproceso distinto del subproceso de interfaz de usuario principal de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="05184-106">Describes the `BackgroundWorker` component, which gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span>  
  
 [<span data-ttu-id="05184-107">Tutorial: Ejecutar una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="05184-107">Walkthrough: Running an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 <span data-ttu-id="05184-108">Muestra cómo utilizar el `BackgroundWorker` componente en el diseñador para ejecutar una operación consume mucho tiempo en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="05184-108">Demonstrates how to use the `BackgroundWorker` component in the designer to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="05184-109">Ejecutar una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="05184-109">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="05184-110">Muestra cómo utilizar el `BackgroundWorker` componente para ejecutar una operación consume mucho tiempo en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="05184-110">Demonstrates how to use the `BackgroundWorker` component to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="05184-111">Tutorial: Implementar un formulario que utiliza una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="05184-111">Walkthrough: Implementing a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="05184-112">Crea una aplicación mediante el diseñador que realiza cálculos matemáticos de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="05184-112">Creates an application using the designer that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="05184-113">Cómo: Implementar un formulario que utiliza una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="05184-113">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="05184-114">Crea una aplicación que realiza cálculos matemáticos de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="05184-114">Creates an application that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="05184-115">Descargar un archivo en segundo plano</span><span class="sxs-lookup"><span data-stu-id="05184-115">How to: Download a File in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-download-a-file-in-the-background.md)  
 <span data-ttu-id="05184-116">Muestra cómo utilizar el `BackgroundWorker` componente para descargar un archivo en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="05184-116">Demonstrates how to use the `BackgroundWorker` component to download a file on a separate thread.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="05184-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="05184-117">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="05184-118">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="05184-118">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 <span data-ttu-id="05184-119">Describe el tipo que contiene datos para el <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> eventos.</span><span class="sxs-lookup"><span data-stu-id="05184-119">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span>  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 <span data-ttu-id="05184-120">Describe el tipo que contiene datos para el <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> eventos.</span><span class="sxs-lookup"><span data-stu-id="05184-120">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="05184-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="05184-121">Related Sections</span></span>  
 [<span data-ttu-id="05184-122">Información general sobre el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="05184-122">Event-based Asynchronous Pattern Overview</span></span>](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="05184-123">Describe cómo el modelo asincrónico pone disponibles las ventajas de las aplicaciones multithreading ocultando muchos de los problemas complejos inherentes al diseño multiproceso.</span><span class="sxs-lookup"><span data-stu-id="05184-123">Describes how the asynchronous pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>
