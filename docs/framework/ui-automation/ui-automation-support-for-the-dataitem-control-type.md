---
title: Compatibilidad de UI Automation para el tipo de control DataItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, Data Item control type
- Data Item control type
- control types, Data Item
ms.assetid: 181708fd-2595-4c43-9abd-75811627d64c
caps.latest.revision: "36"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: be826cce87d428a156bb7a10d858e5848b2f1143
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ui-automation-support-for-the-dataitem-control-type"></a>Compatibilidad de UI Automation para el tipo de control DataItem
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se ofrece información sobre la compatibilidad de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] con el tipo de control DataItem. En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , un tipo de control es un conjunto de condiciones que debe cumplir un control para poder usar la propiedad <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Entre las condiciones se incluyen instrucciones específicas para la estructura de árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , valores de propiedad [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] y patrones de control.  
  
 Una entrada de una lista de contactos es un ejemplo de un control de elemento de datos. Un control de elemento de datos contiene información de interés para un usuario final. Es más complicado que el elemento de lista simple porque contiene información más completa.  
  
 En las secciones siguientes se definen la estructura del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , las propiedades, los patrones de control y los eventos necesarios para el tipo de control DataItem. Los requisitos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] se aplican a todos los controles de elemento de datos, ya sean [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]o [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Estructura de árbol de automatización de interfaz de usuario necesaria  
 En la tabla siguiente se detallan la vista de control y la vista de contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que pertenece a los controles de elemento de datos y se describe lo que puede incluirse en cada vista. Para más información sobre el árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).  
  
|Árbol[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] - Vista de control|Árbol[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] - Vista de contenido|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|DataItem<br /><br /> -Varía (0 o más; se puede estructurar en jerarquía)|DataItem<br /><br /> -Varía (0 o más; se puede estructurar en jerarquía)|  
  
 Un elemento de datos de una cuadrícula de datos puede hospedar diversos objetos, entre los que se incluye otra capa de elementos de datos o elementos de cuadrícula concretos como controles de edición, texto o imágenes. Si el elemento de datos tiene un rol de objeto concreto, el elemento debe exponerse como un tipo de control concreto; por ejemplo, un tipo de control ListItem para un elemento de datos seleccionable de la cuadrícula.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Propiedades de Automatización de la interfaz de usuario necesarias  
 En la tabla siguiente se muestran las propiedades que tienen un valor o una definición que es especialmente relevante para los controles de elemento de datos. Para más información sobre las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).  
  
|Property|Valor|Notas|  
|--------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vea las notas.|El valor de esta propiedad debe ser único en todos los controles de una aplicación.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vea las notas.|El rectángulo exterior que contiene el control completo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vea las notas.|Se admite si hay un rectángulo delimitador. Si no todos los puntos que se encuentran dentro del rectángulo delimitador son seleccionables, y realiza pruebas de aciertos especializadas, invalide y ofrezca un punto en el que hacer clic.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|DataItem|Este valor es el mismo para todos los marcos de trabajo de la interfaz de usuario.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|El control de elemento de datos siempre debe ser contenido.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|El control de elemento de datos siempre debe ser un control.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vea las notas.|Si el control puede recibir el enfoque del teclado, debe admitir esta propiedad.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ItemStatusProperty>|Vea las notas.|Si el control contiene un estado que se actualiza dinámicamente, se debe admitir esta propiedad para que una tecnología de asistencia pueda recibir actualizaciones cuando cambia el estado del elemento.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ItemTypeProperty>|Vea las notas.|Este es el valor de cadena que transmite al usuario final el objeto subyacente que representa el elemento. Algunos ejemplos son "Archivo multimedia" o "Contacto".|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Los controles de elemento de datos no tienen una etiqueta de texto estático.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"elemento de datos"|Cadena localizada que corresponde al tipo de control DataItem.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vea las notas.|El control de elemento de datos siempre contiene un elemento de texto principal que está relacionado con lo que el usuario asociaría como el identificador más semántico para el elemento.|  
  
<a name="_Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Patrones de control necesarios para la automatización de la interfaz de usuario  
 En la tabla siguiente se muestran los patrones de control de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] necesarios para que todos los controles de elemento de datos los admitan. Para más información sobre los patrones de control, vea [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).  
  
|Patrón de control|Compatibilidad|Notas|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Depende|Si el elemento de datos se puede expandir o contraer para mostrar y ocultar información, se debe admitir el patrón ExpandCollapse.|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider>|Depende|Los elementos de datos admitirán el patrón GridItem cuando una colección de elementos de datos esté disponible dentro de un contenedor en el que se pueda navegar espacialmente de un elemento a otro.|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider>|Depende|Todos los elementos de datos admiten la capacidad de desplazamiento para verlos con el patrón ScrollItem cuando su contenedor de datos tiene más elementos de los que caben en la pantalla.|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Sí|Todos los elementos de datos deben admitir el patrón SelectionItem para indicar cuándo está seleccionado el elemento.|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider>|Depende|Si el elemento de datos contenido dentro de un tipo de control DataGrid admitirá este patrón.|  
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Depende|Si el elemento de datos contiene un estado que se puede recorrer cíclicamente.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|Depende|Si el texto primario del elemento de datos es editable, se debe admitir el patrón Value.|  
  
