---
title: "Compatibilidad de UI Automation con controles estándar"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
caps.latest.revision: "11"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 71a5a2e4319debf1a4d8ddd08d7f0979443682b9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="966c9-102">Compatibilidad de UI Automation con controles estándar</span><span class="sxs-lookup"><span data-stu-id="966c9-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="966c9-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="966c9-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="966c9-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="966c9-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="966c9-105">En este tema se incluye información sobre la compatibilidad de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] con controles estándar en las aplicaciones desarrolladas para los marcos de trabajo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]y [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="966c9-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="966c9-106">Controles de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="966c9-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="966c9-107">Todos los elementos de control [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] que ofrecen información o compatibilidad para la interacción del usuario tienen compatibilidad nativa completa con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="966c9-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="966c9-108">Otros elementos, como paneles, no son visibles para [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="966c9-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="966c9-109">Controles de Win32</span><span class="sxs-lookup"><span data-stu-id="966c9-109">Win32 Controls</span></span>  
 <span data-ttu-id="966c9-110">La mayoría de los controles [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de los proveedores del cliente en UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="966c9-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="966c9-111">Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="966c9-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="966c9-112">Solo se proporciona compatibilidad completa para controles desde la versión 6 de ComCtrl32.dll (disponibles con [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] y versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="966c9-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="966c9-113">Se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="966c9-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="966c9-114">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="966c9-114">Class name</span></span>|<span data-ttu-id="966c9-115">Tipo de control</span><span class="sxs-lookup"><span data-stu-id="966c9-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="966c9-116">Botón</span><span class="sxs-lookup"><span data-stu-id="966c9-116">Button</span></span>|<span data-ttu-id="966c9-117">Botón</span><span class="sxs-lookup"><span data-stu-id="966c9-117">Button</span></span>|  
|<span data-ttu-id="966c9-118">Botón</span><span class="sxs-lookup"><span data-stu-id="966c9-118">Button</span></span>|<span data-ttu-id="966c9-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="966c9-119">RadioButton</span></span>|  
|<span data-ttu-id="966c9-120">Botón</span><span class="sxs-lookup"><span data-stu-id="966c9-120">Button</span></span>|<span data-ttu-id="966c9-121">Agrupar</span><span class="sxs-lookup"><span data-stu-id="966c9-121">Group</span></span>|  
|<span data-ttu-id="966c9-122">Botón</span><span class="sxs-lookup"><span data-stu-id="966c9-122">Button</span></span>|<span data-ttu-id="966c9-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="966c9-123">CheckBox</span></span>|  
|<span data-ttu-id="966c9-124">Botón</span><span class="sxs-lookup"><span data-stu-id="966c9-124">Button</span></span>|<span data-ttu-id="966c9-125">Hipervínculo</span><span class="sxs-lookup"><span data-stu-id="966c9-125">Hyperlink</span></span>|  
|<span data-ttu-id="966c9-126">Botón</span><span class="sxs-lookup"><span data-stu-id="966c9-126">Button</span></span>|<span data-ttu-id="966c9-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="966c9-127">SplitButton</span></span>|  
|<span data-ttu-id="966c9-128">Botón</span><span class="sxs-lookup"><span data-stu-id="966c9-128">Button</span></span>|<span data-ttu-id="966c9-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="966c9-129">CheckBox</span></span>|  
|<span data-ttu-id="966c9-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="966c9-130">ComboBoxEx32</span></span>|<span data-ttu-id="966c9-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="966c9-131">ComboBox</span></span>|  
|<span data-ttu-id="966c9-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="966c9-132">ComboBox</span></span>|<span data-ttu-id="966c9-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="966c9-133">ComboBox</span></span>|  
|<span data-ttu-id="966c9-134">Editar</span><span class="sxs-lookup"><span data-stu-id="966c9-134">Edit</span></span>|<span data-ttu-id="966c9-135">Documento</span><span class="sxs-lookup"><span data-stu-id="966c9-135">Document</span></span>|  
|<span data-ttu-id="966c9-136">Editar</span><span class="sxs-lookup"><span data-stu-id="966c9-136">Edit</span></span>|<span data-ttu-id="966c9-137">Editar</span><span class="sxs-lookup"><span data-stu-id="966c9-137">Edit</span></span>|  
|<span data-ttu-id="966c9-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="966c9-138">SysLink</span></span>|<span data-ttu-id="966c9-139">Hipervínculo</span><span class="sxs-lookup"><span data-stu-id="966c9-139">Hyperlink</span></span>|  
|<span data-ttu-id="966c9-140">Estático</span><span class="sxs-lookup"><span data-stu-id="966c9-140">Static</span></span>|<span data-ttu-id="966c9-141">Texto</span><span class="sxs-lookup"><span data-stu-id="966c9-141">Text</span></span>|  
|<span data-ttu-id="966c9-142">Estático</span><span class="sxs-lookup"><span data-stu-id="966c9-142">Static</span></span>|<span data-ttu-id="966c9-143">Imagen</span><span class="sxs-lookup"><span data-stu-id="966c9-143">Image</span></span>|  
|<span data-ttu-id="966c9-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="966c9-144">SysIPAddress32</span></span>|<span data-ttu-id="966c9-145">Personalizados</span><span class="sxs-lookup"><span data-stu-id="966c9-145">Custom</span></span>|  
|<span data-ttu-id="966c9-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="966c9-146">SysHeader32</span></span>|<span data-ttu-id="966c9-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="966c9-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="966c9-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="966c9-148">SysListView32</span></span>|<span data-ttu-id="966c9-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="966c9-149">DataGrid</span></span>|  
|<span data-ttu-id="966c9-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="966c9-150">SysListView32</span></span>|<span data-ttu-id="966c9-151">Lista</span><span class="sxs-lookup"><span data-stu-id="966c9-151">List</span></span>|  
|<span data-ttu-id="966c9-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="966c9-152">ListBox</span></span>|<span data-ttu-id="966c9-153">Lista</span><span class="sxs-lookup"><span data-stu-id="966c9-153">List</span></span>|  
|<span data-ttu-id="966c9-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="966c9-154">ListBox</span></span>|<span data-ttu-id="966c9-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="966c9-155">ListItem</span></span>|  
|<span data-ttu-id="966c9-156">#32768</span><span class="sxs-lookup"><span data-stu-id="966c9-156">#32768</span></span>|<span data-ttu-id="966c9-157">Menú</span><span class="sxs-lookup"><span data-stu-id="966c9-157">Menu</span></span>|  
|<span data-ttu-id="966c9-158">#32768</span><span class="sxs-lookup"><span data-stu-id="966c9-158">#32768</span></span>|<span data-ttu-id="966c9-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="966c9-159">MenuItem</span></span>|  
|<span data-ttu-id="966c9-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="966c9-160">msctls_progress32</span></span>|<span data-ttu-id="966c9-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="966c9-161">ProgressBar</span></span>|  
|<span data-ttu-id="966c9-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="966c9-162">RichEdit</span></span>|<span data-ttu-id="966c9-163">Documento.</span><span class="sxs-lookup"><span data-stu-id="966c9-163">Document.</span></span> <span data-ttu-id="966c9-164">Vea la nota.</span><span class="sxs-lookup"><span data-stu-id="966c9-164">See note.</span></span>|  
|<span data-ttu-id="966c9-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="966c9-165">RichEdit20A</span></span>|<span data-ttu-id="966c9-166">Documento</span><span class="sxs-lookup"><span data-stu-id="966c9-166">Document</span></span>|  
|<span data-ttu-id="966c9-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="966c9-167">RichEdit20W</span></span>|<span data-ttu-id="966c9-168">Documento</span><span class="sxs-lookup"><span data-stu-id="966c9-168">Document</span></span>|  
|<span data-ttu-id="966c9-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="966c9-169">RichEdit50W</span></span>|<span data-ttu-id="966c9-170">Documento</span><span class="sxs-lookup"><span data-stu-id="966c9-170">Document</span></span>|  
|<span data-ttu-id="966c9-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="966c9-171">ScrollBar</span></span>|<span data-ttu-id="966c9-172">Slider</span><span class="sxs-lookup"><span data-stu-id="966c9-172">Slider</span></span>|  
|<span data-ttu-id="966c9-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="966c9-173">msctls_trackbar32</span></span>|<span data-ttu-id="966c9-174">Slider</span><span class="sxs-lookup"><span data-stu-id="966c9-174">Slider</span></span>|  
|<span data-ttu-id="966c9-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="966c9-175">msctls_updown32</span></span>|<span data-ttu-id="966c9-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="966c9-176">Spinner</span></span>|  
|<span data-ttu-id="966c9-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="966c9-177">msctls_statusbar32</span></span>|<span data-ttu-id="966c9-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="966c9-178">StatusBar</span></span>|  
|<span data-ttu-id="966c9-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="966c9-179">SysTabControl32</span></span>|<span data-ttu-id="966c9-180">Tab</span><span class="sxs-lookup"><span data-stu-id="966c9-180">Tab</span></span>|  
|<span data-ttu-id="966c9-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="966c9-181">SysTabControl32</span></span>|<span data-ttu-id="966c9-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="966c9-182">TabItem</span></span>|  
|<span data-ttu-id="966c9-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="966c9-183">ToolbarWindow32</span></span>|<span data-ttu-id="966c9-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="966c9-184">ToolBar</span></span>|  
|<span data-ttu-id="966c9-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="966c9-185">ToolbarWindow32</span></span>|<span data-ttu-id="966c9-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="966c9-186">MenuItem</span></span>|  
|<span data-ttu-id="966c9-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="966c9-187">ToolbarWindow32</span></span>|<span data-ttu-id="966c9-188">Botón</span><span class="sxs-lookup"><span data-stu-id="966c9-188">Button</span></span>|  
|<span data-ttu-id="966c9-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="966c9-189">ToolbarWindow32</span></span>|<span data-ttu-id="966c9-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="966c9-190">CheckBox</span></span>|  
|<span data-ttu-id="966c9-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="966c9-191">ToolbarWindow32</span></span>|<span data-ttu-id="966c9-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="966c9-192">RadioButton</span></span>|  
|<span data-ttu-id="966c9-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="966c9-193">ToolbarWindow32</span></span>|<span data-ttu-id="966c9-194">Separador</span><span class="sxs-lookup"><span data-stu-id="966c9-194">Separator</span></span>|  
|<span data-ttu-id="966c9-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="966c9-195">tooltips_class32</span></span>|<span data-ttu-id="966c9-196">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="966c9-196">ToolTip</span></span>|  
|<span data-ttu-id="966c9-197">#32774</span><span class="sxs-lookup"><span data-stu-id="966c9-197">#32774</span></span>|<span data-ttu-id="966c9-198">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="966c9-198">ToolTip</span></span>|  
|<span data-ttu-id="966c9-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="966c9-199">ReBarWindow32</span></span>|<span data-ttu-id="966c9-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="966c9-200">Toolbar</span></span>|  
|<span data-ttu-id="966c9-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="966c9-201">SysTreeView32</span></span>|<span data-ttu-id="966c9-202">Árbol</span><span class="sxs-lookup"><span data-stu-id="966c9-202">Tree</span></span>|  
|<span data-ttu-id="966c9-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="966c9-203">SysTreeView32</span></span>|<span data-ttu-id="966c9-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="966c9-204">TreeItem</span></span>|  
  
 <span data-ttu-id="966c9-205">**Nota** El control RichEdit solo se admite para las versiones incluidas con [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (en RichEd20.dll versión 3.1 y posteriores, y MsftEdit.dll versión 4.1 y posteriores).</span><span class="sxs-lookup"><span data-stu-id="966c9-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="966c9-206">No se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="966c9-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="966c9-207">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="966c9-207">Class name</span></span>|<span data-ttu-id="966c9-208">Tipo de control</span><span class="sxs-lookup"><span data-stu-id="966c9-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="966c9-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="966c9-209">SysAnimate32</span></span>|<span data-ttu-id="966c9-210">Imagen</span><span class="sxs-lookup"><span data-stu-id="966c9-210">Image</span></span>|  
|<span data-ttu-id="966c9-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="966c9-211">SysPager</span></span>|<span data-ttu-id="966c9-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="966c9-212">Spinner</span></span>|  
|<span data-ttu-id="966c9-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="966c9-213">SysDateTimePick32</span></span>|<span data-ttu-id="966c9-214">Personalizados</span><span class="sxs-lookup"><span data-stu-id="966c9-214">Custom</span></span>|  
|<span data-ttu-id="966c9-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="966c9-215">SysMonthCal32</span></span>|<span data-ttu-id="966c9-216">Calendario</span><span class="sxs-lookup"><span data-stu-id="966c9-216">Calendar</span></span>|  
|<span data-ttu-id="966c9-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="966c9-217">MS_WINNOTE</span></span>|<span data-ttu-id="966c9-218">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="966c9-218">Tooltip</span></span>|  
|<span data-ttu-id="966c9-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="966c9-219">VBBubble</span></span>|<span data-ttu-id="966c9-220">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="966c9-220">Tooltip</span></span>|  
|<span data-ttu-id="966c9-221">ScrollBar (cuando se usa como control independiente)</span><span class="sxs-lookup"><span data-stu-id="966c9-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="966c9-222">Slider</span><span class="sxs-lookup"><span data-stu-id="966c9-222">Slider</span></span>|  
|<span data-ttu-id="966c9-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="966c9-223">SuperGrid</span></span>|<span data-ttu-id="966c9-224">Personalizados</span><span class="sxs-lookup"><span data-stu-id="966c9-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="966c9-225">Controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="966c9-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="966c9-226">Los controles[!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de los proveedores del cliente en UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="966c9-226">[!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="966c9-227">Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="966c9-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="966c9-228">Normalmente, los controles [!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] que son contenedores administrado para controles comunes [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] son compatibles con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="966c9-228">Typically, [!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="966c9-229">Se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="966c9-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="966c9-230">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="966c9-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="966c9-231">Botón</span><span class="sxs-lookup"><span data-stu-id="966c9-231">Button</span></span>|  
|<span data-ttu-id="966c9-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="966c9-232">CheckBox</span></span>|  
|<span data-ttu-id="966c9-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="966c9-233">CheckedListBox</span></span>|  
|<span data-ttu-id="966c9-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="966c9-234">ColorDialog</span></span>|  
|<span data-ttu-id="966c9-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="966c9-235">ComboBox</span></span>|  
|<span data-ttu-id="966c9-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="966c9-236">FolderBrowser</span></span>|  
|<span data-ttu-id="966c9-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="966c9-237">FontDialog</span></span>|  
|<span data-ttu-id="966c9-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="966c9-238">GroupBox</span></span>|  
|<span data-ttu-id="966c9-239">HScrollBar</span><span class="sxs-lookup"><span data-stu-id="966c9-239">HscrollBar</span></span>|  
|<span data-ttu-id="966c9-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="966c9-240">ImageList</span></span>|  
|<span data-ttu-id="966c9-241">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="966c9-241">Label</span></span>|  
|<span data-ttu-id="966c9-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="966c9-242">ListBox</span></span>|  
|<span data-ttu-id="966c9-243">ListView</span><span class="sxs-lookup"><span data-stu-id="966c9-243">ListView</span></span>|  
|<span data-ttu-id="966c9-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="966c9-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="966c9-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="966c9-245">MonthCalendar</span></span>|  
|<span data-ttu-id="966c9-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="966c9-246">NotifyIcon</span></span>|  
|<span data-ttu-id="966c9-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="966c9-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="966c9-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="966c9-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="966c9-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="966c9-249">PrintDialog</span></span>|  
|<span data-ttu-id="966c9-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="966c9-250">ProgressBar</span></span>|  
|<span data-ttu-id="966c9-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="966c9-251">RadioButton</span></span>|  
|<span data-ttu-id="966c9-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="966c9-252">RichTextBox</span></span>|  
|<span data-ttu-id="966c9-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="966c9-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="966c9-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="966c9-254">ScrollableControl</span></span>|  
|<span data-ttu-id="966c9-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="966c9-255">SoundPlayer</span></span>|  
|<span data-ttu-id="966c9-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="966c9-256">StatusBar</span></span>|  
|<span data-ttu-id="966c9-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="966c9-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="966c9-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="966c9-258">TextBox</span></span>|  
|<span data-ttu-id="966c9-259">Temporizador</span><span class="sxs-lookup"><span data-stu-id="966c9-259">Timer</span></span>|  
|<span data-ttu-id="966c9-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="966c9-260">Toolbar</span></span>|  
|<span data-ttu-id="966c9-261">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="966c9-261">ToolTip</span></span>|  
|<span data-ttu-id="966c9-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="966c9-262">TrackBar</span></span>|  
|<span data-ttu-id="966c9-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="966c9-263">TreeView</span></span>|  
|<span data-ttu-id="966c9-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="966c9-264">VscrollBar</span></span>|  
|<span data-ttu-id="966c9-265">ExploradorWeb</span><span class="sxs-lookup"><span data-stu-id="966c9-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="966c9-266">Los siguientes controles solo están expuestos a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de su compatibilidad con [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="966c9-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="966c9-267">Es posible que algunas funciones no estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="966c9-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="966c9-268">Nombre del control</span><span class="sxs-lookup"><span data-stu-id="966c9-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="966c9-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="966c9-269">BindingSource</span></span>|  
|<span data-ttu-id="966c9-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="966c9-270">DataGrid</span></span>|  
|<span data-ttu-id="966c9-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="966c9-271">DataGridView</span></span>|  
|<span data-ttu-id="966c9-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="966c9-272">DataNavigator</span></span>|  
|<span data-ttu-id="966c9-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="966c9-273">DomainUpDown</span></span>|  
|<span data-ttu-id="966c9-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="966c9-274">ErrorProvider</span></span>|  
|<span data-ttu-id="966c9-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="966c9-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="966c9-276">Form</span><span class="sxs-lookup"><span data-stu-id="966c9-276">Form</span></span>|  
|<span data-ttu-id="966c9-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="966c9-277">LinkLabel</span></span>|  
|<span data-ttu-id="966c9-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="966c9-278">HelpProvider</span></span>|  
|<span data-ttu-id="966c9-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="966c9-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="966c9-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="966c9-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="966c9-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="966c9-281">NumericUpDown</span></span>|  
|<span data-ttu-id="966c9-282">Panel</span><span class="sxs-lookup"><span data-stu-id="966c9-282">Panel</span></span>|  
|<span data-ttu-id="966c9-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="966c9-283">PictureBox</span></span>|  
|<span data-ttu-id="966c9-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="966c9-284">PrintDocument</span></span>|  
|<span data-ttu-id="966c9-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="966c9-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="966c9-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="966c9-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="966c9-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="966c9-287">PropertyGrid</span></span>|  
|<span data-ttu-id="966c9-288">Control de usuario</span><span class="sxs-lookup"><span data-stu-id="966c9-288">UserControl</span></span>|  
|<span data-ttu-id="966c9-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="966c9-289">ToolStrip</span></span>|  
|<span data-ttu-id="966c9-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="966c9-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="966c9-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="966c9-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="966c9-292">Divisor</span><span class="sxs-lookup"><span data-stu-id="966c9-292">Splitter</span></span>|  
|<span data-ttu-id="966c9-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="966c9-293">RaftingContainer</span></span>|  
|<span data-ttu-id="966c9-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="966c9-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="966c9-295">Vea también</span><span class="sxs-lookup"><span data-stu-id="966c9-295">See Also</span></span>  
 [<span data-ttu-id="966c9-296">UI Automation Control Types</span><span class="sxs-lookup"><span data-stu-id="966c9-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
