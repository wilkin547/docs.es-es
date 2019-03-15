---
title: Compatibilidad con valores alto de PPP en Windows Forms
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1641702c7b1c3d3b0e83c59a96529de70f699d17
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2019
ms.locfileid: "57843614"
---
# <a name="high-dpi-support-in-windows-forms"></a><span data-ttu-id="55f93-102">Compatibilidad con valores alto de PPP en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="55f93-102">High DPI support in Windows Forms</span></span>

<span data-ttu-id="55f93-103">A partir de .NET Framework 4.7, Windows Forms incluye mejoras para los valores altos de PPP comunes y escenarios de PPP dinámicos.</span><span class="sxs-lookup"><span data-stu-id="55f93-103">Starting with the .NET Framework 4.7, Windows Forms includes enhancements for common high DPI and dynamic DPI scenarios.</span></span> <span data-ttu-id="55f93-104">Se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="55f93-104">These include:</span></span>

- <span data-ttu-id="55f93-105">Controles de mejoras en la escala y el diseño de una serie de formularios de Windows, como el <xref:System.Windows.Forms.MonthCalendar> control y el <xref:System.Windows.Forms.CheckedListBox> control.</span><span class="sxs-lookup"><span data-stu-id="55f93-105">Improvements in the scaling and layout of a number of Windows Forms controls, such as the <xref:System.Windows.Forms.MonthCalendar> control and the <xref:System.Windows.Forms.CheckedListBox> control.</span></span>

- <span data-ttu-id="55f93-106">Paso único ajuste de escala.</span><span class="sxs-lookup"><span data-stu-id="55f93-106">Single-pass scaling.</span></span>  <span data-ttu-id="55f93-107">En .NET Framework 4.6 y versiones anteriores, el escalado se realizó a través de varias pasadas, lo que provocó algunos controles escalar más que era necesario.</span><span class="sxs-lookup"><span data-stu-id="55f93-107">In the .NET Framework 4.6 and earlier versions, scaling was performed through multiple passes, which caused some controls to be scaled more than was necessary.</span></span>

- <span data-ttu-id="55f93-108">Compatibilidad con escenarios de PPP dinámicos en el que el usuario cambia el factor de escala o PPP después de que se ha iniciado una aplicación de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="55f93-108">Support for dynamic DPI scenarios in which the user changes the DPI or scale factor after a Windows Forms application has been launched.</span></span>

<span data-ttu-id="55f93-109">En las versiones de .NET Framework a partir de .NET Framework 4.7, mayor compatibilidad con PPP elevado es una característica opcional.</span><span class="sxs-lookup"><span data-stu-id="55f93-109">In versions of the .NET Framework starting with the .NET Framework 4.7, enhanced high DPI support is an opt-in feature.</span></span> <span data-ttu-id="55f93-110">Debe configurar la aplicación para aprovechar sus ventajas.</span><span class="sxs-lookup"><span data-stu-id="55f93-110">You must configure your application to take advantage of it.</span></span>

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a><span data-ttu-id="55f93-111">Configuración de la aplicación de Windows Forms para la compatibilidad con PPP elevado</span><span class="sxs-lookup"><span data-stu-id="55f93-111">Configuring your Windows Forms app for high DPI support</span></span>

<span data-ttu-id="55f93-112">Las nuevas características de Windows Forms que admiten reconocimiento de PPP alta solo están disponibles en las aplicaciones que tienen como destino .NET Framework 4.7 y que se ejecutan en sistemas operativos de Windows a partir de Windows 10 Creators Update.</span><span class="sxs-lookup"><span data-stu-id="55f93-112">The new Windows Forms features that support high DPI awareness are available only in applications that target the .NET Framework 4.7 and are running on Windows operating systems starting with the Windows 10 Creators Update.</span></span>

<span data-ttu-id="55f93-113">Además, para configurar la compatibilidad con PPP elevado en su aplicación de Windows Forms, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55f93-113">In addition, to configure high DPI support in your Windows Forms application, you must do the following:</span></span>

