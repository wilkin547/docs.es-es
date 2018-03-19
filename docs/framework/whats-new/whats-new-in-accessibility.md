---
title: Novedades de accesibilidad en .NET Framework
ms.custom: updateeachrelease
ms.date: 10/13/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5f17550bc0cc4919f00dc93c8e92d258b38c4f76
ms.sourcegitcommit: 1c0b0f082b3f300e54b4d069b317ac724c88ddc3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2018
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="8f73c-102">Novedades de accesibilidad en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8f73c-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="8f73c-103">.NET Framework aspira a que las aplicaciones sean más accesibles para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8f73c-103">The .NET Framework aims at making applications more accessibile for your users.</span></span> <span data-ttu-id="8f73c-104">Las características de accesibilidad permiten que una aplicación proporcione una experiencia adecuada para los usuarios de la tecnología de asistencia.</span><span class="sxs-lookup"><span data-stu-id="8f73c-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="8f73c-105">A partir de .NET Framework 4.7.1, .NET Framework incluye muchas mejoras de accesibilidad que permiten a los desarrolladores crear aplicaciones accesibles.</span><span class="sxs-lookup"><span data-stu-id="8f73c-105">Starting with the .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span> 

<span data-ttu-id="8f73c-106">Las nuevas características de accesibilidad están habilitadas de forma predeterminada para las aplicaciones para .NET Framework 4.7.1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="8f73c-106">The new accessibility features are enabled by default for applications that target the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="8f73c-107">Además, las aplicaciones para versiones anteriores de .NET Framework que se ejecutan en .NET Framework 4.7.1 o posterior pueden anular los comportamientos de accesibilidad heredados (y, por tanto, usar las mejoras de accesibilidad de .NET Framework 4.7.1) al agregar el siguiente modificador al elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) de la sección [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8f73c-107">In addition, applications that target an earlier version of the .NET Framework but are running on the .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby opt in to the accessibility improvements in the .NET Framework 4.7.1) by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="8f73c-108">Del mismo modo, las aplicaciones para versiones de .NET Framework a partir de la 4.7.1 pueden deshabilitar las características de accesibilidad al agregar el siguiente modificador al elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) en la sección [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8f73c-108">Similarly, applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a><span data-ttu-id="8f73c-109">Novedades de accesibilidad en .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="8f73c-109">What's new in accessibility in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="8f73c-110">.NET Framework 4.7.1 incluye nuevas características de accesibilidad en las áreas siguientes:</span><span class="sxs-lookup"><span data-stu-id="8f73c-110">The .NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="8f73c-111">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="8f73c-111">Windows Presentation Foundation (WPF)</span></span>](#windows-presentation-foundation-wpf)

- [<span data-ttu-id="8f73c-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8f73c-112">Windows Forms</span></span>](#windows-forms-accessibility-improvements)

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="8f73c-113">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="8f73c-113">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="8f73c-114">**Mejoras del lector de pantalla**</span><span class="sxs-lookup"><span data-stu-id="8f73c-114">**Screen reader improvements**</span></span>

<span data-ttu-id="8f73c-115">Si las mejoras de accesibilidad están habilitadas, .NET Framework 4.7.1 incluye las siguientes mejoras que afectan a los lectores de pantalla:</span><span class="sxs-lookup"><span data-stu-id="8f73c-115">If accessibility improvements are enabled, the .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="8f73c-116">En .NET Framework 4.7 y versiones anteriores, los lectores de pantalla anunciaban los controles <xref:System.Windows.Controls.Expander> como botones.</span><span class="sxs-lookup"><span data-stu-id="8f73c-116">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="8f73c-117">A partir de .NET Framework 4.7.1, se anuncian correctamente como grupos que se pueden contraer y expandir.</span><span class="sxs-lookup"><span data-stu-id="8f73c-117">Starting with the .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="8f73c-118">En .NET Framework 4.7 y versiones anteriores, los lectores de pantalla anunciaban los controles <xref:System.Windows.Controls.DataGridCell> como "personalizados".</span><span class="sxs-lookup"><span data-stu-id="8f73c-118">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="8f73c-119">A partir de .NET Framework 4.7.1, se anuncian correctamente como celdas de cuadrícula de datos (localizadas).</span><span class="sxs-lookup"><span data-stu-id="8f73c-119">Starting with the .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>
 
- <span data-ttu-id="8f73c-120">A partir de .NET Framework 4.7.1, los lectores de pantalla anuncian el nombre de un <xref:System.Windows.Controls.ComboBox> editable.</span><span class="sxs-lookup"><span data-stu-id="8f73c-120">Starting with the .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="8f73c-121">En .NET Framework 4.7 y versiones anteriores, los controles <xref:System.Windows.Controls.PasswordBox> se anunciaban como "no hay elemento a la vista" o tenían un comportamiento incorrecto.</span><span class="sxs-lookup"><span data-stu-id="8f73c-121">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="8f73c-122">Este problema se corrigió a partir de .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="8f73c-122">This issue is fixed starting with the .NET Framework 4.7.1.</span></span>     

<span data-ttu-id="8f73c-123">**Compatibilidad con las regiones activas de UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="8f73c-123">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="8f73c-124">Los lectores de pantalla como Narrador ayudan a los usuarios a leer el contenido de la interfaz de usuario de una aplicación, normalmente mediante salida de texto a voz del contenido de la interfaz de usuario que tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="8f73c-124">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="8f73c-125">Pero si un elemento de la interfaz de usuario cambia y no tiene el foco, puede que no se notifique al usuario y este pierda información importante.</span><span class="sxs-lookup"><span data-stu-id="8f73c-125">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="8f73c-126">Las regiones activas aspiran a resolver este problema.</span><span class="sxs-lookup"><span data-stu-id="8f73c-126">Live regions aim at solving this problem.</span></span> <span data-ttu-id="8f73c-127">Un desarrollador puede usarlas para informar al lector de pantalla o a cualquier otro cliente de UIAutomation de que se ha realizado un cambio importante en un elemento de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="8f73c-127">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="8f73c-128">Luego el lector de pantalla puede decidir cómo y cuándo informar al usuario de este cambio.</span><span class="sxs-lookup"><span data-stu-id="8f73c-128">The screen reader can then decide how and when to inform the user of this change.</span></span> 

<span data-ttu-id="8f73c-129">Para admitir las regiones activas, se han agregado las siguientes API a WPF:</span><span class="sxs-lookup"><span data-stu-id="8f73c-129">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="8f73c-130">Los campos <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> y <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>, que identifican a la propiedad **LiveSetting** y al evento **LiveRegionChanged**.</span><span class="sxs-lookup"><span data-stu-id="8f73c-130">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="8f73c-131">Se pueden establecer mediante XAML.</span><span class="sxs-lookup"><span data-stu-id="8f73c-131">They can be set by using XAML.</span></span>

- <span data-ttu-id="8f73c-132">La propiedad adjunta **AutomationProperties.LiveSetting**, que informa al lector de pantalla de la importancia del cambio de la interfaz de usuario para el usuario.</span><span class="sxs-lookup"><span data-stu-id="8f73c-132">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="8f73c-133">La propiedad <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>, que identifica a la propiedad adjunta **AutomationProperties.LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="8f73c-133">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>
 
- <span data-ttu-id="8f73c-134">El método <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>, que se puede invalidar para proporcionar un valor **LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="8f73c-134">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="8f73c-135">Los métodos <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> y <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>, que obtienen y establecen un valor **LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="8f73c-135">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>
 
- <span data-ttu-id="8f73c-136">La enumeración <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>, que define los siguientes posibles valores **LiveSetting**:</span><span class="sxs-lookup"><span data-stu-id="8f73c-136">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

   - <span data-ttu-id="8f73c-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8f73c-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8f73c-138">El elemento no envía notificaciones si ha cambiado el contenido de la región activa.</span><span class="sxs-lookup"><span data-stu-id="8f73c-138">The element does not send notifications if the content of the live region has changed.</span></span>   
   - <span data-ttu-id="8f73c-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8f73c-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8f73c-140">El elemento envía notificaciones que no interrumpen el trabajo si ha cambiado el contenido de la región activa.</span><span class="sxs-lookup"><span data-stu-id="8f73c-140">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>   

  - <span data-ttu-id="8f73c-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8f73c-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8f73c-142">El elemento envía notificaciones que interrumpen el trabajo si ha cambiado el contenido de la región activa.</span><span class="sxs-lookup"><span data-stu-id="8f73c-142">The element sends interruptive notifications if the content of the live region has changed.</span></span>   

<span data-ttu-id="8f73c-143">Puede crear una región activa si establece la propiedad **AutomationProperties.LiveSetting** en el elemento de interés, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8f73c-143">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="8f73c-144">Cuando cambian los datos de la región activa y necesita informar a un lector de pantalla, puede generar un evento de forma explícita, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="8f73c-144">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="8f73c-145">**Contraste alto**</span><span class="sxs-lookup"><span data-stu-id="8f73c-145">**High contrast**</span></span>

<span data-ttu-id="8f73c-146">A partir de .NET Framework 4.7.1, se han realizado mejoras de contraste alto en diversos controles de WPF.</span><span class="sxs-lookup"><span data-stu-id="8f73c-146">Starting with the .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="8f73c-147">Ahora son visibles cuando el tema <xref:System.Windows.SystemParameters.HighContrast%2A> está establecido.</span><span class="sxs-lookup"><span data-stu-id="8f73c-147">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="8f73c-148">Se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8f73c-148">These include:</span></span>

- <span data-ttu-id="8f73c-149">Control <xref:System.Windows.Controls.Expander></span><span class="sxs-lookup"><span data-stu-id="8f73c-149"><xref:System.Windows.Controls.Expander> control</span></span>

    <span data-ttu-id="8f73c-150">El objeto visual de foco del control <xref:System.Windows.Controls.Expander> ahora es visible.</span><span class="sxs-lookup"><span data-stu-id="8f73c-150">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="8f73c-151">Los objetos visuales de teclado de los controles <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.RadioButton> también son visibles.</span><span class="sxs-lookup"><span data-stu-id="8f73c-151">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="8f73c-152">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8f73c-152">For example:</span></span>

    <span data-ttu-id="8f73c-153">Antes:</span><span class="sxs-lookup"><span data-stu-id="8f73c-153">Before:</span></span> 
    
    ![Control de expansor con foco antes de las mejoras de accesibilidad](media/expander-before.png)

    <span data-ttu-id="8f73c-155">Después:</span><span class="sxs-lookup"><span data-stu-id="8f73c-155">After:</span></span> 

    ![Control de expansor con foco después de las mejoras de accesibilidad](media/expander-after.png)

- <span data-ttu-id="8f73c-157">Controles <xref:System.Windows.Controls.CheckBox> y <xref:System.Windows.Controls.RadioButton></span><span class="sxs-lookup"><span data-stu-id="8f73c-157"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>
 
    <span data-ttu-id="8f73c-158">El texto de los controles <xref:System.Windows.Controls.CheckBox> y <xref:System.Windows.Controls.RadioButton> ahora es más fácil de ver cuando se selecciona en los temas de contraste alto.</span><span class="sxs-lookup"><span data-stu-id="8f73c-158">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="8f73c-159">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8f73c-159">For example:</span></span>

    <span data-ttu-id="8f73c-160">Antes:</span><span class="sxs-lookup"><span data-stu-id="8f73c-160">Before:</span></span> 

    ![Botón de opción de contraste alto con foco antes de las mejoras de accesibilidad](media/radio-button-before.png)
    
    <span data-ttu-id="8f73c-162">Después:</span><span class="sxs-lookup"><span data-stu-id="8f73c-162">After:</span></span> 

    ![Botón de opción de contraste alto con foco después de las mejoras de accesibilidad](media/radio-button-after.png)

- <span data-ttu-id="8f73c-164">Control <xref:System.Windows.Controls.ComboBox></span><span class="sxs-lookup"><span data-stu-id="8f73c-164"><xref:System.Windows.Controls.ComboBox> control</span></span>
 
    <span data-ttu-id="8f73c-165">A partir de .NET Framework 4.7.1, el borde de un control <xref:System.Windows.Controls.ComboBox> deshabilitado es del mismo color que el texto deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="8f73c-165">Starting with the .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="8f73c-166">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8f73c-166">For example:</span></span>
    
    <span data-ttu-id="8f73c-167">Antes:</span><span class="sxs-lookup"><span data-stu-id="8f73c-167">Before:</span></span> 

     ![Borde y texto de cuadro combinado deshabilitado antes de las mejoras de accesibilidad](media/combo-disabled-before.png)

    <span data-ttu-id="8f73c-169">Después:</span><span class="sxs-lookup"><span data-stu-id="8f73c-169">After:</span></span>   

     ![Borde y texto de cuadro combinado deshabilitado después de las mejoras de accesibilidad](media/combo-disabled-after.png)

    <span data-ttu-id="8f73c-171">Además, los botones deshabilitados y con foco usan el color de tema correcto.</span><span class="sxs-lookup"><span data-stu-id="8f73c-171">In addition, disabled and focused buttons use the correct theme color.</span></span>

    <span data-ttu-id="8f73c-172">Antes:</span><span class="sxs-lookup"><span data-stu-id="8f73c-172">Before:</span></span>

    ![Colores de tema de botón antes de las mejoras de accesibilidad](media/button-themes-before.png) 
    
    <span data-ttu-id="8f73c-174">Después:</span><span class="sxs-lookup"><span data-stu-id="8f73c-174">After:</span></span> 

    ![Colores de tema de botón después de las mejoras de accesibilidad](media/button-themes-after.png) 

    <span data-ttu-id="8f73c-176">Por último, en .NET Framework 4.7 y versiones anteriores, al establecer el estilo de un control <xref:System.Windows.Controls.ComboBox> en `Toolbar.ComboBoxStyleKey`, la flecha de lista desplegable se hacía invisible.</span><span class="sxs-lookup"><span data-stu-id="8f73c-176">Finally, in the .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="8f73c-177">Este problema se corrigió a partir de .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="8f73c-177">This issue is fixed starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="8f73c-178">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8f73c-178">For example:</span></span>

    <span data-ttu-id="8f73c-179">Antes:</span><span class="sxs-lookup"><span data-stu-id="8f73c-179">Before:</span></span> 

    ![Toolbar.ComboBoxStyleKey antes de las mejoras de accesibilidad](media/comboboxstylekey-before.png) 
    
    <span data-ttu-id="8f73c-181">Después:</span><span class="sxs-lookup"><span data-stu-id="8f73c-181">After:</span></span> 

    ![Toolbar.ComboBoxStyleKey después de las mejoras de accesibilidad](media/comboboxstylekey-after.png) 

- <span data-ttu-id="8f73c-183">Control <xref:System.Windows.Controls.DataGrid></span><span class="sxs-lookup"><span data-stu-id="8f73c-183"><xref:System.Windows.Controls.DataGrid> control</span></span>

    <span data-ttu-id="8f73c-184">A partir de .NET Framework 4.7.1, la flecha de indicador de orden de los controles <xref:System.Windows.Controls.DataGrid> usa los colores de tema correctos.</span><span class="sxs-lookup"><span data-stu-id="8f73c-184">Starting with the .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="8f73c-185">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8f73c-185">For example:</span></span>

    <span data-ttu-id="8f73c-186">Antes:</span><span class="sxs-lookup"><span data-stu-id="8f73c-186">Before:</span></span> 

    ![Flecha de indicador de orden antes de las mejoras de accesibilidad](media/sort-indicator-before.png) 
    
    <span data-ttu-id="8f73c-188">Después:</span><span class="sxs-lookup"><span data-stu-id="8f73c-188">After:</span></span>   
 
    ![Flecha de indicador de orden después de las mejoras de accesibilidad](media/sort-indicator-after.png) 
    
    <span data-ttu-id="8f73c-190">Además, en .NET Framework 4.7 y versiones anteriores, el estilo de vínculo predeterminado cambiaba a un color incorrecto cuando se colocaba el mouse encima en los modos de contraste alto.</span><span class="sxs-lookup"><span data-stu-id="8f73c-190">In addition, in the .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="8f73c-191">Esto se ha resuelto a partir de .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="8f73c-191">This is resolved starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="8f73c-192">Del mismo modo, a partir de .NET Framework 4.7.1, las columnas de casilla <xref:System.Windows.Controls.DataGrid> usan los colores esperados para comentarios de foco de teclado.</span><span class="sxs-lookup"><span data-stu-id="8f73c-192">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with the .NET Framework 4.7.1.</span></span>

    <span data-ttu-id="8f73c-193">Antes:</span><span class="sxs-lookup"><span data-stu-id="8f73c-193">Before:</span></span> 

    ![Estilo de vínculo predeterminado de cuadrícula de datos antes de las mejoras de accesibilidad](media/default-link-style-before.png) 
 
    <span data-ttu-id="8f73c-195">Después:</span><span class="sxs-lookup"><span data-stu-id="8f73c-195">After:</span></span>    
  
    ![Estilo de vínculo predeterminado de cuadrícula de datos después de las mejoras de accesibilidad](media/default-link-style-after.png)  

<span data-ttu-id="8f73c-197">Para más información sobre las mejoras de accesibilidad de WPF en .NET Framework 4.7.1, vea [Mejoras de accesibilidad en WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span><span class="sxs-lookup"><span data-stu-id="8f73c-197">For more information on WPF accessibility improvements in the .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

## <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="8f73c-198">Mejoras de accesibilidad de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8f73c-198">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="8f73c-199">En .NET Framework 4.7.1, Windows Forms (WinForms) incluye cambios de accesibilidad en las áreas siguientes.</span><span class="sxs-lookup"><span data-stu-id="8f73c-199">In the .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="8f73c-200">**Visualización mejorada en modo de contraste alto**</span><span class="sxs-lookup"><span data-stu-id="8f73c-200">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="8f73c-201">A partir de .NET Framework 4.7.1, varios controles de WinForms ofrecen una representación mejorada en los modos de contraste alto disponibles en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8f73c-201">Starting with the .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="8f73c-202">Windows 10 ha cambiado los valores de algunos colores del sistema de contraste alto y Windows Forms se basa en el marco de trabajo de Windows 10 Win32.</span><span class="sxs-lookup"><span data-stu-id="8f73c-202">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="8f73c-203">Para obtener la mejor experiencia, trabaje en la versión más reciente de Windows y use los cambios más recientes del sistema operativo al agregar un archivo app.manifest en una aplicación de prueba y quitar los comentarios de la línea del sistema operativo compatible con Windows 10 para tenga este aspecto:</span><span class="sxs-lookup"><span data-stu-id="8f73c-203">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!-- Windows 10 -->
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
<span data-ttu-id="8f73c-204">Algunos ejemplos de cambios de contraste alto:</span><span class="sxs-lookup"><span data-stu-id="8f73c-204">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="8f73c-205">Las marcas de verificación de los elementos <xref:System.Windows.Forms.MenuStrip> son más fáciles de ver.</span><span class="sxs-lookup"><span data-stu-id="8f73c-205">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="8f73c-206">Cuando se activan, los elementos <xref:System.Windows.Forms.MenuStrip> deshabilitados son más fáciles de ver.</span><span class="sxs-lookup"><span data-stu-id="8f73c-206">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="8f73c-207">El texto de un control <xref:System.Windows.Forms.Button> seleccionado contrasta con el color de selección.</span><span class="sxs-lookup"><span data-stu-id="8f73c-207">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="8f73c-208">El texto deshabilitado es más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="8f73c-208">Disabled text is easier to read.</span></span> <span data-ttu-id="8f73c-209">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8f73c-209">For example:</span></span>

    <span data-ttu-id="8f73c-210">Antes:</span><span class="sxs-lookup"><span data-stu-id="8f73c-210">Before:</span></span>

    ![Texto deshabilitado antes de las mejoras de accesibilidad](media/wf-disabled-before.png) 

    <span data-ttu-id="8f73c-212">Después:</span><span class="sxs-lookup"><span data-stu-id="8f73c-212">After:</span></span>

    ![Texto deshabilitado después de las mejoras de accesibilidad](media/wf-disabled-after.png) 

- <span data-ttu-id="8f73c-214">Mejoras de contraste alto en el cuadro de diálogo de excepción de subproceso.</span><span class="sxs-lookup"><span data-stu-id="8f73c-214">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="8f73c-215">**Compatibilidad mejorada con Narrador**</span><span class="sxs-lookup"><span data-stu-id="8f73c-215">**Improved Narrator support**</span></span>

<span data-ttu-id="8f73c-216">Windows Forms en .NET Framework 4.7.1 incluye las siguientes mejoras de accesibilidad para Narrador:</span><span class="sxs-lookup"><span data-stu-id="8f73c-216">Windows Forms in the .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="8f73c-217">Narrador, así como otras herramientas de automatización de la interfaz de usuario, pueden acceder al control <xref:System.Windows.Forms.MonthCalendar>.</span><span class="sxs-lookup"><span data-stu-id="8f73c-217">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="8f73c-218">El control <xref:System.Windows.Forms.CheckedListBox> avisa a Narrador cuando ha cambiado el estado de activación de un elemento para que el usuario sepa que ha cambiado el valor de un elemento de lista.</span><span class="sxs-lookup"><span data-stu-id="8f73c-218">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>
 
- <span data-ttu-id="8f73c-219">El control <xref:System.Windows.Forms.DataGridViewCell> notifica el estado correcto de solo lectura a Narrador.</span><span class="sxs-lookup"><span data-stu-id="8f73c-219">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>
 
- <span data-ttu-id="8f73c-220">Narrador ahora puede leer texto <xref:System.Windows.Forms.ToolStripMenuItem> deshabilitado, mientras que anteriormente omitía los elementos de menú deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="8f73c-220">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="8f73c-221">**Compatibilidad mejorada con los patrones de accesibilidad de UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="8f73c-221">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="8f73c-222">A partir de .NET Framework 4.7.1, los desarrolladores de herramientas de tecnología de accesibilidad pueden aprovechar los patrones comunes de accesibilidad de API y las propiedades de varios controles de WinForms.</span><span class="sxs-lookup"><span data-stu-id="8f73c-222">Starting with the .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="8f73c-223">Estas mejoras de accesibilidad incluyen:</span><span class="sxs-lookup"><span data-stu-id="8f73c-223">These accessibility improvements include:</span></span>

- <span data-ttu-id="8f73c-224"><xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.ToolStripSplitButton> ahora son compatibles con el [patrón de expansión o contracción](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="8f73c-224">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>
 
- <span data-ttu-id="8f73c-225"><xref:System.Windows.Forms.DataGridViewCheckBoxCell> ahora es compatible con el [patrón de alternancia](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="8f73c-225">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>
 
- <span data-ttu-id="8f73c-226">El control <xref:System.Windows.Forms.ToolStripItem> admite la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> y el [patrón de expansión o contracción](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="8f73c-226">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="8f73c-227">Los controles <xref:System.Windows.Forms.NumericUpDown> y <xref:System.Windows.Forms.DomainUpDown> admiten la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>.</span><span class="sxs-lookup"><span data-stu-id="8f73c-227">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property.</span></span>

<span data-ttu-id="8f73c-228">**Experiencia mejorada del explorador de propiedades**</span><span class="sxs-lookup"><span data-stu-id="8f73c-228">**Improved property browser experience**</span></span>

<span data-ttu-id="8f73c-229">A partir de .NET Framework 4.7.1, Windows Forms incluye:</span><span class="sxs-lookup"><span data-stu-id="8f73c-229">Starting with the .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="8f73c-230">Una mejor navegación mediante teclado gracias a las distintas ventanas de selección desplegables.</span><span class="sxs-lookup"><span data-stu-id="8f73c-230">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="8f73c-231">Una reducción de puntos de tabulación innecesarios.</span><span class="sxs-lookup"><span data-stu-id="8f73c-231">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="8f73c-232">Mejor notificación de tipos de control.</span><span class="sxs-lookup"><span data-stu-id="8f73c-232">Better reporting of control types.</span></span>
- <span data-ttu-id="8f73c-233">Comportamiento mejorado de Narrador.</span><span class="sxs-lookup"><span data-stu-id="8f73c-233">Improved narrator behavior.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="8f73c-234">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f73c-234">See Also</span></span>
[<span data-ttu-id="8f73c-235">Novedades de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8f73c-235">What's new in the .NET Framework</span></span>](whats-new.md)   
 
