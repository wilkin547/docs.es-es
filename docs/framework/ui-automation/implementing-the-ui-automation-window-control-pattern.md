---
title: Implementar el patrón de control Window de UI Automation
description: Revise las directrices y convenciones para implementar el patrón de control window en la automatización de la interfaz de usuario. Conocer los miembros necesarios para la interfaz IWindowProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Window
- UI Automation, Window control pattern
- Window control pattern
ms.assetid: a28cb286-296e-4a62-b4cb-55ad636ebccc
ms.openlocfilehash: b43884393974e6f2863da6a4a5ca8f305e5a160c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286102"
---
# <a name="implementing-the-ui-automation-window-control-pattern"></a><span data-ttu-id="7a928-104">Implementar el patrón de control Window de UI Automation</span><span class="sxs-lookup"><span data-stu-id="7a928-104">Implementing the UI Automation Window Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="7a928-105">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="7a928-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="7a928-106">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="7a928-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="7a928-107">En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IWindowProvider>, incluida la información sobre las propiedades, los métodos y los eventos de <xref:System.Windows.Automation.WindowPattern> .</span><span class="sxs-lookup"><span data-stu-id="7a928-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IWindowProvider>, including information about <xref:System.Windows.Automation.WindowPattern> properties, methods, and events.</span></span> <span data-ttu-id="7a928-108">Al final del tema se ofrecen vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="7a928-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="7a928-109">El <xref:System.Windows.Automation.WindowPattern> patrón de control se usa para admitir controles que proporcionan la funcionalidad fundamental basada en ventanas dentro de una interfaz gráfica de usuario (GUI) tradicional.</span><span class="sxs-lookup"><span data-stu-id="7a928-109">The <xref:System.Windows.Automation.WindowPattern> control pattern is used to support controls that provide fundamental window-based functionality within a traditional graphical user interface (GUI).</span></span> <span data-ttu-id="7a928-110">Entre los ejemplos de controles que deben implementar este patrón de control se incluyen las ventanas de aplicación de nivel superior, las ventanas secundarias de interfaz de múltiples documentos (MDI), los controles de panel de división de tamaño ajustable, los cuadros de diálogo modales y las ventanas de ayuda de globo.</span><span class="sxs-lookup"><span data-stu-id="7a928-110">Examples of controls that must implement this control pattern include top-level application windows, multiple-document interface (MDI) child windows, resizable split pane controls, modal dialogs and balloon help windows.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="7a928-111">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="7a928-111">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="7a928-112">Al implementar el patrón de control Window, tenga en cuenta las siguientes directrices y convenciones:</span><span class="sxs-lookup"><span data-stu-id="7a928-112">When implementing the Window control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="7a928-113">Para admitir la capacidad de modificar el tamaño de la ventana y la posición de la pantalla mediante Automatización de la interfaz de usuario, un control debe implementar <xref:System.Windows.Automation.Provider.ITransformProvider> además de <xref:System.Windows.Automation.Provider.IWindowProvider>.</span><span class="sxs-lookup"><span data-stu-id="7a928-113">To support the ability to modify both window size and screen position using UI Automation, a control must implement <xref:System.Windows.Automation.Provider.ITransformProvider> in addition to <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
- <span data-ttu-id="7a928-114">Los controles que contienen barras de título y elementos de barra de título que permiten que el control se mueva, cambie de tamaño, se maximice, minimice o se cierre son normalmente necesarios para implementar <xref:System.Windows.Automation.Provider.IWindowProvider>.</span><span class="sxs-lookup"><span data-stu-id="7a928-114">Controls that contain title bars and title bar elements that enable the control to be moved, resized, maximized, minimized, or closed are typically required to implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
- <span data-ttu-id="7a928-115">Los controles como los elementos emergentes de información sobre herramientas y las listas desplegables de menús o cuadros combinados normalmente no implementan <xref:System.Windows.Automation.Provider.IWindowProvider>.</span><span class="sxs-lookup"><span data-stu-id="7a928-115">Controls such as tooltip pop-ups and combo box or menu drop-downs do not typically implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
- <span data-ttu-id="7a928-116">Las ventanas de globo de ayuda se diferencian de los elementos emergentes de información sobre herramientas básicos en el aprovisionamiento de un botón de cierre de tipo ventana.</span><span class="sxs-lookup"><span data-stu-id="7a928-116">Balloon help windows are differentiated from basic tooltip pop-ups by the provision of a window-like Close button.</span></span>  
  
- <span data-ttu-id="7a928-117">El modo de pantalla completa no es compatible con IWindowProvider, ya que es una característica específica de una aplicación y no es el comportamiento de ventana típico.</span><span class="sxs-lookup"><span data-stu-id="7a928-117">Full-screen mode is not supported by IWindowProvider as it is feature-specific to an application and is not typical window behavior.</span></span>  
  
<a name="Required_Members_for_IWindowProvider"></a>

## <a name="required-members-for-iwindowprovider"></a><span data-ttu-id="7a928-118">Miembros necesarios para IWindowProvider</span><span class="sxs-lookup"><span data-stu-id="7a928-118">Required Members for IWindowProvider</span></span>  

 <span data-ttu-id="7a928-119">Para la interfaz de IWindowProvider, se requieren los siguientes métodos, eventos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="7a928-119">The following properties, methods, and events are required for the IWindowProvider interface.</span></span>  
  
