---
title: Windows Forms Agregar elemento de configuración
ms.date: 04/07/2017
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75a66ee7ca1d7c99de6e2cc9a1d502ea58dbf9f7
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422828"
---
# <a name="windows-forms-add-configuration-element"></a>Windows Forms Agregar elemento de configuración

El `<add>` elemento agrega una clave predeterminada que especifica si la aplicación de formulario de Windows admite las características agregadas a las aplicaciones de Windows Forms en .NET Framework 4.7 o versiones posteriores.

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
| `key`     | Atributo necesario. Nombre de clave predefinido que se corresponde con una determinada característica personalizable de Windows Forms. |
| `value`   | Atributo necesario. Valor que se asigna a `key`. |

### <a name="key-attribute-names-and-associated-values"></a>`key` los nombres de atributos y valores asociados

| `key` Nombre | Valores | Descripción |
| ---------- | ------ | ----------- |
| "AnchorLayout.DisableSinglePassControlScaling" | "true"&#124;"false" | Indica si los controles delimitados se escalan en un único paso. "true" para deshabilitar solo pasa escalado; en caso contrario, false. Consulte la sección "Solo pasar escalado" en el [comentarios](#remarks) para obtener más información. |
| "DpiAwareness" | "PerMonitorV2"&#124;"false" | Indica si una aplicación tiene reconocimiento de PPP. Establezca la clave para "PerMonitorV2" para admitir el reconocimiento de PPP; en caso contrario, establézcalo en "false". Reconocimiento de PPP es una característica opcional; para aprovechar las ventajas de la compatibilidad con PPP elevado de Windows Forms, debe establecer su valor a "PerMonitorV2". Consulte la [comentarios](#remarks) sección para obtener más información. |
| "CheckedListBox.DisableHighDpiImprovements" | "true"&#124;"false" | Indica si el <xref:System.Windows.Forms.CheckedListBox> control aprovecha las ventajas de adaptación y diseño de las mejoras introducidas en .NET Framework 4.7. "true" para dejar de participar en las mejoras de diseño y ajuste de escala; en caso contrario, "false". |
| "DataGridView.DisableHighDpiImprovements" | "true"&#124;"false" | Indica si el <xref:System.Windows.Forms.DataGridView> controlar adaptación y diseño de las mejoras introducidas en .NET Framework 4.7. "true" para dejar de participar en el reconocimiento de PPP; "false" en caso contrario. |
| "DisableDpiChangedMessageHandling" | "true"&#124;"false" | "true" para optar por recibir los mensajes relacionados con los cambios; de ajuste de PPP "false" en caso contrario. Consulte la [comentarios](#remarks) sección para obtener más información. |
| "EnableWindowsFormsHighDpiAutoResizing" | "true"&#124;"false" | Indica si una aplicación de Windows Forms cambia automáticamente de tamaño debido a cambios de escala de PPP. "true" para habilitar el cambio de tamaño automático; en caso contrario, false. |
| "Form.DisableSinglePassControlScaling" | "true"&#124;"false" | Indica si el <xref:System.Windows.Forms.Form> se escala en un único paso. paso único es "true" para deshabilitar escalado; en caso contrario, false. Consulte la sección "Solo pasar escalado" en el [comentarios](#remarks) para obtener más información. |
| "MonthCalendar.DisableSinglePassControlScaling" | "true"&#124;"false" | Indica si el <xref:System.Windows.Forms.MonthCalendar> se escala el control en un único paso. paso único es "true" para deshabilitar escalado; en caso contrario, false. Consulte la sección "Solo pasar escalado" en el [comentarios](#remarks) para obtener más información. |
| "Toolstrip.DisableHighDpiImprovements" | "true"&#124;"false" | Indica si el <xref:System.Windows.Forms.ToolStrip> control aprovecha las ventajas de adaptación y diseño de las mejoras introducidas en .NET Framework 4.7. "true" para dejar de participar en el reconocimiento de PPP; "false" en caso contrario. |

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

| Elemento | Descripción |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md) | Configura la compatibilidad con nuevas características de aplicación de Windows Forms. |

## <a name="remarks"></a>Comentarios

A partir de .NET Framework 4.7, el elemento `<System.Windows.Forms.ApplicationConfigurationSection>` permite configurar las aplicaciones de Windows Forms para aprovechar las características agregadas en versiones recientes de .NET Framework.

El `<System.Windows.Forms.ApplicationConfigurationSection>` elemento le permite agregar uno o varios secundarios `<add>` elementos, cada uno de los cuales define un valor de configuración específico.

