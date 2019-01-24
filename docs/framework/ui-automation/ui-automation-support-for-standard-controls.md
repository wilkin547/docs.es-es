---
title: Compatibilidad de UI Automation con controles estándar
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 9c5e4133a3bc1f019ada00299df929c2e3915880
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726590"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="5a356-102">Compatibilidad de UI Automation con controles estándar</span><span class="sxs-lookup"><span data-stu-id="5a356-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="5a356-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="5a356-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="5a356-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="5a356-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="5a356-105">En este tema se incluye información sobre la compatibilidad de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] con controles estándar en las aplicaciones desarrolladas para los marcos de trabajo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]y [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5a356-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="5a356-106">Controles de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="5a356-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="5a356-107">Todos los elementos de control [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] que ofrecen información o compatibilidad para la interacción del usuario tienen compatibilidad nativa completa con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a356-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="5a356-108">Otros elementos, como paneles, no son visibles para [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a356-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="5a356-109">Controles de Win32</span><span class="sxs-lookup"><span data-stu-id="5a356-109">Win32 Controls</span></span>  
 <span data-ttu-id="5a356-110">La mayoría de los controles [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de los proveedores del cliente en UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="5a356-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="5a356-111">Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="5a356-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="5a356-112">Solo se proporciona compatibilidad completa para controles desde la versión 6 de ComCtrl32.dll (disponibles con [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] y versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="5a356-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="5a356-113">Se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="5a356-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="5a356-114">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="5a356-114">Class name</span></span>|<span data-ttu-id="5a356-115">Tipo de control</span><span class="sxs-lookup"><span data-stu-id="5a356-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="5a356-116">Botón</span><span class="sxs-lookup"><span data-stu-id="5a356-116">Button</span></span>|<span data-ttu-id="5a356-117">Botón</span><span class="sxs-lookup"><span data-stu-id="5a356-117">Button</span></span>|  
|<span data-ttu-id="5a356-118">Botón</span><span class="sxs-lookup"><span data-stu-id="5a356-118">Button</span></span>|<span data-ttu-id="5a356-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="5a356-119">RadioButton</span></span>|  
|<span data-ttu-id="5a356-120">Botón</span><span class="sxs-lookup"><span data-stu-id="5a356-120">Button</span></span>|<span data-ttu-id="5a356-121">Agrupar</span><span class="sxs-lookup"><span data-stu-id="5a356-121">Group</span></span>|  
|<span data-ttu-id="5a356-122">Botón</span><span class="sxs-lookup"><span data-stu-id="5a356-122">Button</span></span>|<span data-ttu-id="5a356-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5a356-123">CheckBox</span></span>|  
|<span data-ttu-id="5a356-124">Botón</span><span class="sxs-lookup"><span data-stu-id="5a356-124">Button</span></span>|<span data-ttu-id="5a356-125">Hipervínculo</span><span class="sxs-lookup"><span data-stu-id="5a356-125">Hyperlink</span></span>|  
|<span data-ttu-id="5a356-126">Botón</span><span class="sxs-lookup"><span data-stu-id="5a356-126">Button</span></span>|<span data-ttu-id="5a356-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="5a356-127">SplitButton</span></span>|  
|<span data-ttu-id="5a356-128">Botón</span><span class="sxs-lookup"><span data-stu-id="5a356-128">Button</span></span>|<span data-ttu-id="5a356-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5a356-129">CheckBox</span></span>|  
|<span data-ttu-id="5a356-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="5a356-130">ComboBoxEx32</span></span>|<span data-ttu-id="5a356-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="5a356-131">ComboBox</span></span>|  
|<span data-ttu-id="5a356-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="5a356-132">ComboBox</span></span>|<span data-ttu-id="5a356-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="5a356-133">ComboBox</span></span>|  
|<span data-ttu-id="5a356-134">Editar</span><span class="sxs-lookup"><span data-stu-id="5a356-134">Edit</span></span>|<span data-ttu-id="5a356-135">Documento</span><span class="sxs-lookup"><span data-stu-id="5a356-135">Document</span></span>|  
|<span data-ttu-id="5a356-136">Editar</span><span class="sxs-lookup"><span data-stu-id="5a356-136">Edit</span></span>|<span data-ttu-id="5a356-137">Editar</span><span class="sxs-lookup"><span data-stu-id="5a356-137">Edit</span></span>|  
|<span data-ttu-id="5a356-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="5a356-138">SysLink</span></span>|<span data-ttu-id="5a356-139">Hipervínculo</span><span class="sxs-lookup"><span data-stu-id="5a356-139">Hyperlink</span></span>|  
|<span data-ttu-id="5a356-140">Estático</span><span class="sxs-lookup"><span data-stu-id="5a356-140">Static</span></span>|<span data-ttu-id="5a356-141">Texto</span><span class="sxs-lookup"><span data-stu-id="5a356-141">Text</span></span>|  
|<span data-ttu-id="5a356-142">Estático</span><span class="sxs-lookup"><span data-stu-id="5a356-142">Static</span></span>|<span data-ttu-id="5a356-143">Imagen</span><span class="sxs-lookup"><span data-stu-id="5a356-143">Image</span></span>|  
|<span data-ttu-id="5a356-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="5a356-144">SysIPAddress32</span></span>|<span data-ttu-id="5a356-145">Personalizados</span><span class="sxs-lookup"><span data-stu-id="5a356-145">Custom</span></span>|  
|<span data-ttu-id="5a356-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="5a356-146">SysHeader32</span></span>|<span data-ttu-id="5a356-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="5a356-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="5a356-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="5a356-148">SysListView32</span></span>|<span data-ttu-id="5a356-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="5a356-149">DataGrid</span></span>|  
|<span data-ttu-id="5a356-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="5a356-150">SysListView32</span></span>|<span data-ttu-id="5a356-151">Lista</span><span class="sxs-lookup"><span data-stu-id="5a356-151">List</span></span>|  
|<span data-ttu-id="5a356-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="5a356-152">ListBox</span></span>|<span data-ttu-id="5a356-153">Lista</span><span class="sxs-lookup"><span data-stu-id="5a356-153">List</span></span>|  
|<span data-ttu-id="5a356-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="5a356-154">ListBox</span></span>|<span data-ttu-id="5a356-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="5a356-155">ListItem</span></span>|  
|<span data-ttu-id="5a356-156">#32768</span><span class="sxs-lookup"><span data-stu-id="5a356-156">#32768</span></span>|<span data-ttu-id="5a356-157">Menú</span><span class="sxs-lookup"><span data-stu-id="5a356-157">Menu</span></span>|  
|<span data-ttu-id="5a356-158">#32768</span><span class="sxs-lookup"><span data-stu-id="5a356-158">#32768</span></span>|<span data-ttu-id="5a356-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="5a356-159">MenuItem</span></span>|  
|<span data-ttu-id="5a356-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="5a356-160">msctls_progress32</span></span>|<span data-ttu-id="5a356-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="5a356-161">ProgressBar</span></span>|  
|<span data-ttu-id="5a356-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="5a356-162">RichEdit</span></span>|<span data-ttu-id="5a356-163">Documento.</span><span class="sxs-lookup"><span data-stu-id="5a356-163">Document.</span></span> <span data-ttu-id="5a356-164">Vea la nota.</span><span class="sxs-lookup"><span data-stu-id="5a356-164">See note.</span></span>|  
|<span data-ttu-id="5a356-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="5a356-165">RichEdit20A</span></span>|<span data-ttu-id="5a356-166">Documento</span><span class="sxs-lookup"><span data-stu-id="5a356-166">Document</span></span>|  
|<span data-ttu-id="5a356-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="5a356-167">RichEdit20W</span></span>|<span data-ttu-id="5a356-168">Documento</span><span class="sxs-lookup"><span data-stu-id="5a356-168">Document</span></span>|  
|<span data-ttu-id="5a356-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="5a356-169">RichEdit50W</span></span>|<span data-ttu-id="5a356-170">Documento</span><span class="sxs-lookup"><span data-stu-id="5a356-170">Document</span></span>|  
|<span data-ttu-id="5a356-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="5a356-171">ScrollBar</span></span>|<span data-ttu-id="5a356-172">Slider</span><span class="sxs-lookup"><span data-stu-id="5a356-172">Slider</span></span>|  
|<span data-ttu-id="5a356-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="5a356-173">msctls_trackbar32</span></span>|<span data-ttu-id="5a356-174">Slider</span><span class="sxs-lookup"><span data-stu-id="5a356-174">Slider</span></span>|  
|<span data-ttu-id="5a356-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="5a356-175">msctls_updown32</span></span>|<span data-ttu-id="5a356-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="5a356-176">Spinner</span></span>|  
|<span data-ttu-id="5a356-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="5a356-177">msctls_statusbar32</span></span>|<span data-ttu-id="5a356-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="5a356-178">StatusBar</span></span>|  
|<span data-ttu-id="5a356-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="5a356-179">SysTabControl32</span></span>|<span data-ttu-id="5a356-180">Tab</span><span class="sxs-lookup"><span data-stu-id="5a356-180">Tab</span></span>|  
|<span data-ttu-id="5a356-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="5a356-181">SysTabControl32</span></span>|<span data-ttu-id="5a356-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="5a356-182">TabItem</span></span>|  
|<span data-ttu-id="5a356-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5a356-183">ToolbarWindow32</span></span>|<span data-ttu-id="5a356-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="5a356-184">ToolBar</span></span>|  
|<span data-ttu-id="5a356-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5a356-185">ToolbarWindow32</span></span>|<span data-ttu-id="5a356-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="5a356-186">MenuItem</span></span>|  
|<span data-ttu-id="5a356-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5a356-187">ToolbarWindow32</span></span>|<span data-ttu-id="5a356-188">Botón</span><span class="sxs-lookup"><span data-stu-id="5a356-188">Button</span></span>|  
|<span data-ttu-id="5a356-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5a356-189">ToolbarWindow32</span></span>|<span data-ttu-id="5a356-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5a356-190">CheckBox</span></span>|  
|<span data-ttu-id="5a356-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5a356-191">ToolbarWindow32</span></span>|<span data-ttu-id="5a356-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="5a356-192">RadioButton</span></span>|  
|<span data-ttu-id="5a356-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5a356-193">ToolbarWindow32</span></span>|<span data-ttu-id="5a356-194">Separador</span><span class="sxs-lookup"><span data-stu-id="5a356-194">Separator</span></span>|  
|<span data-ttu-id="5a356-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="5a356-195">tooltips_class32</span></span>|<span data-ttu-id="5a356-196">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="5a356-196">ToolTip</span></span>|  
|<span data-ttu-id="5a356-197">#32774</span><span class="sxs-lookup"><span data-stu-id="5a356-197">#32774</span></span>|<span data-ttu-id="5a356-198">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="5a356-198">ToolTip</span></span>|  
|<span data-ttu-id="5a356-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="5a356-199">ReBarWindow32</span></span>|<span data-ttu-id="5a356-200">Barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="5a356-200">Toolbar</span></span>|  
|<span data-ttu-id="5a356-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="5a356-201">SysTreeView32</span></span>|<span data-ttu-id="5a356-202">Árbol</span><span class="sxs-lookup"><span data-stu-id="5a356-202">Tree</span></span>|  
|<span data-ttu-id="5a356-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="5a356-203">SysTreeView32</span></span>|<span data-ttu-id="5a356-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="5a356-204">TreeItem</span></span>|  
  
 <span data-ttu-id="5a356-205">**Nota** El control RichEdit solo se admite para las versiones incluidas con [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (en RichEd20.dll versión 3.1 y posteriores, y MsftEdit.dll versión 4.1 y posteriores).</span><span class="sxs-lookup"><span data-stu-id="5a356-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="5a356-206">No se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="5a356-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="5a356-207">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="5a356-207">Class name</span></span>|<span data-ttu-id="5a356-208">Tipo de control</span><span class="sxs-lookup"><span data-stu-id="5a356-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="5a356-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="5a356-209">SysAnimate32</span></span>|<span data-ttu-id="5a356-210">Imagen</span><span class="sxs-lookup"><span data-stu-id="5a356-210">Image</span></span>|  
|<span data-ttu-id="5a356-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="5a356-211">SysPager</span></span>|<span data-ttu-id="5a356-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="5a356-212">Spinner</span></span>|  
|<span data-ttu-id="5a356-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="5a356-213">SysDateTimePick32</span></span>|<span data-ttu-id="5a356-214">Personalizados</span><span class="sxs-lookup"><span data-stu-id="5a356-214">Custom</span></span>|  
|<span data-ttu-id="5a356-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="5a356-215">SysMonthCal32</span></span>|<span data-ttu-id="5a356-216">Calendario</span><span class="sxs-lookup"><span data-stu-id="5a356-216">Calendar</span></span>|  
|<span data-ttu-id="5a356-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="5a356-217">MS_WINNOTE</span></span>|<span data-ttu-id="5a356-218">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="5a356-218">Tooltip</span></span>|  
|<span data-ttu-id="5a356-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="5a356-219">VBBubble</span></span>|<span data-ttu-id="5a356-220">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="5a356-220">Tooltip</span></span>|  
|<span data-ttu-id="5a356-221">ScrollBar (cuando se usa como control independiente)</span><span class="sxs-lookup"><span data-stu-id="5a356-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="5a356-222">Slider</span><span class="sxs-lookup"><span data-stu-id="5a356-222">Slider</span></span>|  
|<span data-ttu-id="5a356-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="5a356-223">SuperGrid</span></span>|<span data-ttu-id="5a356-224">Personalizados</span><span class="sxs-lookup"><span data-stu-id="5a356-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="5a356-225">Controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5a356-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="5a356-226">Controles de formularios Windows Forms se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de proveedores del lado cliente en UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="5a356-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="5a356-227">Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="5a356-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="5a356-228">Normalmente, los controles de Windows Forms que son contenedores administran para [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controles comunes son compatibles con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a356-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="5a356-229">Se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="5a356-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="5a356-230">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="5a356-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="5a356-231">Botón</span><span class="sxs-lookup"><span data-stu-id="5a356-231">Button</span></span>|  
|<span data-ttu-id="5a356-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5a356-232">CheckBox</span></span>|  
|<span data-ttu-id="5a356-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="5a356-233">CheckedListBox</span></span>|  
|<span data-ttu-id="5a356-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="5a356-234">ColorDialog</span></span>|  
|<span data-ttu-id="5a356-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="5a356-235">ComboBox</span></span>|  
|<span data-ttu-id="5a356-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="5a356-236">FolderBrowser</span></span>|  
|<span data-ttu-id="5a356-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="5a356-237">FontDialog</span></span>|  
|<span data-ttu-id="5a356-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="5a356-238">GroupBox</span></span>|  
|<span data-ttu-id="5a356-239">HScrollBar</span><span class="sxs-lookup"><span data-stu-id="5a356-239">HscrollBar</span></span>|  
|<span data-ttu-id="5a356-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="5a356-240">ImageList</span></span>|  
|<span data-ttu-id="5a356-241">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="5a356-241">Label</span></span>|  
|<span data-ttu-id="5a356-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="5a356-242">ListBox</span></span>|  
|<span data-ttu-id="5a356-243">ListView</span><span class="sxs-lookup"><span data-stu-id="5a356-243">ListView</span></span>|  
|<span data-ttu-id="5a356-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="5a356-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="5a356-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="5a356-245">MonthCalendar</span></span>|  
|<span data-ttu-id="5a356-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="5a356-246">NotifyIcon</span></span>|  
|<span data-ttu-id="5a356-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="5a356-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="5a356-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="5a356-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="5a356-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="5a356-249">PrintDialog</span></span>|  
|<span data-ttu-id="5a356-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="5a356-250">ProgressBar</span></span>|  
|<span data-ttu-id="5a356-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="5a356-251">RadioButton</span></span>|  
|<span data-ttu-id="5a356-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="5a356-252">RichTextBox</span></span>|  
|<span data-ttu-id="5a356-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="5a356-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="5a356-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="5a356-254">ScrollableControl</span></span>|  
|<span data-ttu-id="5a356-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="5a356-255">SoundPlayer</span></span>|  
|<span data-ttu-id="5a356-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="5a356-256">StatusBar</span></span>|  
|<span data-ttu-id="5a356-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="5a356-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="5a356-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="5a356-258">TextBox</span></span>|  
|<span data-ttu-id="5a356-259">Temporizador</span><span class="sxs-lookup"><span data-stu-id="5a356-259">Timer</span></span>|  
|<span data-ttu-id="5a356-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="5a356-260">Toolbar</span></span>|  
|<span data-ttu-id="5a356-261">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="5a356-261">ToolTip</span></span>|  
|<span data-ttu-id="5a356-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="5a356-262">TrackBar</span></span>|  
|<span data-ttu-id="5a356-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="5a356-263">TreeView</span></span>|  
|<span data-ttu-id="5a356-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="5a356-264">VscrollBar</span></span>|  
|<span data-ttu-id="5a356-265">ExploradorWeb</span><span class="sxs-lookup"><span data-stu-id="5a356-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="5a356-266">Los siguientes controles solo están expuestos a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de su compatibilidad con [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a356-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="5a356-267">Es posible que algunas funciones no estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="5a356-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="5a356-268">Nombre del control</span><span class="sxs-lookup"><span data-stu-id="5a356-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="5a356-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="5a356-269">BindingSource</span></span>|  
|<span data-ttu-id="5a356-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="5a356-270">DataGrid</span></span>|  
|<span data-ttu-id="5a356-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="5a356-271">DataGridView</span></span>|  
|<span data-ttu-id="5a356-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="5a356-272">DataNavigator</span></span>|  
|<span data-ttu-id="5a356-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="5a356-273">DomainUpDown</span></span>|  
|<span data-ttu-id="5a356-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="5a356-274">ErrorProvider</span></span>|  
|<span data-ttu-id="5a356-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5a356-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="5a356-276">Form</span><span class="sxs-lookup"><span data-stu-id="5a356-276">Form</span></span>|  
|<span data-ttu-id="5a356-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="5a356-277">LinkLabel</span></span>|  
|<span data-ttu-id="5a356-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="5a356-278">HelpProvider</span></span>|  
|<span data-ttu-id="5a356-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="5a356-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="5a356-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="5a356-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="5a356-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="5a356-281">NumericUpDown</span></span>|  
|<span data-ttu-id="5a356-282">Panel</span><span class="sxs-lookup"><span data-stu-id="5a356-282">Panel</span></span>|  
|<span data-ttu-id="5a356-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="5a356-283">PictureBox</span></span>|  
|<span data-ttu-id="5a356-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="5a356-284">PrintDocument</span></span>|  
|<span data-ttu-id="5a356-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="5a356-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="5a356-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="5a356-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="5a356-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="5a356-287">PropertyGrid</span></span>|  
|<span data-ttu-id="5a356-288">Control de usuario</span><span class="sxs-lookup"><span data-stu-id="5a356-288">UserControl</span></span>|  
|<span data-ttu-id="5a356-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="5a356-289">ToolStrip</span></span>|  
|<span data-ttu-id="5a356-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5a356-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="5a356-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="5a356-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="5a356-292">Divisor</span><span class="sxs-lookup"><span data-stu-id="5a356-292">Splitter</span></span>|  
|<span data-ttu-id="5a356-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="5a356-293">RaftingContainer</span></span>|  
|<span data-ttu-id="5a356-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="5a356-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a356-295">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a356-295">See also</span></span>
- [<span data-ttu-id="5a356-296">Tipos de control de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="5a356-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
