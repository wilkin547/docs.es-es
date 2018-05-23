---
title: Novedades de accesibilidad en .NET Framework
ms.custom: updateeachrelease
ms.date: 04/10/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fe7e15e482028b9988d7e560b98be19b6c07427
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="2813b-102">Novedades de accesibilidad en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2813b-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="2813b-103">.NET Framework aspira a que las aplicaciones sean más accesibles para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2813b-103">The .NET Framework aims at making applications more accessible for your users.</span></span> <span data-ttu-id="2813b-104">Las características de accesibilidad permiten que una aplicación proporcione una experiencia adecuada para los usuarios de la tecnología de asistencia.</span><span class="sxs-lookup"><span data-stu-id="2813b-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="2813b-105">A partir de .NET Framework 4.7.1, .NET Framework incluye muchas mejoras de accesibilidad que permiten a los desarrolladores crear aplicaciones accesibles.</span><span class="sxs-lookup"><span data-stu-id="2813b-105">Starting with the .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span> 

## <a name="accessibility-switches"></a><span data-ttu-id="2813b-106">Modificadores de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="2813b-106">Accessibility switches</span></span>

<span data-ttu-id="2813b-107">Puede configurar la aplicación para que opte por recibir características de accesibilidad si su destino es .NET Framework 4.7 o una versión anterior, pero se ejecuta en .NET Framework 4.7.1 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="2813b-107">You can configure your app to opt into accessibility features if it targets the .NET Framework 4.7 or an earlier version but is running on the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="2813b-108">También la puede configurar para que use características heredadas (en vez de aprovechar las ventajas de las características de accesibilidad) si su destino es .NET Framework 4.7.1 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="2813b-108">You can also configure your app to use legacy features (and not take advantage of accessibility features) if it targets the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="2813b-109">Cada versión de .NET Framework que incluya características de accesibilidad cuenta con un modificador de accesibilidad específico de la versión correspondiente, que se agrega al elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) en la sección [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2813b-109">Each version of the .NET Framework that includes accessibility features has a version-specific accessibility switch, which you add to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> <span data-ttu-id="2813b-110">Estos son los modificadores admitidos:</span><span class="sxs-lookup"><span data-stu-id="2813b-110">The following are the supported switches:</span></span>

|<span data-ttu-id="2813b-111">Versión</span><span class="sxs-lookup"><span data-stu-id="2813b-111">Version</span></span>|<span data-ttu-id="2813b-112">Modificador</span><span class="sxs-lookup"><span data-stu-id="2813b-112">Switch</span></span>|
|---|---|
|<span data-ttu-id="2813b-113">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="2813b-113">.NET Framework 4.7.1</span></span>|<span data-ttu-id="2813b-114">"Switch.UseLegacyAccessibilityFeatures"</span><span class="sxs-lookup"><span data-stu-id="2813b-114">"Switch.UseLegacyAccessibilityFeatures"</span></span>|
|<span data-ttu-id="2813b-115">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="2813b-115">.NET Framework 4.7.2</span></span>|<span data-ttu-id="2813b-116">"Switch.UseLegacyAccessibilityFeatures.2"</span><span class="sxs-lookup"><span data-stu-id="2813b-116">"Switch.UseLegacyAccessibilityFeatures.2"</span></span>|

### <a name="taking-advantage-of-accessibility-enhancements"></a><span data-ttu-id="2813b-117">Aprovechar las mejoras de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="2813b-117">Taking advantage of accessibility enhancements</span></span>

<span data-ttu-id="2813b-118">Las nuevas características de accesibilidad están habilitadas de forma predeterminada para las aplicaciones para .NET Framework 4.7.1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="2813b-118">The new accessibility features are enabled by default for applications that target the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="2813b-119">Además, las aplicaciones para versiones anteriores de .NET Framework que se ejecutan en .NET Framework 4.7.1 o posterior pueden optar por no recibir comportamientos de accesibilidad heredados (y, por tanto, usar las mejoras de accesibilidad correspondientes) si se agregan modificadores al elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) de la sección [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del archivo de configuración de la aplicación y sus valores se establecen en `false`.</span><span class="sxs-lookup"><span data-stu-id="2813b-119">In addition, applications that target an earlier version of the .NET Framework but are running on the .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby take advantage of accessibility improvements) by adding switches to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `false`.</span></span> <span data-ttu-id="2813b-120">El siguiente código muestra cómo optar por recibir las mejoras de accesibilidad incluidas en .NET Framework 4.7.1:</span><span class="sxs-lookup"><span data-stu-id="2813b-120">The following shows how to opt in to accessibility enhancements introduced in the .NET Framework 4.7.1:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="2813b-121">Si decide optar por recibir las características de accesibilidad en una versión posterior de .NET Framework, deberá optar por recibir también las características de versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2813b-121">If you choose to opt in to accessibility features in a later version of the .NET Framework, you must also explicitly opt in to the features from earlier versions of the .NET Framework.</span></span> <span data-ttu-id="2813b-122">Para configurar la aplicación para que use las mejoras de accesibilidad de .NET Framework 4.7.1 y 4.7.2, se necesita el siguiente elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):</span><span class="sxs-lookup"><span data-stu-id="2813b-122">Configuring your app to take advantage of accessibility improvements in both the .NET Framework 4.7.1 and 4.7.2 requires the following [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

### <a name="restoring-legacy-behavior"></a><span data-ttu-id="2813b-123">Restaurar el comportamiento heredado</span><span class="sxs-lookup"><span data-stu-id="2813b-123">Restoring legacy behavior</span></span>

