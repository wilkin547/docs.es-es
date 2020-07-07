---
ms.openlocfilehash: c8e1c91f4fee8aa896b6617c815fe2a4b6d22f2a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614886"
---
### <a name="accessibility-improvements-in-windows-forms-controls"></a>Mejoras de accesibilidad en controles de Windows Forms

#### <a name="details"></a>Detalles

Windows Forms mejora su funcionamiento con las tecnologías de accesibilidad para ofrecer una mejor compatibilidad con los clientes de Windows Forms. Entre estos se incluyen los cambios siguientes a partir de .NET Framework 4.7.1:

- Cambios para mejorar la presentación durante el modo de contraste alto.
- Cambios para mejorar la experiencia del Explorador de propiedades. Las mejoras en el Explorador de propiedades incluyen las siguientes:
- Una mejor navegación mediante teclado gracias a las distintas ventanas de selección desplegables.
- Se reducen las tabulaciones innecesarias.
- Mejor notificación de tipos de control.
- Comportamiento mejorado de Narrador.
- Cambios para implementar los patrones de accesibilidad de interfaz de usuario que faltan en los controles.

#### <a name="suggestion"></a>Sugerencia

**Cómo participar o no en estos cambios** Para que la aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.7.1 o una versión posterior. La aplicación se puede beneficiar de estos cambios de cualquiera de las maneras siguientes:

- Se recompila para tener .NET Framework 4.7.1 como destino. Estos cambios de accesibilidad están habilitados de forma predeterminada para las aplicaciones de Windows Forms destinadas a .NET Framework 4.7.1 o una versión posterior.
- No participa en los comportamientos de accesibilidad heredados mediante la adición del [modificador de AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) a la sección `<runtime>` del archivo app.config y estableciéndolo en `false`, como se muestra en el ejemplo siguiente.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
  </runtime>
