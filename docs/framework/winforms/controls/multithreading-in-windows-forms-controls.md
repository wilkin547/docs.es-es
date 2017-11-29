---
title: "Subprocesamiento múltiple en los controles de formularios Windows Forms"
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
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c4651ca9707dcf0fac2edea0f004275cfcf18cf2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="bb69b-102">Subprocesamiento múltiple en los controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bb69b-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="bb69b-103">En muchas aplicaciones, puede hacer que la interfaz de usuario (UI) sean más receptivos mediante la realización de operaciones que consumen muchos recursos en otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="bb69b-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="bb69b-104">Existen una serie de herramientas para multithreading los controles de formularios Windows Forms, incluido el <xref:System.Threading> espacio de nombres, el <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> método y el `BackgroundWorker` componente.</span><span class="sxs-lookup"><span data-stu-id="bb69b-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb69b-105">El `BackgroundWorker` componente reemplaza y agrega funcionalidad a la <xref:System.Threading> espacio de nombres y el <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> método; sin embargo, estos se conservan para la compatibilidad con versiones anteriores y uso futuro, si elige.</span><span class="sxs-lookup"><span data-stu-id="bb69b-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="bb69b-106">Para obtener más información, consulte [general sobre el componente BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bb69b-106">For more information, see [BackgroundWorker Component Overview](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb69b-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bb69b-107">In This Section</span></span>  
 [<span data-ttu-id="bb69b-108">Realizar llamadas seguras para subprocesos en controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bb69b-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="bb69b-109">Muestra cómo realizar llamadas seguras para subprocesos a controles de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="bb69b-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="bb69b-110">Utilizar un subproceso en segundo plano para buscar archivos</span><span class="sxs-lookup"><span data-stu-id="bb69b-110">How to: Use a Background Thread to Search for Files</span></span>](../../../../docs/framework/winforms/controls/how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="bb69b-111">Muestra cómo utilizar el <xref:System.Threading> espacio de nombres y el <xref:System.Windows.Forms.Control.BeginInvoke%2A> método para buscar archivos de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="bb69b-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="bb69b-112">Referencia</span><span class="sxs-lookup"><span data-stu-id="bb69b-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="bb69b-113">Documenta un componente que encapsula un subproceso de trabajo para las operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="bb69b-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="bb69b-114">Documenta cómo cargar un sonido de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="bb69b-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="bb69b-115">Documenta cómo cargar una imagen de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="bb69b-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bb69b-116">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="bb69b-116">Related Sections</span></span>  
 [<span data-ttu-id="bb69b-117">Ejecutar una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="bb69b-117">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="bb69b-118">Muestra cómo realizar una operación que consumen muchos recursos con el <xref:System.ComponentModel.BackgroundWorker> componente.</span><span class="sxs-lookup"><span data-stu-id="bb69b-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="bb69b-119">Información general sobre el componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="bb69b-119">BackgroundWorker Component Overview</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 <span data-ttu-id="bb69b-120">Proporciona temas que describen cómo utilizar el <xref:System.ComponentModel.BackgroundWorker> componente para las operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="bb69b-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