|<span data-ttu-id="7a928-120">Miembro requerido</span><span class="sxs-lookup"><span data-stu-id="7a928-120">Required member</span></span>|<span data-ttu-id="7a928-121">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="7a928-121">Member type</span></span>|<span data-ttu-id="7a928-122">Notas</span><span class="sxs-lookup"><span data-stu-id="7a928-122">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.InteractionState%2A>|<span data-ttu-id="7a928-123">Propiedad</span><span class="sxs-lookup"><span data-stu-id="7a928-123">Property</span></span>|<span data-ttu-id="7a928-124">None</span><span class="sxs-lookup"><span data-stu-id="7a928-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsModal%2A>|<span data-ttu-id="7a928-125">Propiedad</span><span class="sxs-lookup"><span data-stu-id="7a928-125">Property</span></span>|<span data-ttu-id="7a928-126">None</span><span class="sxs-lookup"><span data-stu-id="7a928-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsTopmost%2A>|<span data-ttu-id="7a928-127">Propiedad</span><span class="sxs-lookup"><span data-stu-id="7a928-127">Property</span></span>|<span data-ttu-id="7a928-128">None</span><span class="sxs-lookup"><span data-stu-id="7a928-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Maximizable%2A>|<span data-ttu-id="7a928-129">Propiedad</span><span class="sxs-lookup"><span data-stu-id="7a928-129">Property</span></span>|<span data-ttu-id="7a928-130">None</span><span class="sxs-lookup"><span data-stu-id="7a928-130">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Minimizable%2A>|<span data-ttu-id="7a928-131">Propiedad</span><span class="sxs-lookup"><span data-stu-id="7a928-131">Property</span></span>|<span data-ttu-id="7a928-132">None</span><span class="sxs-lookup"><span data-stu-id="7a928-132">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.VisualState%2A>|<span data-ttu-id="7a928-133">Propiedad</span><span class="sxs-lookup"><span data-stu-id="7a928-133">Property</span></span>|<span data-ttu-id="7a928-134">None</span><span class="sxs-lookup"><span data-stu-id="7a928-134">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Close%2A>|<span data-ttu-id="7a928-135">Método</span><span class="sxs-lookup"><span data-stu-id="7a928-135">Method</span></span>|<span data-ttu-id="7a928-136">None</span><span class="sxs-lookup"><span data-stu-id="7a928-136">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A>|<span data-ttu-id="7a928-137">Método</span><span class="sxs-lookup"><span data-stu-id="7a928-137">Method</span></span>|<span data-ttu-id="7a928-138">None</span><span class="sxs-lookup"><span data-stu-id="7a928-138">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A>|<span data-ttu-id="7a928-139">Método</span><span class="sxs-lookup"><span data-stu-id="7a928-139">Method</span></span>|<span data-ttu-id="7a928-140">None</span><span class="sxs-lookup"><span data-stu-id="7a928-140">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|<span data-ttu-id="7a928-141">Evento</span><span class="sxs-lookup"><span data-stu-id="7a928-141">Event</span></span>|<span data-ttu-id="7a928-142">None</span><span class="sxs-lookup"><span data-stu-id="7a928-142">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|<span data-ttu-id="7a928-143">Evento</span><span class="sxs-lookup"><span data-stu-id="7a928-143">Event</span></span>|<span data-ttu-id="7a928-144">None</span><span class="sxs-lookup"><span data-stu-id="7a928-144">None</span></span>|  
|<xref:System.Windows.Automation.WindowInteractionState>|<span data-ttu-id="7a928-145">Evento</span><span class="sxs-lookup"><span data-stu-id="7a928-145">Event</span></span>|<span data-ttu-id="7a928-146">No se garantiza que sea <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span><span class="sxs-lookup"><span data-stu-id="7a928-146">Is not guaranteed to be <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span></span>|  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="7a928-147">Excepciones</span><span class="sxs-lookup"><span data-stu-id="7a928-147">Exceptions</span></span>  

 <span data-ttu-id="7a928-148">Los proveedores deben producir las siguientes excepciones.</span><span class="sxs-lookup"><span data-stu-id="7a928-148">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="7a928-149">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="7a928-149">Exception type</span></span>|<span data-ttu-id="7a928-150">Condición</span><span class="sxs-lookup"><span data-stu-id="7a928-150">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A><br /><br /> <span data-ttu-id="7a928-151">: Cuando un control no admite un comportamiento solicitado.</span><span class="sxs-lookup"><span data-stu-id="7a928-151">-   When a control does not support a requested behavior.</span></span>|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A><br /><br /> <span data-ttu-id="7a928-152">: Cuando el parámetro no es un número válido.</span><span class="sxs-lookup"><span data-stu-id="7a928-152">-   When the parameter is not a valid number.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a928-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a928-153">See also</span></span>

- [<span data-ttu-id="7a928-154">Información general acerca de los patrones de control de UI Automation</span><span class="sxs-lookup"><span data-stu-id="7a928-154">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="7a928-155">Patrones de control compatibles en un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="7a928-155">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="7a928-156">Patrones de controles de UI Automation para clientes</span><span class="sxs-lookup"><span data-stu-id="7a928-156">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="7a928-157">Información general sobre el árbol de la UI Automation</span><span class="sxs-lookup"><span data-stu-id="7a928-157">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="7a928-158">Utilizar el almacenamiento en caché en la UI Automation</span><span class="sxs-lookup"><span data-stu-id="7a928-158">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