</configuration>
```

En las aplicaciones destinadas a .NET Framework 4.7.1 o una versión posterior, y en las que se quiere conservar el comportamiento de accesibilidad heredado, se puede participar en el uso de las características de accesibilidad heredadas si se establece explícitamente este modificador de AppContext en `true`.<p/>Para obtener información general de la automatización de la interfaz de usuario, vea la [información general sobre la Automatización de la interfaz de usuario](~/docs/framework/ui-automation/ui-automation-overview.md).<p/>**Compatibilidad agregada para propiedades y patrones de Automatización de la interfaz de usuario**<br/>Los clientes de accesibilidad pueden aprovechar las ventajas de las nuevas funciones de accesibilidad de WinForms mediante modelos de invocación comunes, que se describen de manera pública. Estos patrones no son específicos de WinForms. Por ejemplo, los clientes de accesibilidad pueden llamar el método QueryInterface en la interfaz IAccessible (MAAS) para obtener una interfaz IServiceProvider. Si esta interfaz está disponible, los clientes pueden usar su método QueryService para solicitar una interfaz IAccessibleEx. Para obtener más información, vea [Using IAccessibleEx from a Client](https://docs.microsoft.com/windows/desktop/WinAuto/using-iaccessibleex-from-a-client) (Uso de IAccessibleEx desde un cliente). A partir de .NET Framework 4.7.1, IServiceProvider e [IAccessibleEx](https://docs.microsoft.com/windows/desktop/WinAuto/iaccessibleex) (cuando corresponda) están disponibles para los objetos de accesibilidad de WinForms.<p/>.NET Framework 4.7.1 agrega compatibilidad para los siguientes patrones y propiedades de automatización de la interfaz de usuario:

- Los controles <xref:System.Windows.Forms.ToolStripSplitButton> y <xref:System.Windows.Forms.ComboBox> admiten ahora el [patrón de expansión o contracción](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).
- El control <xref:System.Windows.Forms.ToolStripMenuItem> tiene un valor de la propiedad [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) de <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType>.
- El control <xref:System.Windows.Forms.ToolStripItem> admite la propiedad <xref:System.Windows.Automation.AutomationElement.NameProperty> y el [patrón de expansión o contracción](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).
- El control <xref:System.Windows.Forms.ToolStripDropDownItem> admite eventos <xref:System.Windows.Forms.AccessibleEvents> en los que se indique StateChange y NameChange cuando la lista desplegable está expandida o contraída.
- El control <xref:System.Windows.Forms.ToolStripDropDownButton> tiene un valor de la propiedad [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) de <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType>.
- El control <xref:System.Windows.Forms.DataGridViewCheckBoxCell> admite el <xref:System.Windows.Automation.TogglePattern>.
- Los controles <xref:System.Windows.Forms.NumericUpDown> y <xref:System.Windows.Forms.DomainUpDown> admiten la propiedad <xref:System.Windows.Automation.AutomationElement.NameProperty> y tienen una propiedad [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md) de <xref:System.Windows.Automation.ControlType.Spinner?displayProperty=nameWithType>.</p>
**Mejoras en el control PropertyGrid** En .NET Framework 4.7.1 se agregan las mejoras siguientes para el control PropertyBrowser:

- El botón **Detalles** del cuadro de diálogo Error que se muestra cuando el usuario escribe un valor incorrecto en el control <xref:System.Windows.Forms.PropertyGrid> admite el [patrón de expansión o contracción](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md), notificaciones de cambio de estado y nombre, y una propiedad [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) con un valor de <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType>.
- El panel de mensajes que se muestra cuando se expande el botón **Detalles** del cuadro de diálogo Error ahora es accesible desde el teclado y permite que Narrador anuncie el contenido del mensaje de error.
- El <xref:System.Windows.Forms.AccessibleRole> de las filas del control <xref:System.Windows.Forms.PropertyGrid> ha cambiado de &quot;Fila&quot; a &quot;Celda&quot;. La celda se asigna a la propiedad ControlType de UIA &quot;DataItem&quot;, que le permite admitir los métodos abreviados de teclado adecuados y los anuncios de Narrador.
- Las filas del control <xref:System.Windows.Forms.PropertyGrid> que representan elementos de encabezado cuando el control <xref:System.Windows.Forms.PropertyGrid> tiene una propiedad <xref:System.Windows.Forms.PropertyGrid.PropertySort> establecida en <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType> tienen un valor de la propiedad [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) de <xref:System.Windows.Automation.ControlType.Button?displayProperty=nameWithType>.
- Las filas del control <xref:System.Windows.Forms.PropertyGrid> que representan elementos de encabezado cuando el control <xref:System.Windows.Forms.PropertyGrid> tiene una propiedad <xref:System.Windows.Forms.PropertyGrid.PropertySort> establecida en <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType> admiten el [patrón de expansión o contracción](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).
- Navegación con el teclado mejorada entre la cuadrícula y la barra de herramientas situada por encima. Al presionar &quot;Mayús-Tab&quot; ahora se selecciona el primer botón de la barra de herramientas, en lugar de la barra de herramientas completa.
- Los controles <xref:System.Windows.Forms.PropertyGrid> que se muestran en el modo de contraste alto ahora dibujarán un rectángulo de foco alrededor del botón de la barra de herramientas que se corresponde al valor de la propiedad <xref:System.Windows.Forms.PropertyGrid.PropertySort> actual.
- Los controles <xref:System.Windows.Forms.PropertyGrid> que se muestran en el modo de contraste alto y que tienen una propiedad <xref:System.Windows.Forms.PropertyGrid.PropertySort> establecida en <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType> ahora mostrarán el fondo de los encabezados de categoría en un color de contraste alto.
- Los controles <xref:System.Windows.Forms.PropertyGrid> marcan mejor la diferencia entre los elementos de la barra de herramientas con el foco y los elementos que indican el valor actual de la propiedad <xref:System.Windows.Forms.PropertyGrid.PropertySort>. Esta revisión está formada por un cambio de contraste alto y un cambio para los escenarios que no son de contraste alto.
- Los elementos ToolBar del control <xref:System.Windows.Forms.PropertyGrid> que indica el valor actual de la propiedad <xref:System.Windows.Forms.PropertyGrid.PropertySort> admiten el <xref:System.Windows.Automation.TogglePattern>.
- Compatibilidad mejorada de Narrador para distinguir la alineación seleccionada en el selector de alineación.
- Cuando se muestra un control <xref:System.Windows.Forms.PropertyGrid> vacío en un formulario, ahora recibirá el foco donde anteriormente no lo hacía.

**Uso de colores definidos por el sistema operativo en los temas de contraste alto**

- En los controles <xref:System.Windows.Forms.Button> y <xref:System.Windows.Forms.CheckBox> con la propiedad <xref:System.Windows.Forms.ButtonBase.FlatStyle> establecida en <xref:System.Windows.Forms.FlatStyle.System?displayProperty=nameWithType>, que es el estilo predeterminado, ahora se usan colores definidos por el sistema operativo en el tema de contraste alto cuando se seleccionan. Anteriormente, los colores de fondo y de texto no tenían contraste y eran difíciles de leer.
- En los controles <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton>, <xref:System.Windows.Forms.Label>, <xref:System.Windows.Forms.LinkLabel> y <xref:System.Windows.Forms.GroupBox> con la propiedad <xref:System.Windows.Forms.Control.Enabled> establecida en **false**, se usaba un color sombreado para representar el texto en los temas de contraste alto, lo que generaba un contraste bajo sobre el fondo. Ahora, en estos controles se usa el color &quot;Texto deshabilitado&quot; definido por el sistema operativo. Esta revisión se aplica a los controles con la propiedad `FlatStyle` establecida en un valor distinto de <xref:System.Windows.Forms.FlatStyle.System?displayProperty=nameWithType>. El sistema operativo representa los últimos controles.
- <xref:System.Windows.Forms.DataGridView> ahora representa un rectángulo visible alrededor del contenido de la celda que tiene el foco actual. Anteriormente, esto no era visible en determinados temas de contraste alto.
- En los controles <xref:System.Windows.Forms.ToolStripMenuItem> con la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Enabled> establecida en **false** ahora se usa el color &quot;Texto deshabilitado&quot; definido por el sistema operativo.
- Los controles <xref:System.Windows.Forms.ToolStripMenuItem> con la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Checked> establecida en **true** ahora representan la marca de verificación asociada en un color del sistema en contraste.  Anteriormente, el color de la marca de verificación no tenía el contraste suficiente y no era visible en los temas de contraste alto.
NOTA: En Windows 10 se han cambiado los valores para algunos colores del sistema de contraste alto. El marco de trabajo de Windows Forms se basa en el marco de trabajo de Win32. Para obtener la mejor experiencia, trabaje en la versión más reciente de Windows y use los cambios más recientes del sistema operativo mediante la adición de un archivo app.manifest en una aplicación de prueba y la eliminación de los comentarios del código siguiente:

```xml
<!-- Windows 10 -->
<supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
```

**Navegación mejorada mediante el teclado**

- Cuando un control <xref:System.Windows.Forms.ComboBox> tiene la propiedad <xref:System.Windows.Forms.ComboBox.DropDownStyle> establecida en <xref:System.Windows.Forms.ComboBoxStyle.DropDownList?displayProperty=nameWithType> y es el primer control del orden de tabulación del formulario, ahora muestra un rectángulo de foco cuando el formulario principal se abre mediante el teclado. Antes de este cambio, el foco del teclado estaba en este control, pero no se representaba un indicador de foco.

**Compatibilidad mejorada con Narrador**

- El control <xref:System.Windows.Forms.MonthCalendar> ha agregado compatibilidad para que las tecnologías de asistencia tengan acceso al control, incluida la capacidad de Narrador de leer el valor del control cuando anteriormente no podía.

- El control <xref:System.Windows.Forms.CheckedListBox> ahora notifica a Narrador cuándo ha cambiado una propiedad <xref:System.Windows.Forms.CheckBox.CheckState?displayProperty=nameWithType>. Anteriormente, Narrador no recibía notificaciones y, como resultado, no se informaba a los usuarios que la propiedad <xref:System.Windows.Forms.CheckBox.CheckState> se había actualizado.
- El control <xref:System.Windows.Forms.LinkLabel> ha cambiado la forma de notificar a Narrador el texto del control. Anteriormente, Narrador anunciaba dos veces este texto y leía los símbolos &quot;&amp;&quot; como texto real, aunque no eran visibles para los usuarios. El texto duplicado se quitó de los anuncios de Narrador, así como los símbolos &quot;&amp;&quot; innecesarios.
- Los tipos de control <xref:System.Windows.Forms.DataGridViewCell> ahora notifican correctamente el estado de solo lectura a Narrador y otras tecnologías de asistencia.
- Ahora Narrador puede leer el menú del sistema de las ventanas secundarias en las aplicaciones [Multiple-Document Interface]~/docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md).
- Ahora, Narrador puede leer los controles <xref:System.Windows.Forms.ToolStripMenuItem> con una propiedad <xref:System.Windows.Forms.ToolStripItem.Enabled?displayProperty=nameWithType> establecida en **false**. Anteriormente Narrador no podía centrarse en los elementos de menú deshabilitados para leer el contenido.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Major       |
| Versión | 4.8         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Forms.ToolStripDropDownButton.CreateAccessibilityInstance?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownAccessibleObject.Name?displayProperty=nameWithType>
- [MonthCalendar.AccessibilityObject](xref:System.Windows.Forms.Control.AccessibilityObject)
