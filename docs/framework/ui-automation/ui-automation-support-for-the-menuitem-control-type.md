---
title: Compatibilidad de UI Automation para el tipo de control MenuItem
description: Obtenga información sobre la compatibilidad de UI Automation para el tipo de control MenuItem. Obtenga información sobre la estructura de árbol necesaria, las propiedades, los patrones de control y los eventos.
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Menu Item
- Menu Item control type
- UI Automation, Menu Item control type
ms.assetid: 54bce311-3d23-40b9-ba90-1bdbdaf8fbba
ms.openlocfilehash: 248fdacee42c3a67c6c3b2d5792b774dfdc8408f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166018"
---
# <a name="ui-automation-support-for-the-menuitem-control-type"></a>Compatibilidad de UI Automation para el tipo de control MenuItem

> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).

En este tema se ofrece información sobre la compatibilidad de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] con el tipo de control MenuItem. Describe la estructura de árbol [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] del control y ofrece las propiedades y los patrones de control que son necesarios para el tipo de control MenuItem.

Un control de menú permite organizar jerárquicamente los elementos asociados a comandos y controladores de eventos. En una aplicación típica de Microsoft Windows, una barra de menús contiene varios elementos de menú (como **archivo**, **Editar**y **ventana**) y cada elemento de menú muestra un menú. Un menú contiene una colección de elementos de menú (como **Nuevo**, **Abierto**y **Cerrar**), que se puede expandir para mostrar elementos de menú adicionales o realizar una acción específica cuando se haga clic en ella. Un elemento de menú se pueden hospedar en un menú, barra de menús o barra de herramientas.

En las secciones siguientes se definen la estructura de árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necesaria, las propiedades, los patrones de control y los eventos para el tipo de control MenuItem. Los [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requisitos de se aplican a todos los controles de lista, ya sean [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] , Win32 o Windows Forms.

<a name="Required_UI_Automation_Tree_Structure"></a>

## <a name="required-ui-automation-tree-structure"></a>Estructura de árbol de Automatización de la interfaz de usuario necesaria

En la tabla siguiente se describe la vista de control y la vista de contenido del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que pertenece a los controles de elemento de menú y se describe lo que puede incluirse en cada vista. Para más información sobre el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Tree Overview](ui-automation-tree-overview.md).

|Vista de control|Vista de contenido|
|------------------|------------------|
|MenuItem "Ayuda"<br /><br /> <ul><li>Menú (submenú de elemento de menú de Ayuda)<br /><br /> <ul><li>MenuItem "Temas de Ayuda"</li><li>MenuItem "Acerca del Bloc de notas"</li></ul></li></ul>|MenuItem "Ayuda"<br /><br /> -MenuItem "temas de ayuda"<br />-MenuItem "acerca del Bloc de notas"|

La vista de control del control de elemento de menú tiene la estructura de árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] mostrada arriba. Tenga en cuenta que el elemento de menú **ayuda** se incluye para ilustrar mejor la estructura en una jerarquía típica de menú a submenú.

Para la vista de contenido, el menú no aparece en el árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] porque no transmite información significativa al usuario final.

<a name="Required_UI_Automation_Properties"></a>

## <a name="required-ui-automation-properties"></a>Propiedades de Automatización de la interfaz de usuario necesarias

En la tabla siguiente se muestran las propiedades [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] cuyo valor o definición es especialmente relevante para los controles de elemento de menú. Para obtener más información sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] las propiedades, vea [UI Automation Properties for clients](ui-automation-properties-for-clients.md).

|Propiedad|Value|Descripción|
|--------------|-----------|-----------------|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vea las notas.|El valor de esta propiedad debe ser único en todos los controles de una aplicación.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vea las notas.|El rectángulo exterior que contiene el control completo.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vea las notas.|Se admite si hay un rectángulo delimitador. Si no todos los puntos que se encuentran dentro del rectángulo delimitador son seleccionables, y realiza pruebas de aciertos especializadas, invalide y ofrezca un punto en el que hacer clic.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vea las notas.|Si el control puede recibir el foco del teclado, debe admitir esta propiedad.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vea las notas.|El control de elemento de menú se incluye en la vista de contenido del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] y tiene como etiqueta propia un nombre.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Sin etiqueta.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|MenuItem|Este valor es el mismo para todos los marcos de trabajo de la interfaz de usuario.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"elemento de menú"|Cadena localizada que corresponde al tipo de control MenuItem.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|El control de elemento de menú nunca se incluye en la vista de contenido del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|El control de elemento de menú se debe incluir siempre en la vista de control del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|

