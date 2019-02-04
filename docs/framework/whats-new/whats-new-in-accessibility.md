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
ms.openlocfilehash: 092b1cfc9350ea398eb18199f19a8eee7ea9f218
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675444"
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>Novedades de accesibilidad en .NET Framework

.NET Framework aspira a que las aplicaciones sean más accesibles para los usuarios. Las características de accesibilidad permiten que una aplicación proporcione una experiencia adecuada para los usuarios de la tecnología de asistencia. A partir de .NET Framework 4.7.1, .NET Framework incluye muchas mejoras de accesibilidad que permiten a los desarrolladores crear aplicaciones accesibles. 

## <a name="accessibility-switches"></a>Modificadores de accesibilidad

Puede configurar la aplicación para que opte por recibir características de accesibilidad si su destino es .NET Framework 4.7 o una versión anterior, pero se ejecuta en .NET Framework 4.7.1 o una versión posterior. También la puede configurar para que use características heredadas (en vez de aprovechar las ventajas de las características de accesibilidad) si su destino es .NET Framework 4.7.1 o una versión posterior. Cada versión de .NET Framework que incluya características de accesibilidad cuenta con un modificador de accesibilidad específico de la versión correspondiente, que se agrega al elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) en la sección [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del archivo de configuración de la aplicación. Estos son los modificadores admitidos:

|Versión|Modificador|
|---|---|
|.NET Framework 4.7.1|"Switch.UseLegacyAccessibilityFeatures"|
|.NET Framework 4.7.2|"Switch.UseLegacyAccessibilityFeatures.2"|

### <a name="taking-advantage-of-accessibility-enhancements"></a>Aprovechar las mejoras de accesibilidad

Las nuevas características de accesibilidad están habilitadas de forma predeterminada para las aplicaciones para .NET Framework 4.7.1 o posterior. Además, las aplicaciones para versiones anteriores de .NET Framework que se ejecutan en .NET Framework 4.7.1 o posterior pueden optar por no recibir comportamientos de accesibilidad heredados (y, por tanto, usar las mejoras de accesibilidad correspondientes) si se agregan modificadores al elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) de la sección [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del archivo de configuración de la aplicación y sus valores se establecen en `false`. El siguiente código muestra cómo optar por recibir las mejoras de accesibilidad incluidas en .NET Framework 4.7.1:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

Si decide optar por recibir las características de accesibilidad en una versión posterior de .NET Framework, deberá optar por recibir también las características de versiones anteriores de .NET Framework. Para configurar la aplicación para que use las mejoras de accesibilidad de .NET Framework 4.7.1 y 4.7.2, se necesita el siguiente elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

### <a name="restoring-legacy-behavior"></a>Restaurar el comportamiento heredado

Las aplicaciones para versiones de .NET Framework a partir de la 4.7.1 pueden deshabilitar las características de accesibilidad; para ello, hay que agregar modificadores al elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) en la sección [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) del archivo de configuración de la aplicación y establecer sus valores en `true`. Por ejemplo, la siguiente configuración opta por no recibir las características de accesibilidad incluidas en .NET Framework 4.7.2:  

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-472"></a>Novedades de accesibilidad en .NET Framework 4.7.2

.NET Framework 4.7.2 incluye nuevas características de accesibilidad en las siguientes áreas:

