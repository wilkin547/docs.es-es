---
title: Compatibilidad de UI Automation con controles estándar
description: Obtenga información sobre la compatibilidad de la automatización de la interfaz de usuario para los controles estándar en las aplicaciones desarrolladas para Windows Presentation Foundation (WPF), Win32 y Windows Forms.
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 0a5a0b61a6492d9efb62799fa610859b247cf26e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261077"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="d8250-103">Compatibilidad de UI Automation con controles estándar</span><span class="sxs-lookup"><span data-stu-id="d8250-103">UI Automation Support for Standard Controls</span></span>

> [!NOTE]
> <span data-ttu-id="d8250-104">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="d8250-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d8250-105">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="d8250-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="d8250-106">Este tema contiene información sobre [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] la compatibilidad con los controles estándar de las aplicaciones desarrolladas para los [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] marcos de trabajo, Win32 y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d8250-106">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>

## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="d8250-107">Controles de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="d8250-107">Windows Presentation Foundation Controls</span></span>  

 <span data-ttu-id="d8250-108">Todos los elementos de control [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] que ofrecen información o compatibilidad para la interacción del usuario tienen compatibilidad nativa completa con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8250-108">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="d8250-109">Otros elementos, como paneles, no son visibles para [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8250-109">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>

## <a name="win32-controls"></a><span data-ttu-id="d8250-110">Controles de Win32</span><span class="sxs-lookup"><span data-stu-id="d8250-110">Win32 Controls</span></span>  

 <span data-ttu-id="d8250-111">La mayoría de los controles Win32 se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de los proveedores del lado cliente en UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="d8250-111">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="d8250-112">Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="d8250-112">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="d8250-113">Solo se proporciona compatibilidad completa con los controles de la versión 6 de *ComCtrl32.dll*.</span><span class="sxs-lookup"><span data-stu-id="d8250-113">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="d8250-114">Se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="d8250-114">The following controls are supported.</span></span>  
  
