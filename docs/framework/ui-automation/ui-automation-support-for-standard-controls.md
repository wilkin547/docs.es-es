---
title: Compatibilidad de UI Automation con controles estándar
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 49277073706444fd611ae41e762442388ac50b71
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789602"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="6563f-102">Compatibilidad de UI Automation con controles estándar</span><span class="sxs-lookup"><span data-stu-id="6563f-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="6563f-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="6563f-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6563f-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="6563f-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="6563f-105">Este tema contiene información sobre la compatibilidad de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] con los controles estándar de las aplicaciones desarrolladas para los marcos de [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32 y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6563f-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="6563f-106">Controles de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="6563f-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="6563f-107">Todos los elementos de control [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] que ofrecen información o compatibilidad para la interacción del usuario tienen compatibilidad nativa completa con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6563f-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="6563f-108">Otros elementos, como paneles, no son visibles para [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6563f-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="6563f-109">Controles de Win32</span><span class="sxs-lookup"><span data-stu-id="6563f-109">Win32 Controls</span></span>  
 <span data-ttu-id="6563f-110">La mayoría de los controles Win32 se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de los proveedores del lado cliente en UIAutomationClientsideProviders. dll.</span><span class="sxs-lookup"><span data-stu-id="6563f-110">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="6563f-111">Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="6563f-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="6563f-112">Solo se proporciona compatibilidad completa con los controles de la versión 6 de *ComCtrl32. dll*.</span><span class="sxs-lookup"><span data-stu-id="6563f-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="6563f-113">Se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="6563f-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="6563f-114">Nombre de clase</span><span class="sxs-lookup"><span data-stu-id="6563f-114">Class name</span></span>|<span data-ttu-id="6563f-115">Tipo de control</span><span class="sxs-lookup"><span data-stu-id="6563f-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="6563f-116">Botón</span><span class="sxs-lookup"><span data-stu-id="6563f-116">Button</span></span>|<span data-ttu-id="6563f-117">Botón</span><span class="sxs-lookup"><span data-stu-id="6563f-117">Button</span></span>|  
|<span data-ttu-id="6563f-118">Botón</span><span class="sxs-lookup"><span data-stu-id="6563f-118">Button</span></span>|<span data-ttu-id="6563f-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="6563f-119">RadioButton</span></span>|  
|<span data-ttu-id="6563f-120">Botón</span><span class="sxs-lookup"><span data-stu-id="6563f-120">Button</span></span>|<span data-ttu-id="6563f-121">Grupo</span><span class="sxs-lookup"><span data-stu-id="6563f-121">Group</span></span>|  
|<span data-ttu-id="6563f-122">Botón</span><span class="sxs-lookup"><span data-stu-id="6563f-122">Button</span></span>|<span data-ttu-id="6563f-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="6563f-123">CheckBox</span></span>|  
|<span data-ttu-id="6563f-124">Botón</span><span class="sxs-lookup"><span data-stu-id="6563f-124">Button</span></span>|<span data-ttu-id="6563f-125">Hipervínculo</span><span class="sxs-lookup"><span data-stu-id="6563f-125">Hyperlink</span></span>|  
|<span data-ttu-id="6563f-126">Botón</span><span class="sxs-lookup"><span data-stu-id="6563f-126">Button</span></span>|<span data-ttu-id="6563f-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="6563f-127">SplitButton</span></span>|  
|<span data-ttu-id="6563f-128">Botón</span><span class="sxs-lookup"><span data-stu-id="6563f-128">Button</span></span>|<span data-ttu-id="6563f-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="6563f-129">CheckBox</span></span>|  
|<span data-ttu-id="6563f-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="6563f-130">ComboBoxEx32</span></span>|<span data-ttu-id="6563f-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="6563f-131">ComboBox</span></span>|  
|<span data-ttu-id="6563f-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="6563f-132">ComboBox</span></span>|<span data-ttu-id="6563f-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="6563f-133">ComboBox</span></span>|  
|<span data-ttu-id="6563f-134">Edit</span><span class="sxs-lookup"><span data-stu-id="6563f-134">Edit</span></span>|<span data-ttu-id="6563f-135">Documento</span><span class="sxs-lookup"><span data-stu-id="6563f-135">Document</span></span>|  
|<span data-ttu-id="6563f-136">Edit</span><span class="sxs-lookup"><span data-stu-id="6563f-136">Edit</span></span>|<span data-ttu-id="6563f-137">Edit</span><span class="sxs-lookup"><span data-stu-id="6563f-137">Edit</span></span>|  
|<span data-ttu-id="6563f-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="6563f-138">SysLink</span></span>|<span data-ttu-id="6563f-139">Hipervínculo</span><span class="sxs-lookup"><span data-stu-id="6563f-139">Hyperlink</span></span>|  
|<span data-ttu-id="6563f-140">Estático</span><span class="sxs-lookup"><span data-stu-id="6563f-140">Static</span></span>|<span data-ttu-id="6563f-141">Text</span><span class="sxs-lookup"><span data-stu-id="6563f-141">Text</span></span>|  
|<span data-ttu-id="6563f-142">Estático</span><span class="sxs-lookup"><span data-stu-id="6563f-142">Static</span></span>|<span data-ttu-id="6563f-143">Imagen</span><span class="sxs-lookup"><span data-stu-id="6563f-143">Image</span></span>|  
|<span data-ttu-id="6563f-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="6563f-144">SysIPAddress32</span></span>|<span data-ttu-id="6563f-145">Personalizado</span><span class="sxs-lookup"><span data-stu-id="6563f-145">Custom</span></span>|  
|<span data-ttu-id="6563f-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="6563f-146">SysHeader32</span></span>|<span data-ttu-id="6563f-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="6563f-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="6563f-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="6563f-148">SysListView32</span></span>|<span data-ttu-id="6563f-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="6563f-149">DataGrid</span></span>|  
|<span data-ttu-id="6563f-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="6563f-150">SysListView32</span></span>|<span data-ttu-id="6563f-151">Lista</span><span class="sxs-lookup"><span data-stu-id="6563f-151">List</span></span>|  
|<span data-ttu-id="6563f-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="6563f-152">ListBox</span></span>|<span data-ttu-id="6563f-153">Lista</span><span class="sxs-lookup"><span data-stu-id="6563f-153">List</span></span>|  
|<span data-ttu-id="6563f-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="6563f-154">ListBox</span></span>|<span data-ttu-id="6563f-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="6563f-155">ListItem</span></span>|  
|<span data-ttu-id="6563f-156">#32768</span><span class="sxs-lookup"><span data-stu-id="6563f-156">#32768</span></span>|<span data-ttu-id="6563f-157">Menú</span><span class="sxs-lookup"><span data-stu-id="6563f-157">Menu</span></span>|  
|<span data-ttu-id="6563f-158">#32768</span><span class="sxs-lookup"><span data-stu-id="6563f-158">#32768</span></span>|<span data-ttu-id="6563f-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="6563f-159">MenuItem</span></span>|  
|<span data-ttu-id="6563f-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="6563f-160">msctls_progress32</span></span>|<span data-ttu-id="6563f-161">Barra de progreso</span><span class="sxs-lookup"><span data-stu-id="6563f-161">ProgressBar</span></span>|  
|<span data-ttu-id="6563f-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="6563f-162">RichEdit</span></span>|<span data-ttu-id="6563f-163">Documento.</span><span class="sxs-lookup"><span data-stu-id="6563f-163">Document.</span></span> <span data-ttu-id="6563f-164">Vea la nota.</span><span class="sxs-lookup"><span data-stu-id="6563f-164">See note.</span></span>|  
|<span data-ttu-id="6563f-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="6563f-165">RichEdit20A</span></span>|<span data-ttu-id="6563f-166">Documento</span><span class="sxs-lookup"><span data-stu-id="6563f-166">Document</span></span>|  
|<span data-ttu-id="6563f-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="6563f-167">RichEdit20W</span></span>|<span data-ttu-id="6563f-168">Documento</span><span class="sxs-lookup"><span data-stu-id="6563f-168">Document</span></span>|  
|<span data-ttu-id="6563f-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="6563f-169">RichEdit50W</span></span>|<span data-ttu-id="6563f-170">Documento</span><span class="sxs-lookup"><span data-stu-id="6563f-170">Document</span></span>|  
|<span data-ttu-id="6563f-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="6563f-171">ScrollBar</span></span>|<span data-ttu-id="6563f-172">Slider</span><span class="sxs-lookup"><span data-stu-id="6563f-172">Slider</span></span>|  
|<span data-ttu-id="6563f-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="6563f-173">msctls_trackbar32</span></span>|<span data-ttu-id="6563f-174">Slider</span><span class="sxs-lookup"><span data-stu-id="6563f-174">Slider</span></span>|  
|<span data-ttu-id="6563f-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="6563f-175">msctls_updown32</span></span>|<span data-ttu-id="6563f-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="6563f-176">Spinner</span></span>|  
|<span data-ttu-id="6563f-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="6563f-177">msctls_statusbar32</span></span>|<span data-ttu-id="6563f-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="6563f-178">StatusBar</span></span>|  
|<span data-ttu-id="6563f-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="6563f-179">SysTabControl32</span></span>|<span data-ttu-id="6563f-180">Tab</span><span class="sxs-lookup"><span data-stu-id="6563f-180">Tab</span></span>|  
|<span data-ttu-id="6563f-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="6563f-181">SysTabControl32</span></span>|<span data-ttu-id="6563f-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="6563f-182">TabItem</span></span>|  
|<span data-ttu-id="6563f-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="6563f-183">ToolbarWindow32</span></span>|<span data-ttu-id="6563f-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="6563f-184">ToolBar</span></span>|  
|<span data-ttu-id="6563f-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="6563f-185">ToolbarWindow32</span></span>|<span data-ttu-id="6563f-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="6563f-186">MenuItem</span></span>|  
|<span data-ttu-id="6563f-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="6563f-187">ToolbarWindow32</span></span>|<span data-ttu-id="6563f-188">Botón</span><span class="sxs-lookup"><span data-stu-id="6563f-188">Button</span></span>|  
|<span data-ttu-id="6563f-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="6563f-189">ToolbarWindow32</span></span>|<span data-ttu-id="6563f-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="6563f-190">CheckBox</span></span>|  
|<span data-ttu-id="6563f-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="6563f-191">ToolbarWindow32</span></span>|<span data-ttu-id="6563f-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="6563f-192">RadioButton</span></span>|  
|<span data-ttu-id="6563f-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="6563f-193">ToolbarWindow32</span></span>|<span data-ttu-id="6563f-194">Separador</span><span class="sxs-lookup"><span data-stu-id="6563f-194">Separator</span></span>|  
|<span data-ttu-id="6563f-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="6563f-195">tooltips_class32</span></span>|<span data-ttu-id="6563f-196">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="6563f-196">ToolTip</span></span>|  
|<span data-ttu-id="6563f-197">#32774</span><span class="sxs-lookup"><span data-stu-id="6563f-197">#32774</span></span>|<span data-ttu-id="6563f-198">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="6563f-198">ToolTip</span></span>|  
|<span data-ttu-id="6563f-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="6563f-199">ReBarWindow32</span></span>|<span data-ttu-id="6563f-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="6563f-200">Toolbar</span></span>|  
|<span data-ttu-id="6563f-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="6563f-201">SysTreeView32</span></span>|<span data-ttu-id="6563f-202">Árbol</span><span class="sxs-lookup"><span data-stu-id="6563f-202">Tree</span></span>|  
|<span data-ttu-id="6563f-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="6563f-203">SysTreeView32</span></span>|<span data-ttu-id="6563f-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="6563f-204">TreeItem</span></span>|  
  
 <span data-ttu-id="6563f-205">**Nota:** El control RichEdit solo se admite para las versiones incluidas con Windows Vista (en RichEd20. dll versión 3,1 y posteriores, y MsftEdit. dll versión 4,1 y posteriores).</span><span class="sxs-lookup"><span data-stu-id="6563f-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="6563f-206">No se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="6563f-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="6563f-207">Nombre de clase</span><span class="sxs-lookup"><span data-stu-id="6563f-207">Class name</span></span>|<span data-ttu-id="6563f-208">Tipo de control</span><span class="sxs-lookup"><span data-stu-id="6563f-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="6563f-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="6563f-209">SysAnimate32</span></span>|<span data-ttu-id="6563f-210">Imagen</span><span class="sxs-lookup"><span data-stu-id="6563f-210">Image</span></span>|  
|<span data-ttu-id="6563f-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="6563f-211">SysPager</span></span>|<span data-ttu-id="6563f-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="6563f-212">Spinner</span></span>|  
|<span data-ttu-id="6563f-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="6563f-213">SysDateTimePick32</span></span>|<span data-ttu-id="6563f-214">Personalizado</span><span class="sxs-lookup"><span data-stu-id="6563f-214">Custom</span></span>|  
|<span data-ttu-id="6563f-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="6563f-215">SysMonthCal32</span></span>|<span data-ttu-id="6563f-216">Calendario</span><span class="sxs-lookup"><span data-stu-id="6563f-216">Calendar</span></span>|  
|<span data-ttu-id="6563f-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="6563f-217">MS_WINNOTE</span></span>|<span data-ttu-id="6563f-218">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="6563f-218">Tooltip</span></span>|  
|<span data-ttu-id="6563f-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="6563f-219">VBBubble</span></span>|<span data-ttu-id="6563f-220">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="6563f-220">Tooltip</span></span>|  
|<span data-ttu-id="6563f-221">ScrollBar (cuando se usa como control independiente)</span><span class="sxs-lookup"><span data-stu-id="6563f-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="6563f-222">Slider</span><span class="sxs-lookup"><span data-stu-id="6563f-222">Slider</span></span>|  
|<span data-ttu-id="6563f-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="6563f-223">SuperGrid</span></span>|<span data-ttu-id="6563f-224">Personalizado</span><span class="sxs-lookup"><span data-stu-id="6563f-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="6563f-225">Controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6563f-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="6563f-226">Windows Forms controles se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de los proveedores del lado cliente en UIAutomationClientsideProviders. dll.</span><span class="sxs-lookup"><span data-stu-id="6563f-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="6563f-227">Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="6563f-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="6563f-228">Normalmente, los Windows Forms controles que son contenedores administrados para controles comunes Win32 son compatibles con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6563f-228">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="6563f-229">Se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="6563f-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="6563f-230">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="6563f-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="6563f-231">Botón</span><span class="sxs-lookup"><span data-stu-id="6563f-231">Button</span></span>|  
|<span data-ttu-id="6563f-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="6563f-232">CheckBox</span></span>|  
|<span data-ttu-id="6563f-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="6563f-233">CheckedListBox</span></span>|  
|<span data-ttu-id="6563f-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="6563f-234">ColorDialog</span></span>|  
|<span data-ttu-id="6563f-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="6563f-235">ComboBox</span></span>|  
|<span data-ttu-id="6563f-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="6563f-236">FolderBrowser</span></span>|  
|<span data-ttu-id="6563f-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="6563f-237">FontDialog</span></span>|  
|<span data-ttu-id="6563f-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="6563f-238">GroupBox</span></span>|  
|<span data-ttu-id="6563f-239">HScrollBar</span><span class="sxs-lookup"><span data-stu-id="6563f-239">HscrollBar</span></span>|  
|<span data-ttu-id="6563f-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="6563f-240">ImageList</span></span>|  
|<span data-ttu-id="6563f-241">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="6563f-241">Label</span></span>|  
|<span data-ttu-id="6563f-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="6563f-242">ListBox</span></span>|  
|<span data-ttu-id="6563f-243">ListView</span><span class="sxs-lookup"><span data-stu-id="6563f-243">ListView</span></span>|  
|<span data-ttu-id="6563f-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="6563f-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="6563f-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="6563f-245">MonthCalendar</span></span>|  
|<span data-ttu-id="6563f-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="6563f-246">NotifyIcon</span></span>|  
|<span data-ttu-id="6563f-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="6563f-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="6563f-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="6563f-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="6563f-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="6563f-249">PrintDialog</span></span>|  
|<span data-ttu-id="6563f-250">Barra de progreso</span><span class="sxs-lookup"><span data-stu-id="6563f-250">ProgressBar</span></span>|  
|<span data-ttu-id="6563f-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="6563f-251">RadioButton</span></span>|  
|<span data-ttu-id="6563f-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="6563f-252">RichTextBox</span></span>|  
|<span data-ttu-id="6563f-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="6563f-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="6563f-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="6563f-254">ScrollableControl</span></span>|  
|<span data-ttu-id="6563f-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="6563f-255">SoundPlayer</span></span>|  
|<span data-ttu-id="6563f-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="6563f-256">StatusBar</span></span>|  
|<span data-ttu-id="6563f-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="6563f-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="6563f-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="6563f-258">TextBox</span></span>|  
|<span data-ttu-id="6563f-259">Temporizador</span><span class="sxs-lookup"><span data-stu-id="6563f-259">Timer</span></span>|  
|<span data-ttu-id="6563f-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="6563f-260">Toolbar</span></span>|  
|<span data-ttu-id="6563f-261">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="6563f-261">ToolTip</span></span>|  
|<span data-ttu-id="6563f-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="6563f-262">TrackBar</span></span>|  
|<span data-ttu-id="6563f-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="6563f-263">TreeView</span></span>|  
|<span data-ttu-id="6563f-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="6563f-264">VscrollBar</span></span>|  
|<span data-ttu-id="6563f-265">ExploradorWeb</span><span class="sxs-lookup"><span data-stu-id="6563f-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="6563f-266">Los siguientes controles se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo a través de la compatibilidad con Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="6563f-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="6563f-267">Es posible que algunas funciones no estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="6563f-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="6563f-268">Nombre del control</span><span class="sxs-lookup"><span data-stu-id="6563f-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="6563f-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="6563f-269">BindingSource</span></span>|  
|<span data-ttu-id="6563f-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="6563f-270">DataGrid</span></span>|  
|<span data-ttu-id="6563f-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="6563f-271">DataGridView</span></span>|  
|<span data-ttu-id="6563f-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="6563f-272">DataNavigator</span></span>|  
|<span data-ttu-id="6563f-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="6563f-273">DomainUpDown</span></span>|  
|<span data-ttu-id="6563f-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="6563f-274">ErrorProvider</span></span>|  
|<span data-ttu-id="6563f-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="6563f-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="6563f-276">Form</span><span class="sxs-lookup"><span data-stu-id="6563f-276">Form</span></span>|  
|<span data-ttu-id="6563f-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="6563f-277">LinkLabel</span></span>|  
|<span data-ttu-id="6563f-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="6563f-278">HelpProvider</span></span>|  
|<span data-ttu-id="6563f-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="6563f-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="6563f-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="6563f-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="6563f-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="6563f-281">NumericUpDown</span></span>|  
|<span data-ttu-id="6563f-282">Panel</span><span class="sxs-lookup"><span data-stu-id="6563f-282">Panel</span></span>|  
|<span data-ttu-id="6563f-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="6563f-283">PictureBox</span></span>|  
|<span data-ttu-id="6563f-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="6563f-284">PrintDocument</span></span>|  
|<span data-ttu-id="6563f-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="6563f-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="6563f-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="6563f-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="6563f-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="6563f-287">PropertyGrid</span></span>|  
|<span data-ttu-id="6563f-288">Control de usuario</span><span class="sxs-lookup"><span data-stu-id="6563f-288">UserControl</span></span>|  
|<span data-ttu-id="6563f-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="6563f-289">ToolStrip</span></span>|  
|<span data-ttu-id="6563f-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="6563f-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="6563f-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="6563f-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="6563f-292">Divisor</span><span class="sxs-lookup"><span data-stu-id="6563f-292">Splitter</span></span>|  
|<span data-ttu-id="6563f-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="6563f-293">RaftingContainer</span></span>|  
|<span data-ttu-id="6563f-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="6563f-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6563f-295">Vea también</span><span class="sxs-lookup"><span data-stu-id="6563f-295">See also</span></span>

- [<span data-ttu-id="6563f-296">UI Automation Control Types</span><span class="sxs-lookup"><span data-stu-id="6563f-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
