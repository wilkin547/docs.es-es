---
title: Información general acerca de las propiedades de UI Automation
description: Vea una amplia introducción a las propiedades de automatización de la interfaz de usuario de Microsoft. Obtenga información sobre los identificadores de propiedad, las propiedades por categoría, localización, propiedades y eventos.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, properties
- properties, UI Automation
ms.assetid: a6c31d7b-b33e-49b3-b5c1-31a345f9b7c8
ms.openlocfilehash: 95729c1d26a9ae7fdec4fa4215f9478251612242
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240399"
---
# <a name="ui-automation-properties-overview"></a>Información general acerca de las propiedades de UI Automation

> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 Los proveedores de Automatización de la interfaz de usuario exponen propiedades en los elementos [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] . Estas propiedades permiten que las aplicaciones de cliente de Automatización de la interfaz de usuario detecten información sobre partes de la [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], especialmente los controles, e incluidos los datos estáticos y dinámicos.  
  
 En esta sección se ofrece información general sobre las propiedades de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] . En los temas siguientes se proporciona información más específica:  
  
- [Propiedades de UI Automation para clientes](ui-automation-properties-for-clients.md)  
  
- [Implementación del proveedor de UI Automation en el servidor](server-side-ui-automation-provider-implementation.md)  
  
<a name="Property_Identifiers"></a>

## <a name="property-identifiers"></a>Identificadores de propiedad  

 Cada propiedad se identifica mediante un número y un nombre. Los nombres de las propiedades se utilizan únicamente para la depuración y el diagnóstico. Los proveedores usan los identificadores numéricos para identificar las solicitudes de propiedad entrantes. Las aplicaciones cliente, sin embargo, solo utilizan <xref:System.Windows.Automation.AutomationProperty>, que encapsula el número y el nombre, para identificar las propiedades que quieren recuperar.  
  
 Los objetos<xref:System.Windows.Automation.AutomationProperty> que representan propiedades determinadas están disponibles como campos en diversas clases. Por motivos de seguridad, los proveedores de Automatización de la interfaz de usuario obtienen estos objetos de un conjunto independiente de clases que están incluidas en Uiautomationtypes.dll.  
  
 En la tabla siguiente se clasifican las propiedades por las clases que contienen los <xref:System.Windows.Automation.AutomationProperty> identificadores.  
  
|Tipos de propiedades|Los clientes obtienen los identificadores de|Los proveedores obtienen los identificadores de|  
|-------------------------|--------------------------|----------------------------|  
|Propiedades comunes a todos los elementos (consulte las tablas siguientes)|<xref:System.Windows.Automation.AutomationElement>|<xref:System.Windows.Automation.AutomationElementIdentifiers>|  
|Posición de una ventana de acoplamiento|<xref:System.Windows.Automation.DockPattern>|<xref:System.Windows.Automation.DockPatternIdentifiers>|  
|Estado de un elemento que se puede expandir y contraer|<xref:System.Windows.Automation.ExpandCollapsePattern>|<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers>|  
|Propiedades de un elemento en una cuadrícula|<xref:System.Windows.Automation.GridItemPattern>|<xref:System.Windows.Automation.GridItemPatternIdentifiers>|  
|Propiedades de una cuadrícula|<xref:System.Windows.Automation.GridPattern>|<xref:System.Windows.Automation.GridPatternIdentifiers>|  
|Vista actual y admitida de un elemento que tiene varias vistas|<xref:System.Windows.Automation.MultipleViewPattern>|<xref:System.Windows.Automation.MultipleViewPatternIdentifiers>|  
|Propiedades de un elemento que se desplaza en un intervalo de valores, como un control deslizante|<xref:System.Windows.Automation.RangeValuePattern>|<xref:System.Windows.Automation.RangeValuePatternIdentifiers>|  
|Propiedades de una ventana desplazable|<xref:System.Windows.Automation.ScrollPattern>|<xref:System.Windows.Automation.ScrollPatternIdentifiers>|  
|Estado y contenedor de un elemento que se puede seleccionar, como en una lista|<xref:System.Windows.Automation.SelectionItemPattern>|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers>|  
|Propiedades de un control que contiene elementos de selección|<xref:System.Windows.Automation.SelectionPattern>|<xref:System.Windows.Automation.SelectionPatternIdentifiers>|  
|Encabezados de fila y columna de un elemento en una tabla|<xref:System.Windows.Automation.TableItemPattern>|<xref:System.Windows.Automation.TableItemPatternIdentifiers>|  
|Encabezados de fila y columna, y orientación, de una tabla|<xref:System.Windows.Automation.TablePattern>|<xref:System.Windows.Automation.TablePatternIdentifiers>|  
|Estado de un control de alternancia|<xref:System.Windows.Automation.TogglePattern>|<xref:System.Windows.Automation.TogglePatternIdentifiers>|  
|Capacidades de un elemento que se pueden mover, girar o cambiar de tamaño|<xref:System.Windows.Automation.TransformPattern>|<xref:System.Windows.Automation.TransformPatternIdentifiers>|  
|Capacidades de lectura y escritura y valor de un elemento que tiene un valor|<xref:System.Windows.Automation.ValuePattern>|<xref:System.Windows.Automation.ValuePatternIdentifiers>|  
|Capacidades y estado de una ventana|<xref:System.Windows.Automation.WindowPattern>|<xref:System.Windows.Automation.WindowPatternIdentifiers>|  
  
