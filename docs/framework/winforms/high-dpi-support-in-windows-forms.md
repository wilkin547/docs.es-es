---
title: Compatibilidad con alta de PPP en Windows Forms
ms.custom: 
ms.date: 05/16/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a68c9278d4e8092be5c744109e56f7cb52498095
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="high-dpi-support-in-windows-forms"></a>Compatibilidad con alta de PPP en Windows Forms

A partir de la 4.7 de .NET Framework, Windows Forms incluye mejoras para una resolución alta comunes y escenarios de PPP dinámicos. Se incluyen los siguientes: 

- Mejoras en el ajuste de escala y el diseño de una serie de formularios Windows Forms controles, como el <xref:System.Windows.Forms.MonthCalendar> control y el <xref:System.Windows.Forms.CheckedListBox> control. 

- Paso único ajuste de escala.  En .NET Framework 4.6 y versiones anteriores, el ajuste de escala se realizó a través de varios supera, lo que provocó algunos controles escalar más que era necesario.

- Compatibilidad con escenarios de PPP dinámicos en el que el usuario cambia el factor de escala o PPP después de que se ha iniciado una aplicación de formularios Windows Forms.

En las versiones de .NET Framework a partir de la 4.7 de .NET Framework, compatibilidad mejorada de PPP alta es una característica opcional. Debe configurar la aplicación para aprovechar las ventajas del mismo.

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a>Configuración de la aplicación de formularios Windows Forms para compatibilidad con alta de PPP

Las nuevas características de Windows Forms que admiten reconocimiento de PPP alta solo están disponibles en las aplicaciones destinadas a la 4.7 de .NET Framework y se ejecutan en sistemas operativos de Windows a partir de la actualización de los creadores de Windows 10. 

Además, para configurar la compatibilidad con alta de PPP en la aplicación de formularios Windows Forms, debe hacer lo siguiente:

- Declarar la compatibilidad con Windows 10.

  Para ello, agregue lo siguiente al archivo de manifiesto:

  ```xml
  <compatibility xmlns="urn:schemas-microsoft.comn:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- Habilitar el reconocimiento de PPP del monitor en el *app.config* archivo.

  Introduce un nuevo Windows Forms [ `<System.Windows.Forms.ApplicationConfigurationSection>` ](../../../docs/framework/configure-apps/file-schema/winforms/index.md) elemento para admitir nuevas características y las personalizaciones que agregado a partir de la 4.7 de .NET Framework. Para aprovechar las ventajas de las nuevas características que admiten valores altos de PPP, agregue lo siguiente al archivo de configuración de la aplicación.   

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>      
  ```
   
  > [!IMPORTANT]
  > En versiones anteriores de .NET Framework, se usa el manifiesto para agregar compatibilidad con alta de PPP. Ya no se recomienda este enfoque, ya que reemplaza la configuración definida en el archivo app.config.
   
- Llame el método estático <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> método.
   
  Debe ser la primera llamada de método en el punto de entrada de la aplicación. Por ejemplo:
   
  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());   
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a>No participar en de características individuales de PPP alta

Establecer el `DpiAwareness` valor `PerMonitorV2` permite altos todas las características de reconocimiento de PPP compatibles con versiones de .NET Framework a partir de la 4.7 de .NET Framework. Normalmente, esto es adecuado para la mayoría de las aplicaciones de Windows Forms. Sin embargo, puede que desee para no participar en una o más características individuales. La razón más importante para hacer esto es que el código de aplicación existente ya controla esa característica.  Por ejemplo, si la aplicación controla el escalado automático, puede deshabilitar la característica cambiar automáticamente el tamaño como sigue:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" /> 
</System.Windows.Forms.ApplicationConfigurationSection>    
```

Para obtener una lista de las claves individuales y sus valores, vea [elemento de configuración Add de Windows Forms](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).

## <a name="new-dpi-change-events"></a>Nuevos eventos de cambio de PPP

A partir de la 4.7 de .NET Framework, tres nuevos eventos le permiten controlar mediante programación los cambios dinámicos de PPP:

- <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, que se desencadena cuando el valor de PPP para un control se cambia mediante programación después de un evento de cambio de PPP para su control primario o se ha producido el formulario.
- <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, que se desencadena cuando el valor de PPP para un control se cambia mediante programación antes de un evento de cambio de PPP para su control primario o se ha producido el formulario.
- <xref:System.Windows.Forms.Form.DpiChanged>, que se desencadena cuando cambia el valor de PPP en el dispositivo de pantalla que actualmente se muestra el formulario.

## <a name="new-helper-methods-and-properties"></a>Propiedades y métodos auxiliares nueva

El 4.7 de .NET Framework también agrega una serie de nuevos métodos auxiliares y propiedades que proporcionan información sobre la escala de PPP y permiten realizar el ajuste de escala de PPP. Se incluyen los siguientes:

- <xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, que convierte un valor de coordenadas lógicas en píxeles del dispositivo.

- <xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, que amplía una imagen de mapa de bits para el valor de PPP lógico para un dispositivo.

- <xref:System.Windows.Forms.Control.DeviceDpi%2A>, que devuelve el valor de PPP para el dispositivo actual.

## <a name="versioning-considerations"></a>Consideraciones de control de versiones

Además de ejecutar en .NET Framework 4.7 y creadores de actualización de Windows 10, la aplicación también puede ejecutarse en un entorno en el que no es compatible con mejoras de PPP alta. En este caso, necesitará desarrollar una reserva para la aplicación. Puede hacerlo para realizar [dibujo personalizado](./controls/user-drawn-controls.md) para controlar el ajuste de escala.

Para ello, también debe determinar el sistema operativo en el que se ejecuta la aplicación. Puede hacerlo mediante código similar al siguiente:

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

Tenga en cuenta que la aplicación no detecte correctamente 10 de Windows si no se muestran como un sistema operativo compatible en el manifiesto de aplicación.

También puede comprobar la versión de .NET Framework que se compiló la aplicación:

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a>Vea también

[Formularios Windows Forms Agregar elemento de configuración](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)  
[Ajustar el tamaño y la escala de Windows Forms](../../../docs/framework/winforms/adjusting-the-size-and-scale-of-windows-forms.md)
