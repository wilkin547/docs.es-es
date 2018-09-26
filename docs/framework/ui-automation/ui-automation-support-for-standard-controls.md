---
title: Compatibilidad de UI Automation con controles estándar
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 68fa7753be76b0681c40e540e86b11c89e7a8ca1
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47193892"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="a25ee-102">Compatibilidad de UI Automation con controles estándar</span><span class="sxs-lookup"><span data-stu-id="a25ee-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="a25ee-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="a25ee-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a25ee-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="a25ee-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="a25ee-105">En este tema se incluye información sobre la compatibilidad de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] con controles estándar en las aplicaciones desarrolladas para los marcos de trabajo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]y [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a25ee-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="a25ee-106">Controles de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="a25ee-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="a25ee-107">Todos los elementos de control [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] que ofrecen información o compatibilidad para la interacción del usuario tienen compatibilidad nativa completa con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a25ee-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="a25ee-108">Otros elementos, como paneles, no son visibles para [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a25ee-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="a25ee-109">Controles de Win32</span><span class="sxs-lookup"><span data-stu-id="a25ee-109">Win32 Controls</span></span>  
 <span data-ttu-id="a25ee-110">La mayoría de los controles [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de los proveedores del cliente en UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="a25ee-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="a25ee-111">Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a25ee-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="a25ee-112">Solo se proporciona compatibilidad completa para controles desde la versión 6 de ComCtrl32.dll (disponibles con [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] y versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="a25ee-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="a25ee-113">Se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="a25ee-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="a25ee-114">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="a25ee-114">Class name</span></span>|<span data-ttu-id="a25ee-115">Tipo de control</span><span class="sxs-lookup"><span data-stu-id="a25ee-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="a25ee-116">Botón</span><span class="sxs-lookup"><span data-stu-id="a25ee-116">Button</span></span>|<span data-ttu-id="a25ee-117">Botón</span><span class="sxs-lookup"><span data-stu-id="a25ee-117">Button</span></span>|  
|<span data-ttu-id="a25ee-118">Botón</span><span class="sxs-lookup"><span data-stu-id="a25ee-118">Button</span></span>|<span data-ttu-id="a25ee-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="a25ee-119">RadioButton</span></span>|  
|<span data-ttu-id="a25ee-120">Botón</span><span class="sxs-lookup"><span data-stu-id="a25ee-120">Button</span></span>|<span data-ttu-id="a25ee-121">Agrupar</span><span class="sxs-lookup"><span data-stu-id="a25ee-121">Group</span></span>|  
|<span data-ttu-id="a25ee-122">Botón</span><span class="sxs-lookup"><span data-stu-id="a25ee-122">Button</span></span>|<span data-ttu-id="a25ee-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a25ee-123">CheckBox</span></span>|  
|<span data-ttu-id="a25ee-124">Botón</span><span class="sxs-lookup"><span data-stu-id="a25ee-124">Button</span></span>|<span data-ttu-id="a25ee-125">Hipervínculo</span><span class="sxs-lookup"><span data-stu-id="a25ee-125">Hyperlink</span></span>|  
|<span data-ttu-id="a25ee-126">Botón</span><span class="sxs-lookup"><span data-stu-id="a25ee-126">Button</span></span>|<span data-ttu-id="a25ee-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="a25ee-127">SplitButton</span></span>|  
|<span data-ttu-id="a25ee-128">Botón</span><span class="sxs-lookup"><span data-stu-id="a25ee-128">Button</span></span>|<span data-ttu-id="a25ee-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a25ee-129">CheckBox</span></span>|  
|<span data-ttu-id="a25ee-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="a25ee-130">ComboBoxEx32</span></span>|<span data-ttu-id="a25ee-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a25ee-131">ComboBox</span></span>|  
|<span data-ttu-id="a25ee-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a25ee-132">ComboBox</span></span>|<span data-ttu-id="a25ee-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a25ee-133">ComboBox</span></span>|  
|<span data-ttu-id="a25ee-134">Editar</span><span class="sxs-lookup"><span data-stu-id="a25ee-134">Edit</span></span>|<span data-ttu-id="a25ee-135">Documento</span><span class="sxs-lookup"><span data-stu-id="a25ee-135">Document</span></span>|  
|<span data-ttu-id="a25ee-136">Editar</span><span class="sxs-lookup"><span data-stu-id="a25ee-136">Edit</span></span>|<span data-ttu-id="a25ee-137">Editar</span><span class="sxs-lookup"><span data-stu-id="a25ee-137">Edit</span></span>|  
|<span data-ttu-id="a25ee-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="a25ee-138">SysLink</span></span>|<span data-ttu-id="a25ee-139">Hipervínculo</span><span class="sxs-lookup"><span data-stu-id="a25ee-139">Hyperlink</span></span>|  
|<span data-ttu-id="a25ee-140">Estático</span><span class="sxs-lookup"><span data-stu-id="a25ee-140">Static</span></span>|<span data-ttu-id="a25ee-141">Texto</span><span class="sxs-lookup"><span data-stu-id="a25ee-141">Text</span></span>|  
|<span data-ttu-id="a25ee-142">Estático</span><span class="sxs-lookup"><span data-stu-id="a25ee-142">Static</span></span>|<span data-ttu-id="a25ee-143">Imagen</span><span class="sxs-lookup"><span data-stu-id="a25ee-143">Image</span></span>|  
|<span data-ttu-id="a25ee-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="a25ee-144">SysIPAddress32</span></span>|<span data-ttu-id="a25ee-145">Personalizados</span><span class="sxs-lookup"><span data-stu-id="a25ee-145">Custom</span></span>|  
|<span data-ttu-id="a25ee-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="a25ee-146">SysHeader32</span></span>|<span data-ttu-id="a25ee-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="a25ee-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="a25ee-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="a25ee-148">SysListView32</span></span>|<span data-ttu-id="a25ee-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="a25ee-149">DataGrid</span></span>|  
|<span data-ttu-id="a25ee-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="a25ee-150">SysListView32</span></span>|<span data-ttu-id="a25ee-151">Lista</span><span class="sxs-lookup"><span data-stu-id="a25ee-151">List</span></span>|  
|<span data-ttu-id="a25ee-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="a25ee-152">ListBox</span></span>|<span data-ttu-id="a25ee-153">Lista</span><span class="sxs-lookup"><span data-stu-id="a25ee-153">List</span></span>|  
|<span data-ttu-id="a25ee-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="a25ee-154">ListBox</span></span>|<span data-ttu-id="a25ee-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="a25ee-155">ListItem</span></span>|  
|<span data-ttu-id="a25ee-156">#32768</span><span class="sxs-lookup"><span data-stu-id="a25ee-156">#32768</span></span>|<span data-ttu-id="a25ee-157">Menú</span><span class="sxs-lookup"><span data-stu-id="a25ee-157">Menu</span></span>|  
|<span data-ttu-id="a25ee-158">#32768</span><span class="sxs-lookup"><span data-stu-id="a25ee-158">#32768</span></span>|<span data-ttu-id="a25ee-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="a25ee-159">MenuItem</span></span>|  
|<span data-ttu-id="a25ee-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="a25ee-160">msctls_progress32</span></span>|<span data-ttu-id="a25ee-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="a25ee-161">ProgressBar</span></span>|  
|<span data-ttu-id="a25ee-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="a25ee-162">RichEdit</span></span>|<span data-ttu-id="a25ee-163">Documento.</span><span class="sxs-lookup"><span data-stu-id="a25ee-163">Document.</span></span> <span data-ttu-id="a25ee-164">Vea la nota.</span><span class="sxs-lookup"><span data-stu-id="a25ee-164">See note.</span></span>|  
|<span data-ttu-id="a25ee-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="a25ee-165">RichEdit20A</span></span>|<span data-ttu-id="a25ee-166">Documento</span><span class="sxs-lookup"><span data-stu-id="a25ee-166">Document</span></span>|  
|<span data-ttu-id="a25ee-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="a25ee-167">RichEdit20W</span></span>|<span data-ttu-id="a25ee-168">Documento</span><span class="sxs-lookup"><span data-stu-id="a25ee-168">Document</span></span>|  
|<span data-ttu-id="a25ee-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="a25ee-169">RichEdit50W</span></span>|<span data-ttu-id="a25ee-170">Documento</span><span class="sxs-lookup"><span data-stu-id="a25ee-170">Document</span></span>|  
|<span data-ttu-id="a25ee-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="a25ee-171">ScrollBar</span></span>|<span data-ttu-id="a25ee-172">Slider</span><span class="sxs-lookup"><span data-stu-id="a25ee-172">Slider</span></span>|  
|<span data-ttu-id="a25ee-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="a25ee-173">msctls_trackbar32</span></span>|<span data-ttu-id="a25ee-174">Slider</span><span class="sxs-lookup"><span data-stu-id="a25ee-174">Slider</span></span>|  
|<span data-ttu-id="a25ee-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="a25ee-175">msctls_updown32</span></span>|<span data-ttu-id="a25ee-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="a25ee-176">Spinner</span></span>|  
|<span data-ttu-id="a25ee-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="a25ee-177">msctls_statusbar32</span></span>|<span data-ttu-id="a25ee-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="a25ee-178">StatusBar</span></span>|  
|<span data-ttu-id="a25ee-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="a25ee-179">SysTabControl32</span></span>|<span data-ttu-id="a25ee-180">Tab</span><span class="sxs-lookup"><span data-stu-id="a25ee-180">Tab</span></span>|  
|<span data-ttu-id="a25ee-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="a25ee-181">SysTabControl32</span></span>|<span data-ttu-id="a25ee-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="a25ee-182">TabItem</span></span>|  
|<span data-ttu-id="a25ee-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a25ee-183">ToolbarWindow32</span></span>|<span data-ttu-id="a25ee-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="a25ee-184">ToolBar</span></span>|  
|<span data-ttu-id="a25ee-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a25ee-185">ToolbarWindow32</span></span>|<span data-ttu-id="a25ee-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="a25ee-186">MenuItem</span></span>|  
|<span data-ttu-id="a25ee-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a25ee-187">ToolbarWindow32</span></span>|<span data-ttu-id="a25ee-188">Botón</span><span class="sxs-lookup"><span data-stu-id="a25ee-188">Button</span></span>|  
|<span data-ttu-id="a25ee-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a25ee-189">ToolbarWindow32</span></span>|<span data-ttu-id="a25ee-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a25ee-190">CheckBox</span></span>|  
|<span data-ttu-id="a25ee-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a25ee-191">ToolbarWindow32</span></span>|<span data-ttu-id="a25ee-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="a25ee-192">RadioButton</span></span>|  
|<span data-ttu-id="a25ee-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a25ee-193">ToolbarWindow32</span></span>|<span data-ttu-id="a25ee-194">Separador</span><span class="sxs-lookup"><span data-stu-id="a25ee-194">Separator</span></span>|  
|<span data-ttu-id="a25ee-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="a25ee-195">tooltips_class32</span></span>|<span data-ttu-id="a25ee-196">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="a25ee-196">ToolTip</span></span>|  
|<span data-ttu-id="a25ee-197">#32774</span><span class="sxs-lookup"><span data-stu-id="a25ee-197">#32774</span></span>|<span data-ttu-id="a25ee-198">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="a25ee-198">ToolTip</span></span>|  
|<span data-ttu-id="a25ee-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="a25ee-199">ReBarWindow32</span></span>|<span data-ttu-id="a25ee-200">Barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="a25ee-200">Toolbar</span></span>|  
|<span data-ttu-id="a25ee-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="a25ee-201">SysTreeView32</span></span>|<span data-ttu-id="a25ee-202">Árbol</span><span class="sxs-lookup"><span data-stu-id="a25ee-202">Tree</span></span>|  
|<span data-ttu-id="a25ee-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="a25ee-203">SysTreeView32</span></span>|<span data-ttu-id="a25ee-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="a25ee-204">TreeItem</span></span>|  
  
 <span data-ttu-id="a25ee-205">**Nota** El control RichEdit solo se admite para las versiones incluidas con [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (en RichEd20.dll versión 3.1 y posteriores, y MsftEdit.dll versión 4.1 y posteriores).</span><span class="sxs-lookup"><span data-stu-id="a25ee-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="a25ee-206">No se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="a25ee-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="a25ee-207">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="a25ee-207">Class name</span></span>|<span data-ttu-id="a25ee-208">Tipo de control</span><span class="sxs-lookup"><span data-stu-id="a25ee-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="a25ee-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="a25ee-209">SysAnimate32</span></span>|<span data-ttu-id="a25ee-210">Imagen</span><span class="sxs-lookup"><span data-stu-id="a25ee-210">Image</span></span>|  
|<span data-ttu-id="a25ee-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="a25ee-211">SysPager</span></span>|<span data-ttu-id="a25ee-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="a25ee-212">Spinner</span></span>|  
|<span data-ttu-id="a25ee-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="a25ee-213">SysDateTimePick32</span></span>|<span data-ttu-id="a25ee-214">Personalizados</span><span class="sxs-lookup"><span data-stu-id="a25ee-214">Custom</span></span>|  
|<span data-ttu-id="a25ee-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="a25ee-215">SysMonthCal32</span></span>|<span data-ttu-id="a25ee-216">Calendario</span><span class="sxs-lookup"><span data-stu-id="a25ee-216">Calendar</span></span>|  
|<span data-ttu-id="a25ee-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="a25ee-217">MS_WINNOTE</span></span>|<span data-ttu-id="a25ee-218">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="a25ee-218">Tooltip</span></span>|  
|<span data-ttu-id="a25ee-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="a25ee-219">VBBubble</span></span>|<span data-ttu-id="a25ee-220">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="a25ee-220">Tooltip</span></span>|  
|<span data-ttu-id="a25ee-221">ScrollBar (cuando se usa como control independiente)</span><span class="sxs-lookup"><span data-stu-id="a25ee-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="a25ee-222">Slider</span><span class="sxs-lookup"><span data-stu-id="a25ee-222">Slider</span></span>|  
|<span data-ttu-id="a25ee-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="a25ee-223">SuperGrid</span></span>|<span data-ttu-id="a25ee-224">Personalizados</span><span class="sxs-lookup"><span data-stu-id="a25ee-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="a25ee-225">Controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a25ee-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="a25ee-226">Controles de formularios Windows Forms se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de proveedores del lado cliente en UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="a25ee-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="a25ee-227">Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a25ee-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="a25ee-228">Normalmente, los controles de Windows Forms que son contenedores administran para [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controles comunes son compatibles con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a25ee-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="a25ee-229">Se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="a25ee-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="a25ee-230">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="a25ee-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="a25ee-231">Botón</span><span class="sxs-lookup"><span data-stu-id="a25ee-231">Button</span></span>|  
|<span data-ttu-id="a25ee-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a25ee-232">CheckBox</span></span>|  
|<span data-ttu-id="a25ee-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="a25ee-233">CheckedListBox</span></span>|  
|<span data-ttu-id="a25ee-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="a25ee-234">ColorDialog</span></span>|  
|<span data-ttu-id="a25ee-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a25ee-235">ComboBox</span></span>|  
|<span data-ttu-id="a25ee-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="a25ee-236">FolderBrowser</span></span>|  
|<span data-ttu-id="a25ee-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="a25ee-237">FontDialog</span></span>|  
|<span data-ttu-id="a25ee-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="a25ee-238">GroupBox</span></span>|  
|<span data-ttu-id="a25ee-239">HScrollBar</span><span class="sxs-lookup"><span data-stu-id="a25ee-239">HscrollBar</span></span>|  
|<span data-ttu-id="a25ee-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="a25ee-240">ImageList</span></span>|  
|<span data-ttu-id="a25ee-241">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="a25ee-241">Label</span></span>|  
|<span data-ttu-id="a25ee-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="a25ee-242">ListBox</span></span>|  
|<span data-ttu-id="a25ee-243">ListView</span><span class="sxs-lookup"><span data-stu-id="a25ee-243">ListView</span></span>|  
|<span data-ttu-id="a25ee-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="a25ee-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="a25ee-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="a25ee-245">MonthCalendar</span></span>|  
|<span data-ttu-id="a25ee-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="a25ee-246">NotifyIcon</span></span>|  
|<span data-ttu-id="a25ee-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="a25ee-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="a25ee-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="a25ee-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="a25ee-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="a25ee-249">PrintDialog</span></span>|  
|<span data-ttu-id="a25ee-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="a25ee-250">ProgressBar</span></span>|  
|<span data-ttu-id="a25ee-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="a25ee-251">RadioButton</span></span>|  
|<span data-ttu-id="a25ee-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="a25ee-252">RichTextBox</span></span>|  
|<span data-ttu-id="a25ee-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="a25ee-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="a25ee-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="a25ee-254">ScrollableControl</span></span>|  
|<span data-ttu-id="a25ee-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="a25ee-255">SoundPlayer</span></span>|  
|<span data-ttu-id="a25ee-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="a25ee-256">StatusBar</span></span>|  
|<span data-ttu-id="a25ee-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="a25ee-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="a25ee-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="a25ee-258">TextBox</span></span>|  
|<span data-ttu-id="a25ee-259">Temporizador</span><span class="sxs-lookup"><span data-stu-id="a25ee-259">Timer</span></span>|  
|<span data-ttu-id="a25ee-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="a25ee-260">Toolbar</span></span>|  
|<span data-ttu-id="a25ee-261">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="a25ee-261">ToolTip</span></span>|  
|<span data-ttu-id="a25ee-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="a25ee-262">TrackBar</span></span>|  
|<span data-ttu-id="a25ee-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="a25ee-263">TreeView</span></span>|  
|<span data-ttu-id="a25ee-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="a25ee-264">VscrollBar</span></span>|  
|<span data-ttu-id="a25ee-265">ExploradorWeb</span><span class="sxs-lookup"><span data-stu-id="a25ee-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="a25ee-266">Los siguientes controles solo están expuestos a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de su compatibilidad con [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a25ee-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="a25ee-267">Es posible que algunas funciones no estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="a25ee-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="a25ee-268">Nombre del control</span><span class="sxs-lookup"><span data-stu-id="a25ee-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="a25ee-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="a25ee-269">BindingSource</span></span>|  
|<span data-ttu-id="a25ee-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="a25ee-270">DataGrid</span></span>|  
|<span data-ttu-id="a25ee-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="a25ee-271">DataGridView</span></span>|  
|<span data-ttu-id="a25ee-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="a25ee-272">DataNavigator</span></span>|  
|<span data-ttu-id="a25ee-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="a25ee-273">DomainUpDown</span></span>|  
|<span data-ttu-id="a25ee-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="a25ee-274">ErrorProvider</span></span>|  
|<span data-ttu-id="a25ee-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a25ee-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="a25ee-276">Form</span><span class="sxs-lookup"><span data-stu-id="a25ee-276">Form</span></span>|  
|<span data-ttu-id="a25ee-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="a25ee-277">LinkLabel</span></span>|  
|<span data-ttu-id="a25ee-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="a25ee-278">HelpProvider</span></span>|  
|<span data-ttu-id="a25ee-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="a25ee-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="a25ee-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="a25ee-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="a25ee-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="a25ee-281">NumericUpDown</span></span>|  
|<span data-ttu-id="a25ee-282">Panel</span><span class="sxs-lookup"><span data-stu-id="a25ee-282">Panel</span></span>|  
|<span data-ttu-id="a25ee-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="a25ee-283">PictureBox</span></span>|  
|<span data-ttu-id="a25ee-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="a25ee-284">PrintDocument</span></span>|  
|<span data-ttu-id="a25ee-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="a25ee-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="a25ee-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="a25ee-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="a25ee-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="a25ee-287">PropertyGrid</span></span>|  
|<span data-ttu-id="a25ee-288">Control de usuario</span><span class="sxs-lookup"><span data-stu-id="a25ee-288">UserControl</span></span>|  
|<span data-ttu-id="a25ee-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="a25ee-289">ToolStrip</span></span>|  
|<span data-ttu-id="a25ee-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a25ee-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="a25ee-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="a25ee-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="a25ee-292">Divisor</span><span class="sxs-lookup"><span data-stu-id="a25ee-292">Splitter</span></span>|  
|<span data-ttu-id="a25ee-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="a25ee-293">RaftingContainer</span></span>|  
|<span data-ttu-id="a25ee-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="a25ee-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a25ee-295">Vea también</span><span class="sxs-lookup"><span data-stu-id="a25ee-295">See Also</span></span>  
 [<span data-ttu-id="a25ee-296">Tipos de control de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="a25ee-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