- [Windows Forms](#winforms472)

- [Windows Presentation Foundation (WPF)](#wpf472)

<a name="winforms472"></a>
### <a name="windows-forms"></a>Windows Forms

**Colores definidos por el sistema operativo en los temas de contraste alto**

A partir de .NET Framework 4.7.2, Windows Forms usa colores definidos por el sistema operativo en los temas de contraste alto. Esto afecta a los siguientes controles:

- La flecha desplegable del control <xref:System.Windows.Forms.ToolStripDropDownButton>.

- Los controles <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> y <xref:System.Windows.Forms.CheckBox> que tienen <xref:System.Windows.Forms.ButtonBase.FlatStyle> establecido en <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> o en <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>. Antes, los colores de fondo y de texto seleccionados no tenían contraste y eran difíciles de leer.

- Controles contenidos en un <xref:System.Windows.Forms.GroupBox> que tiene su propiedad <xref:System.Windows.Forms.Control.Enabled> establecida en `false`.
 
- Los controles <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox> y <xref:System.Windows.Forms.ToolStripDropDownButton> que tienen una relación de contraste de luminosidad mayor en el modo de contraste alto.

- La propiedad <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> de <xref:System.Windows.Forms.DataGridViewLinkCell>.

**Mejoras de Narrador**

A partir de .NET Framework 4.7.2, la compatibilidad con Narrador ha mejorado de la siguiente manera:

- El valor de la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> se anuncia al anunciar el texto de un objeto <xref:System.Windows.Forms.ToolStripMenuItem>. 

- Indica cuándo un objeto <xref:System.Windows.Forms.ToolStripMenuItem> tiene su propiedad <xref:System.Windows.Forms.Control.Enabled> establecida en `false`.

- Ofrece información sobre el estado de una casilla cuando la propiedad <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> está establecida en `true`.

- El orden de foco del Modo de examen de Narrador es coherente con el orden visual de los controles del cuadro de diálogo de descarga de ClickOnce.

**Mejoras de DataGridView**

A partir de .NET Framework 4.7.2, el control <xref:System.Windows.Forms.DataGridView> presenta las siguientes mejoras de accesibilidad:

- Las filas se pueden ordenar con el teclado. Un usuario puede presionar la tecla F3 para ordenar por la columna actual.

- Cuando <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> se establece en <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, el encabezado de columna cambia de color para indicar la columna actual cuando el usuario se desplaza entre las celdas de la fila actual.

- La propiedad <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> de <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> devuelve el control primario correcto.

**Indicaciones visuales mejoradas**

- Los controles <xref:System.Windows.Forms.RadioButton> y <xref:System.Windows.Forms.CheckBox> con una propiedad <xref:System.Windows.Forms.ButtonBase.Text> vacía se mostrará un indicador de foco cuando reciban el foco.

**Compatibilidad con la cuadrícula de propiedades mejorada**

- Ahora los elementos secundarios del control <xref:System.Windows.Forms.PropertyGrid> devuelven un valor `true` para la propiedad <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> solo cuando un elemento PropertyGrid está habilitado.

- Los elementos secundarios del control <xref:System.Windows.Forms.PropertyGrid> devuelven un valor `false` para la propiedad <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> solo cuando el usuario pueda modificar un elemento PropertyGrid.

**Navegación mejorada mediante el teclado**

- El control <xref:System.Windows.Forms.ToolStripButton> permite el foco cuando se incluye dentro de un control <xref:System.Windows.Forms.ToolStripPanel> que tiene la propiedad <xref:System.Windows.Forms.ToolStripPanel.TabStop> establecida en `true`.

<a name="wpf472"></a>
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Cambios en los controles CheckBox y RadioButton**

En .NET Framework 4.7.1 y versiones anteriores, los controles <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> y <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> de WPF tenían objetos visuales de foco incoherentes y, en los temas Clásico y Contraste alto, eran incorrectos.  Estos problemas se producen en casos en los que no se ha definido ningún contenido para los controles.  Esto puede hacer que la transición entre los temas sea confusa y el objeto visual de foco difícil de ver.

En .NET Framework 4.7.2, estos objetos visuales son ahora más coherentes entre los temas y se ven más fácilmente en los temas Clásico y Contraste alto.

**Controles de WinForms hospedados en una aplicación WPF**

En un control de WinForms hospedado en una aplicación WPF en .NET Framework 4.7.1 y versiones anteriores, no se podía usar el tabulador para salir de la capa de WinForms si el primer o último control de esa capa era el control <xref:System.Windows.Forms.Integration.ElementHost> de WPF. Ahora, en .NET Framework 4.7.2 se puede usar el tabulador para salir de la capa de WinForms.

Con todo, puede que las aplicaciones automatizadas que se basan en que el foco no escape nunca de la capa de WinForms dejen de funcionar según lo previsto.

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a>Novedades de accesibilidad en .NET Framework 4.7.1

.NET Framework 4.7.1 incluye nuevas características de accesibilidad en las áreas siguientes:

- [Windows Presentation Foundation (WPF)](#wpf471)

- [Windows Forms](#winforms471)

- [Controles web ASP.NET](#aspnet471)

- [Herramientas del SDK de .NET](#tools471)

- [Diseñador de flujo de trabajo de Windows Workflow Foundation (WF)](#wf471)

<a name="wpf471"></a>
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

<a name="winforms471"></a>
### <a name="windows-forms-accessibility-improvements"></a>Mejoras de accesibilidad de Windows Forms

En .NET Framework 4.7.1, Windows Forms (WinForms) incluye cambios de accesibilidad en las áreas siguientes.

**Visualización mejorada en modo de contraste alto**

A partir de .NET Framework 4.7.1, varios controles de WinForms ofrecen una representación mejorada en los modos de contraste alto disponibles en el sistema operativo. Windows 10 ha cambiado los valores de algunos colores del sistema de contraste alto y Windows Forms se basa en el marco de trabajo de Windows 10 Win32. Para obtener la mejor experiencia, trabaje en la versión más reciente de Windows y use los cambios más recientes del sistema operativo mediante la adición de un archivo app.manifest en una aplicación de prueba y quite los comentarios de la línea del sistema operativo compatible con Windows 10 para tenga este aspecto:

```xml
<!-- Windows 10 -->
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
 
<a name="aspnet471"></a>
### <a name="aspnet-web-controls"></a>Controles web ASP.NET

A partir de .NET Framework 4.7.1 y Visual Studio 2017 15.3, ASP.NET mejora el funcionamiento de los controles web ASP.NET con la tecnología de accesibilidad en Visual Studio. Los cambios son los siguientes:

- Cambios para implementar patrones de accesibilidad de interfaz de usuario que faltan en los controles, como el cuadro de diálogo **Agregar campo** en el **Asistente para vistas de detalles** o el cuadro de diálogo **Configurar ListView** del **Asistente de ListView**.

- Cambios para mejorar la presentación en el modo Contraste alto, como el **Editor de campos del elemento de paginación de datos**.

- Cambios para mejorar las experiencias de navegación del teclado para los controles, como el cuadro de diálogo **Campos** del **Asistente para editar campos del elemento de paginación** del control DataPager, el cuadro de diálogo **Configurar ObjectContext** o el cuadro de diálogo **Configurar selección de datos** del **Asistente para configurar origen de datos**.

<a name="tools471"></a>
### <a name="net-sdk-tools"></a>Herramientas del SDK de .NET

Se han corregido varios problemas de accesibilidad para mejorar la [herramienta del editor de configuración (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) y la [herramienta del visor de seguimiento de servicios (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md). La mayoría eran problemas menores como un nombre sin definir o determinados patrones de automatización de la interfaz de usuario que no se implementaban correctamente. Aunque muchos usuarios no son conscientes de estos valores incorrectos, los clientes que usen tecnologías de asistencia como lectores de pantalla encontrarán estas herramientas del SDK más accesibles. 

Estas mejoras cambian algunos comportamientos anteriores, como el orden del foco de teclado.

<a name="wf471"></a>
### <a name="windows-workflow-foundation-wf-workflow-designer"></a>Diseñador de flujo de trabajo de Windows Workflow Foundation (WF)

Los cambios de accesibilidad en el Diseñador de flujo de trabajo son los siguientes:

- El orden de tabulación cambia de izquierda a derecha y de arriba a abajo en algunos controles:

  - La ventana Inicializar correlación para establecer los datos de correlación para la actividad <xref:System.ServiceModel.Activities.InitializeCorrelation>.

  - La ventana Definición de contenido para las actividades <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> y <xref:System.ServiceModel.Activities.ReceiveReply>.

- Hay más funciones disponibles a través del teclado:

  - Al editar las propiedades de una actividad, los grupos de propiedades se pueden contraer mediante el teclado la primera vez que obtienen el foco.

  - Los iconos de advertencia son accesibles con el teclado.

  - El botón **Más propiedades** de la ventana **Propiedades** es accesible con el teclado.

  - Los usuarios del teclado pueden tener acceso a los elementos de encabezado en los paneles **Argumentos** y **Variables** del Diseñador de flujo de trabajo.

- Visibilidad mejorada de los elementos con el foco, por ejemplo cuando:

  - Se agregan filas a las cuadrículas de datos usadas por los diseñadores de actividad y el Diseñador de flujo de trabajo.

  - Desplazamiento entre campos en las actividades <xref:System.ServiceModel.Activities.ReceiveReply> y <xref:System.ServiceModel.Activities.SendReply>.

  - Establecimiento de valores predeterminados para variables o argumentos.

- Los lectores de pantalla ahora pueden reconocer correctamente:

  - Los puntos de interrupción establecidos en el Diseñador de flujo de trabajo.

  - Las actividades <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> y <xref:System.ServiceModel.Activities.CorrelationScope>.
  - El contenido de la actividad <xref:System.ServiceModel.Activities.Receive>.

  - El tipo de destino para la actividad <xref:System.Activities.Statements.InvokeMethod>.

  - El cuadro combinado Excepción y la sección Finally de la actividad <xref:System.Activities.Statements.TryCatch>.

  - El cuadro combinado Tipo de mensaje, el divisor de la ventana Agregar inicializadores de correlación, la ventana Definición de contenido y la ventana Definición de CorrelatesOn en las actividades de mensajería (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> y <xref:System.ServiceModel.Activities.ReceiveReply>).

  - Transiciones a máquina de estados y destinos de transición.

  - Anotaciones y conectores en las actividades <xref:System.Activities.Statements.FlowDecision>.

  - Los menús contextuales (clic con el botón derecho) para las actividades.

  - Los editores de valor de propiedad, el botón Borrar búsqueda, los botones de ordenación Por categoría y Alfabético, y el cuadro de diálogo Editor de expresiones en la cuadrícula de propiedades.

  - El porcentaje de zoom en el Diseñador de flujo de trabajo.

  - El separador en las actividades <xref:System.Activities.Statements.Parallel> y <xref:System.Activities.Statements.Pick>.

  - La actividad <xref:System.Activities.Statements.InvokeDelegate>.

  - La ventana Seleccionar tipos para las actividades de diccionario (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>`, etc.).

  - La ventana Examinar y seleccionar un tipo .NET.

  - Rutas de navegación en el Diseñador de flujo de trabajo.

- Los usuarios que elijan temas de contraste alto verán muchas mejoras en la visibilidad del Diseñador de flujo de trabajo y sus controles, como relaciones de contraste mejoradas entre los elementos y cuadros de selección más evidentes para los elementos del foco.

## <a name="see-also"></a>Vea también

- [Novedades de .NET Framework](whats-new.md)

