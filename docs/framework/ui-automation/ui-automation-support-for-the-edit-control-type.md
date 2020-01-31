---
title: Compatibilidad de la automatización de la interfaz de usuario para el tipo de control Edit
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Edit
- Edit control type
- UI Automation, Edit control type
ms.assetid: 6db9d231-c0a0-4e17-910e-ac80357f774f
ms.openlocfilehash: cdbb400d438231689fe35c4bff2bd2946b6bed80
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789505"
---
# <a name="ui-automation-support-for-the-edit-control-type"></a>Compatibilidad de la automatización de la interfaz de usuario para el tipo de control Edit

> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).

En este tema se ofrece información sobre la compatibilidad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] con el tipo de control Edit. En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], un tipo de control es un conjunto de condiciones que un control debe cumplir para poder usar la propiedad <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Entre las condiciones se incluyen instrucciones específicas para la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , los patrones de control y los valores de propiedad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .

Los controles de edición habilitan a un usuario para que vea y edite una línea de texto simple sin compatibilidad con formato enriquecido.

En las secciones siguientes se definen la estructura de árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necesaria, las propiedades, los patrones de control y los eventos para el tipo de control Edit. Los requisitos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] se aplican a todos los controles de edición, ya sean [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], Win32 o Windows Forms.

<a name="Required_UI_Automation_Tree_Structure"></a>

## <a name="required-ui-automation-tree-structure"></a>Estructura de árbol de Automatización de la interfaz de usuario necesaria

En la tabla siguiente se describe la vista de control y la vista de contenido del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que pertenece a los controles de edición y se describe lo que puede incluirse en cada vista. Para más información sobre el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Tree Overview](ui-automation-tree-overview.md).

|Vista de control|Vista Contenido|
|------------------|------------------|
|Edit|Edit|

Los controles que implementan el tipo de control Edit no tendrán barras de desplazamiento en la vista de control del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] porque es un control de línea única. La única línea de texto puede encapsularse en algunos escenarios de diseño. El tipo de control Edit es idóneo para contener pequeñas cantidades de texto editable o seleccionable.

<a name="Required_UI_Automation_Properties"></a>

## <a name="required-ui-automation-properties"></a>Propiedades de Automatización de la interfaz de usuario necesarias

En la tabla siguiente se muestran las propiedades [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] cuyo valor o definición es especialmente relevante para los controles de edición. Para más información sobre las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).