<a name="Properties_by_Category"></a>

## <a name="properties-by-category"></a>Propiedades por categoría  

 En las siguientes tablas se clasifican las propiedades cuyos identificadores se encuentran en <xref:System.Windows.Automation.AutomationElement> y <xref:System.Windows.Automation.AutomationElementIdentifiers> . Estas propiedades son comunes para todos los controles. Salvo algunas de ellas, todas suelen ser estáticas a lo largo de la duración de la aplicación de proveedor; la mayoría de propiedades dinámicas están asociadas con patrones de control.  
  
 En la columna **Property Access** se enumeran los otros descriptores de acceso de cada propiedad, además de <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> y <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>. Para más información sobre la obtención de propiedades en una aplicación cliente, consulte [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
> [!NOTE]
> Para obtener información específica sobre cada propiedad, siga el vínculo de la columna **Property Access** .  
  
### <a name="display-characteristics"></a>Características de presentación  
  
|Identificador de la propiedad|Property Access|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>|  
|<xref:System.Windows.Automation.AutomationElement.CultureProperty>|N/D|  
|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsOffscreen%2A>|  
|<xref:System.Windows.Automation.AutomationElement.OrientationProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Orientation%2A>|  
  
### <a name="element-type"></a>Tipo de elemento  
  
|Identificador de la propiedad|Property Access|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsContentElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsControlElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LocalizedControlType%2A>|  
  
### <a name="identification"></a>Identificación  
  
|Identificador de la propiedad|Property Access|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AutomationId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClassNameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ClassName%2A>|  
|<xref:System.Windows.Automation.AutomationElement.FrameworkIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.FrameworkId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LabeledByProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LabeledBy%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ProcessIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ProcessId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.RuntimeIdProperty>|<xref:System.Windows.Automation.AutomationElement.GetRuntimeId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NativeWindowHandleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.NativeWindowHandle%2A>|  
  
### <a name="interaction"></a>Interacción  
  
|Identificador de la propiedad|Property Access|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AcceleratorKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AccessKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>|<xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>|  
|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HasKeyboardFocus%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsEnabled%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsKeyboardFocusable%2A>|  
  
### <a name="support-for-patterns"></a>Compatibilidad con patrones  
  
|Identificador de la propiedad|Property Access|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsDockPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsExpandCollapsePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsInvokePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsMultipleViewPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsRangeValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTableItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTablePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTogglePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTransformPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsWindowPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
  
### <a name="miscellaneous"></a>Varios  
  
|Identificador de la propiedad|Property Access|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsRequiredForFormProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsRequiredForForm%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsPassword%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemStatusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemStatus%2A>|  
  
<a name="Localization"></a>

## <a name="localization"></a>Localización  

 Los proveedores[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] deben presentar las siguientes propiedades en el idioma del sistema operativo:  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AcceleratorKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AccessKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>  
  
<a name="Properties_and_Events"></a>

## <a name="properties-and-events"></a>Propiedades y eventos  

 El concepto de eventos de cambio de propiedad está estrechamente relacionado con las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Para las propiedades dinámicas, la aplicación cliente necesita una manera de saber que un valor de propiedad ha cambiado, por lo que puede actualizar su caché de información o reaccionar a la nueva información de alguna otra manera.  
  
 Los proveedores generan eventos cuando cambia algo en la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . Por ejemplo, si se selecciona o se desactiva una casilla, la implementación del proveedor del patrón Toggle genera un evento de cambio de propiedad. Los proveedores pueden generar eventos de forma selectiva, dependiendo de si hay clientes en escucha de eventos o en escucha de eventos específicos.  
  
 No todos los cambios de propiedades generan eventos; esto depende totalmente de la implementación del proveedor de Automatización de la interfaz de usuario del elemento. Por ejemplo, los proveedores de proxy estándares para cuadros de lista no generan un evento cuando el elemento <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> cambia. En este caso, la aplicación debe estar en su lugar a la escucha de un elemento <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>.  
  
 Los clientes se ponen a la escucha de eventos suscribiéndose a ellos. La suscripción a eventos supone la creación de métodos delegados que pueden controlar los eventos y, después, pasan los métodos a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] junto con los eventos específicos que se tratarán en esos métodos. Para los eventos de cambio de propiedad en concreto, los clientes deben implementar <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>.  
  
## <a name="see-also"></a>Vea también

- [Almacenar en caché en los clientes de automatización de la interfaz de usuario](caching-in-ui-automation-clients.md)
- [Propiedades de UI Automation para clientes](ui-automation-properties-for-clients.md)
- [Implementación del proveedor de UI Automation en el servidor](server-side-ui-automation-provider-implementation.md)
- [Buscar un elemento de UI Automation basándose en una condición de propiedad](find-a-ui-automation-element-based-on-a-property-condition.md)
- [Devolución de propiedades por parte de un proveedor de UI Automation](return-properties-from-a-ui-automation-provider.md)
- [Provocar eventos desde un proveedor de UI Automation](raise-events-from-a-ui-automation-provider.md)
