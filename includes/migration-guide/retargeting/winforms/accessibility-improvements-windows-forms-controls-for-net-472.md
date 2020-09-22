---
ms.openlocfilehash: a21824862d6cad046b5d6186f9d6db9c20438304
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606638"
---
### <a name="accessibility-improvements-in-windows-forms-controls-for-net-472"></a>Mejoras de accesibilidad en controles de Windows Forms para .NET 4.7.2

#### <a name="details"></a>Detalles

El marco de trabajo de Windows Forms mejora su funcionamiento con las tecnologías de accesibilidad para ofrecer una mejor compatibilidad con los clientes de Windows Forms. Entre otros, se incluyen los cambios siguientes:

- Cambios para mejorar la presentación durante el modo de contraste alto.
- Cambios para mejorar la navegación mediante el teclado en los controles DataGridView y MenuStrip.
- Cambios en la interacción con Narrador.

#### <a name="suggestion"></a>Sugerencia

**Cómo participar o no en estos cambios** Para que la aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.7.2 o una versión posterior. La aplicación se puede beneficiar de estos cambios de cualquiera de las maneras siguientes:

- Se recompila para tener .NET Framework 4.7.2 como destino. Estos cambios de accesibilidad están habilitados de forma predeterminada para las aplicaciones de Windows Forms destinadas a .NET Framework 4.7.2 o una versión posterior.
- Tiene como destino .NET Framework 4.7.1 o una versión anterior, y no participa en los comportamientos de accesibilidad heredados mediante la adición del [modificador de AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección `<runtime>` del archivo app.config y estableciéndolo en `false`, como se muestra en el ejemplo siguiente.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
  </runtime>
</configuration>
```

Tenga en cuenta que para participar en las características de accesibilidad agregadas en .NET Framework 4.7.2, también se debe participar en las características de accesibilidad de .NET Framework 4.7.1. En las aplicaciones destinadas a .NET Framework 4.7.2 o una versión posterior, y en las que se quiere conservar el comportamiento de accesibilidad heredado, se puede participar en el uso de las características de accesibilidad heredadas si se establece explícitamente este modificador de AppContext en `true`.

**Uso de colores definidos por el sistema operativo en los temas de contraste alto**

- En la flecha desplegable del control <xref:System.Windows.Forms.ToolStripDropDownButton> ahora se usan colores definidos por el sistema operativo en el tema de contraste alto.
- En los controles <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> y <xref:System.Windows.Forms.CheckBox> con <xref:System.Windows.Forms.ButtonBase.FlatStyle> establecido en <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> o <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType> ahora se usan colores definidos por el sistema operativo en el tema de contraste alto cuando se seleccionan. Anteriormente, los colores de fondo y de texto no tenían contraste y eran difíciles de leer.
- En los controles incluidos en un control <xref:System.Windows.Forms.GroupBox> que tiene su propiedad <xref:System.Windows.Forms.Control.Enabled> establecida en `false` ahora se usarán colores definidos por el sistema operativo en el tema de contraste alto.
- Los controles <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox> y <xref:System.Windows.Forms.ToolStripDropDownButton> tienen una relación de contraste de luminosidad mayor en el modo de contraste alto.
- En <xref:System.Windows.Forms.DataGridViewLinkCell> se usarán de forma predeterminada colores definidos por el sistema operativo en el modo de contraste alto para la propiedad <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor?displayProperty=nameWithType>.
NOTA: En Windows 10 se han cambiado los valores para algunos colores del sistema de contraste alto. El marco de trabajo de Windows Forms se basa en el marco de trabajo de Win32. Para obtener la mejor experiencia, trabaje en la versión más reciente de Windows y use los cambios más recientes del sistema operativo mediante la adición de un archivo app.manifest en una aplicación de prueba y la eliminación de los comentarios del código siguiente:

```xml
<!-- Windows 10 -->
<supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
```

**Compatibilidad mejorada con Narrador**

- Ahora Narrador anuncia el valor de la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> al anunciar el texto de un objeto <xref:System.Windows.Forms.ToolStripMenuItem>.
- Ahora Narrador indica cuándo un objeto <xref:System.Windows.Forms.ToolStripMenuItem> tiene su propiedad <xref:System.Windows.Forms.Control.Enabled> establecida en `false`.
- Ahora Narrador ofrece información sobre el estado de una casilla cuando la propiedad <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> está establecida en `true`.
- El orden de foco del Modo de examen de Narrador ahora es coherente con el orden visual de los controles del cuadro de diálogo de descarga de ClickOnce.

**Compatibilidad de accesibilidad de DataGridView mejorada**

- Ahora las filas de un control <xref:System.Windows.Forms.DataGridView> se pueden ordenar mediante el teclado. Ahora un usuario puede presionar la tecla F3 para ordenar por la columna actual.
- Cuando <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> se establece en <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, el encabezado de columna cambiará de color para indicar la columna actual cuando el usuario se desplaza entre las celdas de la fila actual.
- Ahora la propiedad <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Parent?displayProperty=nameWithType> devuelve el control primario correcto.

**Indicaciones visuales mejoradas**

- Ahora en los controles <xref:System.Windows.Forms.RadioButton> y <xref:System.Windows.Forms.CheckBox> con una propiedad <xref:System.Windows.Forms.ButtonBase.Text> vacía se mostrará un indicador de foco cuando reciban el foco.

**Compatibilidad con la cuadrícula de propiedades mejorada**

- Ahora los elementos secundarios del control <xref:System.Windows.Forms.PropertyGrid> devuelven un valor `true` para la propiedad <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> solo cuando un elemento PropertyGrid está habilitado.
- Ahora los elementos secundarios del control <xref:System.Windows.Forms.PropertyGrid> devuelven un valor `false` para la propiedad <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> solo cuando el usuario pueda modificar un elemento PropertyGrid.
Para obtener información general de la automatización de la interfaz de usuario, vea la [información general sobre la Automatización de la interfaz de usuario](../../../../docs/framework/ui-automation/ui-automation-overview.md).</p>**Navegación mejorada mediante el teclado**

- <xref:System.Windows.Forms.ToolStripButton> ahora permite el foco cuando se incluye dentro de un control <xref:System.Windows.Forms.ToolStripPanel> que tiene la propiedad <xref:System.Windows.Forms.ToolStripPanel.TabStop> establecida en`true`.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Major       |
| Versión | 4.7.2       |
| Tipo    | Redestinación |
