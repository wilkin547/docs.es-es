---
title: Subprocesamiento múltiple en los controles de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cf6790172b7445ad154eead5d17f8efddd78ffee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952678"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="20502-102">Subprocesamiento múltiple en los controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="20502-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="20502-103">En muchas aplicaciones, puede hacer que la interfaz de usuario (UI) tenga mayor capacidad de respuesta al realizar operaciones que consumen mucho tiempo en otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="20502-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="20502-104">Hay varias herramientas disponibles para el multithreading de los controles Windows Forms, incluido el <xref:System.Threading> espacio de nombres <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> , el método y `BackgroundWorker` el componente.</span><span class="sxs-lookup"><span data-stu-id="20502-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="20502-105">El `BackgroundWorker` componente reemplaza y agrega funcionalidad <xref:System.Threading> al espacio de nombres y <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> al método; sin embargo, se conservan por compatibilidad con versiones anteriores y uso futuro, si así lo decide.</span><span class="sxs-lookup"><span data-stu-id="20502-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="20502-106">Para obtener más información, vea [información general sobre el componente BackgroundWorker](backgroundworker-component-overview.md).</span><span class="sxs-lookup"><span data-stu-id="20502-106">For more information, see [BackgroundWorker Component Overview](backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20502-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="20502-107">In This Section</span></span>  
 [<span data-ttu-id="20502-108">Cómo: Realizar llamadas seguras para subprocesos a controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="20502-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="20502-109">Muestra cómo realizar llamadas seguras para subprocesos a controles Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="20502-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="20502-110">Cómo: Usar un subproceso en segundo plano para buscar archivos</span><span class="sxs-lookup"><span data-stu-id="20502-110">How to: Use a Background Thread to Search for Files</span></span>](how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="20502-111">Muestra cómo usar el <xref:System.Threading> espacio de nombres y el <xref:System.Windows.Forms.Control.BeginInvoke%2A> método para buscar archivos de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="20502-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="20502-112">Referencia</span><span class="sxs-lookup"><span data-stu-id="20502-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="20502-113">Documenta un componente que encapsula un subproceso de trabajo para las operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="20502-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="20502-114">Documenta cómo cargar un sonido de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="20502-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="20502-115">Documenta cómo cargar una imagen de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="20502-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="20502-116">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="20502-116">Related Sections</span></span>  
 [<span data-ttu-id="20502-117">Cómo: Ejecutar una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="20502-117">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="20502-118">Muestra cómo realizar una operación que consume mucho tiempo con el <xref:System.ComponentModel.BackgroundWorker> componente.</span><span class="sxs-lookup"><span data-stu-id="20502-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="20502-119">Información general sobre el componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="20502-119">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="20502-120">Proporciona temas que describen cómo usar el <xref:System.ComponentModel.BackgroundWorker> componente para las operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="20502-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
