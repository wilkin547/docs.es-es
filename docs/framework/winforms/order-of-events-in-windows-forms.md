---
title: Orden de eventos en los formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], order of
- focus event order
- application shutdown event order
- sequence [Windows Forms], of events
- validation events [Windows Forms], order of
- application startup event order
ms.assetid: e81db09b-4453-437f-b78a-62d7cd5c9829
ms.openlocfilehash: a88fd7b912063af5961a2bb366b42b0f67411f5f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720299"
---
# <a name="order-of-events-in-windows-forms"></a><span data-ttu-id="64249-102">Orden de eventos en los formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="64249-102">Order of Events in Windows Forms</span></span>
<span data-ttu-id="64249-103">El orden en que se producen los eventos en las aplicaciones de Windows Forms es de particular interés para los programadores a los que les preocupa controlar cada uno de estos eventos uno por uno.</span><span class="sxs-lookup"><span data-stu-id="64249-103">The order in which events are raised in Windows Forms applications is of particular interest to developers concerned with handling each of these events in turn.</span></span> <span data-ttu-id="64249-104">Cuando una situación requiere un control minucioso de los eventos, por ejemplo, cuando se vuelven a dibujar partes del formulario, es necesario conocer el orden exacto en que los eventos se producen en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="64249-104">When a situation calls for meticulous handling of events, such as when you are redrawing parts of the form, an awareness of the precise order in which events are raised at run time is necessary.</span></span> <span data-ttu-id="64249-105">En este tema se proporcionan algunos detalles sobre el orden de los eventos en varias fases importantes de la duración de las aplicaciones y los controles.</span><span class="sxs-lookup"><span data-stu-id="64249-105">This topic provides some details on the order of events during several important stages in the lifetime of applications and controls.</span></span> <span data-ttu-id="64249-106">Para obtener detalles concretos sobre el orden de los eventos de entrada del mouse, consulte [eventos del Mouse en Windows Forms](mouse-events-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="64249-106">For specific details about the order of mouse input events, see [Mouse Events in Windows Forms](mouse-events-in-windows-forms.md).</span></span> <span data-ttu-id="64249-107">Para obtener información general de eventos en Windows Forms, consulte [información general sobre eventos](events-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="64249-107">For an overview of events in Windows Forms, see [Events Overview](events-overview-windows-forms.md).</span></span> <span data-ttu-id="64249-108">Para obtener más información acerca de la creación de controladores de eventos, consulte [información general sobre controladores de eventos](event-handlers-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="64249-108">For details about the makeup of event handlers, see [Event Handlers Overview](event-handlers-overview-windows-forms.md).</span></span>  
  
## <a name="application-startup-and-shutdown-events"></a><span data-ttu-id="64249-109">Eventos de inicio y cierre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="64249-109">Application Startup and Shutdown Events</span></span>  
 <span data-ttu-id="64249-110">Las clases <xref:System.Windows.Forms.Form> y <xref:System.Windows.Forms.Control> exponen un conjunto de eventos relacionados con el inicio y el cierre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="64249-110">The <xref:System.Windows.Forms.Form> and <xref:System.Windows.Forms.Control> classes expose a set of events related to application startup and shutdown.</span></span> <span data-ttu-id="64249-111">Cuando se inicia una aplicación de Windows Forms, se generan los eventos de inicio del formulario principal en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="64249-111">When a Windows Forms application starts, the startup events of the main form are raised in the following order:</span></span>  
  
-   <xref:System.Windows.Forms.Control.HandleCreated?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Control.BindingContextChanged?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Control.VisibleChanged?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Activated?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Shown?displayProperty=nameWithType>  
  
 <span data-ttu-id="64249-112">Cuando se cierra una aplicación, se generan los eventos de cierre del formulario principal en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="64249-112">When an application closes, the shutdown events of the main form are raised in the following order:</span></span>  
  
-   <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Closed?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.FormClosed?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Deactivate?displayProperty=nameWithType>  
  
 <span data-ttu-id="64249-113">El evento <xref:System.Windows.Forms.Application.ApplicationExit> de la clase <xref:System.Windows.Forms.Application> se genera después de los eventos de cierre del formulario principal.</span><span class="sxs-lookup"><span data-stu-id="64249-113">The <xref:System.Windows.Forms.Application.ApplicationExit> event of the <xref:System.Windows.Forms.Application> class is raised after the shutdown events of the main form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64249-114">Visual Basic 2005 incluye eventos de aplicación adicionales, como <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup?displayProperty=nameWithType> y <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="64249-114">Visual Basic 2005 includes additional application events, such as <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup?displayProperty=nameWithType> and <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown?displayProperty=nameWithType>.</span></span>  
  
## <a name="focus-and-validation-events"></a><span data-ttu-id="64249-115">Eventos de foco y validación</span><span class="sxs-lookup"><span data-stu-id="64249-115">Focus and Validation Events</span></span>  
 <span data-ttu-id="64249-116">Al cambiar el foco mediante el teclado (TAB, MAYÚS+TAB, etc.) mediante una llamada a los métodos <xref:System.Windows.Forms.Control.Select%2A> o <xref:System.Windows.Forms.Control.SelectNextControl%2A>, o estableciendo la propiedad <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> en el formulario actual, los eventos de foco de la clase <xref:System.Windows.Forms.Control> se generan en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="64249-116">When you change the focus by using the keyboard (TAB, SHIFT+TAB, and so on), by calling the <xref:System.Windows.Forms.Control.Select%2A> or <xref:System.Windows.Forms.Control.SelectNextControl%2A> methods, or by setting the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property to the current form, focus events of the <xref:System.Windows.Forms.Control> class occur in the following order:</span></span>  
  
-   <xref:System.Windows.Forms.Control.Enter>  
  
-   <xref:System.Windows.Forms.Control.GotFocus>  
  
-   <xref:System.Windows.Forms.Control.Leave>  
  
-   <xref:System.Windows.Forms.Control.Validating>  
  
-   <xref:System.Windows.Forms.Control.Validated>  
  
-   <xref:System.Windows.Forms.Control.LostFocus>  
  
 <span data-ttu-id="64249-117">Al cambiar el foco mediante el mouse o mediante una llamada al método <xref:System.Windows.Forms.Control.Focus%2A>, los eventos de foco de la clase <xref:System.Windows.Forms.Control> se generan en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="64249-117">When you change the focus by using the mouse or by calling the <xref:System.Windows.Forms.Control.Focus%2A> method, focus events of the <xref:System.Windows.Forms.Control> class occur in the following order:</span></span>  
  
-   <xref:System.Windows.Forms.Control.Enter>  
  
-   <xref:System.Windows.Forms.Control.GotFocus>  
  
-   <xref:System.Windows.Forms.Control.LostFocus>  
  
-   <xref:System.Windows.Forms.Control.Leave>  
  
-   <xref:System.Windows.Forms.Control.Validating>  
  
-   <xref:System.Windows.Forms.Control.Validated>  
  
## <a name="see-also"></a><span data-ttu-id="64249-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="64249-118">See also</span></span>
- [<span data-ttu-id="64249-119">Crear controladores de eventos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="64249-119">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