Para obtener información general de la compatibilidad con alta concentración de PPP de Windows Forms, consulte [alto PPP admite en Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).

### <a name="dpiawareness"></a>DpiAwareness

Las aplicaciones de Windows Forms que se ejecutan en versiones de Windows a partir de Windows 10 Creators Edition y versiones de destino de .NET Framework a partir de .NET Framework 4.7 pueden configurarse para aprovechar las mejoras de PPP alta introducidas en .NET Framework 4.7. Se incluyen los siguientes:

- Compatibilidad con escenarios de PPP dinámicos en el que el usuario cambia el factor de escala o PPP después de que se ha iniciado una aplicación de Windows Forms.

- Controles de mejoras en la escala y el diseño de una serie de formularios de Windows, como el <xref:System.Windows.Forms.MonthCalendar> control y el <xref:System.Windows.Forms.CheckedListBox> control.

Reconocimiento de PPP alta es una característica opcional; de forma predeterminada, el valor de `DpiAwareness` es `false`. Puede optar a soporte técnico de Windows Forms para que el reconocimiento de PPP estableciendo el valor de esta clave para `PerMonitorV2` en el archivo de configuración de la aplicación. Si está habilitado el reconocimiento de PPP, también se activarán todas las características individuales de PPP. Se incluyen los siguientes:

- PPP puede cambiar los mensajes, que se controlan mediante el `DisableDpiChangedMessageHandling` clave.

- Soporte técnico de PPP dinámico, que está controlado por la `EnableWindowsFormsHighDpiAutoResizing` clave.

- Sola pasada se escala el control, que se controla mediante el `Form.DisableSinglePassControlScaling` individuales <xref:System.Windows.Forms.Form> controla, por el `AnchorLayout.DisableSinglePassControlScaling` clave para los controles delimitados y por la `MonthCalendar.DisableSinglePassControlScaling` clave para el <xref:System.Windows.Forms.MonthCalendar> control

- Alto PPP adaptación y diseño mejoras, que está controlado por la `CheckListBox.DisableHighDpiImprovements` clave para el <xref:System.Windows.Forms.CheckedListBox> controlar, mediante el `DataGridView.DisableHighDpiImprovements` clave para el <xref:System.Windows.Forms.DataGridView> control y por la `Toolstrip.DisableHighDpiImprovements` clave para el <xref:System.Windows.Forms.ToolStrip> control.

El valor opt predeterminado único proporcionado estableciendo `DpiAwareness` a `PerMonitorV2` son más que suficientes para nuevas aplicaciones de Windows Forms. Sin embargo, puede, a continuación, rechazar las mejoras de PPP alta individuales mediante la adición de la clave correspondiente al archivo de configuración de la aplicación. Por ejemplo, para aprovechar todas las nuevas características de PPP, excepto la compatibilidad con PPP dinámico, agregaría el siguiente al archivo de configuración de la aplicación:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
   <add key="DpiAwareness" value="PerMonitorV2" />
   <!-- Disable dynamic DPI support -->
   <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

Normalmente, rechazar una característica determinada porque ha elegido controlarlo mediante programación.

Para obtener más información sobre el aprovechamiento de la compatibilidad con valores altos de PPP en aplicaciones de Windows Forms, consulte [alto PPP admite en Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).

### <a name="disabledpichangedmessagehandling"></a>DisableDpiChangedMessageHandling

A partir de .NET Framework 4.7, controles de formularios Windows Forms plantear una serie de eventos relacionados con los cambios en la escala de PPP. Estos incluyen el <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, y <xref:System.Windows.Forms.Form.DpiChanged> eventos. El valor de la `DisableDpiChangedMessageHandling` clave determina si se generan estos eventos en una aplicación de Windows Forms.

### <a name="single-pass-scaling"></a>Escalado de paso único

Escalar único o varios pass influye en la capacidad de respuesta percibida de la interfaz de usuario y la apariencia visual de elementos de la interfaz de usuario ya que se escalan. A partir de .NET Framework 4.7, Windows Forms usa escalado paso único. En versiones anteriores de .NET Framework, el escalado se realizó a través de varias pasadas, lo que provocó algunos controles escalar más que era necesario. Escalado solo pase sólo debe deshabilitarse si depende de la aplicación en el comportamiento anterior.

## <a name="see-also"></a>Vea también

- [Sección de configuración de Windows Forms](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md)
- [Compatibilidad con valores altos de PPP en Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
