---
title: "Implementar el patrón de control Window de UI Automation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, Window
- UI Automation, Window control pattern
- Window control pattern
ms.assetid: a28cb286-296e-4a62-b4cb-55ad636ebccc
caps.latest.revision: "21"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 3f1b44184f1a241943d9fa9d60a62a703dbaf0d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-the-ui-automation-window-control-pattern"></a><span data-ttu-id="3d082-102">Implementar el patrón de control Window de UI Automation</span><span class="sxs-lookup"><span data-stu-id="3d082-102">Implementing the UI Automation Window Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="3d082-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="3d082-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="3d082-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="3d082-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="3d082-105">En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IWindowProvider>, incluida la información sobre las propiedades, los métodos y los eventos de <xref:System.Windows.Automation.WindowPattern> .</span><span class="sxs-lookup"><span data-stu-id="3d082-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IWindowProvider>, including information about <xref:System.Windows.Automation.WindowPattern> properties, methods, and events.</span></span> <span data-ttu-id="3d082-106">Al final del tema se ofrecen vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="3d082-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="3d082-107">El patrón de control <xref:System.Windows.Automation.WindowPattern> se utiliza para admitir controles que ofrecen funcionalidad fundamental basada dentro de una [!INCLUDE[TLA#tla_gui](../../../includes/tlasharptla-gui-md.md)]tradicional.</span><span class="sxs-lookup"><span data-stu-id="3d082-107">The <xref:System.Windows.Automation.WindowPattern> control pattern is used to support controls that provide fundamental window-based functionality within a traditional [!INCLUDE[TLA#tla_gui](../../../includes/tlasharptla-gui-md.md)].</span></span> <span data-ttu-id="3d082-108">Entre los ejemplos de controles que deben implementar este patrón de control se incluyen las ventanas de la aplicación de nivel superior, las ventanas secundarias de [!INCLUDE[TLA#tla_mdi](../../../includes/tlasharptla-mdi-md.md)] , los controles de panel de división que se pueden cambiar de tamaño, los cuadros de diálogo modales y las ventanas de globo de ayuda.</span><span class="sxs-lookup"><span data-stu-id="3d082-108">Examples of controls that must implement this control pattern include top-level application windows, [!INCLUDE[TLA#tla_mdi](../../../includes/tlasharptla-mdi-md.md)] child windows, resizable split pane controls, modal dialogs and balloon help windows.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="3d082-109">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="3d082-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="3d082-110">Al implementar el patrón de control Window, tenga en cuenta las siguientes directrices y convenciones:</span><span class="sxs-lookup"><span data-stu-id="3d082-110">When implementing the Window control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="3d082-111">Para admitir la capacidad de modificar el tamaño de la ventana y la posición de la pantalla mediante Automatización de la interfaz de usuario, un control debe implementar <xref:System.Windows.Automation.Provider.ITransformProvider> además de <xref:System.Windows.Automation.Provider.IWindowProvider>.</span><span class="sxs-lookup"><span data-stu-id="3d082-111">To support the ability to modify both window size and screen position using UI Automation, a control must implement <xref:System.Windows.Automation.Provider.ITransformProvider> in addition to <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
-   <span data-ttu-id="3d082-112">Los controles que contienen barras de título y elementos de barra de título que permiten que el control se mueva, cambie de tamaño, se maximice, minimice o se cierre son normalmente necesarios para implementar <xref:System.Windows.Automation.Provider.IWindowProvider>.</span><span class="sxs-lookup"><span data-stu-id="3d082-112">Controls that contain title bars and title bar elements that enable the control to be moved, resized, maximized, minimized, or closed are typically required to implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
-   <span data-ttu-id="3d082-113">Los controles como los elementos emergentes de información sobre herramientas y las listas desplegables de menús o cuadros combinados normalmente no implementan <xref:System.Windows.Automation.Provider.IWindowProvider>.</span><span class="sxs-lookup"><span data-stu-id="3d082-113">Controls such as tooltip pop-ups and combo box or menu drop-downs do not typically implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
-   <span data-ttu-id="3d082-114">Las ventanas de globo de ayuda se diferencian de los elementos emergentes de información sobre herramientas básicos en el aprovisionamiento de un botón de cierre de tipo ventana.</span><span class="sxs-lookup"><span data-stu-id="3d082-114">Balloon help windows are differentiated from basic tooltip pop-ups by the provision of a window-like Close button.</span></span>  
  
-   <span data-ttu-id="3d082-115">El modo de pantalla completa no es compatible con IWindowProvider, ya que es una característica específica de una aplicación y no es el comportamiento de ventana típico.</span><span class="sxs-lookup"><span data-stu-id="3d082-115">Full-screen mode is not supported by IWindowProvider as it is feature-specific to an application and is not typical window behavior.</span></span>  
  
<a name="Required_Members_for_IWindowProvider"></a>   
## <a name="required-members-for-iwindowprovider"></a><span data-ttu-id="3d082-116">Miembros necesarios para IWindowProvider</span><span class="sxs-lookup"><span data-stu-id="3d082-116">Required Members for IWindowProvider</span></span>  
 <span data-ttu-id="3d082-117">Para la interfaz de IWindowProvider, se requieren los siguientes métodos, eventos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="3d082-117">The following properties, methods, and events are required for the IWindowProvider interface.</span></span>  
  