<span data-ttu-id="2813b-124">Las aplicaciones para versiones de .NET Framework a partir de la 4.7.1 pueden deshabilitar las características de accesibilidad; para ello, hay que agregar modificadores al elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) en la sección [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del archivo de configuración de la aplicación y establecer sus valores en `true`.</span><span class="sxs-lookup"><span data-stu-id="2813b-124">Applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding switches to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `true`.</span></span> <span data-ttu-id="2813b-125">Por ejemplo, la siguiente configuración opta por no recibir las características de accesibilidad incluidas en .NET Framework 4.7.2:</span><span class="sxs-lookup"><span data-stu-id="2813b-125">For example, the following configuration opts out of accessibility features introduced in .NET Framework 4.7.2:</span></span>  

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-472"></a><span data-ttu-id="2813b-126">Novedades de accesibilidad en .NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="2813b-126">What's new in accessibility in the .NET Framework 4.7.2</span></span>

<span data-ttu-id="2813b-127">.NET Framework 4.7.2 incluye nuevas características de accesibilidad en las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="2813b-127">The .NET Framework 4.7.2 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="2813b-128">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2813b-128">Windows Forms</span></span>](#winforms472)

- [<span data-ttu-id="2813b-129">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="2813b-129">Windows Presentation Foundation (WPF)</span></span>](#wpf472)

<a name="winforms472"></a>
### <a name="windows-forms"></a><span data-ttu-id="2813b-130">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2813b-130">Windows Forms</span></span>

<span data-ttu-id="2813b-131">**Colores definidos por el sistema operativo en los temas de contraste alto**</span><span class="sxs-lookup"><span data-stu-id="2813b-131">**OS-defined colors in High Contrast themes**</span></span>

<span data-ttu-id="2813b-132">A partir de .NET Framework 4.7.2, Windows Forms usa colores definidos por el sistema operativo en los temas de contraste alto.</span><span class="sxs-lookup"><span data-stu-id="2813b-132">Starting with .NET Framework 4.7.2, Windows Forms uses colors defined by the operating system in High Contrast themes.</span></span> <span data-ttu-id="2813b-133">Esto afecta a los siguientes controles:</span><span class="sxs-lookup"><span data-stu-id="2813b-133">This affects the following controls:</span></span>

- <span data-ttu-id="2813b-134">La flecha desplegable del control <xref:System.Windows.Forms.ToolStripDropDownButton>.</span><span class="sxs-lookup"><span data-stu-id="2813b-134">The drop-down arrow of the <xref:System.Windows.Forms.ToolStripDropDownButton> control.</span></span>

- <span data-ttu-id="2813b-135">Los controles <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> y <xref:System.Windows.Forms.CheckBox> que tienen <xref:System.Windows.Forms.ButtonBase.FlatStyle> establecido en <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> o en <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2813b-135">The <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with <xref:System.Windows.Forms.ButtonBase.FlatStyle> set to <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> or <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2813b-136">Antes, los colores de fondo y de texto seleccionados no tenían contraste y eran difíciles de leer.</span><span class="sxs-lookup"><span data-stu-id="2813b-136">Previously, selected text and background colors were not contrasting and were hard to read.</span></span>

- <span data-ttu-id="2813b-137">Controles contenidos en un <xref:System.Windows.Forms.GroupBox> que tiene su propiedad <xref:System.Windows.Forms.Control.Enabled> establecida en `false`.</span><span class="sxs-lookup"><span data-stu-id="2813b-137">Controls contained within a <xref:System.Windows.Forms.GroupBox> that has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>
 
- <span data-ttu-id="2813b-138">Los controles <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox> y <xref:System.Windows.Forms.ToolStripDropDownButton> que tienen una relación de contraste de luminosidad mayor en el modo de contraste alto.</span><span class="sxs-lookup"><span data-stu-id="2813b-138">The <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox>, and <xref:System.Windows.Forms.ToolStripDropDownButton> controls, which have an increased luminosity contrast ratio in High Contrast Mode.</span></span>

- <span data-ttu-id="2813b-139">La propiedad <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> de <xref:System.Windows.Forms.DataGridViewLinkCell>.</span><span class="sxs-lookup"><span data-stu-id="2813b-139">The <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> property of the <xref:System.Windows.Forms.DataGridViewLinkCell>.</span></span>

<span data-ttu-id="2813b-140">**Mejoras de Narrador**</span><span class="sxs-lookup"><span data-stu-id="2813b-140">**Narrator improvements**</span></span>

<span data-ttu-id="2813b-141">A partir de .NET Framework 4.7.2, la compatibilidad con Narrador ha mejorado de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="2813b-141">Starting with the .NET Framework 4.7.2, Narrator support is enhanced as follows:</span></span>

- <span data-ttu-id="2813b-142">El valor de la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> se anuncia al anunciar el texto de un objeto <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="2813b-142">It announces the value of the <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> property when announcing the text of a <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span> 

- <span data-ttu-id="2813b-143">Indica cuándo un objeto <xref:System.Windows.Forms.ToolStripMenuItem> tiene su propiedad <xref:System.Windows.Forms.Control.Enabled> establecida en `false`.</span><span class="sxs-lookup"><span data-stu-id="2813b-143">It indicates when a <xref:System.Windows.Forms.ToolStripMenuItem> has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="2813b-144">Ofrece información sobre el estado de una casilla cuando la propiedad <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> está establecida en `true`.</span><span class="sxs-lookup"><span data-stu-id="2813b-144">It gives feedback on the state of a check box when the <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> property is set to `true`.</span></span>

- <span data-ttu-id="2813b-145">El orden de foco del Modo de examen de Narrador es coherente con el orden visual de los controles del cuadro de diálogo de descarga de ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="2813b-145">Narrator's Scan Mode focus order is consistent with the visual order of the controls on the ClickOnce download dialog window.</span></span>

<span data-ttu-id="2813b-146">**Mejoras de DataGridView**</span><span class="sxs-lookup"><span data-stu-id="2813b-146">**DataGridView improvements**</span></span>

<span data-ttu-id="2813b-147">A partir de .NET Framework 4.7.2, el control <xref:System.Windows.Forms.DataGridView> presenta las siguientes mejoras de accesibilidad:</span><span class="sxs-lookup"><span data-stu-id="2813b-147">Starting with the .NET Framework 4.7.2, the <xref:System.Windows.Forms.DataGridView> control has introduced the following accessibility improvements:</span></span>

- <span data-ttu-id="2813b-148">Las filas se pueden ordenar con el teclado.</span><span class="sxs-lookup"><span data-stu-id="2813b-148">Rows can be sorted using the keyboard.</span></span> <span data-ttu-id="2813b-149">Un usuario puede presionar la tecla F3 para ordenar por la columna actual.</span><span class="sxs-lookup"><span data-stu-id="2813b-149">A user can use the F3 key in order to sort by the current column.</span></span>

- <span data-ttu-id="2813b-150">Cuando <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> se establece en <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, el encabezado de columna cambia de color para indicar la columna actual cuando el usuario se desplaza entre las celdas de la fila actual.</span><span class="sxs-lookup"><span data-stu-id="2813b-150">When the <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> is set to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, the column header changes color to indicate the current column as the user tabs through the cells in the current row.</span></span>

- <span data-ttu-id="2813b-151">La propiedad <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> de <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> devuelve el control primario correcto.</span><span class="sxs-lookup"><span data-stu-id="2813b-151">The <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> property of a  <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> returns the correct parent control.</span></span>

<span data-ttu-id="2813b-152">**Indicaciones visuales mejoradas**</span><span class="sxs-lookup"><span data-stu-id="2813b-152">**Improved visual cues**</span></span>

- <span data-ttu-id="2813b-153">Los controles <xref:System.Windows.Forms.RadioButton> y <xref:System.Windows.Forms.CheckBox> con una propiedad <xref:System.Windows.Forms.ButtonBase.Text> vacía se mostrará un indicador de foco cuando reciban el foco.</span><span class="sxs-lookup"><span data-stu-id="2813b-153">The <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with an empty <xref:System.Windows.Forms.ButtonBase.Text> property  display a focus indicator when they receive the focus.</span></span>

<span data-ttu-id="2813b-154">**Compatibilidad con la cuadrícula de propiedades mejorada**</span><span class="sxs-lookup"><span data-stu-id="2813b-154">**Improved Property Grid Support**</span></span>

- <span data-ttu-id="2813b-155">Ahora los elementos secundarios del control <xref:System.Windows.Forms.PropertyGrid> devuelven un valor `true` para la propiedad <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> solo cuando un elemento PropertyGrid está habilitado.</span><span class="sxs-lookup"><span data-stu-id="2813b-155">The <xref:System.Windows.Forms.PropertyGrid> control child elements now return a `true` for the  <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> property only when a PropertyGrid element is enabled.</span></span>

- <span data-ttu-id="2813b-156">Los elementos secundarios del control <xref:System.Windows.Forms.PropertyGrid> devuelven un valor `false` para la propiedad <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> solo cuando el usuario pueda modificar un elemento PropertyGrid.</span><span class="sxs-lookup"><span data-stu-id="2813b-156">The <xref:System.Windows.Forms.PropertyGrid> control child elements return a `false` for the <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> property only when a PropertyGrid element can be changed by the user.</span></span>

<span data-ttu-id="2813b-157">**Navegación mejorada mediante el teclado**</span><span class="sxs-lookup"><span data-stu-id="2813b-157">**Improved keyboard navigation**</span></span>

- <span data-ttu-id="2813b-158">El control <xref:System.Windows.Forms.ToolStripButton> permite el foco cuando se incluye dentro de un control <xref:System.Windows.Forms.ToolStripPanel> que tiene la propiedad <xref:System.Windows.Forms.ToolStripPanel.TabStop> establecida en `true`.</span><span class="sxs-lookup"><span data-stu-id="2813b-158">The <xref:System.Windows.Forms.ToolStripButton> control allows focus when contained within a <xref:System.Windows.Forms.ToolStripPanel> that has the <xref:System.Windows.Forms.ToolStripPanel.TabStop> property set to `true`</span></span>

<a name="wpf472"></a>
### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="2813b-159">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="2813b-159">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="2813b-160">**Cambios en los controles CheckBox y RadioButton**</span><span class="sxs-lookup"><span data-stu-id="2813b-160">**Changes to the CheckBox and RadioButton controls**</span></span>

<span data-ttu-id="2813b-161">En .NET Framework 4.7.1 y versiones anteriores, los controles <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> y <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> de WPF tenían objetos visuales de foco incoherentes y, en los temas Clásico y Contraste alto, eran incorrectos.</span><span class="sxs-lookup"><span data-stu-id="2813b-161">In the .NET Framework 4.7.1 and earlier versions, the WPF <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> and <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> controls have inconsistent and, in Classic and High Contrast themes, incorrect focus visuals.</span></span>  <span data-ttu-id="2813b-162">Estos problemas se producen en casos en los que no se ha definido ningún contenido para los controles.</span><span class="sxs-lookup"><span data-stu-id="2813b-162">These issues occur in cases where the controls do not have any content set.</span></span>  <span data-ttu-id="2813b-163">Esto puede hacer que la transición entre los temas sea confusa y el objeto visual de foco difícil de ver.</span><span class="sxs-lookup"><span data-stu-id="2813b-163">This can make the transition between themes confusing and the focus visual hard to see.</span></span>

<span data-ttu-id="2813b-164">En .NET Framework 4.7.2, estos objetos visuales son ahora más coherentes entre los temas y se ven más fácilmente en los temas Clásico y Contraste alto.</span><span class="sxs-lookup"><span data-stu-id="2813b-164">In the .NET Framework 4.7.2, these visuals are now more consistent across themes and more easily visible in Classic and High Contrast themes.</span></span>

<span data-ttu-id="2813b-165">**Controles de WinForms hospedados en una aplicación WPF**</span><span class="sxs-lookup"><span data-stu-id="2813b-165">**WinForms controls hosted in a WPF application**</span></span>

<span data-ttu-id="2813b-166">En un control de WinForms hospedado en una aplicación WPF en .NET Framework 4.7.1 y versiones anteriores, no se podía usar el tabulador para salir de la capa de WinForms si el primer o último control de esa capa era el control <xref:System.Windows.Forms.Integration.ElementHost> de WPF.</span><span class="sxs-lookup"><span data-stu-id="2813b-166">For WinForms control hosted in a WPF application in the .NET Framework 4.7.1 and earlier versions, users couldn't tab out of the WinForms layer if the first or last control in that layer is the WPF <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span> <span data-ttu-id="2813b-167">Ahora, en .NET Framework 4.7.2 se puede usar el tabulador para salir de la capa de WinForms.</span><span class="sxs-lookup"><span data-stu-id="2813b-167">In the .NET Framework 4.7.2, users are now able to tab out of the WinForms layer.</span></span>

<span data-ttu-id="2813b-168">Con todo, puede que las aplicaciones automatizadas que se basan en que el foco no escape nunca de la capa de WinForms dejen de funcionar según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="2813b-168">However, automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a><span data-ttu-id="2813b-169">Novedades de accesibilidad en .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="2813b-169">What's new in accessibility in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="2813b-170">.NET Framework 4.7.1 incluye nuevas características de accesibilidad en las áreas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2813b-170">The .NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="2813b-171">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="2813b-171">Windows Presentation Foundation (WPF)</span></span>](#wpf471)

- [<span data-ttu-id="2813b-172">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2813b-172">Windows Forms</span></span>](#winforms471)

- [<span data-ttu-id="2813b-173">Controles web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2813b-173">ASP.NET web controls</span></span>](#aspnet471)

- [<span data-ttu-id="2813b-174">Herramientas del SDK de .NET</span><span class="sxs-lookup"><span data-stu-id="2813b-174">.NET SDK Tools</span></span>](#tools471)

- [<span data-ttu-id="2813b-175">Diseñador de flujo de trabajo de Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="2813b-175">Windows Workflow Foundation (WF) Workflow Designer</span></span>](#wf471)

<a name="wpf471"></a>
### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="2813b-176">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="2813b-176">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="2813b-177">**Mejoras del lector de pantalla**</span><span class="sxs-lookup"><span data-stu-id="2813b-177">**Screen reader improvements**</span></span>

<span data-ttu-id="2813b-178">Si las mejoras de accesibilidad están habilitadas, .NET Framework 4.7.1 incluye las siguientes mejoras que afectan a los lectores de pantalla:</span><span class="sxs-lookup"><span data-stu-id="2813b-178">If accessibility improvements are enabled, the .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="2813b-179">En .NET Framework 4.7 y versiones anteriores, los lectores de pantalla anunciaban los controles <xref:System.Windows.Controls.Expander> como botones.</span><span class="sxs-lookup"><span data-stu-id="2813b-179">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="2813b-180">A partir de .NET Framework 4.7.1, se anuncian correctamente como grupos que se pueden contraer y expandir.</span><span class="sxs-lookup"><span data-stu-id="2813b-180">Starting with the .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="2813b-181">En .NET Framework 4.7 y versiones anteriores, los lectores de pantalla anunciaban los controles <xref:System.Windows.Controls.DataGridCell> como "personalizados".</span><span class="sxs-lookup"><span data-stu-id="2813b-181">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="2813b-182">A partir de .NET Framework 4.7.1, se anuncian correctamente como celdas de cuadrícula de datos (localizadas).</span><span class="sxs-lookup"><span data-stu-id="2813b-182">Starting with the .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>
 
- <span data-ttu-id="2813b-183">A partir de .NET Framework 4.7.1, los lectores de pantalla anuncian el nombre de un <xref:System.Windows.Controls.ComboBox> editable.</span><span class="sxs-lookup"><span data-stu-id="2813b-183">Starting with the .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="2813b-184">En .NET Framework 4.7 y versiones anteriores, los controles <xref:System.Windows.Controls.PasswordBox> se anunciaban como "no hay elemento a la vista" o tenían un comportamiento incorrecto.</span><span class="sxs-lookup"><span data-stu-id="2813b-184">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="2813b-185">Este problema se corrigió a partir de .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="2813b-185">This issue is fixed starting with the .NET Framework 4.7.1.</span></span>

<span data-ttu-id="2813b-186">**Compatibilidad con las regiones activas de UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="2813b-186">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="2813b-187">Los lectores de pantalla como Narrador ayudan a los usuarios a leer el contenido de la interfaz de usuario de una aplicación, normalmente mediante salida de texto a voz del contenido de la interfaz de usuario que tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="2813b-187">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="2813b-188">Pero si un elemento de la interfaz de usuario cambia y no tiene el foco, puede que no se notifique al usuario y este pierda información importante.</span><span class="sxs-lookup"><span data-stu-id="2813b-188">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="2813b-189">Las regiones activas aspiran a resolver este problema.</span><span class="sxs-lookup"><span data-stu-id="2813b-189">Live regions aim at solving this problem.</span></span> <span data-ttu-id="2813b-190">Un desarrollador puede usarlas para informar al lector de pantalla o a cualquier otro cliente de UIAutomation de que se ha realizado un cambio importante en un elemento de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="2813b-190">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="2813b-191">Luego el lector de pantalla puede decidir cómo y cuándo informar al usuario de este cambio.</span><span class="sxs-lookup"><span data-stu-id="2813b-191">The screen reader can then decide how and when to inform the user of this change.</span></span> 

<span data-ttu-id="2813b-192">Para admitir las regiones activas, se han agregado las siguientes API a WPF:</span><span class="sxs-lookup"><span data-stu-id="2813b-192">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="2813b-193">Los campos <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> y <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>, que identifican a la propiedad **LiveSetting** y al evento **LiveRegionChanged**.</span><span class="sxs-lookup"><span data-stu-id="2813b-193">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="2813b-194">Se pueden establecer mediante XAML.</span><span class="sxs-lookup"><span data-stu-id="2813b-194">They can be set by using XAML.</span></span>

- <span data-ttu-id="2813b-195">La propiedad adjunta **AutomationProperties.LiveSetting**, que informa al lector de pantalla de la importancia del cambio de la interfaz de usuario para el usuario.</span><span class="sxs-lookup"><span data-stu-id="2813b-195">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="2813b-196">La propiedad <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>, que identifica a la propiedad adjunta **AutomationProperties.LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="2813b-196">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>
 
- <span data-ttu-id="2813b-197">El método <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>, que se puede invalidar para proporcionar un valor **LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="2813b-197">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="2813b-198">Los métodos <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> y <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>, que obtienen y establecen un valor **LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="2813b-198">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>
 
- <span data-ttu-id="2813b-199">La enumeración <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>, que define los siguientes posibles valores **LiveSetting**:</span><span class="sxs-lookup"><span data-stu-id="2813b-199">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

   - <span data-ttu-id="2813b-200"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2813b-200"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2813b-201">El elemento no envía notificaciones si ha cambiado el contenido de la región activa.</span><span class="sxs-lookup"><span data-stu-id="2813b-201">The element does not send notifications if the content of the live region has changed.</span></span>   
   - <span data-ttu-id="2813b-202"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2813b-202"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2813b-203">El elemento envía notificaciones que no interrumpen el trabajo si ha cambiado el contenido de la región activa.</span><span class="sxs-lookup"><span data-stu-id="2813b-203">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>   

  - <span data-ttu-id="2813b-204"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2813b-204"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2813b-205">El elemento envía notificaciones que interrumpen el trabajo si ha cambiado el contenido de la región activa.</span><span class="sxs-lookup"><span data-stu-id="2813b-205">The element sends interruptive notifications if the content of the live region has changed.</span></span>   

<span data-ttu-id="2813b-206">Puede crear una región activa si establece la propiedad **AutomationProperties.LiveSetting** en el elemento de interés, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2813b-206">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="2813b-207">Cuando cambian los datos de la región activa y necesita informar a un lector de pantalla, puede generar un evento de forma explícita, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2813b-207">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="2813b-208">**Contraste alto**</span><span class="sxs-lookup"><span data-stu-id="2813b-208">**High contrast**</span></span>

<span data-ttu-id="2813b-209">A partir de .NET Framework 4.7.1, se han realizado mejoras de contraste alto en diversos controles de WPF.</span><span class="sxs-lookup"><span data-stu-id="2813b-209">Starting with the .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="2813b-210">Ahora son visibles cuando el tema <xref:System.Windows.SystemParameters.HighContrast%2A> está establecido.</span><span class="sxs-lookup"><span data-stu-id="2813b-210">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="2813b-211">Se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2813b-211">These include:</span></span>

- <span data-ttu-id="2813b-212">Control <xref:System.Windows.Controls.Expander></span><span class="sxs-lookup"><span data-stu-id="2813b-212"><xref:System.Windows.Controls.Expander> control</span></span>

    <span data-ttu-id="2813b-213">El objeto visual de foco del control <xref:System.Windows.Controls.Expander> ahora es visible.</span><span class="sxs-lookup"><span data-stu-id="2813b-213">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="2813b-214">Los objetos visuales de teclado de los controles <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.RadioButton> también son visibles.</span><span class="sxs-lookup"><span data-stu-id="2813b-214">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="2813b-215">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2813b-215">For example:</span></span>

    <span data-ttu-id="2813b-216">Antes:</span><span class="sxs-lookup"><span data-stu-id="2813b-216">Before:</span></span> 
    
    ![Control de expansor con foco antes de las mejoras de accesibilidad](media/expander-before.png)

    <span data-ttu-id="2813b-218">Después:</span><span class="sxs-lookup"><span data-stu-id="2813b-218">After:</span></span> 

    ![Control de expansor con foco después de las mejoras de accesibilidad](media/expander-after.png)

- <span data-ttu-id="2813b-220">Controles <xref:System.Windows.Controls.CheckBox> y <xref:System.Windows.Controls.RadioButton></span><span class="sxs-lookup"><span data-stu-id="2813b-220"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>
 
    <span data-ttu-id="2813b-221">El texto de los controles <xref:System.Windows.Controls.CheckBox> y <xref:System.Windows.Controls.RadioButton> ahora es más fácil de ver cuando se selecciona en los temas de contraste alto.</span><span class="sxs-lookup"><span data-stu-id="2813b-221">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="2813b-222">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2813b-222">For example:</span></span>

    <span data-ttu-id="2813b-223">Antes:</span><span class="sxs-lookup"><span data-stu-id="2813b-223">Before:</span></span> 

    ![Botón de opción de contraste alto con foco antes de las mejoras de accesibilidad](media/radio-button-before.png)
    
    <span data-ttu-id="2813b-225">Después:</span><span class="sxs-lookup"><span data-stu-id="2813b-225">After:</span></span> 

    ![Botón de opción de contraste alto con foco después de las mejoras de accesibilidad](media/radio-button-after.png)

- <span data-ttu-id="2813b-227">Control <xref:System.Windows.Controls.ComboBox></span><span class="sxs-lookup"><span data-stu-id="2813b-227"><xref:System.Windows.Controls.ComboBox> control</span></span>
 
    <span data-ttu-id="2813b-228">A partir de .NET Framework 4.7.1, el borde de un control <xref:System.Windows.Controls.ComboBox> deshabilitado es del mismo color que el texto deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="2813b-228">Starting with the .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="2813b-229">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2813b-229">For example:</span></span>
    
    <span data-ttu-id="2813b-230">Antes:</span><span class="sxs-lookup"><span data-stu-id="2813b-230">Before:</span></span> 

     ![Borde y texto de cuadro combinado deshabilitado antes de las mejoras de accesibilidad](media/combo-disabled-before.png)

    <span data-ttu-id="2813b-232">Después:</span><span class="sxs-lookup"><span data-stu-id="2813b-232">After:</span></span>   

     ![Borde y texto de cuadro combinado deshabilitado después de las mejoras de accesibilidad](media/combo-disabled-after.png)

    <span data-ttu-id="2813b-234">Además, los botones deshabilitados y con foco usan el color de tema correcto.</span><span class="sxs-lookup"><span data-stu-id="2813b-234">In addition, disabled and focused buttons use the correct theme color.</span></span>

    <span data-ttu-id="2813b-235">Antes:</span><span class="sxs-lookup"><span data-stu-id="2813b-235">Before:</span></span>

    ![Colores de tema de botón antes de las mejoras de accesibilidad](media/button-themes-before.png) 
    
    <span data-ttu-id="2813b-237">Después:</span><span class="sxs-lookup"><span data-stu-id="2813b-237">After:</span></span> 

    ![Colores de tema de botón después de las mejoras de accesibilidad](media/button-themes-after.png) 

    <span data-ttu-id="2813b-239">Por último, en .NET Framework 4.7 y versiones anteriores, al establecer el estilo de un control <xref:System.Windows.Controls.ComboBox> en `Toolbar.ComboBoxStyleKey`, la flecha de lista desplegable se hacía invisible.</span><span class="sxs-lookup"><span data-stu-id="2813b-239">Finally, in the .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="2813b-240">Este problema se corrigió a partir de .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="2813b-240">This issue is fixed starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="2813b-241">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2813b-241">For example:</span></span>

    <span data-ttu-id="2813b-242">Antes:</span><span class="sxs-lookup"><span data-stu-id="2813b-242">Before:</span></span> 

    ![Toolbar.ComboBoxStyleKey antes de las mejoras de accesibilidad](media/comboboxstylekey-before.png) 
    
    <span data-ttu-id="2813b-244">Después:</span><span class="sxs-lookup"><span data-stu-id="2813b-244">After:</span></span> 

    ![Toolbar.ComboBoxStyleKey después de las mejoras de accesibilidad](media/comboboxstylekey-after.png) 

- <span data-ttu-id="2813b-246">Control <xref:System.Windows.Controls.DataGrid></span><span class="sxs-lookup"><span data-stu-id="2813b-246"><xref:System.Windows.Controls.DataGrid> control</span></span>

    <span data-ttu-id="2813b-247">A partir de .NET Framework 4.7.1, la flecha de indicador de orden de los controles <xref:System.Windows.Controls.DataGrid> usa los colores de tema correctos.</span><span class="sxs-lookup"><span data-stu-id="2813b-247">Starting with the .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="2813b-248">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2813b-248">For example:</span></span>

    <span data-ttu-id="2813b-249">Antes:</span><span class="sxs-lookup"><span data-stu-id="2813b-249">Before:</span></span> 

    ![Flecha de indicador de orden antes de las mejoras de accesibilidad](media/sort-indicator-before.png) 
    
    <span data-ttu-id="2813b-251">Después:</span><span class="sxs-lookup"><span data-stu-id="2813b-251">After:</span></span>   
 
    ![Flecha de indicador de orden después de las mejoras de accesibilidad](media/sort-indicator-after.png) 
    
    <span data-ttu-id="2813b-253">Además, en .NET Framework 4.7 y versiones anteriores, el estilo de vínculo predeterminado cambiaba a un color incorrecto cuando se colocaba el mouse encima en los modos de contraste alto.</span><span class="sxs-lookup"><span data-stu-id="2813b-253">In addition, in the .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="2813b-254">Esto se ha resuelto a partir de .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="2813b-254">This is resolved starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="2813b-255">Del mismo modo, a partir de .NET Framework 4.7.1, las columnas de casilla <xref:System.Windows.Controls.DataGrid> usan los colores esperados para comentarios de foco de teclado.</span><span class="sxs-lookup"><span data-stu-id="2813b-255">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with the .NET Framework 4.7.1.</span></span>

    <span data-ttu-id="2813b-256">Antes:</span><span class="sxs-lookup"><span data-stu-id="2813b-256">Before:</span></span> 

    ![Estilo de vínculo predeterminado de cuadrícula de datos antes de las mejoras de accesibilidad](media/default-link-style-before.png) 
 
    <span data-ttu-id="2813b-258">Después:</span><span class="sxs-lookup"><span data-stu-id="2813b-258">After:</span></span>    
  
    ![Estilo de vínculo predeterminado de cuadrícula de datos después de las mejoras de accesibilidad](media/default-link-style-after.png)  

<span data-ttu-id="2813b-260">Para más información sobre las mejoras de accesibilidad de WPF en .NET Framework 4.7.1, vea [Mejoras de accesibilidad en WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span><span class="sxs-lookup"><span data-stu-id="2813b-260">For more information on WPF accessibility improvements in the .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

<a name="winforms471"></a>
## <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="2813b-261">Mejoras de accesibilidad de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2813b-261">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="2813b-262">En .NET Framework 4.7.1, Windows Forms (WinForms) incluye cambios de accesibilidad en las áreas siguientes.</span><span class="sxs-lookup"><span data-stu-id="2813b-262">In the .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="2813b-263">**Visualización mejorada en modo de contraste alto**</span><span class="sxs-lookup"><span data-stu-id="2813b-263">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="2813b-264">A partir de .NET Framework 4.7.1, varios controles de WinForms ofrecen una representación mejorada en los modos de contraste alto disponibles en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="2813b-264">Starting with the .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="2813b-265">Windows 10 ha cambiado los valores de algunos colores del sistema de contraste alto y Windows Forms se basa en el marco de trabajo de Windows 10 Win32.</span><span class="sxs-lookup"><span data-stu-id="2813b-265">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="2813b-266">Para obtener la mejor experiencia, trabaje en la versión más reciente de Windows y use los cambios más recientes del sistema operativo al agregar un archivo app.manifest en una aplicación de prueba y quitar los comentarios de la línea del sistema operativo compatible con Windows 10 para tenga este aspecto:</span><span class="sxs-lookup"><span data-stu-id="2813b-266">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!-- Windows 10 -->
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
<span data-ttu-id="2813b-267">Algunos ejemplos de cambios de contraste alto:</span><span class="sxs-lookup"><span data-stu-id="2813b-267">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="2813b-268">Las marcas de verificación de los elementos <xref:System.Windows.Forms.MenuStrip> son más fáciles de ver.</span><span class="sxs-lookup"><span data-stu-id="2813b-268">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="2813b-269">Cuando se activan, los elementos <xref:System.Windows.Forms.MenuStrip> deshabilitados son más fáciles de ver.</span><span class="sxs-lookup"><span data-stu-id="2813b-269">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="2813b-270">El texto de un control <xref:System.Windows.Forms.Button> seleccionado contrasta con el color de selección.</span><span class="sxs-lookup"><span data-stu-id="2813b-270">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="2813b-271">El texto deshabilitado es más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="2813b-271">Disabled text is easier to read.</span></span> <span data-ttu-id="2813b-272">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2813b-272">For example:</span></span>

    <span data-ttu-id="2813b-273">Antes:</span><span class="sxs-lookup"><span data-stu-id="2813b-273">Before:</span></span>

    ![Texto deshabilitado antes de las mejoras de accesibilidad](media/wf-disabled-before.png) 

    <span data-ttu-id="2813b-275">Después:</span><span class="sxs-lookup"><span data-stu-id="2813b-275">After:</span></span>

    ![Texto deshabilitado después de las mejoras de accesibilidad](media/wf-disabled-after.png) 

- <span data-ttu-id="2813b-277">Mejoras de contraste alto en el cuadro de diálogo de excepción de subproceso.</span><span class="sxs-lookup"><span data-stu-id="2813b-277">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="2813b-278">**Compatibilidad mejorada con Narrador**</span><span class="sxs-lookup"><span data-stu-id="2813b-278">**Improved Narrator support**</span></span>

<span data-ttu-id="2813b-279">Windows Forms en .NET Framework 4.7.1 incluye las siguientes mejoras de accesibilidad para Narrador:</span><span class="sxs-lookup"><span data-stu-id="2813b-279">Windows Forms in the .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="2813b-280">Narrador, así como otras herramientas de automatización de la interfaz de usuario, pueden acceder al control <xref:System.Windows.Forms.MonthCalendar>.</span><span class="sxs-lookup"><span data-stu-id="2813b-280">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="2813b-281">El control <xref:System.Windows.Forms.CheckedListBox> avisa a Narrador cuando ha cambiado el estado de activación de un elemento para que el usuario sepa que ha cambiado el valor de un elemento de lista.</span><span class="sxs-lookup"><span data-stu-id="2813b-281">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>
 
- <span data-ttu-id="2813b-282">El control <xref:System.Windows.Forms.DataGridViewCell> notifica el estado correcto de solo lectura a Narrador.</span><span class="sxs-lookup"><span data-stu-id="2813b-282">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>
 
- <span data-ttu-id="2813b-283">Narrador ahora puede leer texto <xref:System.Windows.Forms.ToolStripMenuItem> deshabilitado, mientras que anteriormente omitía los elementos de menú deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="2813b-283">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="2813b-284">**Compatibilidad mejorada con los patrones de accesibilidad de UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="2813b-284">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="2813b-285">A partir de .NET Framework 4.7.1, los desarrolladores de herramientas de tecnología de accesibilidad pueden aprovechar los patrones comunes de accesibilidad de API y las propiedades de varios controles de WinForms.</span><span class="sxs-lookup"><span data-stu-id="2813b-285">Starting with the .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="2813b-286">Estas mejoras de accesibilidad incluyen:</span><span class="sxs-lookup"><span data-stu-id="2813b-286">These accessibility improvements include:</span></span>

- <span data-ttu-id="2813b-287"><xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.ToolStripSplitButton> ahora son compatibles con el [patrón de expansión o contracción](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="2813b-287">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>
 
- <span data-ttu-id="2813b-288"><xref:System.Windows.Forms.DataGridViewCheckBoxCell> ahora es compatible con el [patrón de alternancia](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="2813b-288">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>
 
- <span data-ttu-id="2813b-289">El control <xref:System.Windows.Forms.ToolStripItem> admite la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> y el [patrón de expansión o contracción](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="2813b-289">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="2813b-290">Los controles <xref:System.Windows.Forms.NumericUpDown> y <xref:System.Windows.Forms.DomainUpDown> admiten la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>.</span><span class="sxs-lookup"><span data-stu-id="2813b-290">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property.</span></span>

<span data-ttu-id="2813b-291">**Experiencia mejorada del explorador de propiedades**</span><span class="sxs-lookup"><span data-stu-id="2813b-291">**Improved property browser experience**</span></span>

<span data-ttu-id="2813b-292">A partir de .NET Framework 4.7.1, Windows Forms incluye:</span><span class="sxs-lookup"><span data-stu-id="2813b-292">Starting with the .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="2813b-293">Una mejor navegación mediante teclado gracias a las distintas ventanas de selección desplegables.</span><span class="sxs-lookup"><span data-stu-id="2813b-293">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="2813b-294">Una reducción de puntos de tabulación innecesarios.</span><span class="sxs-lookup"><span data-stu-id="2813b-294">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="2813b-295">Mejor notificación de tipos de control.</span><span class="sxs-lookup"><span data-stu-id="2813b-295">Better reporting of control types.</span></span>
- <span data-ttu-id="2813b-296">Comportamiento mejorado de Narrador.</span><span class="sxs-lookup"><span data-stu-id="2813b-296">Improved narrator behavior.</span></span>
 
<a name="aspnet471"></a>
## <a name="aspnet-web-controls"></a><span data-ttu-id="2813b-297">Controles web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2813b-297">ASP.NET web controls</span></span>

<span data-ttu-id="2813b-298">A partir de .NET Framework 4.7.1 y Visual Studio 2017 15.3, ASP.NET mejora el funcionamiento de los controles web ASP.NET con la tecnología de accesibilidad en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2813b-298">Starting with the .NET Framework 4.7.1 and Visual Studio 2017 15.3, ASP.NET improves how ASP.NET web controls work with accessibility technology in Visual Studio.</span></span> <span data-ttu-id="2813b-299">Los cambios son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2813b-299">Changes include the following:</span></span>

- <span data-ttu-id="2813b-300">Cambios para implementar patrones de accesibilidad de interfaz de usuario que faltan en los controles, como el cuadro de diálogo **Agregar campo** en el **Asistente para vistas de detalles** o el cuadro de diálogo **Configurar ListView** del **Asistente de ListView**.</span><span class="sxs-lookup"><span data-stu-id="2813b-300">Changes to implement missing UI accessibility patterns in controls, like the **Add Field** dialog in the **Details View** wizard, or the **Configure ListView** dialog of the **ListView** wizard.</span></span>

- <span data-ttu-id="2813b-301">Cambios para mejorar la presentación en el modo Contraste alto, como el **Editor de campos del elemento de paginación de datos**.</span><span class="sxs-lookup"><span data-stu-id="2813b-301">Changes to improve the display in High Contrast mode, like the **Data Pager Fields Editor**.</span></span>

- <span data-ttu-id="2813b-302">Cambios para mejorar las experiencias de navegación del teclado para los controles, como el cuadro de diálogo **Campos** del **Asistente para editar campos del elemento de paginación** del control DataPager, el cuadro de diálogo **Configurar ObjectContext** o el cuadro de diálogo **Configurar selección de datos** del **Asistente para configurar origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="2813b-302">Changes to improve the keyboard navigation experiences for controls, like the **Fields** dialog in the **Edit Pager Fields** wizard of the DataPager control, the **Configure ObjectContext** dialog, or the **Configure Data Selection** dialog of the **Configure Data Source** wizard.</span></span>

<a name="tools471"></a>
## <a name="net-sdk-tools"></a><span data-ttu-id="2813b-303">Herramientas del SDK de .NET</span><span class="sxs-lookup"><span data-stu-id="2813b-303">.NET SDK Tools</span></span>

<span data-ttu-id="2813b-304">Se han corregido varios problemas de accesibilidad para mejorar la [herramienta del editor de configuración (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) y la [herramienta del visor de seguimiento de servicios (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="2813b-304">The [Configuration Editor Tool (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) and [Service Trace Viewer Tool (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="2813b-305">La mayoría eran problemas menores como un nombre sin definir o determinados patrones de automatización de la interfaz de usuario que no se implementaban correctamente.</span><span class="sxs-lookup"><span data-stu-id="2813b-305">Most of these were small issues, like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="2813b-306">Aunque muchos usuarios no son conscientes de estos valores incorrectos, los clientes que usen tecnologías de asistencia como lectores de pantalla encontrarán estas herramientas del SDK más accesibles.</span><span class="sxs-lookup"><span data-stu-id="2813b-306">While many users won’t be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span> 

<span data-ttu-id="2813b-307">Estas mejoras cambian algunos comportamientos anteriores, como el orden del foco de teclado.</span><span class="sxs-lookup"><span data-stu-id="2813b-307">These enhancements change some previous behaviors, such as keyboard focus order.</span></span>

<a name="wf471"></a>
## <a name="windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="2813b-308">Diseñador de flujo de trabajo de Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="2813b-308">Windows Workflow Foundation (WF) Workflow Designer</span></span>

<span data-ttu-id="2813b-309">Los cambios de accesibilidad en el Diseñador de flujo de trabajo son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2813b-309">Accessibility changes in the Workflow Designer include the following:</span></span>

- <span data-ttu-id="2813b-310">El orden de tabulación cambia de izquierda a derecha y de arriba a abajo en algunos controles:</span><span class="sxs-lookup"><span data-stu-id="2813b-310">The tab order changes to left to right and top to bottom in some controls:</span></span>

  - <span data-ttu-id="2813b-311">La ventana Inicializar correlación para establecer los datos de correlación para la actividad <xref:System.ServiceModel.Activities.InitializeCorrelation>.</span><span class="sxs-lookup"><span data-stu-id="2813b-311">The initialize correlation window for setting correlation data for the <xref:System.ServiceModel.Activities.InitializeCorrelation> activity.</span></span>

  - <span data-ttu-id="2813b-312">La ventana Definición de contenido para las actividades <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> y <xref:System.ServiceModel.Activities.ReceiveReply>.</span><span class="sxs-lookup"><span data-stu-id="2813b-312">The content definition window for the <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply> activities.</span></span>

- <span data-ttu-id="2813b-313">Hay más funciones disponibles a través del teclado:</span><span class="sxs-lookup"><span data-stu-id="2813b-313">More functions are available via the keyboard:</span></span>

  - <span data-ttu-id="2813b-314">Al editar las propiedades de una actividad, los grupos de propiedades se pueden contraer mediante el teclado la primera vez que obtienen el foco.</span><span class="sxs-lookup"><span data-stu-id="2813b-314">When editing the properties of an activity, property groups can be collapsed by keyboard the first time they are focused.</span></span>

  - <span data-ttu-id="2813b-315">Los iconos de advertencia son accesibles con el teclado.</span><span class="sxs-lookup"><span data-stu-id="2813b-315">Warning icons are accessible by keyboard.</span></span>

  - <span data-ttu-id="2813b-316">El botón **Más propiedades** de la ventana **Propiedades** es accesible con el teclado.</span><span class="sxs-lookup"><span data-stu-id="2813b-316">The **More Properties** button in the **Properties** window is accessible by keyboard.</span></span>

  - <span data-ttu-id="2813b-317">Los usuarios del teclado pueden tener acceso a los elementos de encabezado en los paneles **Argumentos** y **Variables** del Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2813b-317">Keyboard users can access the header items in the **Arguments** and **Variables** panes of the Workflow Designer.</span></span>

- <span data-ttu-id="2813b-318">Visibilidad mejorada de los elementos con el foco, por ejemplo cuando:</span><span class="sxs-lookup"><span data-stu-id="2813b-318">Improved visibility of items with focus, such as when:</span></span>

  - <span data-ttu-id="2813b-319">Se agregan filas a las cuadrículas de datos usadas por los diseñadores de actividad y el Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2813b-319">Adding rows to data grids used by the Workflow Designer and activity designers.</span></span>

  - <span data-ttu-id="2813b-320">Desplazamiento entre campos en las actividades <xref:System.ServiceModel.Activities.ReceiveReply> y <xref:System.ServiceModel.Activities.SendReply>.</span><span class="sxs-lookup"><span data-stu-id="2813b-320">Tabbing through fields in the <xref:System.ServiceModel.Activities.ReceiveReply> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>

  - <span data-ttu-id="2813b-321">Establecimiento de valores predeterminados para variables o argumentos.</span><span class="sxs-lookup"><span data-stu-id="2813b-321">Setting default values for variables or arguments</span></span>

- <span data-ttu-id="2813b-322">Los lectores de pantalla ahora pueden reconocer correctamente:</span><span class="sxs-lookup"><span data-stu-id="2813b-322">Screen readers can now correctly recognize:</span></span>

  - <span data-ttu-id="2813b-323">Los puntos de interrupción establecidos en el Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2813b-323">Breakpoints set in the workflow designer.</span></span>

  - <span data-ttu-id="2813b-324">Las actividades <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> y <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="2813b-324">The <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision>, and <xref:System.ServiceModel.Activities.CorrelationScope> activities.</span></span>
  - <span data-ttu-id="2813b-325">El contenido de la actividad <xref:System.ServiceModel.Activities.Receive>.</span><span class="sxs-lookup"><span data-stu-id="2813b-325">The contents of the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>

  - <span data-ttu-id="2813b-326">El tipo de destino para la actividad <xref:System.Activities.Statements.InvokeMethod>.</span><span class="sxs-lookup"><span data-stu-id="2813b-326">The Target Type for the <xref:System.Activities.Statements.InvokeMethod> activity.</span></span>

  - <span data-ttu-id="2813b-327">El cuadro combinado Excepción y la sección Finally de la actividad <xref:System.Activities.Statements.TryCatch>.</span><span class="sxs-lookup"><span data-stu-id="2813b-327">The Exception combo box and the Finally section in the <xref:System.Activities.Statements.TryCatch> activity.</span></span>

  - <span data-ttu-id="2813b-328">El cuadro combinado Tipo de mensaje, el divisor de la ventana Agregar inicializadores de correlación, la ventana Definición de contenido y la ventana Definición de CorrelatesOn en las actividades de mensajería (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> y <xref:System.ServiceModel.Activities.ReceiveReply>).</span><span class="sxs-lookup"><span data-stu-id="2813b-328">The Message Type combo box, the splitter in the Add Correlation Initializers window, the Content Definition window, and the CorrelatesOn Definition window in the messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>

  - <span data-ttu-id="2813b-329">Transiciones a máquina de estados y destinos de transición.</span><span class="sxs-lookup"><span data-stu-id="2813b-329">State machine transitions and transitions destinations.</span></span>

  - <span data-ttu-id="2813b-330">Anotaciones y conectores en las actividades <xref:System.Activities.Statements.FlowDecision>.</span><span class="sxs-lookup"><span data-stu-id="2813b-330">Annotations and connectors on <xref:System.Activities.Statements.FlowDecision> activities.</span></span>

  - <span data-ttu-id="2813b-331">Los menús contextuales (clic con el botón derecho) para las actividades.</span><span class="sxs-lookup"><span data-stu-id="2813b-331">The context (right-click) menus for activities.</span></span>

  - <span data-ttu-id="2813b-332">Los editores de valor de propiedad, el botón Borrar búsqueda, los botones de ordenación Por categoría y Alfabético, y el cuadro de diálogo Editor de expresiones en la cuadrícula de propiedades.</span><span class="sxs-lookup"><span data-stu-id="2813b-332">The property value editors, the Clear Search button, the By Category and Alphabetical sort buttons, and the Expression Editor dialog in the properties grid.</span></span>

  - <span data-ttu-id="2813b-333">El porcentaje de zoom en el Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2813b-333">The zoom percentage in the Workflow Designer.</span></span>

  - <span data-ttu-id="2813b-334">El separador en las actividades <xref:System.Activities.Statements.Parallel> y <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="2813b-334">The separator in <xref:System.Activities.Statements.Parallel> and <xref:System.Activities.Statements.Pick> activities.</span></span>

  - <span data-ttu-id="2813b-335">La actividad <xref:System.Activities.Statements.InvokeDelegate>.</span><span class="sxs-lookup"><span data-stu-id="2813b-335">The <xref:System.Activities.Statements.InvokeDelegate> activity.</span></span>

  - <span data-ttu-id="2813b-336">La ventana Seleccionar tipos para las actividades de diccionario (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>`, etc.).</span><span class="sxs-lookup"><span data-stu-id="2813b-336">The Select Types window for dictionary activities (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>`, etc.).</span></span>

  - <span data-ttu-id="2813b-337">La ventana Examinar y seleccionar un tipo .NET.</span><span class="sxs-lookup"><span data-stu-id="2813b-337">The Browse and Select .NET Type window.</span></span>

  - <span data-ttu-id="2813b-338">Rutas de navegación en el Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2813b-338">Breadcrumbs in the Workflow Designer.</span></span>

- <span data-ttu-id="2813b-339">Los usuarios que elijan temas de contraste alto verán muchas mejoras en la visibilidad del Diseñador de flujo de trabajo y sus controles, como relaciones de contraste mejoradas entre los elementos y cuadros de selección más evidentes para los elementos del foco.</span><span class="sxs-lookup"><span data-stu-id="2813b-339">Users who choose High Contrast themes will see many improvements in the visibility of the Workflow Designer and its controls, like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="2813b-340">Vea también</span><span class="sxs-lookup"><span data-stu-id="2813b-340">See Also</span></span>

[<span data-ttu-id="2813b-341">Novedades de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2813b-341">What's new in the .NET Framework</span></span>](whats-new.md)
 
