---
title: Implementación del patrón de control MultipleView de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, MultipleView control pattern
- MultipleView control pattern
- control patterns, MultipleView
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
ms.openlocfilehash: c9199e0ea1971c22bfc1f6334b9d2d9d73bb048c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435055"
---
# <a name="implementing-the-ui-automation-multipleview-control-pattern"></a><span data-ttu-id="d456d-102">Implementación del patrón de control MultipleView de UI Automation</span><span class="sxs-lookup"><span data-stu-id="d456d-102">Implementing the UI Automation MultipleView Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="d456d-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="d456d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d456d-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="d456d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="d456d-105">En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IMultipleViewProvider>y se incluye información sobre eventos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="d456d-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, including information about events and properties.</span></span> <span data-ttu-id="d456d-106">Al final del tema se ofrecen vínculos a referencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="d456d-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="d456d-107">El patrón de control <xref:System.Windows.Automation.MultipleViewPattern> se usa para admitir controles que ofrecen y pueden cambiar entre varias representaciones del mismo conjunto de información o controles secundarios.</span><span class="sxs-lookup"><span data-stu-id="d456d-107">The <xref:System.Windows.Automation.MultipleViewPattern> control pattern is used to support controls that provide, and are able to switch between, multiple representations of the same set of information or child controls.</span></span>  
  
 <span data-ttu-id="d456d-108">Entre los ejemplos de controles que pueden presentar varias vistas se incluye la vista de lista (que puede mostrar su contenido como miniaturas, mosaicos, iconos o detalles), gráficos de Microsoft Excel (circular, línea, barra, valor de celda con una fórmula), documentos de Microsoft Word (normal, diseño web, imprimir diseño, diseño de lectura, esquema), calendario de Microsoft Outlook (año, mes, semana, día) y máscaras de Media Player de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="d456d-108">Examples of controls that can present multiple views include the list view (which can show its contents as thumbnails, tiles, icons, or details), Microsoft Excel charts (pie, line, bar, cell value with a formula), Microsoft Word documents (normal, Web layout, print layout, reading layout, outline), Microsoft Outlook calendar (year, month, week, day), and Microsoft Windows Media Player skins.</span></span> <span data-ttu-id="d456d-109">Las vistas admitidas las determina el desarrollador del control y son específicas de cada control.</span><span class="sxs-lookup"><span data-stu-id="d456d-109">The supported views are determined by the control developer and are specific to each control.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="d456d-110">Directrices y convenciones de implementación</span><span class="sxs-lookup"><span data-stu-id="d456d-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="d456d-111">Al implementar el patrón de control Multiple View, tenga en cuenta las siguientes directrices y convenciones:</span><span class="sxs-lookup"><span data-stu-id="d456d-111">When implementing the Multiple View control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="d456d-112"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> también se debe implementar en un contenedor que administre la vista actual si es diferente de un control que ofrece la vista actual.</span><span class="sxs-lookup"><span data-stu-id="d456d-112"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> should also be implemented on a container that manages the current view if it is different from a control that provides the current view.</span></span> <span data-ttu-id="d456d-113">Por ejemplo, el Explorador de Windows contiene un control de lista para el contenido de la carpeta actual, mientras que la vista del control se administra desde la aplicación del Explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="d456d-113">For example, Windows Explorer contains a List control for the current folder content while the view for the control is managed from the Windows Explorer application.</span></span>  
  
- <span data-ttu-id="d456d-114">No se considera que un control que puede ordenar su contenido admita varias vistas.</span><span class="sxs-lookup"><span data-stu-id="d456d-114">A control that is able to sort its content is not considered to support multiple views.</span></span>  
  
- <span data-ttu-id="d456d-115">La colección de vistas debe ser idéntica en todas las instancias.</span><span class="sxs-lookup"><span data-stu-id="d456d-115">The collection of views must be identical across instances.</span></span>  
  
