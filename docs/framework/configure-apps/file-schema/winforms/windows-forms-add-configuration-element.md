---
title: "Formularios Windows Forms Agregar elemento de configuración"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 828a28769e164535d4dde989ef8cce91caf9cb48
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2017
---
# <a name="windows-forms-add-configuration-element"></a>Formularios Windows Forms Agregar elemento de configuración

El `<add>` elemento agrega una clave predefinida que especifica si la aplicación de Windows Forms admite características agregadas a las aplicaciones de Windows Forms en el 4.7 de .NET Framework o una versión posterior.

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
| `key`     | Atributo necesario. Nombre de clave predefinido que se corresponde con una determinada característica personalizable de formularios Windows Forms. |
| `value`   | Atributo necesario. El valor que se asigna a `key`. |

### <a name="key-attribute-names-and-associated-values"></a>`key`nombres de atributos y valores asociados

| Nombre `key` | Valores | Descripción |
| ---------- | ------ | ----------- |
| "AnchorLayout.DisableSinglePassControlScaling" | "true" &#124;" False" | Indica si se escalan anclados controles en un solo paso. pasa "true" para deshabilitar el único ajuste de escala; en caso contrario, false. Vea la sección "Solo pasar escalado" en la [comentarios](#Remarks) para obtener más información. |
| "DpiAwareness" | "PerMonitorV2" &#124;" False" | Indica si una aplicación es compatible con PPP. Establezca la clave para "PerMonitorV2" para admitir el reconocimiento de PPP; de lo contrario, establézcala en "false". Reconocimiento de PPP es una característica opcional; para aprovechar las ventajas de la compatibilidad con PPP alta de formularios Windows Forms, debe establecer su valor en "PerMonitorV2". Consulte la [comentarios](#remarks) sección para obtener más información. |
| "CheckedListBox.DisableHighDpiImprovements" | "true" &#124;" False" | Indica si el <xref:System.Windows.Forms.CheckedListBox> control aprovecha las ventajas de ajuste de escala y el diseño mejoras introducidas en la 4.7 de .NET Framework. "true" para no participar en las mejoras de diseño y caling; en caso contrario, "false". |
| "DataGridView.DisableHighDpiImprovements" | "true" &#124;" False" | Indica si la <xref:System.Windows.Forms.DataGridView> controlar el ajuste de escala y el diseño mejoras introducidas en la 4.7 de .NET Framework. "true" para no participar en el reconocimiento de PPP; "false" en caso contrario. |
| "DisableDpiChangedMessageHandling" | "true" &#124;" False" | "true" para no participar en la recepción de mensajes relacionados con cambios; de ajuste de escala de PPP "false" en caso contrario. Consulte la [comentarios](#remarks) sección para obtener más información. |
| "EnableWindowsFormsHighDpiAutoResizing" | "true" &#124;" False" | Indica si una aplicación de formularios Windows Forms cambia automáticamente de tamaño debido a cambios de escala de PPP. "true" para habilitar el cambio de tamaño automático; en caso contrario, false. |
| "Form.DisableSinglePassControlScaling" | "true" &#124;" False" | Indica si el <xref:System.Windows.Forms.Form> se escala en un solo paso. "true" para deshabilitar la fase de único ajuste de escala; en caso contrario, false. Vea la sección "Solo pasar escalado" en la [comentarios](#Remarks) para obtener más información. |
| "MonthCalendar.DisableSinglePassControlScaling" | "true" &#124;" False" | Indica si el <xref:System.Windows.Forms.MonthCalendar> se escala el control en un solo paso. "true" para deshabilitar la fase de único ajuste de escala; en caso contrario, false. Vea la sección "Solo pasar escalado" en la [comentarios](#Remarks) para obtener más información. |
| "Toolstrip.DisableHighDpiImprovements" | "true" &#124;" False" | Indica si el <xref:System.Windows.Forms.ToolStrip> control aprovecha las ventajas de ajuste de escala y el diseño mejoras introducidas en la 4.7 de .NET Framework. "true" para no participar en el reconocimiento de PPP; "false" en caso contrario. |

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

| Elemento | Descripción |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md) | Configura el soporte para las nuevas características de aplicación de Windows Forms. |

## <a name="a-nameremarks--remarks"></a><a name="remarks" />Comentarios

A partir de .NET Framework 4.7, el elemento `<System.Windows.Forms.ApplicationConfigurationSection>` permite configurar las aplicaciones de Windows Forms para aprovechar las características agregadas en versiones recientes de .NET Framework. 

El `<System.Windows.Forms.ApplicationConfigurationSection>` elemento le permite agregar uno o más secundarios `<add>` elementos, cada uno de los cuales define un valor de configuración específico.  

