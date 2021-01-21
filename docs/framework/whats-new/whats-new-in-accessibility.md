---
title: Novedades de accesibilidad en .NET Framework
titleSuffix: ''
description: Vea las novedades de la accesibilidad de .NET, a partir de .NET Framework 4.7.1. Las características de accesibilidad permiten que una aplicación proporcione la experiencia adecuada para los usuarios de tecnología de asistencia.
ms.date: 01/05/2021
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
ms.openlocfilehash: c2ebaed8bf347eb8d8764f4bdf76dcc33db86bad
ms.sourcegitcommit: 3a8f1979a98c6c19217a1930e0af5908988eb8ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "98536169"
---
# <a name="whats-new-in-accessibility-in-net-framework"></a><span data-ttu-id="6bef1-104">Novedades de accesibilidad en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6bef1-104">What's new in accessibility in .NET Framework</span></span>

<span data-ttu-id="6bef1-105">.NET Framework aspira a que las aplicaciones sean más accesibles para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6bef1-105">.NET Framework aims to make applications more accessible for your users.</span></span> <span data-ttu-id="6bef1-106">Las características de accesibilidad permiten que una aplicación proporcione una experiencia adecuada para los usuarios de la tecnología de asistencia.</span><span class="sxs-lookup"><span data-stu-id="6bef1-106">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="6bef1-107">A partir de .NET Framework 4.7.1, .NET Framework incluye muchas mejoras de accesibilidad que permiten a los desarrolladores crear aplicaciones accesibles.</span><span class="sxs-lookup"><span data-stu-id="6bef1-107">Starting with .NET Framework 4.7.1, .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span>

## <a name="accessibility-switches"></a><span data-ttu-id="6bef1-108">Modificadores de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="6bef1-108">Accessibility switches</span></span>

<span data-ttu-id="6bef1-109">Puede configurar la aplicación para que opte por recibir características de accesibilidad si su destino es .NET Framework 4.7 o una versión anterior, pero se ejecuta en .NET Framework 4.7.1 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="6bef1-109">You can configure your app to opt into accessibility features if it targets .NET Framework 4.7 or an earlier version but is running on .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="6bef1-110">También la puede configurar para que use características heredadas (en vez de aprovechar las ventajas de las características de accesibilidad) si su destino es .NET Framework 4.7.1 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="6bef1-110">You can also configure your app to use legacy features (and not take advantage of accessibility features) if it targets .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="6bef1-111">Cada versión de .NET Framework que incluye características de accesibilidad cuenta con un modificador de accesibilidad específico de la versión correspondiente, que se agrega al elemento [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) en la sección [`<runtime>`](../configure-apps/file-schema/runtime/index.md) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6bef1-111">Each .NET Framework version that includes accessibility features has a version-specific accessibility switch, which you add to the [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](../configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> <span data-ttu-id="6bef1-112">Estos son los modificadores admitidos:</span><span class="sxs-lookup"><span data-stu-id="6bef1-112">The following are the supported switches:</span></span>

|<span data-ttu-id="6bef1-113">Versión</span><span class="sxs-lookup"><span data-stu-id="6bef1-113">Version</span></span>|<span data-ttu-id="6bef1-114">Modificador</span><span class="sxs-lookup"><span data-stu-id="6bef1-114">Switch</span></span>|
|---|---|
|<span data-ttu-id="6bef1-115">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="6bef1-115">.NET Framework 4.7.1</span></span>|<span data-ttu-id="6bef1-116">"Switch.UseLegacyAccessibilityFeatures"</span><span class="sxs-lookup"><span data-stu-id="6bef1-116">"Switch.UseLegacyAccessibilityFeatures"</span></span>|
|<span data-ttu-id="6bef1-117">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="6bef1-117">.NET Framework 4.7.2</span></span>|<span data-ttu-id="6bef1-118">"Switch.UseLegacyAccessibilityFeatures.2"</span><span class="sxs-lookup"><span data-stu-id="6bef1-118">"Switch.UseLegacyAccessibilityFeatures.2"</span></span>|
|<span data-ttu-id="6bef1-119">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="6bef1-119">.NET Framework 4.8</span></span>|<span data-ttu-id="6bef1-120">"Switch.UseLegacyAccessibilityFeatures.3"</span><span class="sxs-lookup"><span data-stu-id="6bef1-120">"Switch.UseLegacyAccessibilityFeatures.3"</span></span>|
|<span data-ttu-id="6bef1-121">11 de agosto de 2020: actualización acumulativa KB4569746 para .NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="6bef1-121">August 11, 2020-KB4569746 Cumulative Update for .NET Framework 4.8</span></span>|<span data-ttu-id="6bef1-122">"Switch.UseLegacyAccessibilityFeatures.4"</span><span class="sxs-lookup"><span data-stu-id="6bef1-122">"Switch.UseLegacyAccessibilityFeatures.4"</span></span>|

### <a name="taking-advantage-of-accessibility-enhancements"></a><span data-ttu-id="6bef1-123">Aprovechar las mejoras de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="6bef1-123">Taking advantage of accessibility enhancements</span></span>