- <span data-ttu-id="55f93-114">Declarar la compatibilidad con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="55f93-114">Declare compatibility with Windows 10.</span></span>

  <span data-ttu-id="55f93-115">Para ello, agregue lo siguiente al archivo de manifiesto:</span><span class="sxs-lookup"><span data-stu-id="55f93-115">To do this, add the following to your manifest file:</span></span>

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- <span data-ttu-id="55f93-116">Habilitar el reconocimiento de PPP por monitor en el *app.config* archivo.</span><span class="sxs-lookup"><span data-stu-id="55f93-116">Enable per-monitor DPI awareness in the *app.config* file.</span></span>

  <span data-ttu-id="55f93-117">Windows Forms presenta un nuevo [ `<System.Windows.Forms.ApplicationConfigurationSection>` ](../configure-apps/file-schema/winforms/index.md) elemento para admitir las nuevas características y personalizaciones agregadas a partir de .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="55f93-117">Windows Forms introduces a new [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) element to support new features and customizations added starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="55f93-118">Para aprovechar las ventajas de las nuevas características que admiten valores altos de PPP, agregue lo siguiente al archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="55f93-118">To take advantage of the new features that support high DPI, add the following to your application configuration file.</span></span>

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>
  ```

  > [!IMPORTANT]
  > <span data-ttu-id="55f93-119">En versiones anteriores de .NET Framework, ha utilizado el manifiesto para agregar compatibilidad con PPP elevado.</span><span class="sxs-lookup"><span data-stu-id="55f93-119">In previous versions of the .NET Framework, you used the manifest to add high DPI support.</span></span> <span data-ttu-id="55f93-120">Ya no se recomienda este enfoque, ya que reemplaza la configuración definida en el archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="55f93-120">This approach is no longer recommended, since it overrides settings defined on the app.config file.</span></span>

- <span data-ttu-id="55f93-121">Llamar a estático <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> método.</span><span class="sxs-lookup"><span data-stu-id="55f93-121">Call the static <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>

  <span data-ttu-id="55f93-122">Debe ser la primera llamada al método en el punto de entrada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="55f93-122">This should be the first method call in your application entry point.</span></span> <span data-ttu-id="55f93-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="55f93-123">For example:</span></span>

  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a><span data-ttu-id="55f93-124">Dejar de participar en características individuales de PPP alta</span><span class="sxs-lookup"><span data-stu-id="55f93-124">Opting out of individual high DPI features</span></span>

<span data-ttu-id="55f93-125">Establecer el `DpiAwareness` valor `PerMonitorV2` habilita altos todas las características de reconocimiento de PPP compatibles con las versiones de .NET Framework a partir de .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="55f93-125">Setting the `DpiAwareness` value to `PerMonitorV2` enables all high DPI awareness features supported by .NET Framework versions starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="55f93-126">Normalmente, esto es adecuado para la mayoría de las aplicaciones de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="55f93-126">Typically, this is adequate for most Windows Forms applications.</span></span> <span data-ttu-id="55f93-127">Sin embargo, desea dejar de participar en una o varias características individuales.</span><span class="sxs-lookup"><span data-stu-id="55f93-127">However, you may want to opt out of one or more individual features.</span></span> <span data-ttu-id="55f93-128">La razón para hacerlo más importante es que el código de aplicación existente ya controla esa característica.</span><span class="sxs-lookup"><span data-stu-id="55f93-128">The most important reason for doing this is that your existing application code already handles that feature.</span></span>  <span data-ttu-id="55f93-129">Por ejemplo, si la aplicación controla el escalado automático, es posible que desea deshabilitar la característica cambiar automáticamente el tamaño como sigue:</span><span class="sxs-lookup"><span data-stu-id="55f93-129">For example, if your application handles auto scaling, you might want to disable the auto-resizing feature as follows:</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

<span data-ttu-id="55f93-130">Para obtener una lista de las claves individuales y sus valores, vea [elemento de configuración agregar Windows Forms](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span><span class="sxs-lookup"><span data-stu-id="55f93-130">For a list of individual keys and their values, see [Windows Forms Add Configuration Element](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span></span>

## <a name="new-dpi-change-events"></a><span data-ttu-id="55f93-131">Nuevos eventos de cambio de PPP</span><span class="sxs-lookup"><span data-stu-id="55f93-131">New DPI change events</span></span>

<span data-ttu-id="55f93-132">A partir de .NET Framework 4.7, tres nuevos eventos le permiten controlar mediante programación los cambios de PPP dinámicos:</span><span class="sxs-lookup"><span data-stu-id="55f93-132">Starting with the .NET Framework 4.7, three new events allow you to programmatically handle dynamic DPI changes:</span></span>

- <span data-ttu-id="55f93-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, que se desencadena cuando se ha producido el formulario o cambia la configuración de PPP para un control mediante programación después de un evento de cambio de PPP para su control primario.</span><span class="sxs-lookup"><span data-stu-id="55f93-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, which is fired when the DPI setting for a control is changed programmatically after a DPI change event for it's parent control or form has occurred.</span></span>
- <span data-ttu-id="55f93-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, que se desencadena cuando se ha producido el formulario o cambia la configuración de PPP para un control mediante programación antes de un evento de cambio de PPP para su control principal.</span><span class="sxs-lookup"><span data-stu-id="55f93-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, which is fired when the DPI setting for a control is changed programmatically before a DPI change event for its parent control or form has occurred.</span></span>
- <span data-ttu-id="55f93-135"><xref:System.Windows.Forms.Form.DpiChanged>, que se desencadena cuando cambia el valor de PPP de la pantalla donde se muestra actualmente el formulario.</span><span class="sxs-lookup"><span data-stu-id="55f93-135"><xref:System.Windows.Forms.Form.DpiChanged>, which is fired when the DPI setting changes on the display device where the form is currently displayed.</span></span>

## <a name="new-helper-methods-and-properties"></a><span data-ttu-id="55f93-136">Las propiedades y los nuevos métodos auxiliares</span><span class="sxs-lookup"><span data-stu-id="55f93-136">New helper methods and properties</span></span>

<span data-ttu-id="55f93-137">.NET Framework 4.7 también agrega un número de propiedades que proporcionan información sobre la escala de PPP y permiten realizar el ajuste de PPP y nuevos métodos auxiliares.</span><span class="sxs-lookup"><span data-stu-id="55f93-137">The .NET Framework 4.7 also adds a number of new helper methods and properties that provide information about DPI scaling and allow you to perform DPI scaling.</span></span> <span data-ttu-id="55f93-138">Se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="55f93-138">These include:</span></span>

- <span data-ttu-id="55f93-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, que convierte un valor de coordenadas lógicas en píxeles del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="55f93-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, which converts a value from logical to device pixels.</span></span>

- <span data-ttu-id="55f93-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, que escala una imagen de mapa de bits para el valor de PPP lógico para un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="55f93-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, which scales a bitmap image to the logical DPI for a device.</span></span>

- <span data-ttu-id="55f93-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, que devuelve el valor de PPP para el dispositivo actual.</span><span class="sxs-lookup"><span data-stu-id="55f93-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, which returns the DPI for the current device.</span></span>

## <a name="versioning-considerations"></a><span data-ttu-id="55f93-142">Consideraciones de control de versiones</span><span class="sxs-lookup"><span data-stu-id="55f93-142">Versioning considerations</span></span>

<span data-ttu-id="55f93-143">Además de que se ejecutan en .NET Framework 4.7 y Windows 10 Creators Update, también puede ejecutar la aplicación en un entorno en el que no es compatible con las mejoras de PPP alta.</span><span class="sxs-lookup"><span data-stu-id="55f93-143">In addition to running on .NET Framework 4.7 and Windows 10 Creators Update, your application may also run in an environment in which it isn't compatible with high DPI improvements.</span></span> <span data-ttu-id="55f93-144">En este caso, necesitará desarrollar una reserva para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="55f93-144">In this case, you'll need to develop a fallback for your application.</span></span> <span data-ttu-id="55f93-145">Puede hacerlo para realizar [dibujo personalizado](./controls/user-drawn-controls.md) para controlar el escalado.</span><span class="sxs-lookup"><span data-stu-id="55f93-145">You can do this to perform [custom drawing](./controls/user-drawn-controls.md) to handle scaling.</span></span>

<span data-ttu-id="55f93-146">Para ello, también deberá determinar el sistema operativo en el que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="55f93-146">To do this, you also need to determine the operating system on which your app is running.</span></span> <span data-ttu-id="55f93-147">Puede hacerlo con código similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="55f93-147">You can do that with code like the following:</span></span>

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

<span data-ttu-id="55f93-148">Tenga en cuenta que la aplicación no detecte correctamente Windows 10 si no aparece como un sistema operativo compatible en el manifiesto de aplicación.</span><span class="sxs-lookup"><span data-stu-id="55f93-148">Note that your application won't successfully detect Windows 10 if it wasn't listed as a supported operating system in the application manifest.</span></span>

<span data-ttu-id="55f93-149">También puede comprobar la versión de .NET Framework que se compiló la aplicación:</span><span class="sxs-lookup"><span data-stu-id="55f93-149">You can also check the version of the .NET Framework that the application was built against:</span></span>

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a><span data-ttu-id="55f93-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="55f93-150">See also</span></span>

- [<span data-ttu-id="55f93-151">Windows Forms Agregar elemento de configuración</span><span class="sxs-lookup"><span data-stu-id="55f93-151">Windows Forms Add Configuration Element</span></span>](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [<span data-ttu-id="55f93-152">Ajustar el tamaño y la escala de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="55f93-152">Adjusting the Size and Scale of Windows Forms</span></span>](adjusting-the-size-and-scale-of-windows-forms.md)
