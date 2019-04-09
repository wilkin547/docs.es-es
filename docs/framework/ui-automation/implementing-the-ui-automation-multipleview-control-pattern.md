---
title: Implementación del patrón de control MultipleView de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, MultipleView control pattern
- MultipleView control pattern
- control patterns, MultipleView
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
ms.openlocfilehash: 74e5908dfcd42d031464ffccedb530be4a71a3f2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125203"
---
# <a name="implementing-the-ui-automation-multipleview-control-pattern"></a><span data-ttu-id="74c4a-102">Implementación del patrón de control MultipleView de UI Automation</span><span class="sxs-lookup"><span data-stu-id="74c4a-102">Implementing the UI Automation MultipleView Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="74c4a-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="74c4a-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="74c4a-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="74c4a-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="74c4a-105">En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, incluida la información sobre eventos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="74c4a-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, including information about events and properties.</span></span> <span data-ttu-id="74c4a-106">Al final del tema se ofrecen vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="74c4a-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="74c4a-107">El patrón de control <xref:System.Windows.Automation.MultipleViewPattern> se usa para admitir controles que ofrecen y pueden cambiar entre varias representaciones del mismo conjunto de información o controles secundarios.</span><span class="sxs-lookup"><span data-stu-id="74c4a-107">The <xref:System.Windows.Automation.MultipleViewPattern> control pattern is used to support controls that provide, and are able to switch between, multiple representations of the same set of information or child controls.</span></span>  
  
 <span data-ttu-id="74c4a-108">Entre los ejemplos de controles que pueden presentar varias vistas se incluyen la vista de lista (que puede mostrar su contenido como miniaturas, mosaicos, iconos o detalles), gráficos [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] (circulares, de líneas, de barras, valor de celda con una fórmula), documentos [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] (normal, diseño web, diseño de impresión, diseño de lectura, esquema), calendario [!INCLUDE[TLA#tla_outlook](../../../includes/tlasharptla-outlook-md.md)] (año, mes, semana, día) y máscaras [!INCLUDE[TLA#tla_wmp](../../../includes/tlasharptla-wmp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="74c4a-108">Examples of controls that can present multiple views include the list view (which can show its contents as thumbnails, tiles, icons, or details), [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] charts (pie, line, bar, cell value with a formula), [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] documents (normal, Web layout, print layout, reading layout, outline), [!INCLUDE[TLA#tla_outlook](../../../includes/tlasharptla-outlook-md.md)] calendar (year, month, week, day), and [!INCLUDE[TLA#tla_wmp](../../../includes/tlasharptla-wmp-md.md)] skins.</span></span> <span data-ttu-id="74c4a-109">Las vistas admitidas las determina el desarrollador del control y son específicas de cada control.</span><span class="sxs-lookup"><span data-stu-id="74c4a-109">The supported views are determined by the control developer and are specific to each control.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="74c4a-110">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="74c4a-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="74c4a-111">Al implementar el patrón de control Multiple View, tenga en cuenta las siguientes directrices y convenciones:</span><span class="sxs-lookup"><span data-stu-id="74c4a-111">When implementing the Multiple View control pattern, note the following guidelines and conventions:</span></span>  
  
-   <xref:System.Windows.Automation.Provider.IMultipleViewProvider> <span data-ttu-id="74c4a-112">También debe implementarse en un contenedor que administra la vista actual si es diferente de un control que proporciona la vista actual.</span><span class="sxs-lookup"><span data-stu-id="74c4a-112">should also be implemented on a container that manages the current view if it is different from a control that provides the current view.</span></span> <span data-ttu-id="74c4a-113">Por ejemplo, el Explorador de Windows contiene un control de lista para el contenido de la carpeta actual, mientras que la vista del control se administra desde la aplicación del Explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="74c4a-113">For example, Windows Explorer contains a List control for the current folder content while the view for the control is managed from the Windows Explorer application.</span></span>  
  
-   <span data-ttu-id="74c4a-114">No se considera que un control que puede ordenar su contenido admita varias vistas.</span><span class="sxs-lookup"><span data-stu-id="74c4a-114">A control that is able to sort its content is not considered to support multiple views.</span></span>  
  
-   <span data-ttu-id="74c4a-115">La colección de vistas debe ser idéntica en todas las instancias.</span><span class="sxs-lookup"><span data-stu-id="74c4a-115">The collection of views must be identical across instances.</span></span>  
  
-   <span data-ttu-id="74c4a-116">Los nombres de vista deben ser adecuados para su usarlo en texto a voz, Braille y otras aplicaciones de lenguaje natural.</span><span class="sxs-lookup"><span data-stu-id="74c4a-116">View names must be suitable for use in Text to Speech, Braille, and other human-readable applications.</span></span>  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>   
## <a name="required-members-for-imultipleviewprovider"></a><span data-ttu-id="74c4a-117">Miembros requeridos para IMultipleViewProvider</span><span class="sxs-lookup"><span data-stu-id="74c4a-117">Required Members for IMultipleViewProvider</span></span>  
 <span data-ttu-id="74c4a-118">Para implementar IMultipleViewProvider, se requieren las siguientes propiedades y métodos.</span><span class="sxs-lookup"><span data-stu-id="74c4a-118">The following properties and methods are required for implementing IMultipleViewProvider.</span></span>  
  
|<span data-ttu-id="74c4a-119">Miembros requeridos</span><span class="sxs-lookup"><span data-stu-id="74c4a-119">Required members</span></span>|<span data-ttu-id="74c4a-120">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="74c4a-120">Member type</span></span>|<span data-ttu-id="74c4a-121">Notas</span><span class="sxs-lookup"><span data-stu-id="74c4a-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|<span data-ttu-id="74c4a-122">Propiedad</span><span class="sxs-lookup"><span data-stu-id="74c4a-122">Property</span></span>|<span data-ttu-id="74c4a-123">Ninguna</span><span class="sxs-lookup"><span data-stu-id="74c4a-123">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|<span data-ttu-id="74c4a-124">Método</span><span class="sxs-lookup"><span data-stu-id="74c4a-124">Method</span></span>|<span data-ttu-id="74c4a-125">Ninguna</span><span class="sxs-lookup"><span data-stu-id="74c4a-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|<span data-ttu-id="74c4a-126">Método</span><span class="sxs-lookup"><span data-stu-id="74c4a-126">Method</span></span>|<span data-ttu-id="74c4a-127">Ninguna</span><span class="sxs-lookup"><span data-stu-id="74c4a-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|<span data-ttu-id="74c4a-128">Método</span><span class="sxs-lookup"><span data-stu-id="74c4a-128">Method</span></span>|<span data-ttu-id="74c4a-129">Ninguna</span><span class="sxs-lookup"><span data-stu-id="74c4a-129">None</span></span>|  
  
 <span data-ttu-id="74c4a-130">No hay ningún evento asociado a este patrón de control.</span><span class="sxs-lookup"><span data-stu-id="74c4a-130">There are no events associated with this control pattern.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="74c4a-131">Excepciones</span><span class="sxs-lookup"><span data-stu-id="74c4a-131">Exceptions</span></span>  
 <span data-ttu-id="74c4a-132">Los proveedores debe generar las siguientes excepciones.</span><span class="sxs-lookup"><span data-stu-id="74c4a-132">Provider must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="74c4a-133">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="74c4a-133">Exception type</span></span>|<span data-ttu-id="74c4a-134">Condición</span><span class="sxs-lookup"><span data-stu-id="74c4a-134">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="74c4a-135">Cuando se llama a <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> o <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> con un parámetro que no es miembro de la colección de vistas compatible.</span><span class="sxs-lookup"><span data-stu-id="74c4a-135">When either <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> or <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> is called with a parameter that is not a member of the supported views collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74c4a-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="74c4a-136">See also</span></span>

- [<span data-ttu-id="74c4a-137">Información general acerca de los patrones de control de UI Automation</span><span class="sxs-lookup"><span data-stu-id="74c4a-137">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="74c4a-138">Patrones de control compatibles en un proveedor de UI Automation</span><span class="sxs-lookup"><span data-stu-id="74c4a-138">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="74c4a-139">Patrones de controles de UI Automation para clientes</span><span class="sxs-lookup"><span data-stu-id="74c4a-139">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="74c4a-140">Información general sobre el árbol de la UI Automation</span><span class="sxs-lookup"><span data-stu-id="74c4a-140">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [<span data-ttu-id="74c4a-141">Utilizar el almacenamiento en caché en la UI Automation</span><span class="sxs-lookup"><span data-stu-id="74c4a-141">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
