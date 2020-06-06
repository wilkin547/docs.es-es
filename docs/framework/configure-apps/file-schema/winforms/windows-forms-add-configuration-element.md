---
title: Windows Forms Agregar elemento de configuración
ms.date: 04/07/2017
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
ms.openlocfilehash: 26b806f84c3e1bc44e0437a8f8806316b14897b8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73109659"
---
# <a name="windows-forms-add-configuration-element"></a>Windows Forms Agregar elemento de configuración

El `<add>` elemento agrega una clave predefinida que especifica si la aplicación de Windows Forms admite características agregadas a Windows Forms aplicaciones en el .NET Framework 4,7 o posterior.

## <a name="syntax"></a>Sintaxis

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="key-name" value="key-value" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

| Atributo | Descripción |
| --------- | ----------- |
| `key`     | Atributo necesario. Un nombre de clave predefinido que corresponde a un determinado Windows Forms característica personalizable. |
| `value`   | Atributo necesario. Valor que se va a asignar a `key`. |

### <a name="key-attribute-names-and-associated-values"></a>`key`nombres de atributos y valores asociados

| Nombre `key` | Valores | Descripción |
| ---------- | ------ | ----------- |
| "AnchorLayout.DisableSinglePassControlScaling" | "true" &#124; "false" | Indica si los controles delimitados se escalan en un solo paso. "true" para deshabilitar el ajuste de escala de un solo paso; en caso contrario, false. Para obtener más información, vea la sección "escalado de paso único" en las [notas](#remarks) . |
| "DpiAwareness" | "PerMonitorV2" &#124; "false" | Indica si una aplicación es compatible con PPP. Establezca la clave en "PerMonitorV2" para admitir el reconocimiento de PPP. de lo contrario, establézcalo en "false". El reconocimiento de PPP es una característica opcional. para aprovechar las ventajas de la compatibilidad con valores altos de PPP Windows Forms, debe establecer su valor en "PerMonitorV2". Vea la sección [comentarios](#remarks) para obtener más información. |
| "CheckedListBox. DisableHighDpiImprovements" | "true" &#124; "false" | Indica si el <xref:System.Windows.Forms.CheckedListBox> control aprovecha las mejoras de escala y diseño introducidas en el .NET Framework 4,7. "true" para no participar en las mejoras de escala y diseño; de lo contrario, es "false". |
| "DataGridView. DisableHighDpiImprovements" | "true" &#124; "false" | Indica si el <xref:System.Windows.Forms.DataGridView> ajuste de escala y el diseño de los controles se introdujeron en el .NET Framework 4,7. "true" para rechazar el reconocimiento de PPP; "false" en caso contrario. |
| "DisableDpiChangedMessageHandling" | "true" &#124; "false" | "true" para excluir la recepción de mensajes relacionados con los cambios de escala de PPP; "false" en caso contrario. Vea la sección [comentarios](#remarks) para obtener más información. |
| "EnableWindowsFormsHighDpiAutoResizing" | "true" &#124; "false" | Indica si se cambia automáticamente el tamaño de una aplicación Windows Forms debido a los cambios de escala de PPP. "true" para habilitar el cambio de tamaño automático; en caso contrario, false. |
| "Form. DisableSinglePassControlScaling" | "true" &#124; "false" | Indica si <xref:System.Windows.Forms.Form> se ha escalado en un solo paso. "true" para deshabilitar el ajuste de escala de un solo paso; en caso contrario, false. Para obtener más información, vea la sección "escalado de paso único" en las [notas](#remarks) . |
| "MonthCalendar. DisableSinglePassControlScaling" | "true" &#124; "false" | Indica si el <xref:System.Windows.Forms.MonthCalendar> control se escala en un solo paso. "true" para deshabilitar el ajuste de escala de un solo paso; en caso contrario, false. Para obtener más información, vea la sección "escalado de paso único" en las [notas](#remarks) . |
| "ToolStrip. DisableHighDpiImprovements" | "true" &#124; "false" | Indica si el <xref:System.Windows.Forms.ToolStrip> control aprovecha las mejoras de escala y diseño introducidas en el .NET Framework 4,7. "true" para rechazar el reconocimiento de PPP; "false" en caso contrario. |

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

| Elemento | Descripción |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](index.md) | Configura la compatibilidad con las nuevas características de la aplicación Windows Forms. |

## <a name="remarks"></a>Comentarios

A partir de .NET Framework 4.7, el elemento `<System.Windows.Forms.ApplicationConfigurationSection>` permite configurar las aplicaciones de Windows Forms para aprovechar las características agregadas en versiones recientes de .NET Framework.

El `<System.Windows.Forms.ApplicationConfigurationSection>` elemento permite agregar uno o varios `<add>` elementos secundarios, cada uno de los cuales define un valor de configuración específico.