<span data-ttu-id="6bef1-124">Las nuevas características de accesibilidad están habilitadas de forma predeterminada para las aplicaciones para .NET Framework 4.7.1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="6bef1-124">The new accessibility features are enabled by default for applications that target .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="6bef1-125">Además, las aplicaciones para versiones anteriores de .NET Framework que se ejecutan en .NET Framework 4.7.1 o posterior pueden optar por no recibir comportamientos de accesibilidad heredados (y, por tanto, usar las mejoras de accesibilidad correspondientes) si se agregan modificadores al elemento [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) de la sección [`<runtime>`](../configure-apps/file-schema/runtime/index.md) del archivo de configuración de la aplicación y sus valores se establecen en `false`.</span><span class="sxs-lookup"><span data-stu-id="6bef1-125">In addition, applications that target an earlier version of the .NET Framework but are running on .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby take advantage of accessibility improvements) by adding switches to the [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](../configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `false`.</span></span> <span data-ttu-id="6bef1-126">En el fragmento de código siguiente se muestra cómo obtener acceso a las mejoras de accesibilidad que se incluyeron en .NET Framework 4.7.1:</span><span class="sxs-lookup"><span data-stu-id="6bef1-126">The following snippet shows how to opt in to the accessibility enhancements that were introduced in .NET Framework 4.7.1:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="6bef1-127">Si decide disponer de las características de accesibilidad en una versión posterior de .NET Framework, deberá optar por recibir también las características de versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="6bef1-127">If you choose to opt in to accessibility features in a later .NET Framework version, you must also explicitly opt in to the features from earlier versions.</span></span> <span data-ttu-id="6bef1-128">Para configurar la aplicación con el fin de aprovechar las mejoras de accesibilidad de .NET Framework 4.7.1 y 4.7.2, agregue el siguiente elemento [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):</span><span class="sxs-lookup"><span data-stu-id="6bef1-128">To configure your app to take advantage of accessibility improvements in both .NET Framework 4.7.1 and 4.7.2, add the the following [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

<span data-ttu-id="6bef1-129">Para configurar la aplicación con el fin de aprovechar las mejoras de accesibilidad en .NET Framework 4.7.1, 4.7.2, 4.8 y la actualización acumulativa de agosto de 2020 de .NET Framework 4.8, agregue el siguiente elemento [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):</span><span class="sxs-lookup"><span data-stu-id="6bef1-129">To configure your app to take advantage of accessibility improvements in .NET Framework 4.7.1, 4.7.2, 4.8, and the August 2020 cumulative update for .NET Framework 4.8, add the following [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value=Switch.UseLegacyAccessibilityFeatures=false|Switch.UseLegacyAccessibilityFeatures.2=false|Switch.UseLegacyAccessibilityFeatures.3=false|Switch.UseLegacyAccessibilityFeatures.4=false"/>
</runtime>
```

### <a name="restoring-legacy-behavior"></a><span data-ttu-id="6bef1-130">Restaurar el comportamiento heredado</span><span class="sxs-lookup"><span data-stu-id="6bef1-130">Restoring legacy behavior</span></span>

<span data-ttu-id="6bef1-131">Las aplicaciones que tienen como destino versiones de .NET Framework a partir de la 4.7.1 permiten deshabilitar las características de accesibilidad. Para ello, hay que agregar modificadores al elemento [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) en la sección [`<runtime>`](../configure-apps/file-schema/runtime/index.md) del archivo de configuración de la aplicación y establecer sus valores en `true`.</span><span class="sxs-lookup"><span data-stu-id="6bef1-131">Applications that target versions of .NET Framework starting with 4.7.1 can disable accessibility features by adding switches to the [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](../configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `true`.</span></span> <span data-ttu-id="6bef1-132">Por ejemplo, la siguiente configuración opta por no recibir las características de accesibilidad incluidas en .NET Framework 4.7.2:</span><span class="sxs-lookup"><span data-stu-id="6bef1-132">For example, the following configuration opts out of accessibility features introduced in .NET Framework 4.7.2:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-august-11-2020-cumulative-update-for-net-framework-48"></a><span data-ttu-id="6bef1-133">Novedades de accesibilidad en la actualización acumulativa del 11 de agosto de 2020 para .NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="6bef1-133">What's new in accessibility in the August 11, 2020 Cumulative Update for .NET Framework 4.8</span></span>

<span data-ttu-id="6bef1-134">La actualización acumulativa del 11 de agosto de 2020 (KB4569746) para .NET Framework 4.8 incluye nuevas características de accesibilidad en Windows Forms:</span><span class="sxs-lookup"><span data-stu-id="6bef1-134">The August 11, 2020-KB4569746 Cumulative Update for .NET Framework 4.8 includes new accessibility features in Windows Forms:</span></span>

- <span data-ttu-id="6bef1-135">Soluciona un problema con el anuncio por parte de lectores de pantalla de los elementos de control `PropertyGrid`, así como el estado expandido o contraído de una categoría.</span><span class="sxs-lookup"><span data-stu-id="6bef1-135">Addresses an issue with announcing `PropertyGrid` control items and a category's expanded/collapsed state by screen readers.</span></span>

- <span data-ttu-id="6bef1-136">Actualiza los patrones accesibles del control `PropertyGrid` y sus elementos internos.</span><span class="sxs-lookup"><span data-stu-id="6bef1-136">Updates the accessible patterns of the `PropertyGrid` control and its inner elements.</span></span>

- <span data-ttu-id="6bef1-137">Actualiza los nombres accesibles de los elementos internos del control `PropertyGrid` para que los lectores de pantalla los anuncien correctamente.</span><span class="sxs-lookup"><span data-stu-id="6bef1-137">Updates the accessible names of the `PropertyGrid` control inner elements so they're correctly announced by screen readers.</span></span>

- <span data-ttu-id="6bef1-138">Aborda las propiedades accesibles de los rectángulos delimitadores para los controles `PropertyGridView`.</span><span class="sxs-lookup"><span data-stu-id="6bef1-138">Addresses bounding rectangle accessible properties for the `PropertyGridView` controls.</span></span>

- <span data-ttu-id="6bef1-139">Permite a los lectores de pantalla anunciar correctamente el estado expandido o contraído de las celdas de cuadro combinado de `DataGridView`.</span><span class="sxs-lookup"><span data-stu-id="6bef1-139">Enables screen readers to correctly announce the expanded/collapsed state of `DataGridView` combo box cells.</span></span>

## <a name="whats-new-in-accessibility-in-net-framework-48"></a><span data-ttu-id="6bef1-140">Novedades de accesibilidad en .NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="6bef1-140">What's new in accessibility in .NET Framework 4.8</span></span>

<span data-ttu-id="6bef1-141">.NET Framework 4.8 incluye nuevas características de accesibilidad en las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="6bef1-141">.NET Framework 4.8 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="6bef1-142">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6bef1-142">Windows Forms</span></span>](#winforms48)

- [<span data-ttu-id="6bef1-143">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="6bef1-143">Windows Presentation Foundation (WPF)</span></span>](#wpf48)

- [<span data-ttu-id="6bef1-144">Diseñador de flujo de trabajo de Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="6bef1-144">Windows Workflow Foundation (WF) workflow designer</span></span>](#wf48)

<a name="winforms48"></a>

### <a name="windows-forms"></a><span data-ttu-id="6bef1-145">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6bef1-145">Windows Forms</span></span>

<span data-ttu-id="6bef1-146">En .NET Framework 4.8, Windows Forms agrega compatibilidad con las regiones activas y eventos de notificación para muchos controles usados frecuentemente.</span><span class="sxs-lookup"><span data-stu-id="6bef1-146">In .NET Framework 4.8, Windows Forms adds support for LiveRegions and Notification Events to many commonly used controls.</span></span> <span data-ttu-id="6bef1-147">También agrega compatibilidad con informaciones sobre herramientas cuando un usuario se desplaza a un control mediante el teclado.</span><span class="sxs-lookup"><span data-stu-id="6bef1-147">It also adds support for ToolTips when a user navigates to a control by using the keyboard.</span></span>

<span data-ttu-id="6bef1-148">**Compatibilidad con las regiones activas de UIA en las etiquetas y StatusStrips**</span><span class="sxs-lookup"><span data-stu-id="6bef1-148">**UIA LiveRegions Support in Labels and StatusStrips**</span></span>

<span data-ttu-id="6bef1-149">Las regiones activas de UIA permiten a los desarrolladores de aplicaciones notificar a los lectores de pantalla un cambio de texto en un control que se encuentra fuera de la ubicación donde el usuario está trabajando.</span><span class="sxs-lookup"><span data-stu-id="6bef1-149">UIA LiveRegions allow application developers to notify screen readers of a text change in a control that is located apart from the location where the user is working.</span></span> <span data-ttu-id="6bef1-150">Esto resulta útil, por ejemplo, para un control <xref:System.Windows.Forms.StatusStrip> que muestra un estado de conexión.</span><span class="sxs-lookup"><span data-stu-id="6bef1-150">This is useful, for example, for a <xref:System.Windows.Forms.StatusStrip> control that shows a connection status.</span></span> <span data-ttu-id="6bef1-151">Si se interrumpe la conexión y cambia el estado, el desarrollador tal vez desee notificarlo al lector de pantalla.</span><span class="sxs-lookup"><span data-stu-id="6bef1-151">If the connection is dropped and the status changes, the developer might want to notify the screen reader.</span></span>

<span data-ttu-id="6bef1-152">A partir de .NET Framework 4.8, Windows Forms implementa las regiones activas de UIA para ambos controles <xref:System.Windows.Forms.Label> y <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-152">Starting with .NET Framework 4.8, Windows Forms implements UIA LiveRegions for both the <xref:System.Windows.Forms.Label> and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="6bef1-153">Por ejemplo, el código siguiente usa la región activa en un control <xref:System.Windows.Forms.Label> denominado `label1`:</span><span class="sxs-lookup"><span data-stu-id="6bef1-153">For example, the following code uses the LiveRegion in a <xref:System.Windows.Forms.Label> control named `label1`:</span></span>

```csharp
public Form1()
{
   InitializeComponent();
   label1.AutomationLiveSetting = AutomationLiveSetting.Polite;
}

…
Label1.Text = “Ready!”;
```

<span data-ttu-id="6bef1-154">Narrador anuncia “Listo”, independientemente de dónde esté interactuando el usuario con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6bef1-154">Narrator announces “Ready” regardless of where the user is interacting with the application.</span></span>

<span data-ttu-id="6bef1-155">También puede implementar su <xref:System.Windows.Forms.UserControl> como una región activa:</span><span class="sxs-lookup"><span data-stu-id="6bef1-155">You can also implement your <xref:System.Windows.Forms.UserControl> as a LiveRegion:</span></span>

```csharp
using System;
using System.Windows.Forms;
using System.Windows.Forms.Automation;

namespace WindowsFormsApplication
{
   public partial class UserControl1 : UserControl, IAutomationLiveRegion
   {
      public UserControl1()
      {
         InitializeComponent();
      }

      public AutomationLiveSetting AutomationLiveSetting { get; set; }
      private AutomationLiveSetting IAutomationLiveRegion.GetLiveSetting()
      {
         return this.AutomationLiveSetting;
      }

      protected override void OnTextChanged(EventArgs e)
      {
         base.OnTextChanged(e);
         AutomationNotifications.UiaRaiseLiveRegionChangedEvent(this.AccessibilityObject);
      }
   }
}
```

<span data-ttu-id="6bef1-156">**Eventos de notificación de UIA**</span><span class="sxs-lookup"><span data-stu-id="6bef1-156">**UIA notification events**</span></span>

<span data-ttu-id="6bef1-157">El evento de notificación de UIA, introducido en Windows 10 Fall Creators Update, permite que la aplicación genere un evento de UIA, lo cual conduce a que Narrador simplemente lleve a cabo un anuncio basado en texto que se proporciona con el evento, sin necesidad de tener un control correspondiente en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="6bef1-157">The UIA Notification event, introduced in Windows 10 Fall Creators Update, allows your app to raise a UIA event, which leads to Narrator simply making an announcement based on text you supply with the event, without the need to have a corresponding control in the UI.</span></span> <span data-ttu-id="6bef1-158">En algunos escenarios, es una manera sencilla de mejorar drásticamente la accesibilidad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6bef1-158">In some scenarios, this is a straightforward way to dramatically improve the accessibility of your app.</span></span> <span data-ttu-id="6bef1-159">También puede ser útil para notificar el progreso de algún proceso que puede tardar mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="6bef1-159">In can also be useful to notify of the progress of some process that may take a long time.</span></span> <span data-ttu-id="6bef1-160">Para obtener más información acerca de los eventos de notificación de UIA, vea [¿Puede su aplicación de escritorio aprovechar el nuevo evento de notificación de la interfaz de usuario?](/archive/blogs/winuiautomation/can-your-desktop-app-leverage-the-new-uia-notification-event-in-order-to-have-narrator-say-exactly-what-your-customers-need)</span><span class="sxs-lookup"><span data-stu-id="6bef1-160">For more information about UIA Notification Events, see [Can your desktop app leverage the new UI Notification event?](/archive/blogs/winuiautomation/can-your-desktop-app-leverage-the-new-uia-notification-event-in-order-to-have-narrator-say-exactly-what-your-customers-need).</span></span>

<span data-ttu-id="6bef1-161">El ejemplo siguiente genera el [evento de notificación](xref:System.Windows.Forms.AccessibleObject.RaiseAutomationNotification%2A):</span><span class="sxs-lookup"><span data-stu-id="6bef1-161">The following example raises the [Notification event](xref:System.Windows.Forms.AccessibleObject.RaiseAutomationNotification%2A):</span></span>

```csharp
MethodInfo raiseMethod = typeof(AccessibleObject).GetMethod("RaiseAutomationNotification");
if (raiseMethod != null) {
   raiseMethod.Invoke(progressBar1.AccessibilityObject, new object[3] {/*Other*/ 4, /*All*/ 2, "The progress is 50%." });
}
```

<span data-ttu-id="6bef1-162">**Informaciones sobre herramientas en el acceso mediante teclado**</span><span class="sxs-lookup"><span data-stu-id="6bef1-162">**ToolTips on keyboard access**</span></span>

<span data-ttu-id="6bef1-163">En las aplicaciones que tienen como destino .NET Framework 4.7.2 y versiones anteriores, solo se puede desencadenar la aparición de la [información sobre herramientas](xref:System.Windows.Forms.ToolTip) de un control moviendo el puntero del mouse en el control.</span><span class="sxs-lookup"><span data-stu-id="6bef1-163">In applications that target .NET Framework 4.7.2 and earlier versions, a control [tooltip](xref:System.Windows.Forms.ToolTip) can only be triggered to pop up by moving a mouse pointer into the control.</span></span> <span data-ttu-id="6bef1-164">A partir de .NET Framework 4.8, un usuario de teclado puede desencadenar la información sobre herramientas de un control poniendo el enfoque en el control mediante una tecla TAB o con las teclas de dirección, con o sin teclas modificadoras.</span><span class="sxs-lookup"><span data-stu-id="6bef1-164">Starting with .NET Framework 4.8, a keyboard user can trigger a control's tooltip by focusing the control using a Tab key or arrow keys with or without modifier keys.</span></span> <span data-ttu-id="6bef1-165">Esta mejora de accesibilidad particular requiere un [modificador de AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):</span><span class="sxs-lookup"><span data-stu-id="6bef1-165">This particular accessibility enhancement requires an additional [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1"/>
   </startup>
   <runtime>
      <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false  -->
      <!-- Please note that disabling Switch.UseLegacyAccessibilityFeatures, Switch.UseLegacyAccessibilityFeatures.2 and Switch.UseLegacyAccessibilityFeatures.3 is required to disable Switch.System.Windows.Forms.UseLegacyToolTipDisplay -->
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="6bef1-166">La siguiente ilustración muestra la información sobre herramientas cuando el usuario ha seleccionado un botón con el teclado.</span><span class="sxs-lookup"><span data-stu-id="6bef1-166">The following figure shows the tooltip when the user has selected a button with the keyboard.</span></span>

![Captura de pantalla de la información sobre herramientas cuando el usuario se desplaza a un botón con el teclado.](./media/whats-new-in-accessibility/select-tooltip-with-keyboard.png)

<a name="wpf48"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="6bef1-168">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="6bef1-168">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="6bef1-169">A partir de .NET Framework 4.8, WPF incluye una serie de mejoras de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="6bef1-169">Starting with .NET Framework 4.8, WPF includes a number of accessibility improvements.</span></span>

<span data-ttu-id="6bef1-170">**Los narradores de pantalla ya no anuncian los elementos con visibilidad oculta o contraída**</span><span class="sxs-lookup"><span data-stu-id="6bef1-170">**Screen narrators no longer announce elements with Collapsed or Hidden visibility**</span></span>

<span data-ttu-id="6bef1-171">El lector de pantalla ya no anuncia los elementos con visibilidad oculta o contraída.</span><span class="sxs-lookup"><span data-stu-id="6bef1-171">Elements with collapsed or hidden visibility are no longer announced by screen reader.</span></span> <span data-ttu-id="6bef1-172">Si se anuncian al usuario las interfaces de usuario que contienen elementos con una visibilidad de <xref:System.Windows.Visibility.Collapsed?displayProperty=nameWithType> o <xref:System.Windows.Visibility.Hidden?displayProperty=nameWithType>, los lectores de pantalla pueden interpretarlos incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="6bef1-172">User interfaces that contain elements with a Visibility of <xref:System.Windows.Visibility.Collapsed?displayProperty=nameWithType> or <xref:System.Windows.Visibility.Hidden?displayProperty=nameWithType> can be misrepresented by screen readers if they are announced to the user.</span></span> <span data-ttu-id="6bef1-173">A partir de .NET Framework 4.8, WPF ya no incluye elementos ocultos o contraídos en la vista de control del árbol de UIAutomation, por lo que los lectores de pantalla ya no pueden anunciar estos elementos.</span><span class="sxs-lookup"><span data-stu-id="6bef1-173">Starting with .NET Framework 4.8, WPF no longer includes collapsed or hidden elements in the Control View of the UIAutomation tree, so the screen readers can no longer announce these elements.</span></span>

<span data-ttu-id="6bef1-174">**Propiedad SelectionTextBrush para su uso con una selección de texto no basada en Adorner**</span><span class="sxs-lookup"><span data-stu-id="6bef1-174">**SelectionTextBrush property for use with non-Adorner based text selection**</span></span>

<span data-ttu-id="6bef1-175">En .NET Framework 4.7.2, WPF agregó la capacidad de dibujar una selección de texto <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.PasswordBox> sin usar la capa de Adorner.</span><span class="sxs-lookup"><span data-stu-id="6bef1-175">In .NET Framework 4.7.2, WPF added the ability to draw <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.PasswordBox> text selection without using the Adorner layer.</span></span> <span data-ttu-id="6bef1-176">El color de primer plano del texto seleccionado en este escenario lo dicta <xref:System.Windows.SystemColors.HighlightTextBrush?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-176">The foreground color of the selected text in this scenario was dictated by <xref:System.Windows.SystemColors.HighlightTextBrush?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="6bef1-177">.NET Framework 4.8 agrega una nueva propiedad, `SelectionTextBrush`, que permite a los desarrolladores seleccionar el pincel específico para el texto seleccionado cuando usan una selección de texto no basada en Adorner.</span><span class="sxs-lookup"><span data-stu-id="6bef1-177">.NET Framework 4.8 adds a new property, `SelectionTextBrush`, that allows developers to select the specific brush for the selected text when using non-Adorner based text selection.</span></span> <span data-ttu-id="6bef1-178">Esta propiedad solo funciona en controles derivados de <xref:System.Windows.Controls.Primitives.TextBoxBase> y el control <xref:System.Windows.Controls.PasswordBox> en aplicaciones de WPF con la selección de texto no basada en Adorner habilitada.</span><span class="sxs-lookup"><span data-stu-id="6bef1-178">This property works only on <xref:System.Windows.Controls.Primitives.TextBoxBase>-derived controls and the <xref:System.Windows.Controls.PasswordBox> control in WPF applications with non-Adorner-based text selection enabled.</span></span> <span data-ttu-id="6bef1-179">No funciona en el control <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-179">It does not work on the <xref:System.Windows.Controls.RichTextBox> control.</span></span> <span data-ttu-id="6bef1-180">Si no está habilitada la selección de texto no basada en Adorner, esta propiedad se omite.</span><span class="sxs-lookup"><span data-stu-id="6bef1-180">If non-Adorner-based text selection is not enabled, this property is ignored.</span></span>

<span data-ttu-id="6bef1-181">Para usar esta propiedad, simplemente agréguela a su código XAML y use el enlace o el pincel adecuado.</span><span class="sxs-lookup"><span data-stu-id="6bef1-181">To use this property, simply add it to your XAML code and use the appropriate brush or binding.</span></span> <span data-ttu-id="6bef1-182">La selección de texto resultante tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="6bef1-182">The resulting text selection looks like this:</span></span>

![Captura de pantalla de la aplicación que se ejecuta con las palabras Hola mundo seleccionadas.](./media/whats-new-in-accessibility/selectiontextbrush-property.png)

<span data-ttu-id="6bef1-184">Puede combinar el uso de las propiedades `SelectionBrush` y `SelectionTextBrush` para generar cualquier combinación de color de primer plano y de fondo que le parezca adecuada.</span><span class="sxs-lookup"><span data-stu-id="6bef1-184">You can combine the use of the `SelectionBrush` and `SelectionTextBrush` properties to generate any background and foreground color combination that you deem appropriate.</span></span>

<span data-ttu-id="6bef1-185">**Compatibilidad con la propiedad de UIAutomation ControllerFor**</span><span class="sxs-lookup"><span data-stu-id="6bef1-185">**Support for the UIAutomation ControllerFor property**</span></span>

<span data-ttu-id="6bef1-186">La propiedad `ControllerFor` de UIAutomation devuelve una matriz de elementos de automatización que son manipulados por el elemento de automatización que es compatible con esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="6bef1-186">UIAutomation’s `ControllerFor` property returns an array of automation elements that are manipulated by the automation element that supports this property.</span></span> <span data-ttu-id="6bef1-187">Esta propiedad se utiliza normalmente para mejorar la accesibilidad de las sugerencias automáticas.</span><span class="sxs-lookup"><span data-stu-id="6bef1-187">This property is commonly used for Auto-suggest accessibility.</span></span> <span data-ttu-id="6bef1-188">`ControllerFor` se utiliza cuando un elemento de automatización afecta a uno o más segmentos de la interfaz de usuario de la aplicación o el escritorio.</span><span class="sxs-lookup"><span data-stu-id="6bef1-188">`ControllerFor` is used when an automation element affects one or more segments of the application UI or the desktop.</span></span> <span data-ttu-id="6bef1-189">De otro modo, resulta difícil asociar el impacto de la operación de control de los elementos de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="6bef1-189">Otherwise, it is hard to associate the impact of the control operation with UI elements.</span></span> <span data-ttu-id="6bef1-190">Esta característica agrega la capacidad de que los controles puedan proporcionar un valor para la propiedad `ControllerFor`.</span><span class="sxs-lookup"><span data-stu-id="6bef1-190">This feature adds the ability for controls to provide a value for the `ControllerFor` property.</span></span>

<span data-ttu-id="6bef1-191">.NET Framework 4.8 agrega un nuevo método virtual, <xref:System.Windows.Automation.Peers.AutomationPeer.GetControlledPeersCore?displayProperty=nameWithType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-191">.NET Framework 4.8 adds a new virtual method, <xref:System.Windows.Automation.Peers.AutomationPeer.GetControlledPeersCore?displayProperty=nameWithType?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6bef1-192">Para proporcionar un valor para la propiedad `ControllerFor`, simplemente reemplace este método y devuelva un `List<AutomationPeer>` para los controles que manipula este <xref:System.Windows.Automation.Peers.AutomationPeer>:</span><span class="sxs-lookup"><span data-stu-id="6bef1-192">To provide a value for the `ControllerFor` property, simply override this method and return a `List<AutomationPeer>` for the controls being manipulated by this <xref:System.Windows.Automation.Peers.AutomationPeer>:</span></span>

```csharp
public class AutoSuggestTextBox: TextBox
{
   protected override AutomationPeer OnCreateAutomationPeer()
   {
      return new AutoSuggestTextBoxAutomationPeer(this);
   }

   public ListBox SuggestionListBox;
}

internal class AutoSuggestTextBoxAutomationPeer : TextBoxAutomationPeer
{
   public AutoSuggestTextBoxAutomationPeer(AutoSuggestTextBox owner) : base(owner)
   {
   }

   protected override List<AutomationPeer> GetControlledPeersCore()
   {
      List<AutomationPeer> controlledPeers = new List<AutomationPeer>();
      AutoSuggestTextBox owner = Owner as AutoSuggestTextBox;
      controlledPeers.Add(UIElementAutomationPeer.CreatePeerForElement(owner.SuggestionListBox));
      return controlledPeers;
   }
}
```

<span data-ttu-id="6bef1-193">**Informaciones sobre herramientas en el acceso mediante teclado**</span><span class="sxs-lookup"><span data-stu-id="6bef1-193">**Tooltips on keyboard access**</span></span>

<span data-ttu-id="6bef1-194">En .NET Framework 4.7.2 y versiones anteriores, las informaciones sobre herramientas se muestran solo cuando el usuario desplaza el cursor del mouse sobre un control.</span><span class="sxs-lookup"><span data-stu-id="6bef1-194">In .NET Framework 4.7.2 and earlier versions, tooltips display only when the user hovers the mouse cursor over a control.</span></span> <span data-ttu-id="6bef1-195">En .NET Framework 4.8, las informaciones sobre herramientas también se muestran en el foco del teclado, así como a través de un método abreviado de teclado.</span><span class="sxs-lookup"><span data-stu-id="6bef1-195">In .NET Framework 4.8, tooltips also display on keyboard focus, as well as via a keyboard shortcut.</span></span>

<span data-ttu-id="6bef1-196">Para habilitar esta característica, una aplicación debe estar destinada a .NET Framework 4.8 o se debe optar por recibirla utilizando los modificadores de [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) `Switch.UseLegacyAccessibilityFeatures.3` y `Switch.UseLegacyToolTipDisplay`.</span><span class="sxs-lookup"><span data-stu-id="6bef1-196">To enable this feature, an application needs to target .NET Framework 4.8 or opt-in by using the `Switch.UseLegacyAccessibilityFeatures.3` and `Switch.UseLegacyToolTipDisplay` [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switches.</span></span> <span data-ttu-id="6bef1-197">Este es un ejemplo de archivo de configuración de aplicación:</span><span class="sxs-lookup"><span data-stu-id="6bef1-197">The following is a sample application configuration file:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
   </startup>
   <runtime>
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.UseLegacyToolTipDisplay=false" />
   </runtime>
</configuration>
```

<span data-ttu-id="6bef1-198">Una vez habilitados, todos los controles que contienen una información sobre herramientas la muestran cuando el control recibe el foco de teclado.</span><span class="sxs-lookup"><span data-stu-id="6bef1-198">Once enabled, all controls that contain a tooltip display it once the control receives keyboard focus.</span></span> <span data-ttu-id="6bef1-199">Puede descartarse la información sobre herramientas dejando transcurrir un determinado tiempo o cambiando el foco del teclado.</span><span class="sxs-lookup"><span data-stu-id="6bef1-199">The tooltip can be dismissed over time or when the keyboard focus changes.</span></span> <span data-ttu-id="6bef1-200">Los usuarios también pueden descartar la información sobre herramientas manualmente mediante el uso de un nuevo método abreviado de teclado Ctrl + Mayús + F10.</span><span class="sxs-lookup"><span data-stu-id="6bef1-200">Users can also dismiss the tooltip manually by using a new keyboard shortcut, Ctrl + Shift + F10.</span></span> <span data-ttu-id="6bef1-201">Una vez que se ha descartado la información sobre herramientas, puede mostrarse de nuevo utilizando el mismo método abreviado de teclado.</span><span class="sxs-lookup"><span data-stu-id="6bef1-201">Once the tooltip has been dismissed it can be displayed again by using the same keyboard shortcut.</span></span>

> [!NOTE]
> <span data-ttu-id="6bef1-202">[Las informaciones sobre herramientas de la cinta de opciones](xref:System.Windows.Controls.Ribbon.RibbonToolTip) en controles <xref:System.Windows.Controls.Ribbon.Ribbon> no se mostrarán en el foco del teclado; solo se muestran mediante el método abreviado de teclado.</span><span class="sxs-lookup"><span data-stu-id="6bef1-202">[Ribbon tooltips](xref:System.Windows.Controls.Ribbon.RibbonToolTip) on <xref:System.Windows.Controls.Ribbon.Ribbon> controls won’t show on keyboard focus; they only show via the keyboard shortcut.</span></span>

<span data-ttu-id="6bef1-203">**Se ha agregado compatibilidad con las propiedades de UIAutomation SizeOfSet y PositionInSet**</span><span class="sxs-lookup"><span data-stu-id="6bef1-203">**Added Support for SizeOfSet and PositionInSet UIAutomation properties**</span></span>

<span data-ttu-id="6bef1-204">Windows 10 introdujo dos nuevas propiedades de UIAutomation, `SizeOfSet` y `PositionInSet`, que las aplicaciones usan para describir el recuento de elementos en un conjunto.</span><span class="sxs-lookup"><span data-stu-id="6bef1-204">Windows 10 introduced two new UIAutomation properties, `SizeOfSet` and `PositionInSet`, which are used by applications to describe the count of items in a set.</span></span> <span data-ttu-id="6bef1-205">Las aplicaciones cliente de UIAutomation, como los lectores de pantalla, posteriormente pueden consultar en una aplicación estas propiedades y anunciar una representación exacta de la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6bef1-205">UIAutomation client applications such as screen readers can then query an application for these properties and announce an accurate representation of the application’s UI.</span></span>

<span data-ttu-id="6bef1-206">A partir de .NET Framework 4.8, WPF expone estas dos propiedades para UIAutomation en aplicaciones de WPF.</span><span class="sxs-lookup"><span data-stu-id="6bef1-206">Starting with .NET Framework 4.8, WPF  exposes these two properties to UIAutomation in WPF applications.</span></span> <span data-ttu-id="6bef1-207">Esto puede realizarse de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="6bef1-207">This can be accomplished in two ways:</span></span>

- <span data-ttu-id="6bef1-208">Mediante el uso de propiedades de dependencia.</span><span class="sxs-lookup"><span data-stu-id="6bef1-208">By using dependency properties.</span></span>

  <span data-ttu-id="6bef1-209">WPF agrega dos nuevas propiedades de dependencia, <xref:System.Windows.Automation.AutomationProperties.SizeOfSet?displayProperty=nameWithType> y <xref:System.Windows.Automation.AutomationProperties.PositionInSet?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-209">WPF adds two new dependency properties, <xref:System.Windows.Automation.AutomationProperties.SizeOfSet?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.PositionInSet?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6bef1-210">Un desarrollador puede usar XAML para establecer sus valores:</span><span class="sxs-lookup"><span data-stu-id="6bef1-210">A developer can use XAML to set their values:</span></span>

  ```xaml
  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="1">Button 1</Button>

  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="2">Button 2</Button>

  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="3">Button 3</Button>
  ```

- <span data-ttu-id="6bef1-211">Invalidando los métodos virtuales AutomationPeer.</span><span class="sxs-lookup"><span data-stu-id="6bef1-211">By overriding AutomationPeer virtual methods.</span></span>

  <span data-ttu-id="6bef1-212">Los métodos virtuales <xref:System.Windows.Automation.Peers.AutomationPeer.GetSizeOfSetCore> y <xref:System.Windows.Automation.Peers.AutomationPeer.GetPositionInSetCore> se han agregado a la clase AutomationPeer.</span><span class="sxs-lookup"><span data-stu-id="6bef1-212">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetSizeOfSetCore> and <xref:System.Windows.Automation.Peers.AutomationPeer.GetPositionInSetCore> virtual methods been added to the AutomationPeer class.</span></span> <span data-ttu-id="6bef1-213">Un desarrollador puede proporcionar valores para `SizeOfSet` y `PositionInSet` reemplazando estos métodos, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6bef1-213">A developer can provide values for `SizeOfSet` and `PositionInSet` by overriding these methods, as shown in the following example:</span></span>

  ```csharp
  public class MyButtonAutomationPeer : ButtonAutomationPeer
  {
    protected override int GetSizeOfSetCore()
    {
        // Call into your own logic to provide a value for SizeOfSet
        return CalculateSizeOfSet();
    }

    protected override int GetPositionInSetCore()
    {
        // Call into your own logic to provide a value for PositionInSet
        return CalculatePositionInSet();
    }
  }
  ```

<span data-ttu-id="6bef1-214">Además, los elementos de instancias de <xref:System.Windows.Controls.ItemsControl> proporcionan un valor para estas propiedades automáticamente sin ninguna acción adicional del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="6bef1-214">In addition, items in <xref:System.Windows.Controls.ItemsControl> instances provide a value for these properties automatically without additional action from the developer.</span></span> <span data-ttu-id="6bef1-215">Si un <xref:System.Windows.Controls.ItemsControl> está agrupado, la colección de grupos se representa como un conjunto y cada grupo se cuenta como un conjunto independiente, con cada elemento dentro del grupo proporcionando su posición dentro del grupo, así como el tamaño del grupo.</span><span class="sxs-lookup"><span data-stu-id="6bef1-215">If an <xref:System.Windows.Controls.ItemsControl> is grouped, the collection of groups is represented as a set, and each group is counted as a separate set, with each item inside that group providing its position inside that group as well as the size of the group.</span></span> <span data-ttu-id="6bef1-216">Los valores automáticos no se ven afectados por la virtualización.</span><span class="sxs-lookup"><span data-stu-id="6bef1-216">Automatic values are not affected by virtualization.</span></span> <span data-ttu-id="6bef1-217">Incluso si un elemento no se materializa, se sigue contabilizando de cara a obtener el tamaño total del conjunto y afecta a la posición en el conjunto de sus elementos del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="6bef1-217">Even if an item is not realized, it is still counted toward the total size of the set and affects the position in the set of its sibling items.</span></span>

<span data-ttu-id="6bef1-218">Solo se proporcionan valores automáticos si la aplicación tiene como destino .NET Framework 4.8.</span><span class="sxs-lookup"><span data-stu-id="6bef1-218">Automatic values are only provided if the application targets .NET Framework 4.8.</span></span> <span data-ttu-id="6bef1-219">Para las aplicaciones que tienen como destino una versión anterior de .NET Framework, puede establecer el [modificador de AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) `Switch.UseLegacyAccessibilityFeatures.3`, tal y como se muestra en el siguiente archivo App.config:</span><span class="sxs-lookup"><span data-stu-id="6bef1-219">For applications that target an earlier version of the .NET Framework, you can set the `Switch.UseLegacyAccessibilityFeatures.3` [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md), as shown in the following App.config file:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
   </startup>
   <runtime>
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
   </runtime>
</configuration>
```

<a name="wf48"></a>

### <a name="windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="6bef1-220">Diseñador de flujo de trabajo de Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="6bef1-220">Windows Workflow Foundation (WF) workflow designer</span></span>

<span data-ttu-id="6bef1-221">El Diseñador de flujo de trabajo incluye los cambios siguientes en .NET Framework 4.8:</span><span class="sxs-lookup"><span data-stu-id="6bef1-221">The workflow designer includes the following changes in .NET Framework 4.8:</span></span>

- <span data-ttu-id="6bef1-222">Los usuarios de Narrador podrán ver mejoras en las etiquetas de caso FlowSwitch.</span><span class="sxs-lookup"><span data-stu-id="6bef1-222">Users using Narrator will see improvements in FlowSwitch case labels.</span></span>

- <span data-ttu-id="6bef1-223">Los usuarios de Narrador podrán ver mejoras en las descripciones de los botones.</span><span class="sxs-lookup"><span data-stu-id="6bef1-223">Users using Narrator will see improvements in button descriptions.</span></span>

- <span data-ttu-id="6bef1-224">Los usuarios que elijan temas de contraste alto verán mejoras en la visibilidad del Diseñador de flujo de trabajo y sus controles, como relaciones de contraste mejoradas entre los elementos y cuadros de selección más evidentes para los elementos del foco.</span><span class="sxs-lookup"><span data-stu-id="6bef1-224">Users who choose High Contrast themes will see improvements in the visibility of the Workflow Designer and its controls, like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

<span data-ttu-id="6bef1-225">Si la aplicación tiene como destino .NET Framework 4.7.2 o una versión anterior, se puede optar por recibir estos cambios estableciendo el [modificador de AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) `Switch.UseLegacyAccessibilityFeatures.3` como `false` en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6bef1-225">If your application targets .NET Framework 4.7.2 or an earlier version, you can opt into these changes by setting the `Switch.UseLegacyAccessibilityFeatures.3` [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to `false` in your application configuration file.</span></span> <span data-ttu-id="6bef1-226">Para obtener más información, consulte la sección [Aprovechar las mejoras de accesibilidad](#taking-advantage-of-accessibility-enhancements) de este artículo.</span><span class="sxs-lookup"><span data-stu-id="6bef1-226">For more information, see the [Taking advantage of accessibility enhancements](#taking-advantage-of-accessibility-enhancements) section in this article.</span></span>

## <a name="whats-new-in-accessibility-in-net-framework-472"></a><span data-ttu-id="6bef1-227">Novedades de accesibilidad en .NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="6bef1-227">What's new in accessibility in .NET Framework 4.7.2</span></span>

<span data-ttu-id="6bef1-228">.NET Framework 4.7.2 incluye nuevas características de accesibilidad en las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="6bef1-228">.NET Framework 4.7.2 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="6bef1-229">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6bef1-229">Windows Forms</span></span>](#winforms472)

- [<span data-ttu-id="6bef1-230">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="6bef1-230">Windows Presentation Foundation (WPF)</span></span>](#wpf472)

<a name="winforms472"></a>

### <a name="windows-forms"></a><span data-ttu-id="6bef1-231">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6bef1-231">Windows Forms</span></span>

<span data-ttu-id="6bef1-232">**Colores definidos por el sistema operativo en los temas de contraste alto**</span><span class="sxs-lookup"><span data-stu-id="6bef1-232">**OS-defined colors in High Contrast themes**</span></span>

<span data-ttu-id="6bef1-233">A partir de .NET Framework 4.7.2, Windows Forms usa colores definidos por el sistema operativo en los temas de contraste alto.</span><span class="sxs-lookup"><span data-stu-id="6bef1-233">Starting with .NET Framework 4.7.2, Windows Forms uses colors defined by the operating system in High Contrast themes.</span></span> <span data-ttu-id="6bef1-234">Esto afecta a los siguientes controles:</span><span class="sxs-lookup"><span data-stu-id="6bef1-234">This affects the following controls:</span></span>

- <span data-ttu-id="6bef1-235">La flecha desplegable del control <xref:System.Windows.Forms.ToolStripDropDownButton>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-235">The drop-down arrow of the <xref:System.Windows.Forms.ToolStripDropDownButton> control.</span></span>

- <span data-ttu-id="6bef1-236">Los controles <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> y <xref:System.Windows.Forms.CheckBox> que tienen <xref:System.Windows.Forms.ButtonBase.FlatStyle> establecido en <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> o en <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-236">The <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with <xref:System.Windows.Forms.ButtonBase.FlatStyle> set to <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> or <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6bef1-237">Antes, los colores de fondo y de texto seleccionados no tenían contraste y eran difíciles de leer.</span><span class="sxs-lookup"><span data-stu-id="6bef1-237">Previously, selected text and background colors were not contrasting and were hard to read.</span></span>

- <span data-ttu-id="6bef1-238">Controles contenidos en un <xref:System.Windows.Forms.GroupBox> que tiene su propiedad <xref:System.Windows.Forms.Control.Enabled> establecida en `false`.</span><span class="sxs-lookup"><span data-stu-id="6bef1-238">Controls contained within a <xref:System.Windows.Forms.GroupBox> that has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="6bef1-239">Los controles <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox> y <xref:System.Windows.Forms.ToolStripDropDownButton> que tienen una relación de contraste de luminosidad mayor en el modo de contraste alto.</span><span class="sxs-lookup"><span data-stu-id="6bef1-239">The <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox>, and <xref:System.Windows.Forms.ToolStripDropDownButton> controls, which have an increased luminosity contrast ratio in High Contrast Mode.</span></span>

- <span data-ttu-id="6bef1-240">La propiedad <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> de <xref:System.Windows.Forms.DataGridViewLinkCell>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-240">The <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> property of the <xref:System.Windows.Forms.DataGridViewLinkCell>.</span></span>

<span data-ttu-id="6bef1-241">**Mejoras de Narrador**</span><span class="sxs-lookup"><span data-stu-id="6bef1-241">**Narrator improvements**</span></span>

<span data-ttu-id="6bef1-242">A partir de .NET Framework 4.7.2, la compatibilidad con Narrador ha mejorado de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6bef1-242">Starting with .NET Framework 4.7.2, Narrator support is enhanced as follows:</span></span>

- <span data-ttu-id="6bef1-243">El valor de la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> se anuncia al anunciar el texto de un objeto <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-243">It announces the value of the <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> property when announcing the text of a <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>

- <span data-ttu-id="6bef1-244">Indica cuándo un objeto <xref:System.Windows.Forms.ToolStripMenuItem> tiene su propiedad <xref:System.Windows.Forms.Control.Enabled> establecida en `false`.</span><span class="sxs-lookup"><span data-stu-id="6bef1-244">It indicates when a <xref:System.Windows.Forms.ToolStripMenuItem> has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="6bef1-245">Ofrece información sobre el estado de una casilla cuando la propiedad <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> está establecida en `true`.</span><span class="sxs-lookup"><span data-stu-id="6bef1-245">It gives feedback on the state of a check box when the <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> property is set to `true`.</span></span>

- <span data-ttu-id="6bef1-246">El orden de foco del Modo de examen de Narrador es coherente con el orden visual de los controles del cuadro de diálogo de descarga de ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="6bef1-246">Narrator's Scan Mode focus order is consistent with the visual order of the controls on the ClickOnce download dialog window.</span></span>

<span data-ttu-id="6bef1-247">**Mejoras de DataGridView**</span><span class="sxs-lookup"><span data-stu-id="6bef1-247">**DataGridView improvements**</span></span>

<span data-ttu-id="6bef1-248">A partir de .NET Framework 4.7.2, el control <xref:System.Windows.Forms.DataGridView> presenta las siguientes mejoras de accesibilidad:</span><span class="sxs-lookup"><span data-stu-id="6bef1-248">Starting with .NET Framework 4.7.2, the <xref:System.Windows.Forms.DataGridView> control has introduced the following accessibility improvements:</span></span>

- <span data-ttu-id="6bef1-249">Las filas se pueden ordenar con el teclado.</span><span class="sxs-lookup"><span data-stu-id="6bef1-249">Rows can be sorted using the keyboard.</span></span> <span data-ttu-id="6bef1-250">Un usuario puede presionar la tecla F3 para ordenar por la columna actual.</span><span class="sxs-lookup"><span data-stu-id="6bef1-250">A user can use the F3 key in order to sort by the current column.</span></span>

- <span data-ttu-id="6bef1-251">Cuando <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> se establece en <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, el encabezado de columna cambia de color para indicar la columna actual cuando el usuario se desplaza entre las celdas de la fila actual.</span><span class="sxs-lookup"><span data-stu-id="6bef1-251">When the <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> is set to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, the column header changes color to indicate the current column as the user tabs through the cells in the current row.</span></span>

- <span data-ttu-id="6bef1-252">La propiedad <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> de <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> devuelve el control primario correcto.</span><span class="sxs-lookup"><span data-stu-id="6bef1-252">The <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> property of a  <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> returns the correct parent control.</span></span>

<span data-ttu-id="6bef1-253">**Indicaciones visuales mejoradas**</span><span class="sxs-lookup"><span data-stu-id="6bef1-253">**Improved visual cues**</span></span>

- <span data-ttu-id="6bef1-254">Los controles <xref:System.Windows.Forms.RadioButton> y <xref:System.Windows.Forms.CheckBox> con una propiedad <xref:System.Windows.Forms.ButtonBase.Text> vacía se mostrará un indicador de foco cuando reciban el foco.</span><span class="sxs-lookup"><span data-stu-id="6bef1-254">The <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with an empty <xref:System.Windows.Forms.ButtonBase.Text> property  display a focus indicator when they receive the focus.</span></span>

<span data-ttu-id="6bef1-255">**Compatibilidad con la cuadrícula de propiedades mejorada**</span><span class="sxs-lookup"><span data-stu-id="6bef1-255">**Improved Property Grid Support**</span></span>

- <span data-ttu-id="6bef1-256">Ahora los elementos secundarios del control <xref:System.Windows.Forms.PropertyGrid> devuelven un valor `true` para la propiedad <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> solo cuando un elemento PropertyGrid está habilitado.</span><span class="sxs-lookup"><span data-stu-id="6bef1-256">The <xref:System.Windows.Forms.PropertyGrid> control child elements now return a `true` for the  <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> property only when a PropertyGrid element is enabled.</span></span>

- <span data-ttu-id="6bef1-257">Los elementos secundarios del control <xref:System.Windows.Forms.PropertyGrid> devuelven un valor `false` para la propiedad <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> solo cuando el usuario pueda modificar un elemento PropertyGrid.</span><span class="sxs-lookup"><span data-stu-id="6bef1-257">The <xref:System.Windows.Forms.PropertyGrid> control child elements return a `false` for the <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> property only when a PropertyGrid element can be changed by the user.</span></span>

<span data-ttu-id="6bef1-258">**Navegación mejorada mediante el teclado**</span><span class="sxs-lookup"><span data-stu-id="6bef1-258">**Improved keyboard navigation**</span></span>

- <span data-ttu-id="6bef1-259">El control <xref:System.Windows.Forms.ToolStripButton> permite el foco cuando se incluye dentro de un control <xref:System.Windows.Forms.ToolStripPanel> que tiene la propiedad <xref:System.Windows.Forms.ToolStripPanel.TabStop> establecida en `true`.</span><span class="sxs-lookup"><span data-stu-id="6bef1-259">The <xref:System.Windows.Forms.ToolStripButton> control allows focus when contained within a <xref:System.Windows.Forms.ToolStripPanel> that has the <xref:System.Windows.Forms.ToolStripPanel.TabStop> property set to `true`</span></span>

<a name="wpf472"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="6bef1-260">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="6bef1-260">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="6bef1-261">**Cambios en los controles CheckBox y RadioButton**</span><span class="sxs-lookup"><span data-stu-id="6bef1-261">**Changes to the CheckBox and RadioButton controls**</span></span>

<span data-ttu-id="6bef1-262">En .NET Framework 4.7.1 y versiones anteriores, los controles <xref:System.Windows.Controls.CheckBox?displayProperty=nameWithType> y <xref:System.Windows.Controls.RadioButton?displayProperty=nameWithType> de WPF tenían objetos visuales de foco incoherentes y, en los temas Clásico y Contraste alto, eran incorrectos.</span><span class="sxs-lookup"><span data-stu-id="6bef1-262">In .NET Framework 4.7.1 and earlier versions, the WPF <xref:System.Windows.Controls.CheckBox?displayProperty=nameWithType> and <xref:System.Windows.Controls.RadioButton?displayProperty=nameWithType> controls have inconsistent and, in Classic and High Contrast themes, incorrect focus visuals.</span></span>  <span data-ttu-id="6bef1-263">Estos problemas se producen en casos en los que no se ha definido ningún contenido para los controles.</span><span class="sxs-lookup"><span data-stu-id="6bef1-263">These issues occur in cases where the controls do not have any content set.</span></span>  <span data-ttu-id="6bef1-264">Esto puede hacer que la transición entre los temas sea confusa y el objeto visual de foco difícil de ver.</span><span class="sxs-lookup"><span data-stu-id="6bef1-264">This can make the transition between themes confusing and the focus visual hard to see.</span></span>

<span data-ttu-id="6bef1-265">En .NET Framework 4.7.2, estos objetos visuales son ahora más coherentes entre los temas y se ven más fácilmente en los temas Clásico y Contraste alto.</span><span class="sxs-lookup"><span data-stu-id="6bef1-265">In .NET Framework 4.7.2, these visuals are now more consistent across themes and more easily visible in Classic and High Contrast themes.</span></span>

<span data-ttu-id="6bef1-266">**Controles de WinForms hospedados en una aplicación WPF**</span><span class="sxs-lookup"><span data-stu-id="6bef1-266">**WinForms controls hosted in a WPF application**</span></span>

<span data-ttu-id="6bef1-267">En un control de WinForms hospedado en una aplicación WPF en .NET Framework 4.7.1 y versiones anteriores, no se podía usar el tabulador para salir de la capa de WinForms si el primer o último control de esa capa era el control <xref:System.Windows.Forms.Integration.ElementHost> de WPF.</span><span class="sxs-lookup"><span data-stu-id="6bef1-267">For WinForms control hosted in a WPF application in .NET Framework 4.7.1 and earlier versions, users couldn't tab out of the WinForms layer if the first or last control in that layer is the WPF <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span> <span data-ttu-id="6bef1-268">Ahora, en .NET Framework 4.7.2 se puede usar el tabulador para salir de la capa de WinForms.</span><span class="sxs-lookup"><span data-stu-id="6bef1-268">In .NET Framework 4.7.2, users are now able to tab out of the WinForms layer.</span></span>

<span data-ttu-id="6bef1-269">Con todo, puede que las aplicaciones automatizadas que se basan en que el foco no escape nunca de la capa de WinForms dejen de funcionar según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="6bef1-269">However, automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>

## <a name="whats-new-in-accessibility-in-net-framework-471"></a><span data-ttu-id="6bef1-270">Novedades de accesibilidad en .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="6bef1-270">What's new in accessibility in .NET Framework 4.7.1</span></span>

<span data-ttu-id="6bef1-271">.NET Framework 4.7.1 incluye nuevas características de accesibilidad en las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="6bef1-271">.NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="6bef1-272">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="6bef1-272">Windows Presentation Foundation (WPF)</span></span>](#wpf471)

- [<span data-ttu-id="6bef1-273">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6bef1-273">Windows Forms</span></span>](#winforms471)

- [<span data-ttu-id="6bef1-274">Controles web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6bef1-274">ASP.NET web controls</span></span>](#aspnet471)

- [<span data-ttu-id="6bef1-275">Herramientas del SDK de .NET</span><span class="sxs-lookup"><span data-stu-id="6bef1-275">.NET SDK Tools</span></span>](#tools471)

- [<span data-ttu-id="6bef1-276">Diseñador de flujo de trabajo de Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="6bef1-276">Windows Workflow Foundation (WF) Workflow Designer</span></span>](#wf471)

<a name="wpf471"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="6bef1-277">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="6bef1-277">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="6bef1-278">**Mejoras del lector de pantalla**</span><span class="sxs-lookup"><span data-stu-id="6bef1-278">**Screen reader improvements**</span></span>

<span data-ttu-id="6bef1-279">Si las mejoras de accesibilidad están habilitadas, .NET Framework 4.7.1 incluye las siguientes mejoras que afectan a los lectores de pantalla:</span><span class="sxs-lookup"><span data-stu-id="6bef1-279">If accessibility improvements are enabled, .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="6bef1-280">En .NET Framework 4.7 y versiones anteriores, los lectores de pantalla anunciaban los controles <xref:System.Windows.Controls.Expander> como botones.</span><span class="sxs-lookup"><span data-stu-id="6bef1-280">In .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="6bef1-281">A partir de .NET Framework 4.7.1, se anuncian correctamente como grupos que se pueden contraer y expandir.</span><span class="sxs-lookup"><span data-stu-id="6bef1-281">Starting with .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="6bef1-282">En .NET Framework 4.7 y versiones anteriores, los lectores de pantalla anunciaban los controles <xref:System.Windows.Controls.DataGridCell> como “personalizados”.</span><span class="sxs-lookup"><span data-stu-id="6bef1-282">In .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="6bef1-283">A partir de .NET Framework 4.7.1, se anuncian correctamente como celdas de cuadrícula de datos (localizadas).</span><span class="sxs-lookup"><span data-stu-id="6bef1-283">Starting with .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>

- <span data-ttu-id="6bef1-284">A partir de .NET Framework 4.7.1, los lectores de pantalla anuncian el nombre de un <xref:System.Windows.Controls.ComboBox> editable.</span><span class="sxs-lookup"><span data-stu-id="6bef1-284">Starting with .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="6bef1-285">En .NET Framework 4.7 y versiones anteriores, los controles <xref:System.Windows.Controls.PasswordBox> se anunciaban como “no hay elemento a la vista” o tenían un comportamiento incorrecto.</span><span class="sxs-lookup"><span data-stu-id="6bef1-285">In .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="6bef1-286">Este problema se corrigió a partir de .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="6bef1-286">This issue is fixed starting with .NET Framework 4.7.1.</span></span>

<span data-ttu-id="6bef1-287">**Compatibilidad con las regiones activas de UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="6bef1-287">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="6bef1-288">Los lectores de pantalla como Narrador ayudan a los usuarios a leer el contenido de la interfaz de usuario de una aplicación, normalmente mediante salida de texto a voz del contenido de la interfaz de usuario que tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="6bef1-288">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="6bef1-289">Pero si un elemento de la interfaz de usuario cambia y no tiene el foco, puede que no se notifique al usuario y este pierda información importante.</span><span class="sxs-lookup"><span data-stu-id="6bef1-289">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="6bef1-290">Las regiones activas aspiran a resolver este problema.</span><span class="sxs-lookup"><span data-stu-id="6bef1-290">Live regions aim at solving this problem.</span></span> <span data-ttu-id="6bef1-291">Un desarrollador puede usarlas para informar al lector de pantalla o a cualquier otro cliente de UIAutomation de que se ha realizado un cambio importante en un elemento de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="6bef1-291">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="6bef1-292">Luego el lector de pantalla puede decidir cómo y cuándo informar al usuario de este cambio.</span><span class="sxs-lookup"><span data-stu-id="6bef1-292">The screen reader can then decide how and when to inform the user of this change.</span></span>

<span data-ttu-id="6bef1-293">Para admitir las regiones activas, se han agregado las siguientes API a WPF:</span><span class="sxs-lookup"><span data-stu-id="6bef1-293">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="6bef1-294">Los campos <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> y <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>, que identifican a la propiedad **LiveSetting** y al evento **LiveRegionChanged**.</span><span class="sxs-lookup"><span data-stu-id="6bef1-294">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="6bef1-295">Se pueden establecer mediante XAML.</span><span class="sxs-lookup"><span data-stu-id="6bef1-295">They can be set by using XAML.</span></span>

- <span data-ttu-id="6bef1-296">La propiedad adjunta **AutomationProperties.LiveSetting**, que informa al lector de pantalla de la importancia del cambio de la interfaz de usuario para el usuario.</span><span class="sxs-lookup"><span data-stu-id="6bef1-296">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="6bef1-297">La propiedad <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>, que identifica a la propiedad adjunta **AutomationProperties.LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="6bef1-297">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>

- <span data-ttu-id="6bef1-298">El método <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>, que se puede invalidar para proporcionar un valor **LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="6bef1-298">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="6bef1-299">Los métodos <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> y <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>, que obtienen y establecen un valor **LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="6bef1-299">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>

- <span data-ttu-id="6bef1-300">La enumeración <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>, que define los siguientes posibles valores **LiveSetting**:</span><span class="sxs-lookup"><span data-stu-id="6bef1-300">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

  - <span data-ttu-id="6bef1-301"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-301"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6bef1-302">El elemento no envía notificaciones si ha cambiado el contenido de la región activa.</span><span class="sxs-lookup"><span data-stu-id="6bef1-302">The element does not send notifications if the content of the live region has changed.</span></span>
  - <span data-ttu-id="6bef1-303"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-303"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6bef1-304">El elemento envía notificaciones que no interrumpen el trabajo si ha cambiado el contenido de la región activa.</span><span class="sxs-lookup"><span data-stu-id="6bef1-304">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>

  - <span data-ttu-id="6bef1-305"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-305"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6bef1-306">El elemento envía notificaciones que interrumpen el trabajo si ha cambiado el contenido de la región activa.</span><span class="sxs-lookup"><span data-stu-id="6bef1-306">The element sends interruptive notifications if the content of the live region has changed.</span></span>

<span data-ttu-id="6bef1-307">Puede crear una región activa si establece la propiedad **AutomationProperties.LiveSetting** en el elemento de interés, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6bef1-307">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="6bef1-308">Cuando cambian los datos de la región activa y necesita informar a un lector de pantalla, puede generar un evento de forma explícita, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6bef1-308">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```

```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="6bef1-309">**Contraste alto**</span><span class="sxs-lookup"><span data-stu-id="6bef1-309">**High contrast**</span></span>

<span data-ttu-id="6bef1-310">A partir de .NET Framework 4.7.1, se han realizado mejoras de contraste alto en diversos controles de WPF.</span><span class="sxs-lookup"><span data-stu-id="6bef1-310">Starting with .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="6bef1-311">Ahora son visibles cuando el tema <xref:System.Windows.SystemParameters.HighContrast%2A> está establecido.</span><span class="sxs-lookup"><span data-stu-id="6bef1-311">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="6bef1-312">Se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6bef1-312">These include:</span></span>

- <span data-ttu-id="6bef1-313">Control <xref:System.Windows.Controls.Expander></span><span class="sxs-lookup"><span data-stu-id="6bef1-313"><xref:System.Windows.Controls.Expander> control</span></span>

  <span data-ttu-id="6bef1-314">El objeto visual de foco del control <xref:System.Windows.Controls.Expander> ahora es visible.</span><span class="sxs-lookup"><span data-stu-id="6bef1-314">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="6bef1-315">Los objetos visuales de teclado de los controles <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.RadioButton> también son visibles.</span><span class="sxs-lookup"><span data-stu-id="6bef1-315">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="6bef1-316">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6bef1-316">For example:</span></span>

  <span data-ttu-id="6bef1-317">Antes:</span><span class="sxs-lookup"><span data-stu-id="6bef1-317">Before:</span></span>

  ![Captura de pantalla del control de expansor con objeto visual de foco y sin foco.](./media/whats-new-in-accessibility/expander-control-before.png)

  <span data-ttu-id="6bef1-319">Después:</span><span class="sxs-lookup"><span data-stu-id="6bef1-319">After:</span></span>

  ![Captura de pantalla del control de expansor con el foco que muestra una línea de puntos alrededor del texto del control.](./media/whats-new-in-accessibility/expander-control-after.png)

- <span data-ttu-id="6bef1-321">Controles <xref:System.Windows.Controls.CheckBox> y <xref:System.Windows.Controls.RadioButton></span><span class="sxs-lookup"><span data-stu-id="6bef1-321"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>

  <span data-ttu-id="6bef1-322">El texto de los controles <xref:System.Windows.Controls.CheckBox> y <xref:System.Windows.Controls.RadioButton> ahora es más fácil de ver cuando se selecciona en los temas de contraste alto.</span><span class="sxs-lookup"><span data-stu-id="6bef1-322">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="6bef1-323">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6bef1-323">For example:</span></span>

  <span data-ttu-id="6bef1-324">Antes:</span><span class="sxs-lookup"><span data-stu-id="6bef1-324">Before:</span></span>

  ![Captura de pantalla de los botones de radio y de comprobación con visibilidad de texto deficiente en los temas de contraste alto.](./media/whats-new-in-accessibility/high-contrast-radio-button-before.png)

  <span data-ttu-id="6bef1-326">Después:</span><span class="sxs-lookup"><span data-stu-id="6bef1-326">After:</span></span>

  ![Captura de pantalla de los botones de radio y de comprobación con una mejor visibilidad de texto en los temas de contraste alto.](./media/whats-new-in-accessibility/high-contrast-radio-button-after.png)

- <span data-ttu-id="6bef1-328">Control <xref:System.Windows.Controls.ComboBox></span><span class="sxs-lookup"><span data-stu-id="6bef1-328"><xref:System.Windows.Controls.ComboBox> control</span></span>

  <span data-ttu-id="6bef1-329">A partir de .NET Framework 4.7.1, el borde de un control <xref:System.Windows.Controls.ComboBox> deshabilitado es del mismo color que el texto deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="6bef1-329">Starting with .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="6bef1-330">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6bef1-330">For example:</span></span>

  <span data-ttu-id="6bef1-331">Antes:</span><span class="sxs-lookup"><span data-stu-id="6bef1-331">Before:</span></span>

  ![Captura de pantalla de un cuadro combinado deshabilitado con borde y texto del control en distintos colores.](./media/whats-new-in-accessibility/combo-disabled-before.png)

  <span data-ttu-id="6bef1-333">Después:</span><span class="sxs-lookup"><span data-stu-id="6bef1-333">After:</span></span>

  ![Captura de pantalla de un cuadro combinado deshabilitado con borde del mismo color que el texto del control.](./media/whats-new-in-accessibility/combo-disabled-after.png)

  <span data-ttu-id="6bef1-335">Además, los botones deshabilitados y con foco usan el color de tema correcto.</span><span class="sxs-lookup"><span data-stu-id="6bef1-335">In addition, disabled and focused buttons use the correct theme color.</span></span>

  <span data-ttu-id="6bef1-336">Antes:</span><span class="sxs-lookup"><span data-stu-id="6bef1-336">Before:</span></span>

  ![Captura de pantalla de un botón negro con texto en gris que indica "Focus Me" (Enfócame).](./media/whats-new-in-accessibility/button-theme-colors-before.png)

  <span data-ttu-id="6bef1-338">Después:</span><span class="sxs-lookup"><span data-stu-id="6bef1-338">After:</span></span>

  ![Captura de pantalla de un botón azul con texto en negro que indica "Focus Me" (Enfócame).](./media/whats-new-in-accessibility/button-theme-colors-after.png)

  <span data-ttu-id="6bef1-340">Por último, en .NET Framework 4.7 y versiones anteriores, al establecer el estilo de un control <xref:System.Windows.Controls.ComboBox> en `Toolbar.ComboBoxStyleKey`, la flecha de lista desplegable se hacía invisible.</span><span class="sxs-lookup"><span data-stu-id="6bef1-340">Finally, in .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="6bef1-341">Este problema se corrigió a partir de .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="6bef1-341">This issue is fixed starting with .NET Framework 4.7.1.</span></span> <span data-ttu-id="6bef1-342">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6bef1-342">For example:</span></span>

  <span data-ttu-id="6bef1-343">Antes:</span><span class="sxs-lookup"><span data-stu-id="6bef1-343">Before:</span></span>

  ![Captura de pantalla de un control de cuadro combinado con una flecha desplegable invisible.](./media/whats-new-in-accessibility/combo-box-style-key-before.png)

  <span data-ttu-id="6bef1-345">Después:</span><span class="sxs-lookup"><span data-stu-id="6bef1-345">After:</span></span>

  ![Captura de pantalla de un control de cuadro combinado que muestra la flecha desplegable.](./media/whats-new-in-accessibility/combo-box-style-key-after.png)

- <span data-ttu-id="6bef1-347">Control <xref:System.Windows.Controls.DataGrid></span><span class="sxs-lookup"><span data-stu-id="6bef1-347"><xref:System.Windows.Controls.DataGrid> control</span></span>

  <span data-ttu-id="6bef1-348">A partir de .NET Framework 4.7.1, la flecha de indicador de orden de los controles <xref:System.Windows.Controls.DataGrid> usa los colores de tema correctos.</span><span class="sxs-lookup"><span data-stu-id="6bef1-348">Starting with .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="6bef1-349">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6bef1-349">For example:</span></span>

  <span data-ttu-id="6bef1-350">Antes:</span><span class="sxs-lookup"><span data-stu-id="6bef1-350">Before:</span></span>

  ![Captura de pantalla de la flecha de indicador de orden antes de las mejoras.](./media/whats-new-in-accessibility/sort-indicator-before.png)

  <span data-ttu-id="6bef1-352">Después:</span><span class="sxs-lookup"><span data-stu-id="6bef1-352">After:</span></span>

  ![Captura de pantalla de la flecha de indicador de orden después de las mejoras.](./media/whats-new-in-accessibility/sort-indicator-after.png)

  <span data-ttu-id="6bef1-354">Además, en .NET Framework 4.7 y versiones anteriores, el estilo de vínculo predeterminado cambiaba a un color incorrecto cuando se colocaba el mouse encima en los modos de contraste alto.</span><span class="sxs-lookup"><span data-stu-id="6bef1-354">In addition, in .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="6bef1-355">Esto se resolvió a partir de .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="6bef1-355">This is resolved starting with .NET Framework 4.7.1.</span></span> <span data-ttu-id="6bef1-356">Del mismo modo, a partir de .NET Framework 4.7.1, las columnas de casilla <xref:System.Windows.Controls.DataGrid> usan los colores esperados para comentarios de foco de teclado.</span><span class="sxs-lookup"><span data-stu-id="6bef1-356">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with .NET Framework 4.7.1.</span></span>

  <span data-ttu-id="6bef1-357">Antes:</span><span class="sxs-lookup"><span data-stu-id="6bef1-357">Before:</span></span>

  ![Captura de pantalla de un vínculo que indica "Click Me!" (Hacer clic aquí)](./media/whats-new-in-accessibility/default-link-style-before.png)

  <span data-ttu-id="6bef1-360">Después:</span><span class="sxs-lookup"><span data-stu-id="6bef1-360">After:</span></span>

  ![Captura de pantalla de un vínculo que indica "Click Me!" (Hacer clic aquí)](./media/whats-new-in-accessibility/default-link-style-after.png)

<span data-ttu-id="6bef1-363">Para más información sobre las mejoras de accesibilidad de WPF en .NET Framework 4.7.1, vea [Mejoras de accesibilidad en WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span><span class="sxs-lookup"><span data-stu-id="6bef1-363">For more information on WPF accessibility improvements in .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

<a name="winforms471"></a>

### <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="6bef1-364">Mejoras de accesibilidad de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6bef1-364">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="6bef1-365">En .NET Framework 4.7.1, Windows Forms (WinForms) incluye cambios de accesibilidad en las áreas siguientes.</span><span class="sxs-lookup"><span data-stu-id="6bef1-365">In .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="6bef1-366">**Visualización mejorada en modo de contraste alto**</span><span class="sxs-lookup"><span data-stu-id="6bef1-366">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="6bef1-367">A partir de .NET Framework 4.7.1, varios controles de WinForms ofrecen una representación mejorada en los modos de contraste alto disponibles en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6bef1-367">Starting with .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="6bef1-368">Windows 10 ha cambiado los valores de algunos colores del sistema de contraste alto y Windows Forms se basa en el marco de trabajo de Windows 10 Win32.</span><span class="sxs-lookup"><span data-stu-id="6bef1-368">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="6bef1-369">Para obtener la mejor experiencia, trabaje en la versión más reciente de Windows y use los cambios más recientes del sistema operativo al agregar un archivo app.manifest en una aplicación de prueba y quitar los comentarios de la línea del sistema operativo compatible con Windows 10 para tenga este aspecto:</span><span class="sxs-lookup"><span data-stu-id="6bef1-369">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!-- Windows 10 -->
<supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
```

<span data-ttu-id="6bef1-370">Algunos ejemplos de cambios de contraste alto:</span><span class="sxs-lookup"><span data-stu-id="6bef1-370">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="6bef1-371">Las marcas de verificación de los elementos <xref:System.Windows.Forms.MenuStrip> son más fáciles de ver.</span><span class="sxs-lookup"><span data-stu-id="6bef1-371">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="6bef1-372">Cuando se activan, los elementos <xref:System.Windows.Forms.MenuStrip> deshabilitados son más fáciles de ver.</span><span class="sxs-lookup"><span data-stu-id="6bef1-372">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="6bef1-373">El texto de un control <xref:System.Windows.Forms.Button> seleccionado contrasta con el color de selección.</span><span class="sxs-lookup"><span data-stu-id="6bef1-373">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="6bef1-374">El texto deshabilitado es más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="6bef1-374">Disabled text is easier to read.</span></span> <span data-ttu-id="6bef1-375">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6bef1-375">For example:</span></span>

  <span data-ttu-id="6bef1-376">Antes:</span><span class="sxs-lookup"><span data-stu-id="6bef1-376">Before:</span></span>

  ![Captura de pantalla de una aplicación que usa distintos controles que se ejecutan en el modo de alto contraste antes de las mejoras de accesibilidad.](./media/whats-new-in-accessibility/high-contrast-mode-menu-items-before.png)

  <span data-ttu-id="6bef1-378">Después:</span><span class="sxs-lookup"><span data-stu-id="6bef1-378">After:</span></span>

  ![Captura de pantalla de una aplicación que usa distintos controles que se ejecutan en el modo de alto contraste después de las mejoras de accesibilidad.](./media/whats-new-in-accessibility/high-contrast-mode-menu-items-after.png)

- <span data-ttu-id="6bef1-380">Mejoras de contraste alto en el cuadro de diálogo de excepción de subproceso.</span><span class="sxs-lookup"><span data-stu-id="6bef1-380">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="6bef1-381">**Compatibilidad mejorada con Narrador**</span><span class="sxs-lookup"><span data-stu-id="6bef1-381">**Improved Narrator support**</span></span>

<span data-ttu-id="6bef1-382">Windows Forms en .NET Framework 4.7.1 incluye las siguientes mejoras de accesibilidad para Narrador:</span><span class="sxs-lookup"><span data-stu-id="6bef1-382">Windows Forms in .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="6bef1-383">Narrador, así como otras herramientas de automatización de la interfaz de usuario, pueden acceder al control <xref:System.Windows.Forms.MonthCalendar>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-383">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="6bef1-384">El control <xref:System.Windows.Forms.CheckedListBox> avisa a Narrador cuando ha cambiado el estado de activación de un elemento para que el usuario sepa que ha cambiado el valor de un elemento de lista.</span><span class="sxs-lookup"><span data-stu-id="6bef1-384">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>

- <span data-ttu-id="6bef1-385">El control <xref:System.Windows.Forms.DataGridViewCell> notifica el estado correcto de solo lectura a Narrador.</span><span class="sxs-lookup"><span data-stu-id="6bef1-385">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>

- <span data-ttu-id="6bef1-386">Narrador ahora puede leer texto <xref:System.Windows.Forms.ToolStripMenuItem> deshabilitado, mientras que anteriormente omitía los elementos de menú deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="6bef1-386">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="6bef1-387">**Compatibilidad mejorada con los patrones de accesibilidad de UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="6bef1-387">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="6bef1-388">A partir de .NET Framework 4.7.1, los desarrolladores de herramientas de tecnología de accesibilidad pueden aprovechar los patrones comunes de accesibilidad de API y las propiedades de varios controles de WinForms.</span><span class="sxs-lookup"><span data-stu-id="6bef1-388">Starting with .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="6bef1-389">Estas mejoras de accesibilidad incluyen:</span><span class="sxs-lookup"><span data-stu-id="6bef1-389">These accessibility improvements include:</span></span>

- <span data-ttu-id="6bef1-390"><xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.ToolStripSplitButton> ahora son compatibles con el [patrón de expansión o contracción](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="6bef1-390">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="6bef1-391"><xref:System.Windows.Forms.DataGridViewCheckBoxCell> ahora es compatible con el [patrón de alternancia](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="6bef1-391">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>

- <span data-ttu-id="6bef1-392">El control <xref:System.Windows.Forms.ToolStripItem> admite la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> y el [patrón de expansión o contracción](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="6bef1-392">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="6bef1-393">Los controles <xref:System.Windows.Forms.NumericUpDown> y <xref:System.Windows.Forms.DomainUpDown> admiten la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-393">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property.</span></span>

<span data-ttu-id="6bef1-394">**Experiencia mejorada del explorador de propiedades**</span><span class="sxs-lookup"><span data-stu-id="6bef1-394">**Improved property browser experience**</span></span>

<span data-ttu-id="6bef1-395">A partir de .NET Framework 4.7.1, Windows Forms incluye:</span><span class="sxs-lookup"><span data-stu-id="6bef1-395">Starting with .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="6bef1-396">Una mejor navegación mediante teclado gracias a las distintas ventanas de selección desplegables.</span><span class="sxs-lookup"><span data-stu-id="6bef1-396">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="6bef1-397">Una reducción de puntos de tabulación innecesarios.</span><span class="sxs-lookup"><span data-stu-id="6bef1-397">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="6bef1-398">Mejor notificación de tipos de control.</span><span class="sxs-lookup"><span data-stu-id="6bef1-398">Better reporting of control types.</span></span>
- <span data-ttu-id="6bef1-399">Comportamiento mejorado de Narrador.</span><span class="sxs-lookup"><span data-stu-id="6bef1-399">Improved narrator behavior.</span></span>

<a name="aspnet471"></a>

### <a name="aspnet-web-controls"></a><span data-ttu-id="6bef1-400">Controles web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6bef1-400">ASP.NET web controls</span></span>

<span data-ttu-id="6bef1-401">A partir de .NET Framework 4.7.1 y la versión 15.3 de Visual Studio 2017, ASP.NET mejora el funcionamiento de los controles web ASP.NET con la tecnología de accesibilidad en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6bef1-401">Starting with .NET Framework 4.7.1 and Visual Studio 2017 version 15.3, ASP.NET improves how ASP.NET web controls work with accessibility technology in Visual Studio.</span></span> <span data-ttu-id="6bef1-402">Los cambios son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6bef1-402">Changes include the following:</span></span>

- <span data-ttu-id="6bef1-403">Cambios para implementar patrones de accesibilidad de interfaz de usuario que faltan en los controles, como el cuadro de diálogo **Agregar campo** en el **Asistente para vistas de detalles** o el cuadro de diálogo **Configurar ListView** del **Asistente de ListView**.</span><span class="sxs-lookup"><span data-stu-id="6bef1-403">Changes to implement missing UI accessibility patterns in controls, like the **Add Field** dialog in the **Details View** wizard, or the **Configure ListView** dialog of the **ListView** wizard.</span></span>

- <span data-ttu-id="6bef1-404">Cambios para mejorar la presentación en el modo Contraste alto, como el **Editor de campos del elemento de paginación de datos**.</span><span class="sxs-lookup"><span data-stu-id="6bef1-404">Changes to improve the display in High Contrast mode, like the **Data Pager Fields Editor**.</span></span>

- <span data-ttu-id="6bef1-405">Cambios para mejorar las experiencias de navegación del teclado para los controles, como el cuadro de diálogo **Campos** del **Asistente para editar campos del elemento de paginación** del control DataPager, el cuadro de diálogo **Configurar ObjectContext** o el cuadro de diálogo **Configurar selección de datos** del **Asistente para configurar origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="6bef1-405">Changes to improve the keyboard navigation experiences for controls, like the **Fields** dialog in the **Edit Pager Fields** wizard of the DataPager control, the **Configure ObjectContext** dialog, or the **Configure Data Selection** dialog of the **Configure Data Source** wizard.</span></span>

<a name="tools471"></a>

### <a name="net-sdk-tools"></a><span data-ttu-id="6bef1-406">Herramientas del SDK de .NET</span><span class="sxs-lookup"><span data-stu-id="6bef1-406">.NET SDK Tools</span></span>

<span data-ttu-id="6bef1-407">Se han corregido varios problemas de accesibilidad para mejorar la [herramienta del editor de configuración (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) y la [herramienta del visor de seguimiento de servicios (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="6bef1-407">The [Configuration Editor Tool (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) and [Service Trace Viewer Tool (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="6bef1-408">La mayoría eran problemas menores como un nombre sin definir o determinados patrones de automatización de la interfaz de usuario que no se implementaban correctamente.</span><span class="sxs-lookup"><span data-stu-id="6bef1-408">Most of these were small issues, like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="6bef1-409">Aunque muchos usuarios no son conscientes de estos valores incorrectos, los clientes que usen tecnologías de asistencia como lectores de pantalla encontrarán estas herramientas del SDK más accesibles.</span><span class="sxs-lookup"><span data-stu-id="6bef1-409">While many users won’t be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span>

<span data-ttu-id="6bef1-410">Estas mejoras cambian algunos comportamientos anteriores, como el orden del foco de teclado.</span><span class="sxs-lookup"><span data-stu-id="6bef1-410">These enhancements change some previous behaviors, such as keyboard focus order.</span></span>

<a name="wf471"></a>

### <a name="windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="6bef1-411">Diseñador de flujo de trabajo de Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="6bef1-411">Windows Workflow Foundation (WF) Workflow Designer</span></span>

<span data-ttu-id="6bef1-412">Los cambios de accesibilidad en el Diseñador de flujo de trabajo son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6bef1-412">Accessibility changes in the Workflow Designer include the following:</span></span>

- <span data-ttu-id="6bef1-413">El orden de tabulación cambia de izquierda a derecha y de arriba a abajo en algunos controles:</span><span class="sxs-lookup"><span data-stu-id="6bef1-413">The tab order changes to left to right and top to bottom in some controls:</span></span>

  - <span data-ttu-id="6bef1-414">La ventana Inicializar correlación para establecer los datos de correlación para la actividad <xref:System.ServiceModel.Activities.InitializeCorrelation>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-414">The initialize correlation window for setting correlation data for the <xref:System.ServiceModel.Activities.InitializeCorrelation> activity.</span></span>

  - <span data-ttu-id="6bef1-415">La ventana Definición de contenido para las actividades <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> y <xref:System.ServiceModel.Activities.ReceiveReply>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-415">The content definition window for the <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply> activities.</span></span>

- <span data-ttu-id="6bef1-416">Hay más funciones disponibles a través del teclado:</span><span class="sxs-lookup"><span data-stu-id="6bef1-416">More functions are available via the keyboard:</span></span>

  - <span data-ttu-id="6bef1-417">Al editar las propiedades de una actividad, los grupos de propiedades se pueden contraer mediante el teclado la primera vez que obtienen el foco.</span><span class="sxs-lookup"><span data-stu-id="6bef1-417">When editing the properties of an activity, property groups can be collapsed by keyboard the first time they are focused.</span></span>

  - <span data-ttu-id="6bef1-418">Los iconos de advertencia son accesibles con el teclado.</span><span class="sxs-lookup"><span data-stu-id="6bef1-418">Warning icons are accessible by keyboard.</span></span>

  - <span data-ttu-id="6bef1-419">El botón **Más propiedades** de la ventana **Propiedades** es accesible con el teclado.</span><span class="sxs-lookup"><span data-stu-id="6bef1-419">The **More Properties** button in the **Properties** window is accessible by keyboard.</span></span>

  - <span data-ttu-id="6bef1-420">Los usuarios del teclado pueden tener acceso a los elementos de encabezado en los paneles **Argumentos** y **Variables** del Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6bef1-420">Keyboard users can access the header items in the **Arguments** and **Variables** panes of the Workflow Designer.</span></span>

- <span data-ttu-id="6bef1-421">Visibilidad mejorada de los elementos con el foco, por ejemplo cuando:</span><span class="sxs-lookup"><span data-stu-id="6bef1-421">Improved visibility of items with focus, such as when:</span></span>

  - <span data-ttu-id="6bef1-422">Se agregan filas a las cuadrículas de datos usadas por los diseñadores de actividad y el Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6bef1-422">Adding rows to data grids used by the Workflow Designer and activity designers.</span></span>

  - <span data-ttu-id="6bef1-423">Desplazamiento entre campos en las actividades <xref:System.ServiceModel.Activities.ReceiveReply> y <xref:System.ServiceModel.Activities.SendReply>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-423">Tabbing through fields in the <xref:System.ServiceModel.Activities.ReceiveReply> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>

  - <span data-ttu-id="6bef1-424">Establecimiento de valores predeterminados para variables o argumentos.</span><span class="sxs-lookup"><span data-stu-id="6bef1-424">Setting default values for variables or arguments</span></span>

- <span data-ttu-id="6bef1-425">Los lectores de pantalla ahora pueden reconocer correctamente:</span><span class="sxs-lookup"><span data-stu-id="6bef1-425">Screen readers can now correctly recognize:</span></span>

  - <span data-ttu-id="6bef1-426">Los puntos de interrupción establecidos en el Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6bef1-426">Breakpoints set in the workflow designer.</span></span>

  - <span data-ttu-id="6bef1-427">Las actividades <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> y <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-427">The <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision>, and <xref:System.ServiceModel.Activities.CorrelationScope> activities.</span></span>
  - <span data-ttu-id="6bef1-428">El contenido de la actividad <xref:System.ServiceModel.Activities.Receive>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-428">The contents of the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>

  - <span data-ttu-id="6bef1-429">El tipo de destino para la actividad <xref:System.Activities.Statements.InvokeMethod>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-429">The Target Type for the <xref:System.Activities.Statements.InvokeMethod> activity.</span></span>

  - <span data-ttu-id="6bef1-430">El cuadro combinado Excepción y la sección Finally de la actividad <xref:System.Activities.Statements.TryCatch>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-430">The Exception combo box and the Finally section in the <xref:System.Activities.Statements.TryCatch> activity.</span></span>

  - <span data-ttu-id="6bef1-431">El cuadro combinado Tipo de mensaje, el divisor de la ventana Agregar inicializadores de correlación, la ventana Definición de contenido y la ventana Definición de CorrelatesOn en las actividades de mensajería (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> y <xref:System.ServiceModel.Activities.ReceiveReply>).</span><span class="sxs-lookup"><span data-stu-id="6bef1-431">The Message Type combo box, the splitter in the Add Correlation Initializers window, the Content Definition window, and the CorrelatesOn Definition window in the messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>

  - <span data-ttu-id="6bef1-432">Transiciones a máquina de estados y destinos de transición.</span><span class="sxs-lookup"><span data-stu-id="6bef1-432">State machine transitions and transitions destinations.</span></span>

  - <span data-ttu-id="6bef1-433">Anotaciones y conectores en las actividades <xref:System.Activities.Statements.FlowDecision>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-433">Annotations and connectors on <xref:System.Activities.Statements.FlowDecision> activities.</span></span>

  - <span data-ttu-id="6bef1-434">Los menús contextuales (clic con el botón derecho) para las actividades.</span><span class="sxs-lookup"><span data-stu-id="6bef1-434">The context (right-click) menus for activities.</span></span>

  - <span data-ttu-id="6bef1-435">Los editores de valor de propiedad, el botón Borrar búsqueda, los botones de ordenación Por categoría y Alfabético, y el cuadro de diálogo Editor de expresiones en la cuadrícula de propiedades.</span><span class="sxs-lookup"><span data-stu-id="6bef1-435">The property value editors, the Clear Search button, the By Category and Alphabetical sort buttons, and the Expression Editor dialog in the properties grid.</span></span>

  - <span data-ttu-id="6bef1-436">El porcentaje de zoom en el Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6bef1-436">The zoom percentage in the Workflow Designer.</span></span>

  - <span data-ttu-id="6bef1-437">El separador en las actividades <xref:System.Activities.Statements.Parallel> y <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-437">The separator in <xref:System.Activities.Statements.Parallel> and <xref:System.Activities.Statements.Pick> activities.</span></span>

  - <span data-ttu-id="6bef1-438">La actividad <xref:System.Activities.Statements.InvokeDelegate>.</span><span class="sxs-lookup"><span data-stu-id="6bef1-438">The <xref:System.Activities.Statements.InvokeDelegate> activity.</span></span>

  - <span data-ttu-id="6bef1-439">La ventana Seleccionar tipos para las actividades de diccionario (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>`, etc.).</span><span class="sxs-lookup"><span data-stu-id="6bef1-439">The Select Types window for dictionary activities (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>`, etc.).</span></span>

  - <span data-ttu-id="6bef1-440">La ventana Examinar y seleccionar un tipo .NET.</span><span class="sxs-lookup"><span data-stu-id="6bef1-440">The Browse and Select .NET Type window.</span></span>

  - <span data-ttu-id="6bef1-441">Rutas de navegación en el Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6bef1-441">Breadcrumbs in the Workflow Designer.</span></span>

- <span data-ttu-id="6bef1-442">Los usuarios que elijan temas de contraste alto verán muchas mejoras en la visibilidad del Diseñador de flujo de trabajo y sus controles, como relaciones de contraste mejoradas entre los elementos y cuadros de selección más evidentes para los elementos del foco.</span><span class="sxs-lookup"><span data-stu-id="6bef1-442">Users who choose High Contrast themes will see many improvements in the visibility of the Workflow Designer and its controls, like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="6bef1-443">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bef1-443">See also</span></span>

- [<span data-ttu-id="6bef1-444">Novedades de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6bef1-444">What's new in the .NET Framework</span></span>](index.md)
