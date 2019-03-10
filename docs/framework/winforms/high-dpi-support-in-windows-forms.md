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
ms.openlocfilehash: 3dbb5af9c5cf1d8796544592602c645584d21a04
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711809"
---
# <a name="high-dpi-support-in-windows-forms"></a>Compatibilidad con valores alto de PPP en Windows Forms

A partir de .NET Framework 4.7, Windows Forms incluye mejoras para los valores altos de PPP comunes y escenarios de PPP dinámicos. Se incluyen los siguientes: 

- Controles de mejoras en la escala y el diseño de una serie de formularios de Windows, como el <xref:System.Windows.Forms.MonthCalendar> control y el <xref:System.Windows.Forms.CheckedListBox> control. 

- Paso único ajuste de escala.  En .NET Framework 4.6 y versiones anteriores, el escalado se realizó a través de varias pasadas, lo que provocó algunos controles escalar más que era necesario.

- Compatibilidad con escenarios de PPP dinámicos en el que el usuario cambia el factor de escala o PPP después de que se ha iniciado una aplicación de Windows Forms.

En las versiones de .NET Framework a partir de .NET Framework 4.7, mayor compatibilidad con PPP elevado es una característica opcional. Debe configurar la aplicación para aprovechar sus ventajas.

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a>Configuración de la aplicación de Windows Forms para la compatibilidad con PPP elevado

Las nuevas características de Windows Forms que admiten reconocimiento de PPP alta solo están disponibles en las aplicaciones que tienen como destino .NET Framework 4.7 y que se ejecutan en sistemas operativos de Windows a partir de Windows 10 Creators Update. 

Además, para configurar la compatibilidad con PPP elevado en su aplicación de Windows Forms, debe hacer lo siguiente:

- Declarar la compatibilidad con Windows 10.

  Para ello, agregue lo siguiente al archivo de manifiesto:

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- Habilitar el reconocimiento de PPP por monitor en el *app.config* archivo.

  Windows Forms presenta un nuevo [ `<System.Windows.Forms.ApplicationConfigurationSection>` ](../configure-apps/file-schema/winforms/index.md) elemento para admitir las nuevas características y personalizaciones agregadas a partir de .NET Framework 4.7. Para aprovechar las ventajas de las nuevas características que admiten valores altos de PPP, agregue lo siguiente al archivo de configuración de la aplicación.   

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>      
  ```
   
  > [!IMPORTANT]
  > En versiones anteriores de .NET Framework, ha utilizado el manifiesto para agregar compatibilidad con PPP elevado. Ya no se recomienda este enfoque, ya que reemplaza la configuración definida en el archivo app.config.
   
- Llamar a estático <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> método.
   
  Debe ser la primera llamada al método en el punto de entrada de la aplicación. Por ejemplo:
   
  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());   
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a>Dejar de participar en características individuales de PPP alta

Establecer el `DpiAwareness` valor `PerMonitorV2` habilita altos todas las características de reconocimiento de PPP compatibles con las versiones de .NET Framework a partir de .NET Framework 4.7. Normalmente, esto es adecuado para la mayoría de las aplicaciones de Windows Forms. Sin embargo, desea dejar de participar en una o varias características individuales. La razón para hacerlo más importante es que el código de aplicación existente ya controla esa característica.  Por ejemplo, si la aplicación controla el escalado automático, es posible que desea deshabilitar la característica cambiar automáticamente el tamaño como sigue:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" /> 
</System.Windows.Forms.ApplicationConfigurationSection>    
```

Para obtener una lista de las claves individuales y sus valores, vea [elemento de configuración agregar Windows Forms](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).

## <a name="new-dpi-change-events"></a>Nuevos eventos de cambio de PPP

A partir de .NET Framework 4.7, tres nuevos eventos le permiten controlar mediante programación los cambios de PPP dinámicos:

- <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, que se desencadena cuando se ha producido el formulario o cambia la configuración de PPP para un control mediante programación después de un evento de cambio de PPP para su control primario.
- <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, que se desencadena cuando se ha producido el formulario o cambia la configuración de PPP para un control mediante programación antes de un evento de cambio de PPP para su control principal.
- <xref:System.Windows.Forms.Form.DpiChanged>, que se desencadena cuando cambia el valor de PPP de la pantalla donde se muestra actualmente el formulario.

## <a name="new-helper-methods-and-properties"></a>Las propiedades y los nuevos métodos auxiliares

.NET Framework 4.7 también agrega un número de propiedades que proporcionan información sobre la escala de PPP y permiten realizar el ajuste de PPP y nuevos métodos auxiliares. Se incluyen los siguientes:

- <xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, que convierte un valor de coordenadas lógicas en píxeles del dispositivo.

- <xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, que escala una imagen de mapa de bits para el valor de PPP lógico para un dispositivo.

- <xref:System.Windows.Forms.Control.DeviceDpi%2A>, que devuelve el valor de PPP para el dispositivo actual.

## <a name="versioning-considerations"></a>Consideraciones de control de versiones

Además de que se ejecutan en .NET Framework 4.7 y Windows 10 Creators Update, también puede ejecutar la aplicación en un entorno en el que no es compatible con las mejoras de PPP alta. En este caso, necesitará desarrollar una reserva para su aplicación. Puede hacerlo para realizar [dibujo personalizado](./controls/user-drawn-controls.md) para controlar el escalado.

Para ello, también deberá determinar el sistema operativo en el que se ejecuta la aplicación. Puede hacerlo con código similar al siguiente:

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

Tenga en cuenta que la aplicación no detecte correctamente Windows 10 si no aparece como un sistema operativo compatible en el manifiesto de aplicación.

También puede comprobar la versión de .NET Framework que se compiló la aplicación:

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a>Vea también

- [Windows Forms Agregar elemento de configuración](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [Ajustar el tamaño y la escala de Windows Forms](adjusting-the-size-and-scale-of-windows-forms.md)