Para obtener información general de soporte técnico de resolución alta de Windows Forms, vea [alta admiten PPP en formularios Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).

### <a name="dpiawareness"></a>DpiAwareness

Aplicaciones de formularios Windows Forms que se ejecutan en versiones de Windows a partir de Windows 10 creadores de edición y destinadas a versiones de .NET Framework a partir de la 4.7 de .NET Framework pueden configurarse para aprovechar las ventajas de las mejoras de PPP alta introducidas en .NET Framework 4.7. Se incluyen los siguientes:

- Compatibilidad con escenarios de PPP dinámicos en el que el usuario cambia el factor de escala o PPP después de que se ha iniciado una aplicación de formularios Windows Forms.

- Mejoras en el ajuste de escala y el diseño de una serie de formularios Windows Forms controles, como el <xref:System.Windows.Forms.MonthCalendar> control y el <xref:System.Windows.Forms.CheckedListBox> control. 

Reconocimiento de PPP alta es una característica opcional; de forma predeterminada, el valor de `DpiAwareness` es `false`. Puede participar en el soporte de formularios Windows Forms para que el reconocimiento de PPP estableciendo el valor de esta clave para `PerMonitorV2` en el archivo de configuración de aplicación. Si está habilitado el reconocimiento de PPP, todas las características individuales de PPP también están habilitadas. Se incluyen los siguientes:

- PPP cambiado mensajes, que están controlados por el `DisableDpiChangedMessageHandling` clave.

- Soporte de PPP dinámico, que está controlado por el `EnableWindowsFormsHighDpiAutoResizing` clave.

- Único paso se escala el control, que se controlan mediante la `Form.DisableSinglePassControlScaling` individuo <xref:System.Windows.Forms.Form> controla, por el `AnchorLayout.DisableSinglePassControlScaling` clave para los controles anclados y por la `MonthCalendar.DisableSinglePassControlScaling` clave para el <xref:System.Windows.Forms.MonthCalendar> control 

- Alta PPP escala y el diseño de las mejoras, que se controla mediante el `CheckListBox.DisableHighDpiImprovements` clave para la <xref:System.Windows.Forms.CheckedListBox> controlar, mediante el `DataGridView.DisableHighDpiImprovements` clave para el <xref:System.Windows.Forms.DataGridView> (control) y el `Toolstrip.DisableHighDpiImprovements` clave para el <xref:System.Windows.Forms.ToolStrip> control.  

La única participación en configuración predeterminada proporcionada estableciendo `DpiAwareness` a `PerMonitorV2` son más que suficientes para las nuevas aplicaciones de Windows Forms. Sin embargo, puede, a continuación, dejar de seguir individuales mejoras alta de PPP agregando la clave correspondiente en el archivo de configuración de aplicación. Por ejemplo, para aprovechar las ventajas de todas la nueva PPP características del salvo dinámica compatibilidad de PPP, agregar lo siguiente al archivo de configuración de la aplicación:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
   <add key="DpiAwareness" value="PerMonitorV2" />
   <--! Disable dynamic DPI support -->
   <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```
Normalmente, para dejar de seguir una característica determinada porque ha decidido controlarla mediante programación.

Para obtener más información sobre el aprovechamiento de la compatibilidad con valores altos de PPP en aplicaciones de Windows Forms, vea [alta admiten PPP en formularios Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).
 
### <a name="disabledpichangedmessagehandling"></a>DisableDpiChangedMessageHandling

A partir de la 4.7 de .NET Framework, los controles de formularios Windows Forms plantear una serie de eventos relacionados con los cambios de ajuste de escala de PPP. Puede tratarse de la <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, y <xref:System.Windows.Forms.Form.DpiChanged> eventos. El valor de la `DisableDpiChangedMessageHandling` clave determina si se generan estos eventos en una aplicación de formularios Windows Forms. 

### <a name="single-pass-scaling"></a>Ajuste de escala de paso único

Escalar único o pasar varios influye en la capacidad de respuesta percibida de la interfaz de usuario y la apariencia visual de los elementos de la interfaz de usuario puesto que se pueden escalar. A partir de la 4.7 de .NET Framework, Windows Forms utiliza una escala de paso único. En versiones anteriores de .NET Framework, el ajuste de escala se realizó a través de varios supera, lo que provocó algunos controles escalar más que era necesario. Ajuste de escala en un solo paso sólo debe deshabilitarse si la aplicación utiliza el comportamiento anterior.  

## <a name="see-also"></a>Vea también
 
[Sección de configuración de Windows Forms](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md)   
[Compatibilidad con valores altos de PPP en Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
