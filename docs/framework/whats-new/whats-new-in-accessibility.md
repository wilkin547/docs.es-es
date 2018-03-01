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
ms.openlocfilehash: e6a6759ae285f2dd101bddf71ea8e5ca792e87df
ms.sourcegitcommit: 957c696f25e39f923a827fc3ad5e8ab72768838c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2018
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>Novedades de accesibilidad en .NET Framework

.NET Framework aspira a que las aplicaciones sean más accesibles para los usuarios. Las características de accesibilidad permiten que una aplicación proporcione una experiencia adecuada para los usuarios de la tecnología de asistencia. A partir de .NET Framework 4.7.1, .NET Framework incluye muchas mejoras de accesibilidad que permiten a los desarrolladores crear aplicaciones accesibles. 

Las nuevas características de accesibilidad están habilitadas de forma predeterminada para las aplicaciones para .NET Framework 4.7.1 o posterior. Además, las aplicaciones para versiones anteriores de .NET Framework que se ejecutan en .NET Framework 4.7.1 o posterior pueden anular los comportamientos de accesibilidad heredados (y, por tanto, usar las mejoras de accesibilidad de .NET Framework 4.7.1) al agregar el siguiente modificador al elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) de la sección [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del archivo de configuración de la aplicación. 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

Del mismo modo, las aplicaciones para versiones de .NET Framework a partir de la 4.7.1 pueden deshabilitar las características de accesibilidad al agregar el siguiente modificador al elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) en la sección [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del archivo de configuración de la aplicación. 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a>Novedades de accesibilidad en .NET Framework 4.7.1

.NET Framework 4.7.1 incluye nuevas características de accesibilidad en las áreas siguientes:

- [Windows Presentation Foundation (WPF)](#windows-presentation-foundation-wpf)

- [Windows Forms](#windows-forms-accessibility-improvements)

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Mejoras del lector de pantalla**

Si las mejoras de accesibilidad están habilitadas, .NET Framework 4.7.1 incluye las siguientes mejoras que afectan a los lectores de pantalla:

- En .NET Framework 4.7 y versiones anteriores, los lectores de pantalla anunciaban los controles <xref:System.Windows.Controls.Expander> como botones. A partir de .NET Framework 4.7.1, se anuncian correctamente como grupos que se pueden contraer y expandir.

- En .NET Framework 4.7 y versiones anteriores, los lectores de pantalla anunciaban los controles <xref:System.Windows.Controls.DataGridCell> como "personalizados". A partir de .NET Framework 4.7.1, se anuncian correctamente como celdas de cuadrícula de datos (localizadas).
 
- A partir de .NET Framework 4.7.1, los lectores de pantalla anuncian el nombre de un <xref:System.Windows.Controls.ComboBox> editable.

- En .NET Framework 4.7 y versiones anteriores, los controles <xref:System.Windows.Controls.PasswordBox> se anunciaban como "no hay elemento a la vista" o tenían un comportamiento incorrecto. Este problema se corrigió a partir de .NET Framework 4.7.1.     

**Compatibilidad con las regiones activas de UIAutomation**

Los lectores de pantalla como Narrador ayudan a los usuarios a leer el contenido de la interfaz de usuario de una aplicación, normalmente mediante salida de texto a voz del contenido de la interfaz de usuario que tiene el foco. Pero si un elemento de la interfaz de usuario cambia y no tiene el foco, puede que no se notifique al usuario y este pierda información importante. Las regiones activas aspiran a resolver este problema. Un desarrollador puede usarlas para informar al lector de pantalla o a cualquier otro cliente de UIAutomation de que se ha realizado un cambio importante en un elemento de la interfaz de usuario. Luego el lector de pantalla puede decidir cómo y cuándo informar al usuario de este cambio. 

Para admitir las regiones activas, se han agregado las siguientes API a WPF:

- Los campos <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> y <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>, que identifican a la propiedad **LiveSetting** y al evento **LiveRegionChanged**. Se pueden establecer mediante XAML.

- La propiedad adjunta **AutomationProperties.LiveSetting**, que informa al lector de pantalla de la importancia del cambio de la interfaz de usuario para el usuario.

- La propiedad <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>, que identifica a la propiedad adjunta **AutomationProperties.LiveSetting**.
 
- El método <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>, que se puede invalidar para proporcionar un valor **LiveSetting**.

- Los métodos <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> y <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>, que obtienen y establecen un valor **LiveSetting**.
 
- La enumeración <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>, que define los siguientes posibles valores **LiveSetting**:

   - <xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>. El elemento no envía notificaciones si ha cambiado el contenido de la región activa.   
   - <xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>. El elemento envía notificaciones que no interrumpen el trabajo si ha cambiado el contenido de la región activa.   

  - <xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>. El elemento envía notificaciones que interrumpen el trabajo si ha cambiado el contenido de la región activa.   

Puede crear una región activa si establece la propiedad **AutomationProperties.LiveSetting** en el elemento de interés, como se muestra en el ejemplo siguiente:   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

Cuando cambian los datos de la región activa y necesita informar a un lector de pantalla, puede generar un evento de forma explícita, como se muestra en el ejemplo siguiente.

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

**Contraste alto**

A partir de .NET Framework 4.7.1, se han realizado mejoras de contraste alto en diversos controles de WPF. Ahora son visibles cuando el tema <xref:System.Windows.SystemParameters.HighContrast%2A> está establecido. Se incluyen los siguientes:

- Control <xref:System.Windows.Controls.Expander>

    El objeto visual de foco del control <xref:System.Windows.Controls.Expander> ahora es visible. Los objetos visuales de teclado de los controles <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.RadioButton> también son visibles. Por ejemplo:

    Antes: 
    
    ![Control de expansor con foco antes de las mejoras de accesibilidad](media/expander-before.png)

    Después: 

    ![Control de expansor con foco después de las mejoras de accesibilidad](media/expander-after.png)

- Controles <xref:System.Windows.Controls.CheckBox> y <xref:System.Windows.Controls.RadioButton>
 
    El texto de los controles <xref:System.Windows.Controls.CheckBox> y <xref:System.Windows.Controls.RadioButton> ahora es más fácil de ver cuando se selecciona en los temas de contraste alto. Por ejemplo:

    Antes: 

    ![Botón de opción de contraste alto con foco antes de las mejoras de accesibilidad](media/radio-button-before.png)
    
    Después: 

    ![Botón de opción de contraste alto con foco después de las mejoras de accesibilidad](media/radio-button-after.png)

- Control <xref:System.Windows.Controls.ComboBox>
 
    A partir de .NET Framework 4.7.1, el borde de un control <xref:System.Windows.Controls.ComboBox> deshabilitado es del mismo color que el texto deshabilitado. Por ejemplo:
    
    Antes: 

     ![Borde y texto de cuadro combinado deshabilitado antes de las mejoras de accesibilidad](media/combo-disabled-before.png)

    Después:   

     ![Borde y texto de cuadro combinado deshabilitado después de las mejoras de accesibilidad](media/combo-disabled-after.png)

    Además, los botones deshabilitados y con foco usan el color de tema correcto.

    Antes:

    ![Colores de tema de botón antes de las mejoras de accesibilidad](media/button-themes-before.png) 
    
    Después: 

    ![Colores de tema de botón después de las mejoras de accesibilidad](media/button-themes-after.png) 

    Por último, en .NET Framework 4.7 y versiones anteriores, al establecer el estilo de un control <xref:System.Windows.Controls.ComboBox> en `Toolbar.ComboBoxStyleKey`, la flecha de lista desplegable se hacía invisible. Este problema se corrigió a partir de .NET Framework 4.7.1. Por ejemplo:

    Antes: 

    ![Toolbar.ComboBoxStyleKey antes de las mejoras de accesibilidad](media/comboboxstylekey-before.png) 
    
    Después: 

    ![Toolbar.ComboBoxStyleKey después de las mejoras de accesibilidad](media/comboboxstylekey-after.png) 

- Control <xref:System.Windows.Controls.DataGrid>

    A partir de .NET Framework 4.7.1, la flecha de indicador de orden de los controles <xref:System.Windows.Controls.DataGrid> usa los colores de tema correctos. Por ejemplo:

    Antes: 

    ![Flecha de indicador de orden antes de las mejoras de accesibilidad](media/sort-indicator-before.png) 
    
    Después:   
 
    ![Flecha de indicador de orden después de las mejoras de accesibilidad](media/sort-indicator-after.png) 
    
    Además, en .NET Framework 4.7 y versiones anteriores, el estilo de vínculo predeterminado cambiaba a un color incorrecto cuando se colocaba el mouse encima en los modos de contraste alto. Esto se ha resuelto a partir de .NET Framework 4.7.1. Del mismo modo, a partir de .NET Framework 4.7.1, las columnas de casilla <xref:System.Windows.Controls.DataGrid> usan los colores esperados para comentarios de foco de teclado.

    Antes: 

    ![Estilo de vínculo predeterminado de cuadrícula de datos antes de las mejoras de accesibilidad](media/default-link-style-before.png) 
 
    Después:    
  
    ![Estilo de vínculo predeterminado de cuadrícula de datos después de las mejoras de accesibilidad](media/default-link-style-after.png)  

Para más información sobre las mejoras de accesibilidad de WPF en .NET Framework 4.7.1, vea [Mejoras de accesibilidad en WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).

## <a name="windows-forms-accessibility-improvements"></a>Mejoras de accesibilidad de Windows Forms

En .NET Framework 4.7.1, Windows Forms (WinForms) incluye cambios de accesibilidad en las áreas siguientes.

**Visualización mejorada en modo de contraste alto**

A partir de .NET Framework 4.7.1, varios controles de WinForms ofrecen una representación mejorada en los modos de contraste alto disponibles en el sistema operativo. Windows 10 ha cambiado los valores de algunos colores del sistema de contraste alto y Windows Forms se basa en el marco de trabajo de Windows 10 Win32. Para obtener la mejor experiencia, trabaje en la versión más reciente de Windows y use los cambios más recientes del sistema operativo al agregar un archivo app.manifest en una aplicación de prueba y quitar los comentarios de la línea del sistema operativo compatible con Windows 10 para tenga este aspecto:

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
Algunos ejemplos de cambios de contraste alto:

- Las marcas de verificación de los elementos <xref:System.Windows.Forms.MenuStrip> son más fáciles de ver.

- Cuando se activan, los elementos <xref:System.Windows.Forms.MenuStrip> deshabilitados son más fáciles de ver.

- El texto de un control <xref:System.Windows.Forms.Button> seleccionado contrasta con el color de selección.

- El texto deshabilitado es más fácil de leer. Por ejemplo:

    Antes:

    ![Texto deshabilitado antes de las mejoras de accesibilidad](media/wf-disabled-before.png) 

    Después:

    ![Texto deshabilitado después de las mejoras de accesibilidad](media/wf-disabled-after.png) 

- Mejoras de contraste alto en el cuadro de diálogo de excepción de subproceso.

**Compatibilidad mejorada con Narrador**

Windows Forms en .NET Framework 4.7.1 incluye las siguientes mejoras de accesibilidad para Narrador:

- Narrador, así como otras herramientas de automatización de la interfaz de usuario, pueden acceder al control <xref:System.Windows.Forms.MonthCalendar>.

- El control <xref:System.Windows.Forms.CheckedListBox> avisa a Narrador cuando ha cambiado el estado de activación de un elemento para que el usuario sepa que ha cambiado el valor de un elemento de lista.
 
- El control <xref:System.Windows.Forms.DataGridViewCell> notifica el estado correcto de solo lectura a Narrador.
 
- Narrador ahora puede leer texto <xref:System.Windows.Forms.ToolStripMenuItem> deshabilitado, mientras que anteriormente omitía los elementos de menú deshabilitados.

**Compatibilidad mejorada con los patrones de accesibilidad de UIAutomation**

A partir de .NET Framework 4.7.1, los desarrolladores de herramientas de tecnología de accesibilidad pueden aprovechar los patrones comunes de accesibilidad de API y las propiedades de varios controles de WinForms. Estas mejoras de accesibilidad incluyen:

- <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.ToolStripSplitButton> ahora son compatibles con el [patrón de expansión o contracción](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).
 
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell> ahora es compatible con el [patrón de alternancia](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).
 
- El control <xref:System.Windows.Forms.ToolStripItem> admite la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> y el [patrón de expansión o contracción](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).

- Los controles <xref:System.Windows.Forms.NumericUpDown> y <xref:System.Windows.Forms.DomainUpDown> admiten la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>.

**Experiencia mejorada del explorador de propiedades**

A partir de .NET Framework 4.7.1, Windows Forms incluye:

- Una mejor navegación mediante teclado gracias a las distintas ventanas de selección desplegables.
- Una reducción de puntos de tabulación innecesarios.
- Mejor notificación de tipos de control.
- Comportamiento mejorado de Narrador.
 
## <a name="see-also"></a>Vea también
[Novedades de .NET Framework](whats-new.md)   
 