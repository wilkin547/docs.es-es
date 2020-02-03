---
title: Compatibilidad con valores altos de PPP
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
ms.openlocfilehash: a5c3125475c2de2cf83a3d97e356b26c0acdde99
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741888"
---
# <a name="high-dpi-support-in-windows-forms"></a>Compatibilidad con PPP alta en Windows Forms

A partir de la .NET Framework 4,7, Windows Forms incluye mejoras en los escenarios comunes de PPP alto y dinámicos. Entre ellas se incluyen las siguientes:

- Mejoras en el ajuste de escala y diseño de varios controles Windows Forms, como el control <xref:System.Windows.Forms.MonthCalendar> y el control <xref:System.Windows.Forms.CheckedListBox>.

- Ajuste de escala de un solo paso.  En el .NET Framework 4,6 y versiones anteriores, el escalado se realizaba a través de varias fases, lo que hacía que algunos controles se escalaran más de lo necesario.

- Compatibilidad con escenarios de PPP dinámicos en los que el usuario cambia los PPP o el factor de escala una vez que se ha iniciado una aplicación Windows Forms.

En las versiones de la .NET Framework a partir del .NET Framework 4,7, la compatibilidad mejorada con PPP alta es una característica opcional. Debe configurar la aplicación para aprovecharla.

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a>Configuración de la aplicación de Windows Forms para la compatibilidad con alta resolución de PPP

Las nuevas características Windows Forms que admiten el reconocimiento de PPP alto solo están disponibles en las aplicaciones que tienen como destino el .NET Framework 4,7 y que se ejecutan en sistemas operativos Windows a partir de Windows 10 Creators Update.

Además, para configurar la compatibilidad con alta PPP en la aplicación Windows Forms, debe hacer lo siguiente:

- Declare la compatibilidad con Windows 10.

  Para ello, agregue lo siguiente al archivo de manifiesto:

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- Habilite el reconocimiento de PPP por monitor en el archivo *app. config* .

  Windows Forms introduce un nuevo elemento [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) para admitir nuevas características y personalizaciones agregadas a partir de la .NET Framework 4,7. Agregue lo siguiente al archivo de configuración de la aplicación para aprovechar las nuevas características que admiten un máximo de PPP.

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>
  ```

  > [!IMPORTANT]
  > En las versiones anteriores de la .NET Framework, se usaba el manifiesto para agregar compatibilidad con PPP alta. Ya no se recomienda este enfoque, ya que reemplaza los valores definidos en el archivo app. config.

- Llame al método estático <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.

  Debe ser la primera llamada al método en el punto de entrada de la aplicación. Por ejemplo:

  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a>No participar en las características de PPP altas individuales

Al establecer el valor de `DpiAwareness` en `PerMonitorV2`, se habilitan todas las características de reconocimiento de PPP altas compatibles con las versiones de .NET Framework a partir del .NET Framework 4,7. Normalmente, esto es adecuado para la mayoría de las aplicaciones Windows Forms. Sin embargo, es posible que desee no participar en una o varias características individuales. La razón más importante para hacerlo es que el código de aplicación existente ya controla esa característica.  Por ejemplo, si la aplicación controla el escalado automático, puede que desee deshabilitar la característica de cambio de tamaño automático de la manera siguiente:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

Para obtener una lista de claves individuales y sus valores, vea [Windows Forms Agregar elemento de configuración](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).

## <a name="new-dpi-change-events"></a>Nuevos eventos de cambio de PPP

A partir de la .NET Framework 4,7, tres nuevos eventos le permiten controlar mediante programación los cambios de PPP dinámicos:

- <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, que se desencadena cuando se cambia mediante programación el valor de PPP para un control después de que se haya producido un evento de cambio de PPP para su control o formulario primario.
- <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, que se desencadena cuando se cambia la configuración de PPP para un control mediante programación antes de que se produzca un evento de cambio de PPP para su control o formulario primario.
- <xref:System.Windows.Forms.Form.DpiChanged>, que se desencadena cuando cambia el valor de PPP en el dispositivo de pantalla donde se muestra actualmente el formulario.

## <a name="new-helper-methods-and-properties"></a>Nuevas propiedades y métodos auxiliares

El .NET Framework 4,7 también agrega una serie de nuevas propiedades y métodos auxiliares que proporcionan información sobre el ajuste de escala de PPP y permiten realizar el ajuste de escala de PPP. Entre ellas se incluyen las siguientes:

- <xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, que convierte un valor de los píxeles lógicos a los de dispositivo.

- <xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, que escala una imagen de mapa de bits al ppp lógico para un dispositivo.

- <xref:System.Windows.Forms.Control.DeviceDpi%2A>, que devuelve el PPP del dispositivo actual.

## <a name="versioning-considerations"></a>Consideraciones sobre el control de versiones

Además de ejecutarse en .NET Framework 4,7 y Windows 10 Creators Update, la aplicación también puede ejecutarse en un entorno en el que no sea compatible con las mejoras de PPP altas. En este caso, deberá desarrollar una reserva para la aplicación. Puede hacer esto para realizar un [dibujo personalizado](./controls/user-drawn-controls.md) con el fin de controlar el escalado.

Para ello, también debe determinar el sistema operativo en el que se ejecuta la aplicación. Puede hacerlo con código como el siguiente:

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

Tenga en cuenta que la aplicación no detectará correctamente Windows 10 si no aparece como un sistema operativo compatible en el manifiesto de aplicación.

También puede comprobar la versión de la .NET Framework en la que se compiló la aplicación:

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a>Consulte también

- [Windows Forms Agregar elemento de configuración](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [Ajustar el tamaño y la escala de Windows Forms](adjusting-the-size-and-scale-of-windows-forms.md)