Para obtener información general sobre la compatibilidad con Windows Forms alta resolución de PPP, consulte [compatibilidad con alta resolución de PPP en Windows Forms](../../../winforms/high-dpi-support-in-windows-forms.md).

### <a name="dpiawareness"></a>DpiAwareness

Windows Forms las aplicaciones que se ejecutan en versiones de Windows a partir de Windows 10 Creators Edition y versiones de destino de la .NET Framework a partir de la .NET Framework 4,7 se pueden configurar para aprovechar las mejoras de PPP altas introducidas en el .NET Framework 4,7. Entre ellas se incluyen las siguientes:

- Compatibilidad con escenarios de PPP dinámicos en los que el usuario cambia los PPP o el factor de escala una vez que se ha iniciado una aplicación Windows Forms.

- Mejoras en el ajuste de escala y diseño de varios controles Windows Forms, como el <xref:System.Windows.Forms.MonthCalendar> control y el <xref:System.Windows.Forms.CheckedListBox> control.

Un reconocimiento de PPP alto es una característica opcional. de forma predeterminada, el valor de `DpiAwareness` es `false` . Puede optar por Windows Forms ' compatibilidad con reconocimiento de PPP estableciendo el valor de esta clave `PerMonitorV2` en en el archivo de configuración de la aplicación. Si está habilitado el reconocimiento de PPP, también se habilitan todas las características de PPP individuales. Entre ellas se incluyen las siguientes:

- Los mensajes cambiados por PPP, controlados por la `DisableDpiChangedMessageHandling` clave.

- Compatibilidad con PPP dinámicos, que se controla mediante la `EnableWindowsFormsHighDpiAutoResizing` clave.

- Ajuste de escala de control de un solo paso, que se controla mediante `Form.DisableSinglePassControlScaling` para <xref:System.Windows.Forms.Form> controles individuales, por la `AnchorLayout.DisableSinglePassControlScaling` clave para controles delimitados y por la `MonthCalendar.DisableSinglePassControlScaling` clave del <xref:System.Windows.Forms.MonthCalendar> control.

- Mejoras de diseño y ajuste de escala de PPP altas, controladas por la `CheckListBox.DisableHighDpiImprovements` clave para el <xref:System.Windows.Forms.CheckedListBox> control, por la `DataGridView.DisableHighDpiImprovements` clave del <xref:System.Windows.Forms.DataGridView> control y por la `Toolstrip.DisableHighDpiImprovements` clave del <xref:System.Windows.Forms.ToolStrip> control.

La configuración de participación predeterminada única que se proporciona al establecer en suele ser `DpiAwareness` `PerMonitorV2` adecuada para las aplicaciones de Windows Forms nuevas. Sin embargo, puede no participar en las mejoras de PPP altas individuales agregando la clave correspondiente al archivo de configuración de la aplicación. Por ejemplo, para aprovechar todas las nuevas características de PPP excepto la compatibilidad con PPP dinámicos, debe agregar lo siguiente al archivo de configuración de la aplicación:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
   <add key="DpiAwareness" value="PerMonitorV2" />
   <!-- Disable dynamic DPI support -->
   <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

Normalmente, se deja de participar en una característica determinada porque se ha elegido administrarla mediante programación.

Para obtener más información sobre cómo aprovechar las ventajas de la compatibilidad con alta PPP en Windows Forms aplicaciones, consulte [compatibilidad con alta PPP en Windows Forms](../../../winforms/high-dpi-support-in-windows-forms.md).

### <a name="disabledpichangedmessagehandling"></a>DisableDpiChangedMessageHandling

A partir de la .NET Framework 4,7, Windows Forms controles elevan varios eventos relacionados con los cambios en el ajuste de escala de PPP. Entre ellos se incluyen los <xref:System.Windows.Forms.Control.DpiChangedAfterParent> <xref:System.Windows.Forms.Control.DpiChangedBeforeParent> eventos, y <xref:System.Windows.Forms.Form.DpiChanged> . El valor de la `DisableDpiChangedMessageHandling` clave determina si estos eventos se generan en una aplicación Windows Forms.

### <a name="single-pass-scaling"></a>Escalado de un solo paso

El escalado de una o varias pases influye en la capacidad de respuesta percibida de la interfaz de usuario y en la apariencia visual de los elementos de la interfaz de usuario a medida que se escalan. A partir de la .NET Framework 4,7, Windows Forms utiliza el escalado de un solo paso. En versiones anteriores del .NET Framework, el escalado se realizaba a través de varias fases, lo que hacía que algunos controles se escalaran más de lo necesario. El ajuste de escala de un solo paso solo debe deshabilitarse si la aplicación depende del comportamiento anterior.

## <a name="see-also"></a>Consulte también

- [Sección de configuración de Windows Forms](index.md)
- [Compatibilidad con PPP alta en Windows Forms](../../../winforms/high-dpi-support-in-windows-forms.md)
