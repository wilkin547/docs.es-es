---
title: Compatibilidad de UI Automation con controles estándar
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: d83713a81e7675a68482890c2401f1a0a6803abc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914233"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="965e2-102">Compatibilidad de UI Automation con controles estándar</span><span class="sxs-lookup"><span data-stu-id="965e2-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="965e2-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="965e2-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="965e2-104">Para obtener la información más [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]reciente acerca [de, consulte API de automatización de Windows: Automatización](https://go.microsoft.com/fwlink/?LinkID=156746)de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="965e2-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="965e2-105">En este tema se incluye información sobre la compatibilidad de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] con controles estándar en las aplicaciones desarrolladas para los marcos de trabajo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]y [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="965e2-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="965e2-106">Controles de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="965e2-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="965e2-107">Todos los elementos de control [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] que ofrecen información o compatibilidad para la interacción del usuario tienen compatibilidad nativa completa con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="965e2-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="965e2-108">Otros elementos, como paneles, no son visibles para [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="965e2-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="965e2-109">Controles de Win32</span><span class="sxs-lookup"><span data-stu-id="965e2-109">Win32 Controls</span></span>  
 <span data-ttu-id="965e2-110">La mayoría de los controles [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de los proveedores del cliente en UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="965e2-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="965e2-111">Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="965e2-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="965e2-112">Solo se proporciona compatibilidad completa para controles desde la versión 6 de ComCtrl32.dll (disponibles con [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] y versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="965e2-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="965e2-113">Se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="965e2-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="965e2-114">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="965e2-114">Class name</span></span>|<span data-ttu-id="965e2-115">Tipo de control</span><span class="sxs-lookup"><span data-stu-id="965e2-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="965e2-116">Botón</span><span class="sxs-lookup"><span data-stu-id="965e2-116">Button</span></span>|<span data-ttu-id="965e2-117">Botón</span><span class="sxs-lookup"><span data-stu-id="965e2-117">Button</span></span>|  
|<span data-ttu-id="965e2-118">Botón</span><span class="sxs-lookup"><span data-stu-id="965e2-118">Button</span></span>|<span data-ttu-id="965e2-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="965e2-119">RadioButton</span></span>|  
|<span data-ttu-id="965e2-120">Botón</span><span class="sxs-lookup"><span data-stu-id="965e2-120">Button</span></span>|<span data-ttu-id="965e2-121">Grupo</span><span class="sxs-lookup"><span data-stu-id="965e2-121">Group</span></span>|  
|<span data-ttu-id="965e2-122">Botón</span><span class="sxs-lookup"><span data-stu-id="965e2-122">Button</span></span>|<span data-ttu-id="965e2-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="965e2-123">CheckBox</span></span>|  
|<span data-ttu-id="965e2-124">Botón</span><span class="sxs-lookup"><span data-stu-id="965e2-124">Button</span></span>|<span data-ttu-id="965e2-125">Hipervínculo</span><span class="sxs-lookup"><span data-stu-id="965e2-125">Hyperlink</span></span>|  
|<span data-ttu-id="965e2-126">Botón</span><span class="sxs-lookup"><span data-stu-id="965e2-126">Button</span></span>|<span data-ttu-id="965e2-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="965e2-127">SplitButton</span></span>|  
|<span data-ttu-id="965e2-128">Botón</span><span class="sxs-lookup"><span data-stu-id="965e2-128">Button</span></span>|<span data-ttu-id="965e2-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="965e2-129">CheckBox</span></span>|  
|<span data-ttu-id="965e2-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="965e2-130">ComboBoxEx32</span></span>|<span data-ttu-id="965e2-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="965e2-131">ComboBox</span></span>|  
|<span data-ttu-id="965e2-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="965e2-132">ComboBox</span></span>|<span data-ttu-id="965e2-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="965e2-133">ComboBox</span></span>|  
|<span data-ttu-id="965e2-134">Editar</span><span class="sxs-lookup"><span data-stu-id="965e2-134">Edit</span></span>|<span data-ttu-id="965e2-135">Documento</span><span class="sxs-lookup"><span data-stu-id="965e2-135">Document</span></span>|  
|<span data-ttu-id="965e2-136">Editar</span><span class="sxs-lookup"><span data-stu-id="965e2-136">Edit</span></span>|<span data-ttu-id="965e2-137">Editar</span><span class="sxs-lookup"><span data-stu-id="965e2-137">Edit</span></span>|  
|<span data-ttu-id="965e2-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="965e2-138">SysLink</span></span>|<span data-ttu-id="965e2-139">Hipervínculo</span><span class="sxs-lookup"><span data-stu-id="965e2-139">Hyperlink</span></span>|  
|<span data-ttu-id="965e2-140">estática</span><span class="sxs-lookup"><span data-stu-id="965e2-140">Static</span></span>|<span data-ttu-id="965e2-141">Text</span><span class="sxs-lookup"><span data-stu-id="965e2-141">Text</span></span>|  
|<span data-ttu-id="965e2-142">Estático</span><span class="sxs-lookup"><span data-stu-id="965e2-142">Static</span></span>|<span data-ttu-id="965e2-143">Image</span><span class="sxs-lookup"><span data-stu-id="965e2-143">Image</span></span>|  
|<span data-ttu-id="965e2-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="965e2-144">SysIPAddress32</span></span>|<span data-ttu-id="965e2-145">Personalizados</span><span class="sxs-lookup"><span data-stu-id="965e2-145">Custom</span></span>|  
|<span data-ttu-id="965e2-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="965e2-146">SysHeader32</span></span>|<span data-ttu-id="965e2-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="965e2-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="965e2-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="965e2-148">SysListView32</span></span>|<span data-ttu-id="965e2-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="965e2-149">DataGrid</span></span>|  
|<span data-ttu-id="965e2-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="965e2-150">SysListView32</span></span>|<span data-ttu-id="965e2-151">Enumerar</span><span class="sxs-lookup"><span data-stu-id="965e2-151">List</span></span>|  
|<span data-ttu-id="965e2-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="965e2-152">ListBox</span></span>|<span data-ttu-id="965e2-153">Enumerar</span><span class="sxs-lookup"><span data-stu-id="965e2-153">List</span></span>|  
|<span data-ttu-id="965e2-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="965e2-154">ListBox</span></span>|<span data-ttu-id="965e2-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="965e2-155">ListItem</span></span>|  
|<span data-ttu-id="965e2-156">#32768</span><span class="sxs-lookup"><span data-stu-id="965e2-156">#32768</span></span>|<span data-ttu-id="965e2-157">Menú</span><span class="sxs-lookup"><span data-stu-id="965e2-157">Menu</span></span>|  
|<span data-ttu-id="965e2-158">#32768</span><span class="sxs-lookup"><span data-stu-id="965e2-158">#32768</span></span>|<span data-ttu-id="965e2-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="965e2-159">MenuItem</span></span>|  
|<span data-ttu-id="965e2-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="965e2-160">msctls_progress32</span></span>|<span data-ttu-id="965e2-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="965e2-161">ProgressBar</span></span>|  
|<span data-ttu-id="965e2-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="965e2-162">RichEdit</span></span>|<span data-ttu-id="965e2-163">Documento.</span><span class="sxs-lookup"><span data-stu-id="965e2-163">Document.</span></span> <span data-ttu-id="965e2-164">Vea la nota.</span><span class="sxs-lookup"><span data-stu-id="965e2-164">See note.</span></span>|  
|<span data-ttu-id="965e2-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="965e2-165">RichEdit20A</span></span>|<span data-ttu-id="965e2-166">Documento</span><span class="sxs-lookup"><span data-stu-id="965e2-166">Document</span></span>|  
|<span data-ttu-id="965e2-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="965e2-167">RichEdit20W</span></span>|<span data-ttu-id="965e2-168">Documento</span><span class="sxs-lookup"><span data-stu-id="965e2-168">Document</span></span>|  
|<span data-ttu-id="965e2-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="965e2-169">RichEdit50W</span></span>|<span data-ttu-id="965e2-170">Documento</span><span class="sxs-lookup"><span data-stu-id="965e2-170">Document</span></span>|  
|<span data-ttu-id="965e2-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="965e2-171">ScrollBar</span></span>|<span data-ttu-id="965e2-172">Slider</span><span class="sxs-lookup"><span data-stu-id="965e2-172">Slider</span></span>|  
|<span data-ttu-id="965e2-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="965e2-173">msctls_trackbar32</span></span>|<span data-ttu-id="965e2-174">Slider</span><span class="sxs-lookup"><span data-stu-id="965e2-174">Slider</span></span>|  
|<span data-ttu-id="965e2-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="965e2-175">msctls_updown32</span></span>|<span data-ttu-id="965e2-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="965e2-176">Spinner</span></span>|  
|<span data-ttu-id="965e2-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="965e2-177">msctls_statusbar32</span></span>|<span data-ttu-id="965e2-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="965e2-178">StatusBar</span></span>|  
|<span data-ttu-id="965e2-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="965e2-179">SysTabControl32</span></span>|<span data-ttu-id="965e2-180">Tab</span><span class="sxs-lookup"><span data-stu-id="965e2-180">Tab</span></span>|  
|<span data-ttu-id="965e2-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="965e2-181">SysTabControl32</span></span>|<span data-ttu-id="965e2-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="965e2-182">TabItem</span></span>|  
|<span data-ttu-id="965e2-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="965e2-183">ToolbarWindow32</span></span>|<span data-ttu-id="965e2-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="965e2-184">ToolBar</span></span>|  
|<span data-ttu-id="965e2-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="965e2-185">ToolbarWindow32</span></span>|<span data-ttu-id="965e2-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="965e2-186">MenuItem</span></span>|  
|<span data-ttu-id="965e2-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="965e2-187">ToolbarWindow32</span></span>|<span data-ttu-id="965e2-188">Botón</span><span class="sxs-lookup"><span data-stu-id="965e2-188">Button</span></span>|  
|<span data-ttu-id="965e2-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="965e2-189">ToolbarWindow32</span></span>|<span data-ttu-id="965e2-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="965e2-190">CheckBox</span></span>|  
|<span data-ttu-id="965e2-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="965e2-191">ToolbarWindow32</span></span>|<span data-ttu-id="965e2-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="965e2-192">RadioButton</span></span>|  
|<span data-ttu-id="965e2-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="965e2-193">ToolbarWindow32</span></span>|<span data-ttu-id="965e2-194">Separador</span><span class="sxs-lookup"><span data-stu-id="965e2-194">Separator</span></span>|  
|<span data-ttu-id="965e2-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="965e2-195">tooltips_class32</span></span>|<span data-ttu-id="965e2-196">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="965e2-196">ToolTip</span></span>|  
|<span data-ttu-id="965e2-197">#32774</span><span class="sxs-lookup"><span data-stu-id="965e2-197">#32774</span></span>|<span data-ttu-id="965e2-198">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="965e2-198">ToolTip</span></span>|  
|<span data-ttu-id="965e2-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="965e2-199">ReBarWindow32</span></span>|<span data-ttu-id="965e2-200">Barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="965e2-200">Toolbar</span></span>|  
|<span data-ttu-id="965e2-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="965e2-201">SysTreeView32</span></span>|<span data-ttu-id="965e2-202">Árbol</span><span class="sxs-lookup"><span data-stu-id="965e2-202">Tree</span></span>|  
|<span data-ttu-id="965e2-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="965e2-203">SysTreeView32</span></span>|<span data-ttu-id="965e2-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="965e2-204">TreeItem</span></span>|  
  
 <span data-ttu-id="965e2-205">**Nota** El control RichEdit solo se admite para las versiones incluidas con [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (en RichEd20.dll versión 3.1 y posteriores, y MsftEdit.dll versión 4.1 y posteriores).</span><span class="sxs-lookup"><span data-stu-id="965e2-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="965e2-206">No se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="965e2-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="965e2-207">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="965e2-207">Class name</span></span>|<span data-ttu-id="965e2-208">Tipo de control</span><span class="sxs-lookup"><span data-stu-id="965e2-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="965e2-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="965e2-209">SysAnimate32</span></span>|<span data-ttu-id="965e2-210">Image</span><span class="sxs-lookup"><span data-stu-id="965e2-210">Image</span></span>|  
|<span data-ttu-id="965e2-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="965e2-211">SysPager</span></span>|<span data-ttu-id="965e2-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="965e2-212">Spinner</span></span>|  
|<span data-ttu-id="965e2-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="965e2-213">SysDateTimePick32</span></span>|<span data-ttu-id="965e2-214">Personalizados</span><span class="sxs-lookup"><span data-stu-id="965e2-214">Custom</span></span>|  
|<span data-ttu-id="965e2-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="965e2-215">SysMonthCal32</span></span>|<span data-ttu-id="965e2-216">Calendario</span><span class="sxs-lookup"><span data-stu-id="965e2-216">Calendar</span></span>|  
|<span data-ttu-id="965e2-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="965e2-217">MS_WINNOTE</span></span>|<span data-ttu-id="965e2-218">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="965e2-218">Tooltip</span></span>|  
|<span data-ttu-id="965e2-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="965e2-219">VBBubble</span></span>|<span data-ttu-id="965e2-220">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="965e2-220">Tooltip</span></span>|  
|<span data-ttu-id="965e2-221">ScrollBar (cuando se usa como control independiente)</span><span class="sxs-lookup"><span data-stu-id="965e2-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="965e2-222">Slider</span><span class="sxs-lookup"><span data-stu-id="965e2-222">Slider</span></span>|  
|<span data-ttu-id="965e2-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="965e2-223">SuperGrid</span></span>|<span data-ttu-id="965e2-224">Personalizados</span><span class="sxs-lookup"><span data-stu-id="965e2-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="965e2-225">Controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="965e2-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="965e2-226">Windows Forms controles se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de los proveedores del lado cliente en UIAutomationClientsideProviders. dll.</span><span class="sxs-lookup"><span data-stu-id="965e2-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="965e2-227">Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="965e2-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="965e2-228">Normalmente Windows Forms, los controles que son contenedores administrados [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] para controles comunes son compatibles [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]con.</span><span class="sxs-lookup"><span data-stu-id="965e2-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="965e2-229">Se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="965e2-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="965e2-230">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="965e2-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="965e2-231">Botón</span><span class="sxs-lookup"><span data-stu-id="965e2-231">Button</span></span>|  
|<span data-ttu-id="965e2-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="965e2-232">CheckBox</span></span>|  
|<span data-ttu-id="965e2-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="965e2-233">CheckedListBox</span></span>|  
|<span data-ttu-id="965e2-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="965e2-234">ColorDialog</span></span>|  
|<span data-ttu-id="965e2-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="965e2-235">ComboBox</span></span>|  
|<span data-ttu-id="965e2-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="965e2-236">FolderBrowser</span></span>|  
|<span data-ttu-id="965e2-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="965e2-237">FontDialog</span></span>|  
|<span data-ttu-id="965e2-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="965e2-238">GroupBox</span></span>|  
|<span data-ttu-id="965e2-239">HScrollBar</span><span class="sxs-lookup"><span data-stu-id="965e2-239">HscrollBar</span></span>|  
|<span data-ttu-id="965e2-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="965e2-240">ImageList</span></span>|  
|<span data-ttu-id="965e2-241">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="965e2-241">Label</span></span>|  
|<span data-ttu-id="965e2-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="965e2-242">ListBox</span></span>|  
|<span data-ttu-id="965e2-243">ListView</span><span class="sxs-lookup"><span data-stu-id="965e2-243">ListView</span></span>|  
|<span data-ttu-id="965e2-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="965e2-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="965e2-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="965e2-245">MonthCalendar</span></span>|  
|<span data-ttu-id="965e2-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="965e2-246">NotifyIcon</span></span>|  
|<span data-ttu-id="965e2-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="965e2-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="965e2-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="965e2-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="965e2-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="965e2-249">PrintDialog</span></span>|  
|<span data-ttu-id="965e2-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="965e2-250">ProgressBar</span></span>|  
|<span data-ttu-id="965e2-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="965e2-251">RadioButton</span></span>|  
|<span data-ttu-id="965e2-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="965e2-252">RichTextBox</span></span>|  
|<span data-ttu-id="965e2-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="965e2-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="965e2-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="965e2-254">ScrollableControl</span></span>|  
|<span data-ttu-id="965e2-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="965e2-255">SoundPlayer</span></span>|  
|<span data-ttu-id="965e2-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="965e2-256">StatusBar</span></span>|  
|<span data-ttu-id="965e2-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="965e2-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="965e2-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="965e2-258">TextBox</span></span>|  
|<span data-ttu-id="965e2-259">Temporizador</span><span class="sxs-lookup"><span data-stu-id="965e2-259">Timer</span></span>|  
|<span data-ttu-id="965e2-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="965e2-260">Toolbar</span></span>|  
|<span data-ttu-id="965e2-261">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="965e2-261">ToolTip</span></span>|  
|<span data-ttu-id="965e2-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="965e2-262">TrackBar</span></span>|  
|<span data-ttu-id="965e2-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="965e2-263">TreeView</span></span>|  
|<span data-ttu-id="965e2-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="965e2-264">VscrollBar</span></span>|  
|<span data-ttu-id="965e2-265">ExploradorWeb</span><span class="sxs-lookup"><span data-stu-id="965e2-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="965e2-266">Los siguientes controles se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo a través de la compatibilidad de Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="965e2-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="965e2-267">Es posible que algunas funciones no estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="965e2-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="965e2-268">Nombre del control</span><span class="sxs-lookup"><span data-stu-id="965e2-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="965e2-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="965e2-269">BindingSource</span></span>|  
|<span data-ttu-id="965e2-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="965e2-270">DataGrid</span></span>|  
|<span data-ttu-id="965e2-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="965e2-271">DataGridView</span></span>|  
|<span data-ttu-id="965e2-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="965e2-272">DataNavigator</span></span>|  
|<span data-ttu-id="965e2-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="965e2-273">DomainUpDown</span></span>|  
|<span data-ttu-id="965e2-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="965e2-274">ErrorProvider</span></span>|  
|<span data-ttu-id="965e2-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="965e2-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="965e2-276">Form</span><span class="sxs-lookup"><span data-stu-id="965e2-276">Form</span></span>|  
|<span data-ttu-id="965e2-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="965e2-277">LinkLabel</span></span>|  
|<span data-ttu-id="965e2-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="965e2-278">HelpProvider</span></span>|  
|<span data-ttu-id="965e2-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="965e2-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="965e2-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="965e2-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="965e2-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="965e2-281">NumericUpDown</span></span>|  
|<span data-ttu-id="965e2-282">Panel</span><span class="sxs-lookup"><span data-stu-id="965e2-282">Panel</span></span>|  
|<span data-ttu-id="965e2-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="965e2-283">PictureBox</span></span>|  
|<span data-ttu-id="965e2-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="965e2-284">PrintDocument</span></span>|  
|<span data-ttu-id="965e2-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="965e2-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="965e2-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="965e2-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="965e2-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="965e2-287">PropertyGrid</span></span>|  
|<span data-ttu-id="965e2-288">Control de usuario</span><span class="sxs-lookup"><span data-stu-id="965e2-288">UserControl</span></span>|  
|<span data-ttu-id="965e2-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="965e2-289">ToolStrip</span></span>|  
|<span data-ttu-id="965e2-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="965e2-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="965e2-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="965e2-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="965e2-292">Divisor</span><span class="sxs-lookup"><span data-stu-id="965e2-292">Splitter</span></span>|  
|<span data-ttu-id="965e2-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="965e2-293">RaftingContainer</span></span>|  
|<span data-ttu-id="965e2-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="965e2-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="965e2-295">Vea también</span><span class="sxs-lookup"><span data-stu-id="965e2-295">See also</span></span>

- [<span data-ttu-id="965e2-296">Tipos de control de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="965e2-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