|<span data-ttu-id="d8250-115">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="d8250-115">Class name</span></span>|<span data-ttu-id="d8250-116">Tipo de control</span><span class="sxs-lookup"><span data-stu-id="d8250-116">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="d8250-117">Button</span><span class="sxs-lookup"><span data-stu-id="d8250-117">Button</span></span>|<span data-ttu-id="d8250-118">Button</span><span class="sxs-lookup"><span data-stu-id="d8250-118">Button</span></span>|  
|<span data-ttu-id="d8250-119">Button</span><span class="sxs-lookup"><span data-stu-id="d8250-119">Button</span></span>|<span data-ttu-id="d8250-120">RadioButton</span><span class="sxs-lookup"><span data-stu-id="d8250-120">RadioButton</span></span>|  
|<span data-ttu-id="d8250-121">Botón</span><span class="sxs-lookup"><span data-stu-id="d8250-121">Button</span></span>|<span data-ttu-id="d8250-122">Grupo</span><span class="sxs-lookup"><span data-stu-id="d8250-122">Group</span></span>|  
|<span data-ttu-id="d8250-123">Botón</span><span class="sxs-lookup"><span data-stu-id="d8250-123">Button</span></span>|<span data-ttu-id="d8250-124">CheckBox</span><span class="sxs-lookup"><span data-stu-id="d8250-124">CheckBox</span></span>|  
|<span data-ttu-id="d8250-125">Botón</span><span class="sxs-lookup"><span data-stu-id="d8250-125">Button</span></span>|<span data-ttu-id="d8250-126">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="d8250-126">Hyperlink</span></span>|  
|<span data-ttu-id="d8250-127">Botón</span><span class="sxs-lookup"><span data-stu-id="d8250-127">Button</span></span>|<span data-ttu-id="d8250-128">SplitButton</span><span class="sxs-lookup"><span data-stu-id="d8250-128">SplitButton</span></span>|  
|<span data-ttu-id="d8250-129">Botón</span><span class="sxs-lookup"><span data-stu-id="d8250-129">Button</span></span>|<span data-ttu-id="d8250-130">CheckBox</span><span class="sxs-lookup"><span data-stu-id="d8250-130">CheckBox</span></span>|  
|<span data-ttu-id="d8250-131">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="d8250-131">ComboBoxEx32</span></span>|<span data-ttu-id="d8250-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="d8250-132">ComboBox</span></span>|  
|<span data-ttu-id="d8250-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="d8250-133">ComboBox</span></span>|<span data-ttu-id="d8250-134">ComboBox</span><span class="sxs-lookup"><span data-stu-id="d8250-134">ComboBox</span></span>|  
|<span data-ttu-id="d8250-135">Editar</span><span class="sxs-lookup"><span data-stu-id="d8250-135">Edit</span></span>|<span data-ttu-id="d8250-136">Documento</span><span class="sxs-lookup"><span data-stu-id="d8250-136">Document</span></span>|  
|<span data-ttu-id="d8250-137">Editar</span><span class="sxs-lookup"><span data-stu-id="d8250-137">Edit</span></span>|<span data-ttu-id="d8250-138">Editar</span><span class="sxs-lookup"><span data-stu-id="d8250-138">Edit</span></span>|  
|<span data-ttu-id="d8250-139">SysLink</span><span class="sxs-lookup"><span data-stu-id="d8250-139">SysLink</span></span>|<span data-ttu-id="d8250-140">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="d8250-140">Hyperlink</span></span>|  
|<span data-ttu-id="d8250-141">Estático</span><span class="sxs-lookup"><span data-stu-id="d8250-141">Static</span></span>|<span data-ttu-id="d8250-142">Texto</span><span class="sxs-lookup"><span data-stu-id="d8250-142">Text</span></span>|  
|<span data-ttu-id="d8250-143">Estático</span><span class="sxs-lookup"><span data-stu-id="d8250-143">Static</span></span>|<span data-ttu-id="d8250-144">Imagen</span><span class="sxs-lookup"><span data-stu-id="d8250-144">Image</span></span>|  
|<span data-ttu-id="d8250-145">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="d8250-145">SysIPAddress32</span></span>|<span data-ttu-id="d8250-146">Personalizados</span><span class="sxs-lookup"><span data-stu-id="d8250-146">Custom</span></span>|  
|<span data-ttu-id="d8250-147">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="d8250-147">SysHeader32</span></span>|<span data-ttu-id="d8250-148">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="d8250-148">Header/HeaderItem</span></span>|  
|<span data-ttu-id="d8250-149">SysListView32</span><span class="sxs-lookup"><span data-stu-id="d8250-149">SysListView32</span></span>|<span data-ttu-id="d8250-150">DataGrid</span><span class="sxs-lookup"><span data-stu-id="d8250-150">DataGrid</span></span>|  
|<span data-ttu-id="d8250-151">SysListView32</span><span class="sxs-lookup"><span data-stu-id="d8250-151">SysListView32</span></span>|<span data-ttu-id="d8250-152">List</span><span class="sxs-lookup"><span data-stu-id="d8250-152">List</span></span>|  
|<span data-ttu-id="d8250-153">ListBox</span><span class="sxs-lookup"><span data-stu-id="d8250-153">ListBox</span></span>|<span data-ttu-id="d8250-154">List</span><span class="sxs-lookup"><span data-stu-id="d8250-154">List</span></span>|  
|<span data-ttu-id="d8250-155">ListBox</span><span class="sxs-lookup"><span data-stu-id="d8250-155">ListBox</span></span>|<span data-ttu-id="d8250-156">ListItem</span><span class="sxs-lookup"><span data-stu-id="d8250-156">ListItem</span></span>|  
|<span data-ttu-id="d8250-157">#32768</span><span class="sxs-lookup"><span data-stu-id="d8250-157">#32768</span></span>|<span data-ttu-id="d8250-158">Menú</span><span class="sxs-lookup"><span data-stu-id="d8250-158">Menu</span></span>|  
|<span data-ttu-id="d8250-159">#32768</span><span class="sxs-lookup"><span data-stu-id="d8250-159">#32768</span></span>|<span data-ttu-id="d8250-160">MenuItem</span><span class="sxs-lookup"><span data-stu-id="d8250-160">MenuItem</span></span>|  
|<span data-ttu-id="d8250-161">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="d8250-161">msctls_progress32</span></span>|<span data-ttu-id="d8250-162">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="d8250-162">ProgressBar</span></span>|  
|<span data-ttu-id="d8250-163">RichEdit</span><span class="sxs-lookup"><span data-stu-id="d8250-163">RichEdit</span></span>|<span data-ttu-id="d8250-164">Documentar.</span><span class="sxs-lookup"><span data-stu-id="d8250-164">Document.</span></span> <span data-ttu-id="d8250-165">Ver nota.</span><span class="sxs-lookup"><span data-stu-id="d8250-165">See note.</span></span>|  
|<span data-ttu-id="d8250-166">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="d8250-166">RichEdit20A</span></span>|<span data-ttu-id="d8250-167">Documento</span><span class="sxs-lookup"><span data-stu-id="d8250-167">Document</span></span>|  
|<span data-ttu-id="d8250-168">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="d8250-168">RichEdit20W</span></span>|<span data-ttu-id="d8250-169">Documento</span><span class="sxs-lookup"><span data-stu-id="d8250-169">Document</span></span>|  
|<span data-ttu-id="d8250-170">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="d8250-170">RichEdit50W</span></span>|<span data-ttu-id="d8250-171">Documento</span><span class="sxs-lookup"><span data-stu-id="d8250-171">Document</span></span>|  
|<span data-ttu-id="d8250-172">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="d8250-172">ScrollBar</span></span>|<span data-ttu-id="d8250-173">Control deslizante</span><span class="sxs-lookup"><span data-stu-id="d8250-173">Slider</span></span>|  
|<span data-ttu-id="d8250-174">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="d8250-174">msctls_trackbar32</span></span>|<span data-ttu-id="d8250-175">Control deslizante</span><span class="sxs-lookup"><span data-stu-id="d8250-175">Slider</span></span>|  
|<span data-ttu-id="d8250-176">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="d8250-176">msctls_updown32</span></span>|<span data-ttu-id="d8250-177">Spinner</span><span class="sxs-lookup"><span data-stu-id="d8250-177">Spinner</span></span>|  
|<span data-ttu-id="d8250-178">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="d8250-178">msctls_statusbar32</span></span>|<span data-ttu-id="d8250-179">StatusBar</span><span class="sxs-lookup"><span data-stu-id="d8250-179">StatusBar</span></span>|  
|<span data-ttu-id="d8250-180">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="d8250-180">SysTabControl32</span></span>|<span data-ttu-id="d8250-181">Pestaña</span><span class="sxs-lookup"><span data-stu-id="d8250-181">Tab</span></span>|  
|<span data-ttu-id="d8250-182">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="d8250-182">SysTabControl32</span></span>|<span data-ttu-id="d8250-183">TabItem</span><span class="sxs-lookup"><span data-stu-id="d8250-183">TabItem</span></span>|  
|<span data-ttu-id="d8250-184">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d8250-184">ToolbarWindow32</span></span>|<span data-ttu-id="d8250-185">ToolBar</span><span class="sxs-lookup"><span data-stu-id="d8250-185">ToolBar</span></span>|  
|<span data-ttu-id="d8250-186">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d8250-186">ToolbarWindow32</span></span>|<span data-ttu-id="d8250-187">MenuItem</span><span class="sxs-lookup"><span data-stu-id="d8250-187">MenuItem</span></span>|  
|<span data-ttu-id="d8250-188">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d8250-188">ToolbarWindow32</span></span>|<span data-ttu-id="d8250-189">Botón</span><span class="sxs-lookup"><span data-stu-id="d8250-189">Button</span></span>|  
|<span data-ttu-id="d8250-190">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d8250-190">ToolbarWindow32</span></span>|<span data-ttu-id="d8250-191">CheckBox</span><span class="sxs-lookup"><span data-stu-id="d8250-191">CheckBox</span></span>|  
|<span data-ttu-id="d8250-192">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d8250-192">ToolbarWindow32</span></span>|<span data-ttu-id="d8250-193">RadioButton</span><span class="sxs-lookup"><span data-stu-id="d8250-193">RadioButton</span></span>|  
|<span data-ttu-id="d8250-194">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d8250-194">ToolbarWindow32</span></span>|<span data-ttu-id="d8250-195">Separador</span><span class="sxs-lookup"><span data-stu-id="d8250-195">Separator</span></span>|  
|<span data-ttu-id="d8250-196">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="d8250-196">tooltips_class32</span></span>|<span data-ttu-id="d8250-197">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="d8250-197">ToolTip</span></span>|  
|<span data-ttu-id="d8250-198">#32774</span><span class="sxs-lookup"><span data-stu-id="d8250-198">#32774</span></span>|<span data-ttu-id="d8250-199">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="d8250-199">ToolTip</span></span>|  
|<span data-ttu-id="d8250-200">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="d8250-200">ReBarWindow32</span></span>|<span data-ttu-id="d8250-201">Barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="d8250-201">Toolbar</span></span>|  
|<span data-ttu-id="d8250-202">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="d8250-202">SysTreeView32</span></span>|<span data-ttu-id="d8250-203">Árbol</span><span class="sxs-lookup"><span data-stu-id="d8250-203">Tree</span></span>|  
|<span data-ttu-id="d8250-204">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="d8250-204">SysTreeView32</span></span>|<span data-ttu-id="d8250-205">TreeItem</span><span class="sxs-lookup"><span data-stu-id="d8250-205">TreeItem</span></span>|  
  
 <span data-ttu-id="d8250-206">**Nota:** El control RichEdit solo se admite para las versiones incluidas con Windows Vista (en RichEd20.dll versión 3,1 y posteriores, y MsftEdit.dll versión 4,1 y posteriores).</span><span class="sxs-lookup"><span data-stu-id="d8250-206">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="d8250-207">No se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="d8250-207">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="d8250-208">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="d8250-208">Class name</span></span>|<span data-ttu-id="d8250-209">Tipo de control</span><span class="sxs-lookup"><span data-stu-id="d8250-209">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="d8250-210">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="d8250-210">SysAnimate32</span></span>|<span data-ttu-id="d8250-211">Imagen</span><span class="sxs-lookup"><span data-stu-id="d8250-211">Image</span></span>|  
