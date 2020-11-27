---
title: Compatibilidad de UI Automation para el tipo de control Document
description: Obtenga información sobre la compatibilidad de UI Automation para el tipo de control Document. Obtenga información sobre la estructura de árbol necesaria, las propiedades, los patrones de control y los eventos.
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Document
- Document control type
- UI Automation, Document control type
ms.assetid: a79d594b-1ca0-4543-8dac-afd2c645201d
ms.openlocfilehash: 964793a9bda6c5db01313578c541557dc62fab73
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96277977"
---
# <a name="ui-automation-support-for-the-document-control-type"></a>Compatibilidad de UI Automation para el tipo de control Document

> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se ofrece información sobre la compatibilidad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] con el tipo de control Document. En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], un tipo de control es un conjunto de condiciones que un control debe cumplir para poder usar la propiedad <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Entre las condiciones se incluyen instrucciones específicas para la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , los patrones de control y los valores de propiedad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Los controles de documento permiten a un usuario ver y manipular varias páginas de texto. A diferencia de los controles de edición que solo admiten una línea simple de texto sin formato, los controles de documento pueden hospedar texto con estilo y formato enriquecidos.  
  
 En las secciones siguientes se definen la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necesaria, las propiedades, los patrones de control y los eventos para el tipo de control Document. Los [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requisitos de se aplican a todos los controles de documento, ya sean [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] , Win32 o Windows Forms.  
  
## <a name="required-ui-automation-tree-structure"></a>Estructura de árbol de Automatización de la interfaz de usuario necesaria  

 En la tabla siguiente se describe la vista de control y la vista de contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que pertenece a los controles de documento y se describe lo que puede incluirse en cada vista. Para más información sobre el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Vista de control|Vista de contenido|  
|------------------|------------------|  
|Documento<br /><br /> -Varía|Documento<br /><br /> -Varía|  
  
## <a name="required-ui-automation-properties"></a>Propiedades de Automatización de la interfaz de usuario necesarias  

 En la tabla siguiente se muestran las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que tienen valor o una definición especialmente relevante para los controles de documento. Para obtener más información sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] las propiedades, vea [UI Automation Properties for clients](ui-automation-properties-for-clients.md).  
  
|Propiedad[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Valor|Notas|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vea las notas.|El valor de esta propiedad debe ser único en todos los controles de una aplicación.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vea las notas.|El rectángulo exterior que contiene el control completo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vea las notas.|El documento tiene un punto en el que se puede hacer clic que provocará que el foco pase al documento de uno de sus elementos del contenedor de documento.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Documento|Este valor es el mismo para todos los marcos de trabajo de la interfaz de usuario.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|El control de documento siempre se incluye en la vista de contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|El control de documento siempre se incluye en la vista de control del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vea las notas.|Si el control puede recibir el foco del teclado, debe admitir esta propiedad.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Vea las notas.|El valor de esta propiedad debe ser la etiqueta del control de documento. Normalmente, se utiliza el título del documento.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"documento"|Cadena localizada que corresponde al tipo de control Document.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vea las notas.|El control de documento normalmente recibe sus nombres del nombre de archivo desde el que se carga. A menudo, esto se muestra en el título de un marco o una ventana contenedora.|  
  
## <a name="required-ui-automation-control-patterns"></a>Patrones de control de Automatización de la interfaz de usuario necesarios  

 En la tabla siguiente se muestran los patrones de control de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que deben admitir los controles de documento. Para más información sobre los patrones de control, vea [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Patrón de control|Soporte técnico|Notas|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollProvider>|Depende|El control de documento puede abarcar más de lo que puede la ventanilla. El control debe admitir el patrón de control Scroll si el contenido es desplazable.|  
|<xref:System.Windows.Automation.Provider.ITextProvider>|Requerido|El control de documento puede abarcar más de lo que puede la ventanilla. El control debe admitir el patrón de control Scroll si el contenido es desplazable.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|Nunca|El control de documento no admite este patrón de control porque el contenido del control a menudo abarca más de una página. Los clientes de Automatización de la interfaz de usuario deben usar <xref:System.Windows.Automation.TextPattern> para obtener información de texto sobre un documento.|  
  
## <a name="required-ui-automation-events"></a>Eventos de Automatización de la interfaz de usuario necesarios  

 En la tabla siguiente se muestran los eventos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que deben admitir todos los controles de documento. Para más información sobre eventos, vea [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Soporte técnico|Notas|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Obligatorio|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Requerido|None|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Obligatorio|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> .|Requerido|None|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Depende|Si el control admite el patrón de control Selection, debe admitir este evento.|  
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextSelectionChangedEvent>|Requerido|None|  
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextChangedEvent>|Obligatorio|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> .|Nunca|None|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Automation.ControlType.Document>
- [Información general sobre tipos de control de UI Automation](ui-automation-control-types-overview.md)
- [Información general sobre UI Automation](ui-automation-overview.md)