<a name="Required_UI_Automation_Control_Patterns"></a>

## <a name="required-ui-automation-control-patterns"></a>Patrones de control de Automatización de la interfaz de usuario necesarios

En la tabla siguiente se muestran los patrones de control [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que se deben admitir por los controles de elemento de menú. Para más información sobre los patrones de control, vea [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).

|Propiedad de patrón de control|Soporte técnico|Notas|
|------------------------------|-------------|-----------|
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Depende|Si el control se puede expandir o contraer, implemente <xref:System.Windows.Automation.Provider.IExpandCollapseProvider>.|
|<xref:System.Windows.Automation.Provider.IInvokeProvider>|Depende|Si el control ejecuta un acción o comando único, implemente <xref:System.Windows.Automation.Provider.IInvokeProvider>.|
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Depende|Si el control representa una opción que se puede activar o desactivar, implemente <xref:System.Windows.Automation.Provider.IToggleProvider>.|
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Depende|Si el control se usa para seleccionar de una lista de opciones entre los elementos de menú, implemente <xref:System.Windows.Automation.Provider.ISelectionItemProvider>.|

<a name="UI_Automation_Events_for_Menu_Item"></a>

## <a name="ui-automation-events-for-menu-item"></a>Eventos de automatización de la interfaz de usuario para elemento de menú

En la tabla siguiente se muestran los eventos [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] asociados al control de elemento de menú.

|Evento|Soporte técnico|Explicación|
|-----------|-------------|-----------------|
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Depende|Se debe generar si el control admite el patrón de control Invoke.|
|Evento cambiado por propiedad<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> .|Depende|Se debe generar si el control admite el patrón de control Toggle.|
|Evento cambiado por propiedad<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> .|Depende|Se debe generar si el control admite el patrón de control Expand Collapse.|
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Depende|Ninguno.|

<a name="Required_UI_Automation_Events"></a>

## <a name="required-ui-automation-events"></a>Eventos de Automatización de la interfaz de usuario necesarios

En la siguiente tabla se muestra los eventos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que se deben admitir por todos los controles de elemento de menú. Para más información sobre los eventos, vea [UI Automation Events Overview](ui-automation-events-overview.md).

|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Soporte técnico/valor|Notas|
|---------------------------------------------------------------------------------|--------------------|-----------|
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Depende|None|
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>|Depende|None|
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|Depende|None|
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Depende|None|
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Requerido|None|
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Requerido|None|
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Requerido|None|
|Evento cambiado por propiedad<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> .|Depende|None|
|Evento cambiado por propiedad<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> .|Depende|None|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Obligatorio|None|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Obligatorio|None|

<a name="Legacy_Issues"></a>

## <a name="legacy-issues"></a>Problemas heredados

Solo se admitirá el patrón de alternancia cuando el elemento de menú Win32 esté activado y se pueda determinar mediante programación si es necesario para admitir el patrón de alternancia. Dado que el elemento de menú Win32 no expone si tiene la capacidad de comprobarse, se admitirá el patrón Invoke cuando no se compruebe el elemento de menú. Se realizará una excepción para admitir siempre Invoke Pattern incluso para elementos de menú que solo deberían admitir Toggle Pattern. Esto es para que los clientes no se confundan en que un elemento que admitía Invoke Pattern (cuando el elemento de menú estaba desactivado) ya no admite el patrón cuando se activa.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Automation.ControlType.MenuItem>
- [Información general acerca de los patrones de control de UI Automation](ui-automation-control-patterns-overview.md)
- [Información general sobre tipos de control de UI Automation](ui-automation-control-types-overview.md)
- [Información general sobre UI Automation](ui-automation-overview.md)
