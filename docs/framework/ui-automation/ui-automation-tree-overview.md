---
title: Información general sobre el árbol de la UI Automation
description: Lea información general sobre los árboles de automatización de la interfaz de usuario. Obtenga información sobre las distintas vistas de un árbol de automatización de la interfaz de usuario, como la vista sin formato, la vista de control y la vista de contenido.
ms.date: 03/30/2017
helpviewer_keywords:
- automation tree
- UI Automation, tree
ms.assetid: 03b98058-bdb3-47a0-8ff7-45e6cdf67166
ms.openlocfilehash: 99735007a3058f45585e812e2ec3f955d7a2c30d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258678"
---
# <a name="ui-automation-tree-overview"></a>Información general sobre el árbol de la UI Automation

> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 Los productos de tecnología de asistencia y los scripts de prueba navegan por el árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] para reunir información sobre [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] y sus elementos.  
  
 En el [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árbol hay un elemento raíz ( <xref:System.Windows.Automation.AutomationElement.RootElement%2A> ) que representa el escritorio actual y cuyos elementos secundarios representan las ventanas de la aplicación. Cada uno de estos elementos secundarios puede contener elementos que representan partes de [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], como menús, botones, barras de herramientas y cuadros de lista. A su vez, estos elementos pueden contener elementos, como elementos de lista.  
  
 El árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] no es una estructura fija y casi nunca se presenta en su totalidad, ya que podría contener miles de elementos. Partes de él se crean conforme se necesitan y pueden experimentar cambios a medida que se agregan, mueven o quitan elementos.  
  
 Los proveedores de Automatización de la interfaz de usuario admiten el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] mediante la implementación de navegación entre los elementos dentro de un fragmento, que consta de una raíz (normalmente hospedada en una ventana) y un subárbol. Sin embargo, a los proveedores no les afecta la navegación de un control a otro. Esto lo administra el núcleo de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], utilizando la información de los proveedores de ventana predeterminados.  
  
<a name="uiautomation_tree_view"></a>

## <a name="views-of-the-automation-tree"></a>Vistas del árbol de automatización  

 Es posible filtrar el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] para crear vistas que solo contengan aquellos objetos <xref:System.Windows.Automation.AutomationElement> que sean relevantes para un cliente determinado. Este enfoque permite a los clientes personalizar la estructura presentada a través de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] para sus necesidades concretas.  
  
 El cliente tiene dos maneras de personalizar la vista: mediante ámbito y mediante filtrado. El ámbito consiste en definir el alcance de la vista, a partir de un elemento base: por ejemplo, la aplicación podría querer buscar únicamente los elementos secundarios directos del escritorio o todos los descendientes de una ventana de aplicación. El filtrado implica definir los tipos de elementos que deben incluirse en la vista.  
  
 Los proveedores de UI Automation admiten el filtrado mediante la definición de propiedades en los elementos, incluidas las propiedades <xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty> y <xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ofrece tres vistas predeterminadas. Estas vistas se definen mediante el tipo de filtrado realizado; el ámbito de cualquier vista lo define la aplicación. Además, la aplicación puede aplicar otros filtros en las propiedades; por ejemplo, para incluir únicamente controles habilitados en una vista de control.  
  
<a name="uiautomation_raw_view"></a>

### <a name="raw-view"></a>Vista sin formato  

 La vista sin formato del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] es el árbol completo de objetos <xref:System.Windows.Automation.AutomationElement> del que el escritorio es la raíz. La vista sin formato sigue estrechamente la estructura de programación nativa de una aplicación y es, por tanto, la vista más detallada disponible. También es la base sobre la que se crean las otras vistas del árbol. Dado que esta vista depende del [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] marco subyacente, la vista sin formato de un [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] botón tendrá una vista sin formato diferente de la de un botón de Win32.  
  
 La vista sin formato se obtiene mediante la búsqueda de elementos sin especificar propiedades o usando el elemento <xref:System.Windows.Automation.TreeWalker.RawViewWalker> para navegar por el árbol.  
  
<a name="uiautomation_control_view"></a>

### <a name="control-view"></a>Vista de control  

 La vista de control del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] simplifica la tarea del producto de tecnología de asistencia de la descripción de [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] al usuario final y le ayuda a interactuar con la aplicación, ya que se asigna estrechamente a la estructura [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] que percibe un usuario final.  
  
 La vista de control es un subconjunto de la vista sin formato. Incluye todos los elementos [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] de la vista sin formato que un usuario final entendería como interactivos o que contribuyen a la estructura lógica del control en la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Algunos ejemplos de elementos [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] que contribuyen a la estructura lógica de la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], pero no son interactivos por sí mismos, son los contenedores de elementos como los encabezados de vistas de lista, las barras de herramientas, los menús y la barra de estado. En la vista de control no se verán los elementos no interactivos que se utilizan simplemente para fines decorativos o de diseño. Un ejemplo es un panel utilizado únicamente para organizar los controles en un cuadro de diálogo, pero no contiene ninguna información en sí. Los elementos no interactivos que se verán en la vista de control son gráficos con información y texto estático en un cuadro de diálogo. Los elementos no interactivos que se incluyen en la vista de control no pueden recibir el foco del teclado.  
  
 La vista de control se obtiene mediante la búsqueda de elementos que tengan la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A> establecida en `true` o mediante el elemento <xref:System.Windows.Automation.TreeWalker.ControlViewWalker> para navegar por el árbol.  
  
<a name="uiautomation_content_view"></a>

### <a name="content-view"></a>Vista de contenido  

 La vista de contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] es un subconjunto de la vista de control. Contiene elementos de [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] que transmiten la información verdadera en una interfaz de usuario, entre la que se incluyen los elementos de [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] que pueden recibir el foco del teclado y texto que no es una etiqueta en un elemento [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Por ejemplo, los valores de un cuadro combinado desplegable aparecerán en la vista de contenido porque representan la información que usa un usuario final. En la vista de contenido, un cuadro combinado y un cuadro de lista se representan como una colección de elementos de [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], donde se pueden seleccionar uno o, quizás, varios elementos. El hecho de que uno siempre esté abierto y otro pueda expandirse y contraerse es irrelevante en la vista de contenido, ya que está diseñada para mostrar los datos, o el contenido, que se muestran al usuario.  
  
 La vista de contenido se obtiene mediante la búsqueda de elementos que tengan la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A> establecida en `true` o mediante el elemento <xref:System.Windows.Automation.TreeWalker.ContentViewWalker> para navegar por el árbol.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Automation.AutomationElement>
- [Información general sobre UI Automation](ui-automation-overview.md)
