---
title: Novedades de accesibilidad en .NET Framework
ms.custom: updateeachrelease
ms.date: 10/13/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4886dad94d3a67e78525241a1538c06b9fe4b0be
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2017
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="f5b4d-102">Novedades de accesibilidad en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f5b4d-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="f5b4d-103">.NET Framework tiene como objetivo en hacer que las aplicaciones más accesible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-103">The .NET Framework aims at making applications more accessibile for your users.</span></span> <span data-ttu-id="f5b4d-104">Características de accesibilidad permiten que una aplicación proporcionar una experiencia adecuada para los usuarios de tecnología de asistencia.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="f5b4d-105">A partir de .NET Framework 4.7.1, .NET Framework incluye un gran número de mejoras de accesibilidad que permiten a los desarrolladores crear aplicaciones accesibles.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-105">Starting with the .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span> 

<span data-ttu-id="f5b4d-106">Las nuevas características de accesibilidad están habilitados de forma predeterminada para las aplicaciones que tienen como destino .NET Framework 4.7.1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-106">The new accessibility features are enabled by default for applications that target the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="f5b4d-107">Además, las aplicaciones que una versión anterior de .NET Framework de destino, pero se ejecutan en .NET Framework 4.7.1 o posterior pueden optar por fuera de los comportamientos de accesibilidad heredado (y, por tanto, participar en las mejoras de accesibilidad en .NET Framework 4.7.1) por agregar el siguiente modificador a la [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento en el [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) sección del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-107">In addition, applications that target an earlier version of the .NET Framework but are running on the .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby opt in to the accessibility improvements in the .NET Framework 4.7.1) by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="f5b4d-108">De forma similar, las aplicaciones destinadas a versiones de .NET Framework a partir de 4.7.1 pueden deshabilitar las características de accesibilidad agregando el siguiente cambio a la [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento en el [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) sección del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-108">Similarly, applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a><span data-ttu-id="f5b4d-109">Novedades de accesibilidad en .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="f5b4d-109">What's new in accessibility in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="f5b4d-110">.NET Framework 4.7.1 incluye nuevas características de accesibilidad en las áreas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-110">The .NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="f5b4d-111">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="f5b4d-111">Windows Presentation Foundation (WPF)</span></span>](#windows-presentation-foundation-wpf)

- [<span data-ttu-id="f5b4d-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f5b4d-112">Windows Forms</span></span>](#windows-forms-accessibility-improvements)

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="f5b4d-113">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="f5b4d-113">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="f5b4d-114">**Mejoras de lector de pantalla**</span><span class="sxs-lookup"><span data-stu-id="f5b4d-114">**Screen reader improvements**</span></span>

<span data-ttu-id="f5b4d-115">Si están habilitadas las mejoras de accesibilidad, .NET Framework 4.7.1 incluye las siguientes mejoras que afectan a los lectores de pantalla:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-115">If accessibility improvements are enabled, the .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="f5b4d-116">4.7 de .NET Framework y versiones anteriores, <xref:System.Windows.Controls.Expander> se anunciaron controles como botones que los lectores de pantalla.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-116">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="f5b4d-117">A partir de .NET Framework 4.7.1, que están correctamente anuncien como grupos expandible.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-117">Starting with the .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="f5b4d-118">4.7 de .NET Framework y versiones anteriores, <xref:System.Windows.Controls.DataGridCell> controles se anuncian por los lectores de pantalla como "custom".</span><span class="sxs-lookup"><span data-stu-id="f5b4d-118">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="f5b4d-119">A partir de .NET Framework 4.7.1, que son ahora correctamente anuncien como celda de cuadrícula de datos (localizada).</span><span class="sxs-lookup"><span data-stu-id="f5b4d-119">Starting with the .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>
 
- <span data-ttu-id="f5b4d-120">A partir de .NET Framework 4.7.1, los lectores de pantalla anuncian el nombre de un editable <xref:System.Windows.Controls.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-120">Starting with the .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="f5b4d-121">4.7 de .NET Framework y versiones anteriores, <xref:System.Windows.Controls.PasswordBox> controles se anuncia como "ningún elemento en la vista" o tenía un comportamiento incorrecto en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-121">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="f5b4d-122">Este problema se corrigió a partir de .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-122">This issue is fixed starting with the .NET Framework 4.7.1.</span></span>     

<span data-ttu-id="f5b4d-123">**Compatibilidad de UIAutomation LiveRegion**</span><span class="sxs-lookup"><span data-stu-id="f5b4d-123">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="f5b4d-124">Los lectores de pantalla como personas de la Ayuda de Narrador leen el contenido de la interfaz de usuario de una aplicación, normalmente salida de texto a voz del contenido de la interfaz de usuario que tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-124">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="f5b4d-125">Sin embargo, si un elemento de interfaz de usuario cambia y no tiene el foco, el usuario no puede recibir notificaciones y puede perder información importante.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-125">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="f5b4d-126">Las regiones en directo están destinados a resolver este problema.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-126">Live regions aim at solving this problem.</span></span> <span data-ttu-id="f5b4d-127">Un desarrollador puede utilizarlos para informar el lector de pantalla o cualquier otro cliente de UIAutomation que se ha realizado un cambio importante para un elemento de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-127">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="f5b4d-128">El lector de pantalla, a continuación, puede decidir cómo y cuándo para informar al usuario de este cambio.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-128">The screen reader can then decide how and when to inform the user of this change.</span></span> 

<span data-ttu-id="f5b4d-129">Para admitir las regiones en vivo, se han agregado las siguientes API de WPF:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-129">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="f5b4d-130">El <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> y <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> campos, que identifican el **LiveSetting** propiedad y el **LiveRegionChanged** eventos.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-130">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="f5b4d-131">Se pueden establecer mediante el uso de XAML.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-131">They can be set by using XAML.</span></span>

- <span data-ttu-id="f5b4d-132">El **AutomationProperties.LiveSetting** propiedad, que informa el lector de pantalla de la importancia del cambio de interfaz de usuario para el usuario adjunta.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-132">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="f5b4d-133">El <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> propiedad, que identifica el **AutomationProperties.LiveSetting** propiedad adjunta.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-133">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>
 
- <span data-ttu-id="f5b4d-134">El <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> método, que se puede invalidar para proporcionar un **LiveSetting** valor.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-134">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="f5b4d-135">El <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> y <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> métodos, que obtener y establecer un **LiveSetting** valor.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-135">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>
 
- <span data-ttu-id="f5b4d-136">El <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeración, que define los posibles **LiveSetting** valores:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-136">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

   - <span data-ttu-id="f5b4d-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f5b4d-138">El elemento no envía notificaciones si ha cambiado el contenido de la región activa.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-138">The element does not send notifications if the content of the live region has changed.</span></span>   
   - <span data-ttu-id="f5b4d-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f5b4d-140">El elemento envía notificaciones que no interrumpen el trabajo si ha cambiado el contenido de la región activa.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-140">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>   

  - <span data-ttu-id="f5b4d-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f5b4d-142">El elemento envía notificaciones que interrumpen el trabajo si ha cambiado el contenido de la región activa.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-142">The element sends interruptive notifications if the content of the live region has changed.</span></span>   

<span data-ttu-id="f5b4d-143">Puede crear un LiveRegion estableciendo la **AutomationProperties.LiveSetting** propiedad del elemento de interés, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-143">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="f5b4d-144">Cuando cambian los datos en la región activa y debe informar a un lector de pantalla, explícitamente genera un evento, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-144">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="f5b4d-145">**Contraste alto**</span><span class="sxs-lookup"><span data-stu-id="f5b4d-145">**High contrast**</span></span>

<span data-ttu-id="f5b4d-146">A partir de .NET Framework 4.7.1, se han realizado mejoras en contraste alto en diversos controles de WPF.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-146">Starting with the .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="f5b4d-147">Ahora son visibles cuando el <xref:System.Windows.SystemParameters.HighContrast%2A> tema esté configurado.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-147">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="f5b4d-148">Se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-148">These include:</span></span>

- <span data-ttu-id="f5b4d-149">Control <xref:System.Windows.Controls.Expander></span><span class="sxs-lookup"><span data-stu-id="f5b4d-149"><xref:System.Windows.Controls.Expander> control</span></span>

    <span data-ttu-id="f5b4d-150">El estilo visual de foco el <xref:System.Windows.Controls.Expander> control ahora está visible.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-150">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="f5b4d-151">Los objetos visuales de teclado para <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, y <xref:System.Windows.Controls.RadioButton> controles también son visibles.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-151">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="f5b4d-152">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-152">For example:</span></span>

    <span data-ttu-id="f5b4d-153">Antes:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-153">Before:</span></span> 
    
    ![Control de botón de expansión tiene el foco antes de mejoras de accesibilidad](media/expander-before.png)

    <span data-ttu-id="f5b4d-155">Después de:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-155">After:</span></span> 

    ![Control de botón de expansión tiene el foco después de mejoras de accesibilidad](media/expander-after.png)

- <span data-ttu-id="f5b4d-157"><xref:System.Windows.Controls.CheckBox>y <xref:System.Windows.Controls.RadioButton> controles</span><span class="sxs-lookup"><span data-stu-id="f5b4d-157"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>
 
    <span data-ttu-id="f5b4d-158">El texto en el <xref:System.Windows.Controls.CheckBox> y <xref:System.Windows.Controls.RadioButton> controles ahora es más fácil ver cuando se selecciona en los temas de contraste alto.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-158">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="f5b4d-159">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-159">For example:</span></span>

    <span data-ttu-id="f5b4d-160">Antes:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-160">Before:</span></span> 

    ![Botón de opción de contraste alto con el foco antes de mejoras de accesibilidad](media/radio-button-before.png)
    
    <span data-ttu-id="f5b4d-162">Después de:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-162">After:</span></span> 

    ![Botón de opción de contraste alto con el foco después de mejoras de accesibilidad](media/radio-button-after.png)

- <span data-ttu-id="f5b4d-164">Control <xref:System.Windows.Controls.ComboBox></span><span class="sxs-lookup"><span data-stu-id="f5b4d-164"><xref:System.Windows.Controls.ComboBox> control</span></span>
 
    <span data-ttu-id="f5b4d-165">A partir de .NET Framework 4.7.1, el borde de un deshabilitado <xref:System.Windows.Controls.ComboBox> control es el mismo color que el texto deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-165">Starting with the .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="f5b4d-166">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-166">For example:</span></span>
    
    <span data-ttu-id="f5b4d-167">Antes:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-167">Before:</span></span> 

     ![Cuadro combinado deshabilitado borde y el texto antes de mejoras de accesibilidad](media/combo-disabled-before.png)

    <span data-ttu-id="f5b4d-169">Después de:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-169">After:</span></span>   

     ![Cuadro combinado deshabilitado borde y el texto después de las mejoras de accesibilidad](media/combo-disabled-after.png)

    <span data-ttu-id="f5b4d-171">Además, los botones de deshabilitado y se centra utilizan el color del tema correcto.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-171">In addition, disabled and focused buttons use the correct theme color.</span></span>

    <span data-ttu-id="f5b4d-172">Antes:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-172">Before:</span></span>

    ![Colores del tema botón antes de mejoras de accesibilidad](media/button-themes-before.png) 
    
    <span data-ttu-id="f5b4d-174">Después de:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-174">After:</span></span> 

    ![Colores del tema botón después de mejoras de accesibilidad](media/button-themes-after.png) 

    <span data-ttu-id="f5b4d-176">Por último, en la 4.7 de .NET Framework y versiones anteriores, establecer un <xref:System.Windows.Controls.ComboBox> estilo del control `Toolbar.ComboBoxStyleKey` provocó la flecha de lista desplegable sea invisible.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-176">Finally, in the .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="f5b4d-177">Este problema se corrigió a partir de .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-177">This issue is fixed starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="f5b4d-178">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-178">For example:</span></span>

    <span data-ttu-id="f5b4d-179">Antes:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-179">Before:</span></span> 

    ![Toolbar.ComboBoxStyleKey antes de las mejoras de accesibilidad](media/comboboxstylekey-before.png) 
    
    <span data-ttu-id="f5b4d-181">Después de:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-181">After:</span></span> 

    ![Toolbar.ComboBoxStyleKey después de mejoras de accesibilidad](media/comboboxstylekey-after.png) 

- <span data-ttu-id="f5b4d-183">Control <xref:System.Windows.Controls.DataGrid></span><span class="sxs-lookup"><span data-stu-id="f5b4d-183"><xref:System.Windows.Controls.DataGrid> control</span></span>

    <span data-ttu-id="f5b4d-184">A partir de .NET Framework 4.7.1, en la flecha de indicador de ordenación <xref:System.Windows.Controls.DataGrid> controla ahora usa corregir colores del tema.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-184">Starting with the .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="f5b4d-185">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-185">For example:</span></span>

    <span data-ttu-id="f5b4d-186">Antes:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-186">Before:</span></span> 

    ![Flecha de indicador de ordenación antes de mejoras de accesibilidad](media/sort-indicator-before.png) 
    
    <span data-ttu-id="f5b4d-188">Después de:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-188">After:</span></span>   
 
    ![Flecha de indicador de ordenación después de mejoras de accesibilidad](media/sort-indicator-after.png) 
    
    <span data-ttu-id="f5b4d-190">Además, 4.7 de .NET Framework y versiones anteriores, el estilo de vínculo predeterminado cambia a un color incorrecto en el mouse (ratón) a lo largo de modos de contraste alto.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-190">In addition, in the .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="f5b4d-191">Esto se resuelve a partir de .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-191">This is resolved starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="f5b4d-192">De forma similar, <xref:System.Windows.Controls.DataGrid> casilla columnas usa los colores esperados para comentarios de foco de teclado a partir de .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-192">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with the .NET Framework 4.7.1.</span></span>

    <span data-ttu-id="f5b4d-193">Antes:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-193">Before:</span></span> 

    ![Estilo de vínculo predeterminado de DataGrid antes de mejoras de accesibilidad](media/default-link-style-before.png) 
 
    <span data-ttu-id="f5b4d-195">Después de:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-195">After:</span></span>    
  
    ![Estilo de vínculo predeterminado de DataGrid después mejoras de accesibilidad](media/default-link-style-after.png)  

<span data-ttu-id="f5b4d-197">Para obtener más información sobre las mejoras de accesibilidad WPF en .NET Framework 4.7.1, consulte [mejoras de accesibilidad en WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span><span class="sxs-lookup"><span data-stu-id="f5b4d-197">For more information on WPF accessibility improvements in the .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

## <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="f5b4d-198">Mejoras de accesibilidad de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f5b4d-198">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="f5b4d-199">En .NET Framework 4.7.1, formularios Windows Forms (WinForms) incluye cambios de accesibilidad en las áreas siguientes.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-199">In the .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="f5b4d-200">**Visualización mejorada en modo de contraste alto**</span><span class="sxs-lookup"><span data-stu-id="f5b4d-200">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="f5b4d-201">A partir de .NET Framework 4.7.1, varios controles de formularios Windows Forms ofrecen generación mejorada en los modos de HighContrast disponibles en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-201">Starting with the .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="f5b4d-202">10 de Windows ha cambiado los valores para algunos colores de contraste alto del sistema y formularios Windows Forms se basa en el marco de trabajo de Windows 10 Win32.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-202">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="f5b4d-203">Para obtener la mejor experiencia, ejecute la versión más reciente de Windows y participar en los cambios más recientes del sistema operativo mediante la adición de que un archivo app.manifest en una aplicación de prueba y quitar el comentario de Windows 10 admite la línea de sistema operativo para que se asemeje a continuación:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-203">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
<span data-ttu-id="f5b4d-204">Algunos ejemplos de cambios de contraste alto:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-204">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="f5b4d-205">Las marcas de verificación en <xref:System.Windows.Forms.MenuStrip> elementos son más fáciles de ver.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-205">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="f5b4d-206">Cuando se selecciona, deshabilitado <xref:System.Windows.Forms.MenuStrip> elementos son más fáciles de ver.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-206">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="f5b4d-207">Texto en un seleccionado <xref:System.Windows.Forms.Button> controlar contrasta con el color de selección.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-207">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="f5b4d-208">Es más fácil de leer texto deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-208">Disabled text is easier to read.</span></span> <span data-ttu-id="f5b4d-209">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-209">For example:</span></span>

    <span data-ttu-id="f5b4d-210">Antes:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-210">Before:</span></span>

    ![Texto deshabilitado antes de mejoras de accesibilidad](media/wf-disabled-before.png) 

    <span data-ttu-id="f5b4d-212">Después de:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-212">After:</span></span>

    ![Texto deshabilitado después de mejoras de accesibilidad](media/wf-disabled-after.png) 

- <span data-ttu-id="f5b4d-214">Mejoras de contraste alto en el cuadro de diálogo de excepción de subproceso.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-214">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="f5b4d-215">**Compatibilidad mejorada con Narrador**</span><span class="sxs-lookup"><span data-stu-id="f5b4d-215">**Improved Narrator support**</span></span>

<span data-ttu-id="f5b4d-216">Formularios Windows Forms en .NET Framework 4.7.1 incluye las siguientes mejoras de accesibilidad para el Narrador:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-216">Windows Forms in the .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="f5b4d-217">El <xref:System.Windows.Forms.MonthCalendar> control puede obtenerse el Narrador, así como otras herramientas de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-217">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="f5b4d-218">El <xref:System.Windows.Forms.CheckedListBox> control notifica Narrador cuando ha cambiado el estado de activación de un elemento por lo que se notifica al usuario que ha cambiado el valor de un elemento de lista.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-218">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>
 
- <span data-ttu-id="f5b4d-219">El <xref:System.Windows.Forms.DataGridViewCell> control notifica el estado correcto de solo lectura para Narrador.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-219">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>
 
- <span data-ttu-id="f5b4d-220">Narrador ahora puede leer deshabilitado <xref:System.Windows.Forms.ToolStripMenuItem> texto, mientras que anteriormente omitía sobre los elementos de menú deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-220">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="f5b4d-221">**Compatibilidad mejorada en patrones de accesibilidad de UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="f5b4d-221">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="f5b4d-222">A partir de .NET Framework 4.7.1, los desarrolladores de herramientas de la tecnología de accesibilidad pueden aprovechar los patrones comunes de accesibilidad de API y las propiedades de varios controles de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-222">Starting with the .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="f5b4d-223">Estas mejoras de accesibilidad son:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-223">These accessibility improvements include:</span></span>

- <span data-ttu-id="f5b4d-224">El <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.ToolStripSplitButton> ahora son compatibles con el [patrónExpandCollapse/](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="f5b4d-224">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>
 
- <span data-ttu-id="f5b4d-225">El <xref:System.Windows.Forms.DataGridViewCheckBoxCell> ahora es compatible con la [patrón toggle](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="f5b4d-225">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>
 
- <span data-ttu-id="f5b4d-226">El <xref:System.Windows.Forms.ToolStripItem> control admite el <xref:System.Windows.Automation.AutomationElement.Name> propiedad y el [patrónExpandCollapse/](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="f5b4d-226">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="f5b4d-227">El <xref:System.Windows.Forms.NumericUpDown> y <xref:System.Windows.Forms.DomainUpDown> controles admiten la <xref:System.Windows.Automation.automationElement.Name> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-227">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.automationElement.Name> property.</span></span>

<span data-ttu-id="f5b4d-228">**Experiencia de exploración de propiedades mejorada**</span><span class="sxs-lookup"><span data-stu-id="f5b4d-228">**Improved property browser experience**</span></span>

<span data-ttu-id="f5b4d-229">A partir de .NET Framework 4.7.1, formularios Windows Forms incluyen:</span><span class="sxs-lookup"><span data-stu-id="f5b4d-229">Starting with the .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="f5b4d-230">Una mejor navegación de teclado a través de las distintas ventanas de selección desplegable.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-230">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="f5b4d-231">Una reducción de posiciones de tabulación innecesarios.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-231">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="f5b4d-232">Mejor generación de informes de los tipos de control.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-232">Better reporting of control types.</span></span>
- <span data-ttu-id="f5b4d-233">Comportamiento mejorado Narrador.</span><span class="sxs-lookup"><span data-stu-id="f5b4d-233">Improved narrator behavior.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="f5b4d-234">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5b4d-234">See Also</span></span>
[<span data-ttu-id="f5b4d-235">Novedades de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f5b4d-235">What's new in the .NET Framework</span></span>](whats-new.md)   
 