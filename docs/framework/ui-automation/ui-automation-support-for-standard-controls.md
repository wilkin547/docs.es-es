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
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="34b51-102">Compatibilidad de UI Automation con controles estándar</span><span class="sxs-lookup"><span data-stu-id="34b51-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="34b51-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="34b51-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="34b51-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="34b51-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="34b51-105">En este tema se incluye información sobre la compatibilidad de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] con controles estándar en las aplicaciones desarrolladas para los marcos de trabajo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]y [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34b51-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="34b51-106">Controles de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="34b51-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="34b51-107">Todos los elementos de control [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] que ofrecen información o compatibilidad para la interacción del usuario tienen compatibilidad nativa completa con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34b51-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="34b51-108">Otros elementos, como paneles, no son visibles para [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34b51-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="34b51-109">Controles de Win32</span><span class="sxs-lookup"><span data-stu-id="34b51-109">Win32 Controls</span></span>  
 <span data-ttu-id="34b51-110">La mayoría de los controles [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de los proveedores del cliente en UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="34b51-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="34b51-111">Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="34b51-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="34b51-112">Solo se proporciona compatibilidad completa para controles desde la versión 6 de ComCtrl32.dll (disponibles con [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] y versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="34b51-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="34b51-113">Se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="34b51-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="34b51-114">Nombre de clase</span><span class="sxs-lookup"><span data-stu-id="34b51-114">Class name</span></span>|<span data-ttu-id="34b51-115">Tipo de control</span><span class="sxs-lookup"><span data-stu-id="34b51-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="34b51-116">Botón</span><span class="sxs-lookup"><span data-stu-id="34b51-116">Button</span></span>|<span data-ttu-id="34b51-117">Botón</span><span class="sxs-lookup"><span data-stu-id="34b51-117">Button</span></span>|  
|<span data-ttu-id="34b51-118">Botón</span><span class="sxs-lookup"><span data-stu-id="34b51-118">Button</span></span>|<span data-ttu-id="34b51-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="34b51-119">RadioButton</span></span>|  
|<span data-ttu-id="34b51-120">Botón</span><span class="sxs-lookup"><span data-stu-id="34b51-120">Button</span></span>|<span data-ttu-id="34b51-121">Grupo</span><span class="sxs-lookup"><span data-stu-id="34b51-121">Group</span></span>|  
|<span data-ttu-id="34b51-122">Botón</span><span class="sxs-lookup"><span data-stu-id="34b51-122">Button</span></span>|<span data-ttu-id="34b51-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="34b51-123">CheckBox</span></span>|  
|<span data-ttu-id="34b51-124">Botón</span><span class="sxs-lookup"><span data-stu-id="34b51-124">Button</span></span>|<span data-ttu-id="34b51-125">Hipervínculo</span><span class="sxs-lookup"><span data-stu-id="34b51-125">Hyperlink</span></span>|  
|<span data-ttu-id="34b51-126">Botón</span><span class="sxs-lookup"><span data-stu-id="34b51-126">Button</span></span>|<span data-ttu-id="34b51-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="34b51-127">SplitButton</span></span>|  
|<span data-ttu-id="34b51-128">Botón</span><span class="sxs-lookup"><span data-stu-id="34b51-128">Button</span></span>|<span data-ttu-id="34b51-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="34b51-129">CheckBox</span></span>|  
|<span data-ttu-id="34b51-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="34b51-130">ComboBoxEx32</span></span>|<span data-ttu-id="34b51-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="34b51-131">ComboBox</span></span>|  
|<span data-ttu-id="34b51-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="34b51-132">ComboBox</span></span>|<span data-ttu-id="34b51-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="34b51-133">ComboBox</span></span>|  
|<span data-ttu-id="34b51-134">Edit</span><span class="sxs-lookup"><span data-stu-id="34b51-134">Edit</span></span>|<span data-ttu-id="34b51-135">Documento</span><span class="sxs-lookup"><span data-stu-id="34b51-135">Document</span></span>|  
|<span data-ttu-id="34b51-136">Edit</span><span class="sxs-lookup"><span data-stu-id="34b51-136">Edit</span></span>|<span data-ttu-id="34b51-137">Edit</span><span class="sxs-lookup"><span data-stu-id="34b51-137">Edit</span></span>|  
|<span data-ttu-id="34b51-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="34b51-138">SysLink</span></span>|<span data-ttu-id="34b51-139">Hipervínculo</span><span class="sxs-lookup"><span data-stu-id="34b51-139">Hyperlink</span></span>|  
|<span data-ttu-id="34b51-140">Estático</span><span class="sxs-lookup"><span data-stu-id="34b51-140">Static</span></span>|<span data-ttu-id="34b51-141">Texto</span><span class="sxs-lookup"><span data-stu-id="34b51-141">Text</span></span>|  
|<span data-ttu-id="34b51-142">Estático</span><span class="sxs-lookup"><span data-stu-id="34b51-142">Static</span></span>|<span data-ttu-id="34b51-143">Imagen</span><span class="sxs-lookup"><span data-stu-id="34b51-143">Image</span></span>|  
|<span data-ttu-id="34b51-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="34b51-144">SysIPAddress32</span></span>|<span data-ttu-id="34b51-145">Personalizar</span><span class="sxs-lookup"><span data-stu-id="34b51-145">Custom</span></span>|  
|<span data-ttu-id="34b51-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="34b51-146">SysHeader32</span></span>|<span data-ttu-id="34b51-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="34b51-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="34b51-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="34b51-148">SysListView32</span></span>|<span data-ttu-id="34b51-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="34b51-149">DataGrid</span></span>|  
|<span data-ttu-id="34b51-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="34b51-150">SysListView32</span></span>|<span data-ttu-id="34b51-151">Lista</span><span class="sxs-lookup"><span data-stu-id="34b51-151">List</span></span>|  
|<span data-ttu-id="34b51-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="34b51-152">ListBox</span></span>|<span data-ttu-id="34b51-153">Lista</span><span class="sxs-lookup"><span data-stu-id="34b51-153">List</span></span>|  
|<span data-ttu-id="34b51-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="34b51-154">ListBox</span></span>|<span data-ttu-id="34b51-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="34b51-155">ListItem</span></span>|  
|<span data-ttu-id="34b51-156">#32768</span><span class="sxs-lookup"><span data-stu-id="34b51-156">#32768</span></span>|<span data-ttu-id="34b51-157">Menú</span><span class="sxs-lookup"><span data-stu-id="34b51-157">Menu</span></span>|  
|<span data-ttu-id="34b51-158">#32768</span><span class="sxs-lookup"><span data-stu-id="34b51-158">#32768</span></span>|<span data-ttu-id="34b51-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="34b51-159">MenuItem</span></span>|  
|<span data-ttu-id="34b51-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="34b51-160">msctls_progress32</span></span>|<span data-ttu-id="34b51-161">Barra de progreso</span><span class="sxs-lookup"><span data-stu-id="34b51-161">ProgressBar</span></span>|  
|<span data-ttu-id="34b51-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="34b51-162">RichEdit</span></span>|<span data-ttu-id="34b51-163">Documentar.</span><span class="sxs-lookup"><span data-stu-id="34b51-163">Document.</span></span> <span data-ttu-id="34b51-164">Vea la nota.</span><span class="sxs-lookup"><span data-stu-id="34b51-164">See note.</span></span>|  
|<span data-ttu-id="34b51-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="34b51-165">RichEdit20A</span></span>|<span data-ttu-id="34b51-166">Documento</span><span class="sxs-lookup"><span data-stu-id="34b51-166">Document</span></span>|  
|<span data-ttu-id="34b51-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="34b51-167">RichEdit20W</span></span>|<span data-ttu-id="34b51-168">Documento</span><span class="sxs-lookup"><span data-stu-id="34b51-168">Document</span></span>|  
|<span data-ttu-id="34b51-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="34b51-169">RichEdit50W</span></span>|<span data-ttu-id="34b51-170">Documento</span><span class="sxs-lookup"><span data-stu-id="34b51-170">Document</span></span>|  
|<span data-ttu-id="34b51-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="34b51-171">ScrollBar</span></span>|<span data-ttu-id="34b51-172">Control deslizante</span><span class="sxs-lookup"><span data-stu-id="34b51-172">Slider</span></span>|  
|<span data-ttu-id="34b51-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="34b51-173">msctls_trackbar32</span></span>|<span data-ttu-id="34b51-174">Control deslizante</span><span class="sxs-lookup"><span data-stu-id="34b51-174">Slider</span></span>|  
|<span data-ttu-id="34b51-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="34b51-175">msctls_updown32</span></span>|<span data-ttu-id="34b51-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="34b51-176">Spinner</span></span>|  
|<span data-ttu-id="34b51-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="34b51-177">msctls_statusbar32</span></span>|<span data-ttu-id="34b51-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="34b51-178">StatusBar</span></span>|  
|<span data-ttu-id="34b51-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="34b51-179">SysTabControl32</span></span>|<span data-ttu-id="34b51-180">Pestaña</span><span class="sxs-lookup"><span data-stu-id="34b51-180">Tab</span></span>|  
|<span data-ttu-id="34b51-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="34b51-181">SysTabControl32</span></span>|<span data-ttu-id="34b51-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="34b51-182">TabItem</span></span>|  
|<span data-ttu-id="34b51-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="34b51-183">ToolbarWindow32</span></span>|<span data-ttu-id="34b51-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="34b51-184">ToolBar</span></span>|  
|<span data-ttu-id="34b51-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="34b51-185">ToolbarWindow32</span></span>|<span data-ttu-id="34b51-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="34b51-186">MenuItem</span></span>|  
|<span data-ttu-id="34b51-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="34b51-187">ToolbarWindow32</span></span>|<span data-ttu-id="34b51-188">Botón</span><span class="sxs-lookup"><span data-stu-id="34b51-188">Button</span></span>|  
|<span data-ttu-id="34b51-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="34b51-189">ToolbarWindow32</span></span>|<span data-ttu-id="34b51-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="34b51-190">CheckBox</span></span>|  
|<span data-ttu-id="34b51-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="34b51-191">ToolbarWindow32</span></span>|<span data-ttu-id="34b51-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="34b51-192">RadioButton</span></span>|  
|<span data-ttu-id="34b51-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="34b51-193">ToolbarWindow32</span></span>|<span data-ttu-id="34b51-194">Separador</span><span class="sxs-lookup"><span data-stu-id="34b51-194">Separator</span></span>|  
|<span data-ttu-id="34b51-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="34b51-195">tooltips_class32</span></span>|<span data-ttu-id="34b51-196">ToolTip</span><span class="sxs-lookup"><span data-stu-id="34b51-196">ToolTip</span></span>|  
|<span data-ttu-id="34b51-197">#32774</span><span class="sxs-lookup"><span data-stu-id="34b51-197">#32774</span></span>|<span data-ttu-id="34b51-198">ToolTip</span><span class="sxs-lookup"><span data-stu-id="34b51-198">ToolTip</span></span>|  
|<span data-ttu-id="34b51-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="34b51-199">ReBarWindow32</span></span>|<span data-ttu-id="34b51-200">Barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="34b51-200">Toolbar</span></span>|  
|<span data-ttu-id="34b51-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="34b51-201">SysTreeView32</span></span>|<span data-ttu-id="34b51-202">Árbol</span><span class="sxs-lookup"><span data-stu-id="34b51-202">Tree</span></span>|  
|<span data-ttu-id="34b51-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="34b51-203">SysTreeView32</span></span>|<span data-ttu-id="34b51-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="34b51-204">TreeItem</span></span>|  
  
 <span data-ttu-id="34b51-205">**Nota:** El control RichEdit solo se admite para las versiones incluidas con Windows Vista (en RichEd20. dll versión 3,1 y posteriores, y MsftEdit. dll versión 4,1 y posteriores).</span><span class="sxs-lookup"><span data-stu-id="34b51-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="34b51-206">No se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="34b51-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="34b51-207">Nombre de clase</span><span class="sxs-lookup"><span data-stu-id="34b51-207">Class name</span></span>|<span data-ttu-id="34b51-208">Tipo de control</span><span class="sxs-lookup"><span data-stu-id="34b51-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="34b51-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="34b51-209">SysAnimate32</span></span>|<span data-ttu-id="34b51-210">Imagen</span><span class="sxs-lookup"><span data-stu-id="34b51-210">Image</span></span>|  
|<span data-ttu-id="34b51-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="34b51-211">SysPager</span></span>|<span data-ttu-id="34b51-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="34b51-212">Spinner</span></span>|  
|<span data-ttu-id="34b51-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="34b51-213">SysDateTimePick32</span></span>|<span data-ttu-id="34b51-214">Personalizar</span><span class="sxs-lookup"><span data-stu-id="34b51-214">Custom</span></span>|  
|<span data-ttu-id="34b51-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="34b51-215">SysMonthCal32</span></span>|<span data-ttu-id="34b51-216">Calendario</span><span class="sxs-lookup"><span data-stu-id="34b51-216">Calendar</span></span>|  
|<span data-ttu-id="34b51-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="34b51-217">MS_WINNOTE</span></span>|<span data-ttu-id="34b51-218">Tooltip</span><span class="sxs-lookup"><span data-stu-id="34b51-218">Tooltip</span></span>|  
|<span data-ttu-id="34b51-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="34b51-219">VBBubble</span></span>|<span data-ttu-id="34b51-220">Tooltip</span><span class="sxs-lookup"><span data-stu-id="34b51-220">Tooltip</span></span>|  
|<span data-ttu-id="34b51-221">ScrollBar (cuando se usa como control independiente)</span><span class="sxs-lookup"><span data-stu-id="34b51-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="34b51-222">Control deslizante</span><span class="sxs-lookup"><span data-stu-id="34b51-222">Slider</span></span>|  
|<span data-ttu-id="34b51-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="34b51-223">SuperGrid</span></span>|<span data-ttu-id="34b51-224">Personalizar</span><span class="sxs-lookup"><span data-stu-id="34b51-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="34b51-225">Controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="34b51-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="34b51-226">Windows Forms controles se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de los proveedores del lado cliente en UIAutomationClientsideProviders. dll.</span><span class="sxs-lookup"><span data-stu-id="34b51-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="34b51-227">Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="34b51-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="34b51-228">Normalmente, los Windows Forms controles que son contenedores administrados para [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controles comunes son compatibles con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34b51-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="34b51-229">Se admiten los siguientes controles.</span><span class="sxs-lookup"><span data-stu-id="34b51-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="34b51-230">Nombre de clase</span><span class="sxs-lookup"><span data-stu-id="34b51-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="34b51-231">Botón</span><span class="sxs-lookup"><span data-stu-id="34b51-231">Button</span></span>|  
|<span data-ttu-id="34b51-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="34b51-232">CheckBox</span></span>|  
|<span data-ttu-id="34b51-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="34b51-233">CheckedListBox</span></span>|  
|<span data-ttu-id="34b51-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="34b51-234">ColorDialog</span></span>|  
|<span data-ttu-id="34b51-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="34b51-235">ComboBox</span></span>|  
|<span data-ttu-id="34b51-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="34b51-236">FolderBrowser</span></span>|  
|<span data-ttu-id="34b51-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="34b51-237">FontDialog</span></span>|  
|<span data-ttu-id="34b51-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="34b51-238">GroupBox</span></span>|  
|<span data-ttu-id="34b51-239">HScrollBar</span><span class="sxs-lookup"><span data-stu-id="34b51-239">HscrollBar</span></span>|  
|<span data-ttu-id="34b51-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="34b51-240">ImageList</span></span>|  
|<span data-ttu-id="34b51-241">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="34b51-241">Label</span></span>|  
|<span data-ttu-id="34b51-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="34b51-242">ListBox</span></span>|  
|<span data-ttu-id="34b51-243">ListView</span><span class="sxs-lookup"><span data-stu-id="34b51-243">ListView</span></span>|  
|<span data-ttu-id="34b51-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="34b51-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="34b51-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="34b51-245">MonthCalendar</span></span>|  
|<span data-ttu-id="34b51-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="34b51-246">NotifyIcon</span></span>|  
|<span data-ttu-id="34b51-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="34b51-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="34b51-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="34b51-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="34b51-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="34b51-249">PrintDialog</span></span>|  
|<span data-ttu-id="34b51-250">Barra de progreso</span><span class="sxs-lookup"><span data-stu-id="34b51-250">ProgressBar</span></span>|  
|<span data-ttu-id="34b51-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="34b51-251">RadioButton</span></span>|  
|<span data-ttu-id="34b51-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="34b51-252">RichTextBox</span></span>|  
|<span data-ttu-id="34b51-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="34b51-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="34b51-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="34b51-254">ScrollableControl</span></span>|  
|<span data-ttu-id="34b51-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="34b51-255">SoundPlayer</span></span>|  
|<span data-ttu-id="34b51-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="34b51-256">StatusBar</span></span>|  
|<span data-ttu-id="34b51-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="34b51-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="34b51-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="34b51-258">TextBox</span></span>|  
|<span data-ttu-id="34b51-259">Temporizador</span><span class="sxs-lookup"><span data-stu-id="34b51-259">Timer</span></span>|  
|<span data-ttu-id="34b51-260">Barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="34b51-260">Toolbar</span></span>|  
|<span data-ttu-id="34b51-261">ToolTip</span><span class="sxs-lookup"><span data-stu-id="34b51-261">ToolTip</span></span>|  
|<span data-ttu-id="34b51-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="34b51-262">TrackBar</span></span>|  
|<span data-ttu-id="34b51-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="34b51-263">TreeView</span></span>|  
|<span data-ttu-id="34b51-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="34b51-264">VscrollBar</span></span>|  
|<span data-ttu-id="34b51-265">ExploradorWeb</span><span class="sxs-lookup"><span data-stu-id="34b51-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="34b51-266">Los siguientes controles se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo a través de la compatibilidad con Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="34b51-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="34b51-267">Es posible que algunas funciones no estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="34b51-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="34b51-268">Nombre del control</span><span class="sxs-lookup"><span data-stu-id="34b51-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="34b51-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="34b51-269">BindingSource</span></span>|  
|<span data-ttu-id="34b51-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="34b51-270">DataGrid</span></span>|  
|<span data-ttu-id="34b51-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="34b51-271">DataGridView</span></span>|  
|<span data-ttu-id="34b51-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="34b51-272">DataNavigator</span></span>|  
|<span data-ttu-id="34b51-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="34b51-273">DomainUpDown</span></span>|  
|<span data-ttu-id="34b51-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="34b51-274">ErrorProvider</span></span>|  
|<span data-ttu-id="34b51-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="34b51-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="34b51-276">Form</span><span class="sxs-lookup"><span data-stu-id="34b51-276">Form</span></span>|  
|<span data-ttu-id="34b51-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="34b51-277">LinkLabel</span></span>|  
|<span data-ttu-id="34b51-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="34b51-278">HelpProvider</span></span>|  
|<span data-ttu-id="34b51-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="34b51-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="34b51-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="34b51-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="34b51-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="34b51-281">NumericUpDown</span></span>|  
|<span data-ttu-id="34b51-282">Panel</span><span class="sxs-lookup"><span data-stu-id="34b51-282">Panel</span></span>|  
|<span data-ttu-id="34b51-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="34b51-283">PictureBox</span></span>|  
|<span data-ttu-id="34b51-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="34b51-284">PrintDocument</span></span>|  
|<span data-ttu-id="34b51-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="34b51-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="34b51-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="34b51-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="34b51-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="34b51-287">PropertyGrid</span></span>|  
|<span data-ttu-id="34b51-288">Control de usuario</span><span class="sxs-lookup"><span data-stu-id="34b51-288">UserControl</span></span>|  
|<span data-ttu-id="34b51-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="34b51-289">ToolStrip</span></span>|  
|<span data-ttu-id="34b51-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="34b51-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="34b51-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="34b51-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="34b51-292">Divisor</span><span class="sxs-lookup"><span data-stu-id="34b51-292">Splitter</span></span>|  
|<span data-ttu-id="34b51-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="34b51-293">RaftingContainer</span></span>|  
|<span data-ttu-id="34b51-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="34b51-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34b51-295">Vea también</span><span class="sxs-lookup"><span data-stu-id="34b51-295">See also</span></span>

- [<span data-ttu-id="34b51-296">UI Automation Control Types</span><span class="sxs-lookup"><span data-stu-id="34b51-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