|<span data-ttu-id="d8250-212">SysPager</span><span class="sxs-lookup"><span data-stu-id="d8250-212">SysPager</span></span>|<span data-ttu-id="d8250-213">Spinner</span><span class="sxs-lookup"><span data-stu-id="d8250-213">Spinner</span></span>|  
|<span data-ttu-id="d8250-214">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="d8250-214">SysDateTimePick32</span></span>|<span data-ttu-id="d8250-215">Personalizados</span><span class="sxs-lookup"><span data-stu-id="d8250-215">Custom</span></span>|  
|<span data-ttu-id="d8250-216">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="d8250-216">SysMonthCal32</span></span>|<span data-ttu-id="d8250-217">Calendario</span><span class="sxs-lookup"><span data-stu-id="d8250-217">Calendar</span></span>|  
|<span data-ttu-id="d8250-218">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="d8250-218">MS_WINNOTE</span></span>|<span data-ttu-id="d8250-219">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="d8250-219">Tooltip</span></span>|  
|<span data-ttu-id="d8250-220">VBBubble</span><span class="sxs-lookup"><span data-stu-id="d8250-220">VBBubble</span></span>|<span data-ttu-id="d8250-221">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="d8250-221">Tooltip</span></span>|  
|<span data-ttu-id="d8250-222">ScrollBar (cuando se usa como control independiente)</span><span class="sxs-lookup"><span data-stu-id="d8250-222">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="d8250-223">Control deslizante</span><span class="sxs-lookup"><span data-stu-id="d8250-223">Slider</span></span>|  
|<span data-ttu-id="d8250-224">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="d8250-224">SuperGrid</span></span>|<span data-ttu-id="d8250-225">Personalizados</span><span class="sxs-lookup"><span data-stu-id="d8250-225">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>