|Propiedad[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|{2&gt;Value&lt;2}|Notas|
|------------------------------------------------------------------------------------|-----------|-----------|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vea las notas.|El valor de esta propiedad debe ser único en todos los controles de una aplicación.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vea las notas.|El rectángulo exterior que contiene el control completo.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vea las notas.|El control de edición debe tener un punto en el que se pueda hacer clic que dé enfoque de entrada a la parte de edición del control cuando un usuario hace clic en el mouse allí.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vea las notas.|Si el control puede recibir el foco del teclado, debe admitir esta propiedad.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vea las notas.|El nombre del control de edición se genera normalmente desde una etiqueta de texto estático. Si no hay ninguna etiqueta de texto estático, el desarrollador de aplicaciones debe asignar un valor de propiedad para `Name` . La propiedad `Name` nunca debe incluir el contenido textual del control de edición.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Vea las notas.|Si hay una etiqueta de texto estático asociada al control, esta propiedad debe exponer una referencia a ese control. Si el control de texto es un subcomponente de otro control, no tendrá un conjunto de propiedades `LabeledBy` .|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Edit|Este valor es el mismo para todos los marcos de trabajo [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] .|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"edición"|Cadena localizada que corresponde al tipo de control Edit.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|Verdadero|El control de edición siempre se incluye en la vista de contenido del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|Verdadero|El control de edición siempre se incluye en la vista de control del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsPasswordProperty>|Vea las notas.|Debe establecerse en true en controles de edición que contienen contraseñas. Si un control de edición contiene el contenido de la contraseña, esta propiedad se puede usar por un lector de pantalla para determinar si las pulsaciones de teclas se deben leer cuando el usuario las introduce.|

<a name="Required_UI_Automation_Control_Patterns"></a>

## <a name="required-ui-automation-control-patterns-and-properties"></a>Propiedades y patrones de control de Automatización de la interfaz de usuario necesarios

En la tabla siguiente se muestran los patrones de control que se deben admitir por todos los controles de edición. Para más información sobre los patrones de control, vea [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).

|Patrón de control/propiedad de patrón de control|Soporte técnico/valor|Notas|
|-----------------------------------------------|--------------------|-----------|
|<xref:System.Windows.Automation.Provider.ITextProvider>|Depende|Los controles de edición deben admitir el patrón de control Text porque siempre debe haber información de texto detallada disponible para los clientes.|
|<xref:System.Windows.Automation.Provider.IValueProvider>|Depende|Todos los controles de edición que toman una cadena deben exponer el patrón Value.|
|<xref:System.Windows.Automation.Provider.IValueProvider.IsReadOnly%2A>|Vea las notas.|Se debe establecer esta propiedad para indicar si el control puede tener un valor establecido mediante programación o si es editable por el usuario.|
|<xref:System.Windows.Automation.Provider.IValueProvider.Value%2A>|Vea las notas.|Esta propiedad devolverá el contenido textual del control de edición. Si la `IsPasswordProperty` se establece en `true`, esta propiedad debe provocar una `InvalidOperationException` cuando se solicite.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider>|Depende|Todos los controles de edición que toman un intervalo numérico deben exponer el patrón de control Range Value.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.Minimum%2A>|Vea las notas.|Esta propiedad debe ser el valor mínimo en el que se puede establecer el contenido del control de edición.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.Maximum%2A>|Vea las notas.|Esta propiedad debe ser el valor máximo en el que se puede establecer el contenido del control de edición.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.SmallChange%2A>|Vea las notas.|Esta propiedad debe indicar el número de posiciones decimales en el que se puede establecer el valor. Si la edición solo acepta enteros, la `SmallChangeProperty` debe ser 1. Si la edición acepta un intervalo de entre 1,0 y 2,0, la `SmallChangeProperty` debe ser 0,1. Si el control de edición acepta un intervalo de entre 1,0 y 2,0, la `SmallChangeProperty` debe ser 0,001.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.LargeChange%2A>|`Null`|Esta propiedad no necesita exponerse en un control de edición.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.Value%2A>|Vea las notas.|Esta propiedad indicará el contenido numérico del control de edición. Cuando se establece un valor más preciso por un cliente [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] dentro de los intervalos especificados en las propiedades `Minimum` y `Maximum` , la propiedad Value se redondeará automáticamente al valor aceptado más cercano.|

<a name="Required_UI_Automation_Events"></a>

## <a name="required-ui-automation-events"></a>Eventos de Automatización de la interfaz de usuario necesarios

En la tabla siguiente se muestran los eventos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que se deben admitir por todos los controles de edición. Para más información sobre eventos, vea [UI Automation Events Overview](ui-automation-events-overview.md).

|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Compatibilidad con|Notas|
|---------------------------------------------------------------------------------|-------------|-----------|
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Requerido|Ninguno|
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextSelectionChangedEvent>|Requerido|Ninguno|
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextChangedEvent>|Requerido|Ninguno|
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Requerido|Ninguno|
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Requerido|Ninguno|
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Requerido|Ninguno|
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> .|Requerido|Ninguno|
|Evento cambiado por propiedad<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> .|Depende|Ninguno|
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> .|Never|Ninguno|
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> .|Never|Ninguno|
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> .|Never|Ninguno|
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> .|Never|Ninguno|
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> .|Never|Ninguno|
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> .|Never|Ninguno|
|Evento cambiado por propiedad<xref:System.Windows.Automation.RangeValuePatternIdentifiers.ValueProperty> .|Depende|Si el control admite el patrón de control Range Value, debe admitir este evento.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Requerido|Ninguno|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Requerido|Ninguno|

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Automation.ControlType.Edit>
- [Información general sobre tipos de control de Automatización de la interfaz de usuario](ui-automation-control-types-overview.md)
- [Información general sobre la Automatización de la interfaz de usuario](ui-automation-overview.md)