<a name="Working_with_Data_Items_in_Large_Lists"></a>   
## <a name="working-with-data-items-in-large-lists"></a>Trabajar con elementos de datos en listas grandes  
 Las listas grandes suelen ser datos virtualizados dentro de marcos [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] para ayudar al rendimiento. Debido a esto, un cliente de Automatización de la interfaz de usuario no puede usar la característica de consulta [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] para extraer el contenido del árbol completo de la misma manera en que lo hace con otros contenedores de elementos. Un cliente debe desplazar el elemento a la vista (o expandir el control para mostrar todas las opciones importantes) antes de acceder al conjunto completo de información del elemento de datos.  
  
 Al llamar a `SetFocus` en la [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] del elemento de datos, el caso [!INCLUDE[TLA#tla_winexpl](../../../includes/tlasharptla-winexpl-md.md)] devolverá correctamente y el foco se establecerá en la edición dentro del subárbol del elemento de datos.  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Eventos de automatización de la interfaz de usuario necesarios  
 En la siguiente tabla se muestran los eventos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que deben admitir todos los controles de elemento de datos. Para más información sobre eventos, vea [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] |Compatibilidad|Notas|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Requerido|Ninguna|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Obligatorio|Ninguna|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Obligatorio|Ninguna|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>evento cambiado por propiedad.|Obligatorio|Ninguna|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> .|Obligatorio|Ninguna|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Obligatorio|Ninguna|  
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Depende|Ninguna|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> .|Depende|Ninguna|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>|Obligatorio|Ninguna|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|Obligatorio|Ninguna|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Obligatorio|Ninguna|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> .|Depende|Ninguna|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> .|Depende|Ninguna|  
  
<a name="Data_Item_Control_Type_Example"></a>   
## <a name="dataitem-control-type-example"></a>Ejemplo de tipo de control DataItem  
 En la imagen siguiente se muestra un tipo de control DataItem en un control List View con compatibilidad con información completa para las columnas.  
  
 ![Gráfico de un control List View con dos elementos de datos](../../../docs/framework/ui-automation/media/uiauto-data-grid-detailed.GIF "uiauto_data_grid_detailed")  
  
 Las vistas de control y de contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que pertenece al control del elemento de datos se muestran a continuación. Los patrones de control de cada elemento de automatización se muestran entre paréntesis. El grupo "Contoso" también forma parte de la cuadrícula del control de host Data Grid.  
  
|Árbol[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] - Vista de control|Árbol[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] - Vista de contenido|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|-Grupo "Contoso" (tabla, cuadrícula)<br />-DataItem "cuentas Receivable.doc" (TableItem, GridItem, SelectionItem, Invoke)<br />-Image "Accounts Receivable.doc"<br />-Editar "Name" (TableItem, GridItem, valor "Accounts Receivable.doc")<br />-Editar "Fecha de modificación" (TableItem, GridItem, valor "25/8/2006 3:29 PM")<br />-Editar "Tamaño" (GridItem, TableItem, valor "11.0 KB)<br />-DataItem "cuentas Payable.doc" (TableItem, GridItem, SelectionItem, Invoke)<br />-   ...|-Grupo "Contoso" (tabla, cuadrícula)<br />-DataItem "cuentas Receivable.doc" (TableItem, GridItem, SelectionItem, Invoke)<br />-Image "Accounts Receivable.doc"<br />-Editar "Name" (TableItem, GridItem, valor "Accounts Receivable.doc")<br />-Editar "Fecha de modificación" (TableItem, GridItem, valor "25/8/2006 3:29 PM")<br />-Editar "Tamaño" (GridItem, TableItem, valor "11.0 KB)<br />-DataItem "cuentas Payable.doc" (TableItem, GridItem, SelectionItem, Invoke)<br />-   …|  
  
 Si una cuadrícula representa una lista de elementos seleccionables, los elementos de la interfaz de usuario correspondientes se pueden exponer con el tipo de control ListItem en lugar del tipo de control DataItem. En el ejemplo anterior, los elementos DataItem ("Accounts Receivable.doc" y "Accounts Payable.doc") de Group ("Contoso") se pueden mejorar si se exponen como tipos de control ListItem, porque ese tipo ya admite el patrón de control SelectionItem.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Automation.ControlType.DataItem>  
 [Información general sobre tipos de control de Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)  
 [Información general sobre la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-overview.md)