## <a name="windows-forms-controls"></a><span data-ttu-id="d8250-226">Controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d8250-226">Windows Forms Controls</span></span>  

 <span data-ttu-id="d8250-227">Windows Forms controles se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de los proveedores del lado cliente en UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="d8250-227">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="d8250-228">Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="d8250-228">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="d8250-229">Normalmente, se admiten Windows Forms controles que son contenedores administrados para controles comunes Win32 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8250-229">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="d8250-230">Se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="d8250-230">The following controls are supported.</span></span>  
  
|<span data-ttu-id="d8250-231">Class Name (Nombre de clase)</span><span class="sxs-lookup"><span data-stu-id="d8250-231">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="d8250-232">Botón</span><span class="sxs-lookup"><span data-stu-id="d8250-232">Button</span></span>|  
|<span data-ttu-id="d8250-233">CheckBox</span><span class="sxs-lookup"><span data-stu-id="d8250-233">CheckBox</span></span>|  
|<span data-ttu-id="d8250-234">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="d8250-234">CheckedListBox</span></span>|  
|<span data-ttu-id="d8250-235">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="d8250-235">ColorDialog</span></span>|  
|<span data-ttu-id="d8250-236">ComboBox</span><span class="sxs-lookup"><span data-stu-id="d8250-236">ComboBox</span></span>|  
|<span data-ttu-id="d8250-237">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="d8250-237">FolderBrowser</span></span>|  
|<span data-ttu-id="d8250-238">FontDialog</span><span class="sxs-lookup"><span data-stu-id="d8250-238">FontDialog</span></span>|  
|<span data-ttu-id="d8250-239">GroupBox</span><span class="sxs-lookup"><span data-stu-id="d8250-239">GroupBox</span></span>|  
|<span data-ttu-id="d8250-240">HScrollBar</span><span class="sxs-lookup"><span data-stu-id="d8250-240">HscrollBar</span></span>|  
|<span data-ttu-id="d8250-241">ImageList</span><span class="sxs-lookup"><span data-stu-id="d8250-241">ImageList</span></span>|  
|<span data-ttu-id="d8250-242">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="d8250-242">Label</span></span>|  
|<span data-ttu-id="d8250-243">ListBox</span><span class="sxs-lookup"><span data-stu-id="d8250-243">ListBox</span></span>|  
|<span data-ttu-id="d8250-244">ListView</span><span class="sxs-lookup"><span data-stu-id="d8250-244">ListView</span></span>|  
|<span data-ttu-id="d8250-245">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="d8250-245">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="d8250-246">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="d8250-246">MonthCalendar</span></span>|  
|<span data-ttu-id="d8250-247">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="d8250-247">NotifyIcon</span></span>|  
|<span data-ttu-id="d8250-248">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="d8250-248">OpenFileDialog</span></span>|  
|<span data-ttu-id="d8250-249">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="d8250-249">PageSetupDialog</span></span>|  
|<span data-ttu-id="d8250-250">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="d8250-250">PrintDialog</span></span>|  
|<span data-ttu-id="d8250-251">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="d8250-251">ProgressBar</span></span>|  
|<span data-ttu-id="d8250-252">RadioButton</span><span class="sxs-lookup"><span data-stu-id="d8250-252">RadioButton</span></span>|  
|<span data-ttu-id="d8250-253">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="d8250-253">RichTextBox</span></span>|  
|<span data-ttu-id="d8250-254">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="d8250-254">SaveFileDialog</span></span>|  
|<span data-ttu-id="d8250-255">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="d8250-255">ScrollableControl</span></span>|  
|<span data-ttu-id="d8250-256">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="d8250-256">SoundPlayer</span></span>|  
|<span data-ttu-id="d8250-257">StatusBar</span><span class="sxs-lookup"><span data-stu-id="d8250-257">StatusBar</span></span>|  
|<span data-ttu-id="d8250-258">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="d8250-258">TabControl/TabPage</span></span>|  
|<span data-ttu-id="d8250-259">TextBox</span><span class="sxs-lookup"><span data-stu-id="d8250-259">TextBox</span></span>|  
|<span data-ttu-id="d8250-260">Temporizador</span><span class="sxs-lookup"><span data-stu-id="d8250-260">Timer</span></span>|  
|<span data-ttu-id="d8250-261">Barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="d8250-261">Toolbar</span></span>|  
|<span data-ttu-id="d8250-262">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="d8250-262">ToolTip</span></span>|  
|<span data-ttu-id="d8250-263">Trackbar</span><span class="sxs-lookup"><span data-stu-id="d8250-263">TrackBar</span></span>|  
|<span data-ttu-id="d8250-264">TreeView</span><span class="sxs-lookup"><span data-stu-id="d8250-264">TreeView</span></span>|  
|<span data-ttu-id="d8250-265">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="d8250-265">VscrollBar</span></span>|  
|<span data-ttu-id="d8250-266">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="d8250-266">WebBrowser</span></span>|  
  
 <span data-ttu-id="d8250-267">Los siguientes controles se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo a través de la compatibilidad de Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="d8250-267">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="d8250-268">Es posible que algunas funciones no estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="d8250-268">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="d8250-269">Nombre del control</span><span class="sxs-lookup"><span data-stu-id="d8250-269">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="d8250-270">BindingSource</span><span class="sxs-lookup"><span data-stu-id="d8250-270">BindingSource</span></span>|  
