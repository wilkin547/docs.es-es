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
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>Novedades de accesibilidad en .NET Framework

.NET Framework tiene como objetivo en hacer que las aplicaciones más accesible para los usuarios. Características de accesibilidad permiten que una aplicación proporcionar una experiencia adecuada para los usuarios de tecnología de asistencia. A partir de .NET Framework 4.7.1, .NET Framework incluye un gran número de mejoras de accesibilidad que permiten a los desarrolladores crear aplicaciones accesibles. 

Las nuevas características de accesibilidad están habilitados de forma predeterminada para las aplicaciones que tienen como destino .NET Framework 4.7.1 o posterior. Además, las aplicaciones que una versión anterior de .NET Framework de destino, pero se ejecutan en .NET Framework 4.7.1 o posterior pueden optar por fuera de los comportamientos de accesibilidad heredado (y, por tanto, participar en las mejoras de accesibilidad en .NET Framework 4.7.1) por agregar el siguiente modificador a la [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento en el [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) sección del archivo de configuración de la aplicación. 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

De forma similar, las aplicaciones destinadas a versiones de .NET Framework a partir de 4.7.1 pueden deshabilitar las características de accesibilidad agregando el siguiente cambio a la [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento en el [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) sección del archivo de configuración de la aplicación. 

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

**Mejoras de lector de pantalla**

Si están habilitadas las mejoras de accesibilidad, .NET Framework 4.7.1 incluye las siguientes mejoras que afectan a los lectores de pantalla:

- 4.7 de .NET Framework y versiones anteriores, <xref:System.Windows.Controls.Expander> se anunciaron controles como botones que los lectores de pantalla. A partir de .NET Framework 4.7.1, que están correctamente anuncien como grupos expandible.

- 4.7 de .NET Framework y versiones anteriores, <xref:System.Windows.Controls.DataGridCell> controles se anuncian por los lectores de pantalla como "custom". A partir de .NET Framework 4.7.1, que son ahora correctamente anuncien como celda de cuadrícula de datos (localizada).
 
- A partir de .NET Framework 4.7.1, los lectores de pantalla anuncian el nombre de un editable <xref:System.Windows.Controls.ComboBox>.

- 4.7 de .NET Framework y versiones anteriores, <xref:System.Windows.Controls.PasswordBox> controles se anuncia como "ningún elemento en la vista" o tenía un comportamiento incorrecto en caso contrario. Este problema se corrigió a partir de .NET Framework 4.7.1.     

**Compatibilidad de UIAutomation LiveRegion**

Los lectores de pantalla como personas de la Ayuda de Narrador leen el contenido de la interfaz de usuario de una aplicación, normalmente salida de texto a voz del contenido de la interfaz de usuario que tiene el foco. Sin embargo, si un elemento de interfaz de usuario cambia y no tiene el foco, el usuario no puede recibir notificaciones y puede perder información importante. Las regiones en directo están destinados a resolver este problema. Un desarrollador puede utilizarlos para informar el lector de pantalla o cualquier otro cliente de UIAutomation que se ha realizado un cambio importante para un elemento de interfaz de usuario. El lector de pantalla, a continuación, puede decidir cómo y cuándo para informar al usuario de este cambio. 

Para admitir las regiones en vivo, se han agregado las siguientes API de WPF:

- El <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> y <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> campos, que identifican el **LiveSetting** propiedad y el **LiveRegionChanged** eventos. Se pueden establecer mediante el uso de XAML.

- El **AutomationProperties.LiveSetting** propiedad, que informa el lector de pantalla de la importancia del cambio de interfaz de usuario para el usuario adjunta.

- El <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> propiedad, que identifica el **AutomationProperties.LiveSetting** propiedad adjunta.
 
- El <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> método, que se puede invalidar para proporcionar un **LiveSetting** valor.

- El <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> y <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> métodos, que obtener y establecer un **LiveSetting** valor.
 
- El <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeración, que define los posibles **LiveSetting** valores:

   - <xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>. El elemento no envía notificaciones si ha cambiado el contenido de la región activa.   
   - <xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>. El elemento envía notificaciones que no interrumpen el trabajo si ha cambiado el contenido de la región activa.   

  - <xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>. El elemento envía notificaciones que interrumpen el trabajo si ha cambiado el contenido de la región activa.   

Puede crear un LiveRegion estableciendo la **AutomationProperties.LiveSetting** propiedad del elemento de interés, como se muestra en el ejemplo siguiente:   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

Cuando cambian los datos en la región activa y debe informar a un lector de pantalla, explícitamente genera un evento, como se muestra en el ejemplo siguiente.

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

**Contraste alto**

A partir de .NET Framework 4.7.1, se han realizado mejoras en contraste alto en diversos controles de WPF. Ahora son visibles cuando el <xref:System.Windows.SystemParameters.HighContrast%2A> tema esté configurado. Se incluyen los siguientes:

- Control <xref:System.Windows.Controls.Expander>

    El estilo visual de foco el <xref:System.Windows.Controls.Expander> control ahora está visible. Los objetos visuales de teclado para <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, y <xref:System.Windows.Controls.RadioButton> controles también son visibles. Por ejemplo:

    Antes: 
    
    ![Control de botón de expansión tiene el foco antes de mejoras de accesibilidad](media/expander-before.png)

    Después de: 

    ![Control de botón de expansión tiene el foco después de mejoras de accesibilidad](media/expander-after.png)

- <xref:System.Windows.Controls.CheckBox>y <xref:System.Windows.Controls.RadioButton> controles
 
    El texto en el <xref:System.Windows.Controls.CheckBox> y <xref:System.Windows.Controls.RadioButton> controles ahora es más fácil ver cuando se selecciona en los temas de contraste alto. Por ejemplo:

    Antes: 

    ![Botón de opción de contraste alto con el foco antes de mejoras de accesibilidad](media/radio-button-before.png)
    
    Después de: 

    ![Botón de opción de contraste alto con el foco después de mejoras de accesibilidad](media/radio-button-after.png)

- Control <xref:System.Windows.Controls.ComboBox>
 
    A partir de .NET Framework 4.7.1, el borde de un deshabilitado <xref:System.Windows.Controls.ComboBox> control es el mismo color que el texto deshabilitado. Por ejemplo:
    
    Antes: 

     ![Cuadro combinado deshabilitado borde y el texto antes de mejoras de accesibilidad](media/combo-disabled-before.png)

    Después de:   

     ![Cuadro combinado deshabilitado borde y el texto después de las mejoras de accesibilidad](media/combo-disabled-after.png)

    Además, los botones de deshabilitado y se centra utilizan el color del tema correcto.

    Antes:

    ![Colores del tema botón antes de mejoras de accesibilidad](media/button-themes-before.png) 
    
    Después de: 

    ![Colores del tema botón después de mejoras de accesibilidad](media/button-themes-after.png) 

    Por último, en la 4.7 de .NET Framework y versiones anteriores, establecer un <xref:System.Windows.Controls.ComboBox> estilo del control `Toolbar.ComboBoxStyleKey` provocó la flecha de lista desplegable sea invisible. Este problema se corrigió a partir de .NET Framework 4.7.1. Por ejemplo:

    Antes: 

    ![Toolbar.ComboBoxStyleKey antes de las mejoras de accesibilidad](media/comboboxstylekey-before.png) 
    
    Después de: 

    ![Toolbar.ComboBoxStyleKey después de mejoras de accesibilidad](media/comboboxstylekey-after.png) 

- Control <xref:System.Windows.Controls.DataGrid>

    A partir de .NET Framework 4.7.1, en la flecha de indicador de ordenación <xref:System.Windows.Controls.DataGrid> controla ahora usa corregir colores del tema. Por ejemplo:

    Antes: 

    ![Flecha de indicador de ordenación antes de mejoras de accesibilidad](media/sort-indicator-before.png) 
    
    Después de:   
 
    ![Flecha de indicador de ordenación después de mejoras de accesibilidad](media/sort-indicator-after.png) 
    
    Además, 4.7 de .NET Framework y versiones anteriores, el estilo de vínculo predeterminado cambia a un color incorrecto en el mouse (ratón) a lo largo de modos de contraste alto. Esto se resuelve a partir de .NET Framework 4.7.1. De forma similar, <xref:System.Windows.Controls.DataGrid> casilla columnas usa los colores esperados para comentarios de foco de teclado a partir de .NET Framework 4.7.1.

    Antes: 

    ![Estilo de vínculo predeterminado de DataGrid antes de mejoras de accesibilidad](media/default-link-style-before.png) 
 
    Después de:    
  
    ![Estilo de vínculo predeterminado de DataGrid después mejoras de accesibilidad](media/default-link-style-after.png)  

Para obtener más información sobre las mejoras de accesibilidad WPF en .NET Framework 4.7.1, consulte [mejoras de accesibilidad en WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).

## <a name="windows-forms-accessibility-improvements"></a>Mejoras de accesibilidad de formularios Windows Forms

En .NET Framework 4.7.1, formularios Windows Forms (WinForms) incluye cambios de accesibilidad en las áreas siguientes.

**Visualización mejorada en modo de contraste alto**

A partir de .NET Framework 4.7.1, varios controles de formularios Windows Forms ofrecen generación mejorada en los modos de HighContrast disponibles en el sistema operativo. 10 de Windows ha cambiado los valores para algunos colores de contraste alto del sistema y formularios Windows Forms se basa en el marco de trabajo de Windows 10 Win32. Para obtener la mejor experiencia, ejecute la versión más reciente de Windows y participar en los cambios más recientes del sistema operativo mediante la adición de que un archivo app.manifest en una aplicación de prueba y quitar el comentario de Windows 10 admite la línea de sistema operativo para que se asemeje a continuación:

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
Algunos ejemplos de cambios de contraste alto:

- Las marcas de verificación en <xref:System.Windows.Forms.MenuStrip> elementos son más fáciles de ver.

- Cuando se selecciona, deshabilitado <xref:System.Windows.Forms.MenuStrip> elementos son más fáciles de ver.

- Texto en un seleccionado <xref:System.Windows.Forms.Button> controlar contrasta con el color de selección.

- Es más fácil de leer texto deshabilitado. Por ejemplo:

    Antes:

    ![Texto deshabilitado antes de mejoras de accesibilidad](media/wf-disabled-before.png) 

    Después de:

    ![Texto deshabilitado después de mejoras de accesibilidad](media/wf-disabled-after.png) 

- Mejoras de contraste alto en el cuadro de diálogo de excepción de subproceso.

**Compatibilidad mejorada con Narrador**

Formularios Windows Forms en .NET Framework 4.7.1 incluye las siguientes mejoras de accesibilidad para el Narrador:

- El <xref:System.Windows.Forms.MonthCalendar> control puede obtenerse el Narrador, así como otras herramientas de automatización de la interfaz de usuario.

- El <xref:System.Windows.Forms.CheckedListBox> control notifica Narrador cuando ha cambiado el estado de activación de un elemento por lo que se notifica al usuario que ha cambiado el valor de un elemento de lista.
 
- El <xref:System.Windows.Forms.DataGridViewCell> control notifica el estado correcto de solo lectura para Narrador.
 
- Narrador ahora puede leer deshabilitado <xref:System.Windows.Forms.ToolStripMenuItem> texto, mientras que anteriormente omitía sobre los elementos de menú deshabilitado.

**Compatibilidad mejorada en patrones de accesibilidad de UIAutomation**

A partir de .NET Framework 4.7.1, los desarrolladores de herramientas de la tecnología de accesibilidad pueden aprovechar los patrones comunes de accesibilidad de API y las propiedades de varios controles de formularios Windows Forms. Estas mejoras de accesibilidad son:

- El <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.ToolStripSplitButton> ahora son compatibles con el [patrónExpandCollapse/](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).
 
- El <xref:System.Windows.Forms.DataGridViewCheckBoxCell> ahora es compatible con la [patrón toggle](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).
 
- El <xref:System.Windows.Forms.ToolStripItem> control admite el <xref:System.Windows.Automation.AutomationElement.Name> propiedad y el [patrónExpandCollapse/](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).

- El <xref:System.Windows.Forms.NumericUpDown> y <xref:System.Windows.Forms.DomainUpDown> controles admiten la <xref:System.Windows.Automation.automationElement.Name> propiedad.

**Experiencia de exploración de propiedades mejorada**

A partir de .NET Framework 4.7.1, formularios Windows Forms incluyen:

- Una mejor navegación de teclado a través de las distintas ventanas de selección desplegable.
- Una reducción de posiciones de tabulación innecesarios.
- Mejor generación de informes de los tipos de control.
- Comportamiento mejorado Narrador.
 
## <a name="see-also"></a>Vea también
[Novedades de .NET Framework](whats-new.md)   
 