- <span data-ttu-id="d456d-116">Los nombres de vista deben ser adecuados para su usarlo en texto a voz, Braille y otras aplicaciones de lenguaje natural.</span><span class="sxs-lookup"><span data-stu-id="d456d-116">View names must be suitable for use in Text to Speech, Braille, and other human-readable applications.</span></span>  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>   
## <a name="required-members-for-imultipleviewprovider"></a><span data-ttu-id="d456d-117">Miembros requeridos para IMultipleViewProvider</span><span class="sxs-lookup"><span data-stu-id="d456d-117">Required Members for IMultipleViewProvider</span></span>  
 <span data-ttu-id="d456d-118">Para implementar IMultipleViewProvider, se requieren las siguientes propiedades y métodos.</span><span class="sxs-lookup"><span data-stu-id="d456d-118">The following properties and methods are required for implementing IMultipleViewProvider.</span></span>  
  
|<span data-ttu-id="d456d-119">Miembros requeridos</span><span class="sxs-lookup"><span data-stu-id="d456d-119">Required members</span></span>|<span data-ttu-id="d456d-120">Tipo de miembro</span><span class="sxs-lookup"><span data-stu-id="d456d-120">Member type</span></span>|<span data-ttu-id="d456d-121">Notas</span><span class="sxs-lookup"><span data-stu-id="d456d-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|<span data-ttu-id="d456d-122">Propiedad</span><span class="sxs-lookup"><span data-stu-id="d456d-122">Property</span></span>|<span data-ttu-id="d456d-123">Ninguno</span><span class="sxs-lookup"><span data-stu-id="d456d-123">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|<span data-ttu-id="d456d-124">Método</span><span class="sxs-lookup"><span data-stu-id="d456d-124">Method</span></span>|<span data-ttu-id="d456d-125">Ninguno</span><span class="sxs-lookup"><span data-stu-id="d456d-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|<span data-ttu-id="d456d-126">Método</span><span class="sxs-lookup"><span data-stu-id="d456d-126">Method</span></span>|<span data-ttu-id="d456d-127">Ninguno</span><span class="sxs-lookup"><span data-stu-id="d456d-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|<span data-ttu-id="d456d-128">Método</span><span class="sxs-lookup"><span data-stu-id="d456d-128">Method</span></span>|<span data-ttu-id="d456d-129">Ninguno</span><span class="sxs-lookup"><span data-stu-id="d456d-129">None</span></span>|  
  
 <span data-ttu-id="d456d-130">No hay ningún evento asociado a este patrón de control.</span><span class="sxs-lookup"><span data-stu-id="d456d-130">There are no events associated with this control pattern.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="d456d-131">Excepciones</span><span class="sxs-lookup"><span data-stu-id="d456d-131">Exceptions</span></span>  
 <span data-ttu-id="d456d-132">Los proveedores debe generar las siguientes excepciones.</span><span class="sxs-lookup"><span data-stu-id="d456d-132">Provider must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="d456d-133">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="d456d-133">Exception type</span></span>|<span data-ttu-id="d456d-134">Condición</span><span class="sxs-lookup"><span data-stu-id="d456d-134">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="d456d-135">Cuando se llama a <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> o <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> con un parámetro que no es miembro de la colección de vistas compatible.</span><span class="sxs-lookup"><span data-stu-id="d456d-135">When either <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> or <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> is called with a parameter that is not a member of the supported views collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d456d-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="d456d-136">See also</span></span>

- [<span data-ttu-id="d456d-137">Información general sobre los patrones de control de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="d456d-137">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="d456d-138">Patrones de control compatibles en un proveedor de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="d456d-138">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="d456d-139">UI Automation Control Patterns for Clients</span><span class="sxs-lookup"><span data-stu-id="d456d-139">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="d456d-140">Información general sobre el árbol de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="d456d-140">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="d456d-141">Uso del almacenamiento en caché en la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="d456d-141">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
