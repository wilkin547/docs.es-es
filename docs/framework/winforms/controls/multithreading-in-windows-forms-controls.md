---
title: Subprocesamiento múltiple en los controles de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cc7f358a62c8057abb77e1f5a28544bb6c858d98
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012729"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="9c943-102">Subprocesamiento múltiple en los controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9c943-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="9c943-103">En muchas aplicaciones, puede hacer que la interfaz de usuario (UI) con más capacidad de respuesta mediante la realización de operaciones que requieren mucho tiempo en otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="9c943-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="9c943-104">Existen varias herramientas para multithreading los controles de Windows Forms, incluido el <xref:System.Threading> espacio de nombres, el <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> método y el `BackgroundWorker` componente.</span><span class="sxs-lookup"><span data-stu-id="9c943-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c943-105">El `BackgroundWorker` componente reemplaza y agrega funcionalidad a la <xref:System.Threading> espacio de nombres y el <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> método; sin embargo, estos se conservan para compatibilidad con versiones anteriores y uso futuro, si elige.</span><span class="sxs-lookup"><span data-stu-id="9c943-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="9c943-106">Para obtener más información, consulte [general sobre el componente BackgroundWorker](backgroundworker-component-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9c943-106">For more information, see [BackgroundWorker Component Overview](backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9c943-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9c943-107">In This Section</span></span>  
 [<span data-ttu-id="9c943-108">Cómo: Realizar llamadas seguras para subprocesos a controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9c943-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="9c943-109">Muestra cómo realizar llamadas seguras para subprocesos a controles de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9c943-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="9c943-110">Cómo: Usar un subproceso en segundo plano para buscar archivos</span><span class="sxs-lookup"><span data-stu-id="9c943-110">How to: Use a Background Thread to Search for Files</span></span>](how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="9c943-111">Se muestra cómo usar el <xref:System.Threading> espacio de nombres y el <xref:System.Windows.Forms.Control.BeginInvoke%2A> método para buscar archivos de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="9c943-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9c943-112">Referencia</span><span class="sxs-lookup"><span data-stu-id="9c943-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="9c943-113">Documenta un componente que encapsula un subproceso de trabajo para las operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="9c943-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="9c943-114">Describe cómo cargar un sonido de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="9c943-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="9c943-115">Describe cómo cargar una imagen de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="9c943-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9c943-116">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="9c943-116">Related Sections</span></span>  
 [<span data-ttu-id="9c943-117">Cómo: Ejecutar una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="9c943-117">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="9c943-118">Muestra cómo realizar una operación lenta con el <xref:System.ComponentModel.BackgroundWorker> componente.</span><span class="sxs-lookup"><span data-stu-id="9c943-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="9c943-119">Información general sobre el componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="9c943-119">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="9c943-120">Proporciona temas que describen cómo usar el <xref:System.ComponentModel.BackgroundWorker> componente para las operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="9c943-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