|<span data-ttu-id="3d082-118">Miembro requerido</span><span class="sxs-lookup"><span data-stu-id="3d082-118">Required member</span></span>|<span data-ttu-id="3d082-119">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="3d082-119">Member type</span></span>|<span data-ttu-id="3d082-120">Notas</span><span class="sxs-lookup"><span data-stu-id="3d082-120">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.InteractionState%2A>|<span data-ttu-id="3d082-121">Property</span><span class="sxs-lookup"><span data-stu-id="3d082-121">Property</span></span>|<span data-ttu-id="3d082-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="3d082-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsModal%2A>|<span data-ttu-id="3d082-123">Property</span><span class="sxs-lookup"><span data-stu-id="3d082-123">Property</span></span>|<span data-ttu-id="3d082-124">Ninguna</span><span class="sxs-lookup"><span data-stu-id="3d082-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsTopmost%2A>|<span data-ttu-id="3d082-125">Property</span><span class="sxs-lookup"><span data-stu-id="3d082-125">Property</span></span>|<span data-ttu-id="3d082-126">Ninguna</span><span class="sxs-lookup"><span data-stu-id="3d082-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Maximizable%2A>|<span data-ttu-id="3d082-127">Property</span><span class="sxs-lookup"><span data-stu-id="3d082-127">Property</span></span>|<span data-ttu-id="3d082-128">Ninguna</span><span class="sxs-lookup"><span data-stu-id="3d082-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Minimizable%2A>|<span data-ttu-id="3d082-129">Property</span><span class="sxs-lookup"><span data-stu-id="3d082-129">Property</span></span>|<span data-ttu-id="3d082-130">Ninguna</span><span class="sxs-lookup"><span data-stu-id="3d082-130">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.VisualState%2A>|<span data-ttu-id="3d082-131">Property</span><span class="sxs-lookup"><span data-stu-id="3d082-131">Property</span></span>|<span data-ttu-id="3d082-132">Ninguna</span><span class="sxs-lookup"><span data-stu-id="3d082-132">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Close%2A>|<span data-ttu-id="3d082-133">Método</span><span class="sxs-lookup"><span data-stu-id="3d082-133">Method</span></span>|<span data-ttu-id="3d082-134">Ninguna</span><span class="sxs-lookup"><span data-stu-id="3d082-134">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A>|<span data-ttu-id="3d082-135">Método</span><span class="sxs-lookup"><span data-stu-id="3d082-135">Method</span></span>|<span data-ttu-id="3d082-136">Ninguna</span><span class="sxs-lookup"><span data-stu-id="3d082-136">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A>|<span data-ttu-id="3d082-137">Método</span><span class="sxs-lookup"><span data-stu-id="3d082-137">Method</span></span>|<span data-ttu-id="3d082-138">Ninguna</span><span class="sxs-lookup"><span data-stu-id="3d082-138">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|<span data-ttu-id="3d082-139">evento</span><span class="sxs-lookup"><span data-stu-id="3d082-139">Event</span></span>|<span data-ttu-id="3d082-140">Ninguna</span><span class="sxs-lookup"><span data-stu-id="3d082-140">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|<span data-ttu-id="3d082-141">evento</span><span class="sxs-lookup"><span data-stu-id="3d082-141">Event</span></span>|<span data-ttu-id="3d082-142">Ninguna</span><span class="sxs-lookup"><span data-stu-id="3d082-142">None</span></span>|  
|<xref:System.Windows.Automation.WindowInteractionState>|<span data-ttu-id="3d082-143">evento</span><span class="sxs-lookup"><span data-stu-id="3d082-143">Event</span></span>|<span data-ttu-id="3d082-144">No se garantiza que sea <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span><span class="sxs-lookup"><span data-stu-id="3d082-144">Is not guaranteed to be <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span></span>|  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="3d082-145">Excepciones</span><span class="sxs-lookup"><span data-stu-id="3d082-145">Exceptions</span></span>  
 <span data-ttu-id="3d082-146">Los proveedores deben producir las siguientes excepciones.</span><span class="sxs-lookup"><span data-stu-id="3d082-146">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="3d082-147">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="3d082-147">Exception type</span></span>|<span data-ttu-id="3d082-148">Condición</span><span class="sxs-lookup"><span data-stu-id="3d082-148">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A><br /><br /> <span data-ttu-id="3d082-149">-Cuando un control no admite un comportamiento solicitado.</span><span class="sxs-lookup"><span data-stu-id="3d082-149">-   When a control does not support a requested behavior.</span></span>|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A><br /><br /> <span data-ttu-id="3d082-150">-Cuando el parámetro no es un número válido.</span><span class="sxs-lookup"><span data-stu-id="3d082-150">-   When the parameter is not a valid number.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d082-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d082-151">See Also</span></span>  
 [<span data-ttu-id="3d082-152">Información general sobre los patrones de control de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="3d082-152">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="3d082-153">Patrones de control compatibles en un proveedor de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="3d082-153">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="3d082-154">Patrones de control de Automatización de la interfaz de usuario para clientes</span><span class="sxs-lookup"><span data-stu-id="3d082-154">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="3d082-155">Información general sobre el árbol de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="3d082-155">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="3d082-156">Uso del almacenamiento en caché en la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="3d082-156">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
