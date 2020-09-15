---
ms.openlocfilehash: e528a41748d9353c96d443f68e15e7a98ee7f4ae
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616306"
---
### <a name="accessibility-improvements-in-windows-forms-controls-for-net-48"></a>Mejoras de accesibilidad en controles de Windows Forms para .NET 4.8

#### <a name="details"></a>Detalles

El marco de trabajo de Windows Forms continúa mejorando su funcionamiento con las tecnologías de accesibilidad para ofrecer una mejor compatibilidad con los clientes de Windows Forms. Entre otros, se incluyen los cambios siguientes:

- Cambios para mejorar la presentación durante el modo de contraste alto.
- Cambios en la interacción con Narrador.
- Cambios en la jerarquía Accesible (mejorando la navegación a través del árbol de automatización de la interfaz de usuario).

#### <a name="suggestion"></a>Sugerencia

**Cómo participar o no en estos cambios** Para que la aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.8. La aplicación puede optar por recibir estos cambios de cualquiera de las maneras siguientes:

- Se recompila para tener .NET Framework 4.8 como destino. Estos cambios de accesibilidad están habilitados de forma predeterminada para las aplicaciones de Windows Forms destinadas a .NET Framework 4.8.
- Tiene como destino .NET Framework 4.7.2 o una versión anterior, y no participa en los comportamientos de accesibilidad heredados mediante la adición del [modificador de AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) siguiente a la sección `<runtime>` del archivo app.config y estableciéndolo en `false`, como se muestra en el ejemplo siguiente.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
  </runtime>
</configuration>
```

Tenga en cuenta que para participar en las características de accesibilidad agregadas en .NET Framework 4.8, también se debe participar en las características de accesibilidad de .NET Framework 4.7.1 y 4.7.2. Las aplicaciones destinadas a .NET Framework 4.8 o una versión posterior, y cuando se quiere conservar el comportamiento de accesibilidad heredado, se puede participar en el uso de las características de accesibilidad heredadas si se establece explícitamente este modificador de AppContext en `true`. Para habilitar la compatibilidad con la invocación de la información sobre herramientas del teclado es necesario es necesario agregar la línea `Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false` al valor AppContextSwitchOverrides:

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false" />
```

Tenga en cuenta que habilitar esta característica requiere participar en las características de accesibilidad de .NET Framework 4.7.1 - 4.8 mencionadas anteriormente. Además, si no participa en algunas de las características de accesibilidad, pero sí en las características de visualización de la información sobre herramientas, se producirá un tiempo de ejecución <xref:System.NotSupportedException> en el primer acceso a estas características. El mensaje de excepción indica que las informaciones sobre herramientas del teclado requieren que se habiliten mejoras de accesibilidad de nivel 3.

**Uso de colores definidos por el sistema operativo en los temas de contraste alto**

- Temas de contraste alto mejorados.

**Compatibilidad mejorada con Narrador**

- Ahora el Narrador anuncia la dirección de ordenación de <xref:System.Windows.Forms.DataGridViewColumn> al anunciar un nombre accesible de un <xref:System.Windows.Forms.DataGridViewCell>.

**Compatibilidad de accesibilidad mejorada con CheckedListBox**

- Compatibilidad mejorada con Narrador para el control de <xref:System.Windows.Forms.CheckedListBox>. Al navegar por el control <xref:System.Windows.Forms.CheckedListBox> utilizando el teclado, el Narrador se centra en el elemento <xref:System.Windows.Forms.CheckedListBox> y lo anuncia.
- Un control CheckedListBox vacío tiene ahora un rectángulo de foco dibujado para un primer elemento virtual cuando el control se enfoca.

**Compatibilidad de accesibilidad mejorada con ComboBox**

- Compatibilidad de la automatización de la interfaz de usuario habilitada para el control <xref:System.Windows.Forms.ComboBox>, con la capacidad para usar notificaciones de automatización de la interfaz de usuario y otras características de automatización de la interfaz de usuario.
**Compatibilidad de accesibilidad de DataGridView mejorada**

- Compatibilidad de la automatización de la interfaz de usuario habilitada para el control <xref:System.Windows.Forms.DataGridView>, con capacidad para usar notificaciones de automatización de la interfaz de usuario y otras características de automatización de la interfaz de usuario.
- El elemento de automatización de la interfaz de usuario que corresponde a <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl> o <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl> ahora es un elemento secundario de la celda de edición correspondiente.

**Compatibilidad de accesibilidad mejorada con LinkLabel**

- Accesibilidad del control <xref:System.Windows.Forms.LinkLabel> mejorada: El Narrador anuncia el estado deshabilitado para el vínculo si el correspondiente control <xref:System.Windows.Forms.LinkLabel> está deshabilitado.

**Compatibilidad de accesibilidad mejorada con ProgressBar**

- Compatibilidad de la automatización de la interfaz de usuario habilitada para el control <xref:System.Windows.Forms.ProgressBar> con la capacidad para usar notificaciones de automatización de la interfaz de usuario y otras características de automatización de la interfaz de usuario. Los desarrolladores ahora pueden usar las notificaciones de automatización de la interfaz de usuario que Narrador puede anunciar para indicar el progreso.
Para obtener información general sobre eventos de la automatización de la interfaz de usuario, incluidos los eventos de notificación de automatización de la interfaz de usuario, consulte [Información general sobre eventos de automatización de la interfaz de usuario](https://docs.microsoft.com/windows/desktop/WinAuto/uiauto-eventsoverview).

**Compatibilidad de accesibilidad mejorada con PropertyGrid**

- Compatibilidad de la automatización de la interfaz de usuario habilitada para el control <xref:System.Windows.Forms.PropertyGrid>, con la capacidad para usar notificaciones de automatización de la interfaz de usuario y otras características de automatización de la interfaz de usuario.
- El elemento de automatización de la interfaz de usuario que corresponde a la propiedad que actualmente se edita es ahora un elemento secundario del elemento de automatización de la interfaz de usuario del correspondiente elemento de propiedad.
- El elemento de propiedad de automatización de la interfaz de usuario es ahora un elemento secundario del correspondiente elemento de categoría, si el control primario <xref:System.Windows.Forms.PropertyGrid> se establece en la vista por categorías.

**Compatibilidad mejorada con ToolStrip**

- Compatibilidad de la automatización de la interfaz de usuario habilitada para el control <xref:System.Windows.Forms.ToolStrip>, con la capacidad para usar notificaciones de automatización de la interfaz de usuario y otras características de automatización de la interfaz de usuario.
- Navegación mejorada a través de elementos <xref:System.Windows.Forms.ToolStrip>.
- En el modo de elementos, el enfoque de Narrador no desaparecerá y no pasará a los elementos ocultos.

**Indicaciones visuales mejoradas**

- Un control <xref:System.Windows.Forms.CheckedListBox> vacío ahora muestra un indicador de enfoque cuando recibe el enfoque.
Nota: La compatibilidad de automatización de la interfaz de usuario está habilitada para los controles en tiempo de ejecución pero no se utiliza en tiempo de diseño. Para obtener información general de la automatización de la interfaz de usuario, vea la [información general sobre la Automatización de la interfaz de usuario](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview).

**Información sobre herramientas de invocación de controles con un teclado**

- Ahora se puede invocar el control de información sobre herramientas centrándose en el control con el teclado. Esta característica debe habilitarse explícitamente para la aplicación (consulte la sección **&quot;Cómo participar o no en estos cambios&quot;** )

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Major       |
| Versión | 4.8         |
| Tipo    | Redestinación |
