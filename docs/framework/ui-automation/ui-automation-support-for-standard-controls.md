---
title: Compatibilidad de UI Automation con controles estándar
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: c59352f908c5f4a1fd2ca6dd631d26bb5d69f09a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441223"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="59f23-102">Compatibilidad de UI Automation con controles estándar</span><span class="sxs-lookup"><span data-stu-id="59f23-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="59f23-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="59f23-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="59f23-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="59f23-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="59f23-105">En este tema se incluye información sobre la compatibilidad de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] con controles estándar en las aplicaciones desarrolladas para los marcos de trabajo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]y [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="59f23-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="59f23-106">Controles de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="59f23-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="59f23-107">Todos los elementos de control [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] que ofrecen información o compatibilidad para la interacción del usuario tienen compatibilidad nativa completa con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59f23-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="59f23-108">Otros elementos, como paneles, no son visibles para [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59f23-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="59f23-109">Controles de Win32</span><span class="sxs-lookup"><span data-stu-id="59f23-109">Win32 Controls</span></span>  
 <span data-ttu-id="59f23-110">La mayoría de los controles [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de los proveedores del cliente en UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="59f23-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="59f23-111">Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="59f23-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="59f23-112">Solo se proporciona compatibilidad completa para controles desde la versión 6 de ComCtrl32.dll (disponibles con [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] y versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="59f23-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="59f23-113">Se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="59f23-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="59f23-114">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="59f23-114">Class name</span></span>|<span data-ttu-id="59f23-115">Tipo de control</span><span class="sxs-lookup"><span data-stu-id="59f23-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="59f23-116">Botón</span><span class="sxs-lookup"><span data-stu-id="59f23-116">Button</span></span>|<span data-ttu-id="59f23-117">Botón</span><span class="sxs-lookup"><span data-stu-id="59f23-117">Button</span></span>|  
|<span data-ttu-id="59f23-118">Botón</span><span class="sxs-lookup"><span data-stu-id="59f23-118">Button</span></span>|<span data-ttu-id="59f23-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="59f23-119">RadioButton</span></span>|  
|<span data-ttu-id="59f23-120">Botón</span><span class="sxs-lookup"><span data-stu-id="59f23-120">Button</span></span>|<span data-ttu-id="59f23-121">Agrupar</span><span class="sxs-lookup"><span data-stu-id="59f23-121">Group</span></span>|  
|<span data-ttu-id="59f23-122">Botón</span><span class="sxs-lookup"><span data-stu-id="59f23-122">Button</span></span>|<span data-ttu-id="59f23-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="59f23-123">CheckBox</span></span>|  
|<span data-ttu-id="59f23-124">Botón</span><span class="sxs-lookup"><span data-stu-id="59f23-124">Button</span></span>|<span data-ttu-id="59f23-125">Hipervínculo</span><span class="sxs-lookup"><span data-stu-id="59f23-125">Hyperlink</span></span>|  
|<span data-ttu-id="59f23-126">Botón</span><span class="sxs-lookup"><span data-stu-id="59f23-126">Button</span></span>|<span data-ttu-id="59f23-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="59f23-127">SplitButton</span></span>|  
|<span data-ttu-id="59f23-128">Botón</span><span class="sxs-lookup"><span data-stu-id="59f23-128">Button</span></span>|<span data-ttu-id="59f23-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="59f23-129">CheckBox</span></span>|  
|<span data-ttu-id="59f23-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="59f23-130">ComboBoxEx32</span></span>|<span data-ttu-id="59f23-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="59f23-131">ComboBox</span></span>|  
|<span data-ttu-id="59f23-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="59f23-132">ComboBox</span></span>|<span data-ttu-id="59f23-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="59f23-133">ComboBox</span></span>|  
|<span data-ttu-id="59f23-134">Editar</span><span class="sxs-lookup"><span data-stu-id="59f23-134">Edit</span></span>|<span data-ttu-id="59f23-135">Documento</span><span class="sxs-lookup"><span data-stu-id="59f23-135">Document</span></span>|  
|<span data-ttu-id="59f23-136">Editar</span><span class="sxs-lookup"><span data-stu-id="59f23-136">Edit</span></span>|<span data-ttu-id="59f23-137">Editar</span><span class="sxs-lookup"><span data-stu-id="59f23-137">Edit</span></span>|  
|<span data-ttu-id="59f23-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="59f23-138">SysLink</span></span>|<span data-ttu-id="59f23-139">Hipervínculo</span><span class="sxs-lookup"><span data-stu-id="59f23-139">Hyperlink</span></span>|  
|<span data-ttu-id="59f23-140">Estático</span><span class="sxs-lookup"><span data-stu-id="59f23-140">Static</span></span>|<span data-ttu-id="59f23-141">Text</span><span class="sxs-lookup"><span data-stu-id="59f23-141">Text</span></span>|  
|<span data-ttu-id="59f23-142">Estático</span><span class="sxs-lookup"><span data-stu-id="59f23-142">Static</span></span>|<span data-ttu-id="59f23-143">Imagen</span><span class="sxs-lookup"><span data-stu-id="59f23-143">Image</span></span>|  
|<span data-ttu-id="59f23-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="59f23-144">SysIPAddress32</span></span>|<span data-ttu-id="59f23-145">Personalizados</span><span class="sxs-lookup"><span data-stu-id="59f23-145">Custom</span></span>|  
|<span data-ttu-id="59f23-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="59f23-146">SysHeader32</span></span>|<span data-ttu-id="59f23-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="59f23-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="59f23-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="59f23-148">SysListView32</span></span>|<span data-ttu-id="59f23-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="59f23-149">DataGrid</span></span>|  
|<span data-ttu-id="59f23-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="59f23-150">SysListView32</span></span>|<span data-ttu-id="59f23-151">Lista</span><span class="sxs-lookup"><span data-stu-id="59f23-151">List</span></span>|  
|<span data-ttu-id="59f23-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="59f23-152">ListBox</span></span>|<span data-ttu-id="59f23-153">Lista</span><span class="sxs-lookup"><span data-stu-id="59f23-153">List</span></span>|  
|<span data-ttu-id="59f23-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="59f23-154">ListBox</span></span>|<span data-ttu-id="59f23-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="59f23-155">ListItem</span></span>|  
|<span data-ttu-id="59f23-156">#32768</span><span class="sxs-lookup"><span data-stu-id="59f23-156">#32768</span></span>|<span data-ttu-id="59f23-157">Menú</span><span class="sxs-lookup"><span data-stu-id="59f23-157">Menu</span></span>|  
|<span data-ttu-id="59f23-158">#32768</span><span class="sxs-lookup"><span data-stu-id="59f23-158">#32768</span></span>|<span data-ttu-id="59f23-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="59f23-159">MenuItem</span></span>|  
|<span data-ttu-id="59f23-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="59f23-160">msctls_progress32</span></span>|<span data-ttu-id="59f23-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="59f23-161">ProgressBar</span></span>|  
|<span data-ttu-id="59f23-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="59f23-162">RichEdit</span></span>|<span data-ttu-id="59f23-163">Documento.</span><span class="sxs-lookup"><span data-stu-id="59f23-163">Document.</span></span> <span data-ttu-id="59f23-164">Vea la nota.</span><span class="sxs-lookup"><span data-stu-id="59f23-164">See note.</span></span>|  
|<span data-ttu-id="59f23-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="59f23-165">RichEdit20A</span></span>|<span data-ttu-id="59f23-166">Documento</span><span class="sxs-lookup"><span data-stu-id="59f23-166">Document</span></span>|  
|<span data-ttu-id="59f23-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="59f23-167">RichEdit20W</span></span>|<span data-ttu-id="59f23-168">Documento</span><span class="sxs-lookup"><span data-stu-id="59f23-168">Document</span></span>|  
|<span data-ttu-id="59f23-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="59f23-169">RichEdit50W</span></span>|<span data-ttu-id="59f23-170">Documento</span><span class="sxs-lookup"><span data-stu-id="59f23-170">Document</span></span>|  
|<span data-ttu-id="59f23-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="59f23-171">ScrollBar</span></span>|<span data-ttu-id="59f23-172">Slider</span><span class="sxs-lookup"><span data-stu-id="59f23-172">Slider</span></span>|  
|<span data-ttu-id="59f23-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="59f23-173">msctls_trackbar32</span></span>|<span data-ttu-id="59f23-174">Slider</span><span class="sxs-lookup"><span data-stu-id="59f23-174">Slider</span></span>|  
|<span data-ttu-id="59f23-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="59f23-175">msctls_updown32</span></span>|<span data-ttu-id="59f23-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="59f23-176">Spinner</span></span>|  
|<span data-ttu-id="59f23-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="59f23-177">msctls_statusbar32</span></span>|<span data-ttu-id="59f23-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="59f23-178">StatusBar</span></span>|  
|<span data-ttu-id="59f23-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="59f23-179">SysTabControl32</span></span>|<span data-ttu-id="59f23-180">Tab</span><span class="sxs-lookup"><span data-stu-id="59f23-180">Tab</span></span>|  
|<span data-ttu-id="59f23-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="59f23-181">SysTabControl32</span></span>|<span data-ttu-id="59f23-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="59f23-182">TabItem</span></span>|  
|<span data-ttu-id="59f23-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="59f23-183">ToolbarWindow32</span></span>|<span data-ttu-id="59f23-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="59f23-184">ToolBar</span></span>|  
|<span data-ttu-id="59f23-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="59f23-185">ToolbarWindow32</span></span>|<span data-ttu-id="59f23-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="59f23-186">MenuItem</span></span>|  
|<span data-ttu-id="59f23-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="59f23-187">ToolbarWindow32</span></span>|<span data-ttu-id="59f23-188">Botón</span><span class="sxs-lookup"><span data-stu-id="59f23-188">Button</span></span>|  
|<span data-ttu-id="59f23-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="59f23-189">ToolbarWindow32</span></span>|<span data-ttu-id="59f23-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="59f23-190">CheckBox</span></span>|  
|<span data-ttu-id="59f23-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="59f23-191">ToolbarWindow32</span></span>|<span data-ttu-id="59f23-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="59f23-192">RadioButton</span></span>|  
|<span data-ttu-id="59f23-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="59f23-193">ToolbarWindow32</span></span>|<span data-ttu-id="59f23-194">Separador</span><span class="sxs-lookup"><span data-stu-id="59f23-194">Separator</span></span>|  
|<span data-ttu-id="59f23-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="59f23-195">tooltips_class32</span></span>|<span data-ttu-id="59f23-196">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="59f23-196">ToolTip</span></span>|  
|<span data-ttu-id="59f23-197">#32774</span><span class="sxs-lookup"><span data-stu-id="59f23-197">#32774</span></span>|<span data-ttu-id="59f23-198">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="59f23-198">ToolTip</span></span>|  
|<span data-ttu-id="59f23-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="59f23-199">ReBarWindow32</span></span>|<span data-ttu-id="59f23-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="59f23-200">Toolbar</span></span>|  
|<span data-ttu-id="59f23-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="59f23-201">SysTreeView32</span></span>|<span data-ttu-id="59f23-202">Árbol</span><span class="sxs-lookup"><span data-stu-id="59f23-202">Tree</span></span>|  
|<span data-ttu-id="59f23-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="59f23-203">SysTreeView32</span></span>|<span data-ttu-id="59f23-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="59f23-204">TreeItem</span></span>|  
  
 <span data-ttu-id="59f23-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span><span class="sxs-lookup"><span data-stu-id="59f23-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="59f23-206">No se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="59f23-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="59f23-207">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="59f23-207">Class name</span></span>|<span data-ttu-id="59f23-208">Tipo de control</span><span class="sxs-lookup"><span data-stu-id="59f23-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="59f23-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="59f23-209">SysAnimate32</span></span>|<span data-ttu-id="59f23-210">Imagen</span><span class="sxs-lookup"><span data-stu-id="59f23-210">Image</span></span>|  
|<span data-ttu-id="59f23-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="59f23-211">SysPager</span></span>|<span data-ttu-id="59f23-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="59f23-212">Spinner</span></span>|  
|<span data-ttu-id="59f23-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="59f23-213">SysDateTimePick32</span></span>|<span data-ttu-id="59f23-214">Personalizados</span><span class="sxs-lookup"><span data-stu-id="59f23-214">Custom</span></span>|  
|<span data-ttu-id="59f23-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="59f23-215">SysMonthCal32</span></span>|<span data-ttu-id="59f23-216">Calendario</span><span class="sxs-lookup"><span data-stu-id="59f23-216">Calendar</span></span>|  
|<span data-ttu-id="59f23-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="59f23-217">MS_WINNOTE</span></span>|<span data-ttu-id="59f23-218">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="59f23-218">Tooltip</span></span>|  
|<span data-ttu-id="59f23-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="59f23-219">VBBubble</span></span>|<span data-ttu-id="59f23-220">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="59f23-220">Tooltip</span></span>|  
|<span data-ttu-id="59f23-221">ScrollBar (cuando se usa como control independiente)</span><span class="sxs-lookup"><span data-stu-id="59f23-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="59f23-222">Slider</span><span class="sxs-lookup"><span data-stu-id="59f23-222">Slider</span></span>|  
|<span data-ttu-id="59f23-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="59f23-223">SuperGrid</span></span>|<span data-ttu-id="59f23-224">Personalizados</span><span class="sxs-lookup"><span data-stu-id="59f23-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="59f23-225">Controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="59f23-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="59f23-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="59f23-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="59f23-227">Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="59f23-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="59f23-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59f23-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="59f23-229">Se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="59f23-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="59f23-230">Nombre de la clase</span><span class="sxs-lookup"><span data-stu-id="59f23-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="59f23-231">Botón</span><span class="sxs-lookup"><span data-stu-id="59f23-231">Button</span></span>|  
|<span data-ttu-id="59f23-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="59f23-232">CheckBox</span></span>|  
|<span data-ttu-id="59f23-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="59f23-233">CheckedListBox</span></span>|  
|<span data-ttu-id="59f23-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="59f23-234">ColorDialog</span></span>|  
|<span data-ttu-id="59f23-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="59f23-235">ComboBox</span></span>|  
|<span data-ttu-id="59f23-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="59f23-236">FolderBrowser</span></span>|  
|<span data-ttu-id="59f23-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="59f23-237">FontDialog</span></span>|  
|<span data-ttu-id="59f23-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="59f23-238">GroupBox</span></span>|  
|<span data-ttu-id="59f23-239">HScrollBar</span><span class="sxs-lookup"><span data-stu-id="59f23-239">HscrollBar</span></span>|  
|<span data-ttu-id="59f23-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="59f23-240">ImageList</span></span>|  
|<span data-ttu-id="59f23-241">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="59f23-241">Label</span></span>|  
|<span data-ttu-id="59f23-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="59f23-242">ListBox</span></span>|  
|<span data-ttu-id="59f23-243">ListView</span><span class="sxs-lookup"><span data-stu-id="59f23-243">ListView</span></span>|  
|<span data-ttu-id="59f23-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="59f23-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="59f23-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="59f23-245">MonthCalendar</span></span>|  
|<span data-ttu-id="59f23-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="59f23-246">NotifyIcon</span></span>|  
|<span data-ttu-id="59f23-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="59f23-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="59f23-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="59f23-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="59f23-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="59f23-249">PrintDialog</span></span>|  
|<span data-ttu-id="59f23-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="59f23-250">ProgressBar</span></span>|  
|<span data-ttu-id="59f23-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="59f23-251">RadioButton</span></span>|  
|<span data-ttu-id="59f23-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="59f23-252">RichTextBox</span></span>|  
|<span data-ttu-id="59f23-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="59f23-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="59f23-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="59f23-254">ScrollableControl</span></span>|  
|<span data-ttu-id="59f23-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="59f23-255">SoundPlayer</span></span>|  
|<span data-ttu-id="59f23-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="59f23-256">StatusBar</span></span>|  
|<span data-ttu-id="59f23-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="59f23-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="59f23-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="59f23-258">TextBox</span></span>|  
|<span data-ttu-id="59f23-259">Temporizador</span><span class="sxs-lookup"><span data-stu-id="59f23-259">Timer</span></span>|  
|<span data-ttu-id="59f23-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="59f23-260">Toolbar</span></span>|  
|<span data-ttu-id="59f23-261">Información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="59f23-261">ToolTip</span></span>|  
|<span data-ttu-id="59f23-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="59f23-262">TrackBar</span></span>|  
|<span data-ttu-id="59f23-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="59f23-263">TreeView</span></span>|  
|<span data-ttu-id="59f23-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="59f23-264">VscrollBar</span></span>|  
|<span data-ttu-id="59f23-265">ExploradorWeb</span><span class="sxs-lookup"><span data-stu-id="59f23-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="59f23-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="59f23-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="59f23-267">Es posible que algunas funciones no estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="59f23-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="59f23-268">Nombre del control</span><span class="sxs-lookup"><span data-stu-id="59f23-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="59f23-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="59f23-269">BindingSource</span></span>|  
|<span data-ttu-id="59f23-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="59f23-270">DataGrid</span></span>|  
|<span data-ttu-id="59f23-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="59f23-271">DataGridView</span></span>|  
|<span data-ttu-id="59f23-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="59f23-272">DataNavigator</span></span>|  
|<span data-ttu-id="59f23-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="59f23-273">DomainUpDown</span></span>|  
|<span data-ttu-id="59f23-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="59f23-274">ErrorProvider</span></span>|  
|<span data-ttu-id="59f23-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="59f23-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="59f23-276">Form</span><span class="sxs-lookup"><span data-stu-id="59f23-276">Form</span></span>|  
|<span data-ttu-id="59f23-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="59f23-277">LinkLabel</span></span>|  
|<span data-ttu-id="59f23-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="59f23-278">HelpProvider</span></span>|  
|<span data-ttu-id="59f23-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="59f23-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="59f23-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="59f23-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="59f23-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="59f23-281">NumericUpDown</span></span>|  
|<span data-ttu-id="59f23-282">Panel</span><span class="sxs-lookup"><span data-stu-id="59f23-282">Panel</span></span>|  
|<span data-ttu-id="59f23-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="59f23-283">PictureBox</span></span>|  
|<span data-ttu-id="59f23-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="59f23-284">PrintDocument</span></span>|  
|<span data-ttu-id="59f23-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="59f23-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="59f23-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="59f23-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="59f23-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="59f23-287">PropertyGrid</span></span>|  
|<span data-ttu-id="59f23-288">Control de usuario</span><span class="sxs-lookup"><span data-stu-id="59f23-288">UserControl</span></span>|  
|<span data-ttu-id="59f23-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="59f23-289">ToolStrip</span></span>|  
|<span data-ttu-id="59f23-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="59f23-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="59f23-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="59f23-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="59f23-292">Divisor</span><span class="sxs-lookup"><span data-stu-id="59f23-292">Splitter</span></span>|  
|<span data-ttu-id="59f23-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="59f23-293">RaftingContainer</span></span>|  
|<span data-ttu-id="59f23-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="59f23-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59f23-295">Vea también</span><span class="sxs-lookup"><span data-stu-id="59f23-295">See also</span></span>

- [<span data-ttu-id="59f23-296">Tipos de control de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="59f23-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