|<span data-ttu-id="d8250-271">DataGrid</span><span class="sxs-lookup"><span data-stu-id="d8250-271">DataGrid</span></span>|  
|<span data-ttu-id="d8250-272">DataGridView</span><span class="sxs-lookup"><span data-stu-id="d8250-272">DataGridView</span></span>|  
|<span data-ttu-id="d8250-273">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="d8250-273">DataNavigator</span></span>|  
|<span data-ttu-id="d8250-274">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="d8250-274">DomainUpDown</span></span>|  
|<span data-ttu-id="d8250-275">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="d8250-275">ErrorProvider</span></span>|  
|<span data-ttu-id="d8250-276">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d8250-276">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="d8250-277">Form</span><span class="sxs-lookup"><span data-stu-id="d8250-277">Form</span></span>|  
|<span data-ttu-id="d8250-278">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="d8250-278">LinkLabel</span></span>|  
|<span data-ttu-id="d8250-279">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="d8250-279">HelpProvider</span></span>|  
|<span data-ttu-id="d8250-280">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="d8250-280">MaskedTextBox</span></span>|  
|<span data-ttu-id="d8250-281">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="d8250-281">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="d8250-282">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="d8250-282">NumericUpDown</span></span>|  
|<span data-ttu-id="d8250-283">Panel</span><span class="sxs-lookup"><span data-stu-id="d8250-283">Panel</span></span>|  
|<span data-ttu-id="d8250-284">PictureBox</span><span class="sxs-lookup"><span data-stu-id="d8250-284">PictureBox</span></span>|  
|<span data-ttu-id="d8250-285">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="d8250-285">PrintDocument</span></span>|  
|<span data-ttu-id="d8250-286">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="d8250-286">PrintPreview-Control</span></span>|  
|<span data-ttu-id="d8250-287">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="d8250-287">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="d8250-288">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="d8250-288">PropertyGrid</span></span>|  
|<span data-ttu-id="d8250-289">Control de usuario</span><span class="sxs-lookup"><span data-stu-id="d8250-289">UserControl</span></span>|  
|<span data-ttu-id="d8250-290">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d8250-290">ToolStrip</span></span>|  
|<span data-ttu-id="d8250-291">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d8250-291">TableLayoutPanel</span></span>|  
|<span data-ttu-id="d8250-292">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="d8250-292">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="d8250-293">Divisor</span><span class="sxs-lookup"><span data-stu-id="d8250-293">Splitter</span></span>|  
|<span data-ttu-id="d8250-294">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="d8250-294">RaftingContainer</span></span>|  
|<span data-ttu-id="d8250-295">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="d8250-295">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8250-296">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8250-296">See also</span></span>

- [<span data-ttu-id="d8250-297">Tipos de control de UI Automation</span><span class="sxs-lookup"><span data-stu-id="d8250-297">UI Automation Control Types</span></span>](ui-automation-control-types.md)
