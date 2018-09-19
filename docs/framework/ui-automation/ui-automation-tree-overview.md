---
title: Información general sobre el árbol de la UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- automation tree
- UI Automation, tree
ms.assetid: 03b98058-bdb3-47a0-8ff7-45e6cdf67166
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 042f3f82a88e987131145f38c1d8f5ecfa8dc487
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46007469"
---
# <a name="ui-automation-tree-overview"></a>Información general sobre el árbol de la UI Automation
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Navegar por los productos de tecnología y los scripts de prueba el [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árbol para reunir información sobre la [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] y sus elementos.  
  
 Dentro de la [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] hay árbol es un elemento raíz (<xref:System.Windows.Automation.AutomationElement.RootElement%2A>) que representa el escritorio actual y cuyos elementos secundarios representan ventanas de la aplicación. Cada uno de estos elementos secundarios puede contener elementos que representan partes de [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] como menús, botones, barras de herramientas y cuadros de lista. A su vez, estos elementos pueden contener elementos, como elementos de lista.  
  
 El [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árbol no es una estructura fija y casi nunca se presenta en su totalidad, ya que podría contener miles de elementos. Partes de él se crean conforme se necesitan y pueden experimentar cambios a medida que se agregan, mueven o quitan elementos.  
  
 Los proveedores de UI Automation admiten el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] mediante la implementación de navegación entre los elementos dentro de un fragmento, que consta de una raíz (normalmente hospedada en una ventana) y un subárbol. Sin embargo, a los proveedores no les afecta la navegación de un control a otro. Administra la [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] núcleo, utilizando la información de los proveedores de ventana predeterminados.  
  
<a name="uiautomation_tree_view"></a>   
## <a name="views-of-the-automation-tree"></a>Vistas del árbol de automatización  
 El [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árbol se puede filtrar para crear vistas que contienen sólo aquellos <xref:System.Windows.Automation.AutomationElement> objetos relevantes para un cliente determinado. Este enfoque permite a los clientes personalizar la estructura presentada a través de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] para sus necesidades concretas.  
  
 El cliente tiene dos maneras de personalizar la vista: mediante ámbito y mediante filtrado. El ámbito consiste en definir el alcance de la vista, a partir de un elemento base: por ejemplo, la aplicación podría querer buscar únicamente los elementos secundarios directos del escritorio o todos los descendientes de una ventana de aplicación. El filtrado implica definir los tipos de elementos que deben incluirse en la vista.  
  
 Los proveedores de UI Automation admiten el filtrado mediante la definición de propiedades en los elementos, incluidas las propiedades <xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty> y <xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ofrece tres vistas predeterminadas. Estas vistas se definen mediante el tipo de filtrado realizado; el ámbito de cualquier vista lo define la aplicación. Además, la aplicación puede aplicar otros filtros en las propiedades; por ejemplo, para incluir únicamente controles habilitados en una vista de control.  
  
<a name="uiautomation_raw_view"></a>   
### <a name="raw-view"></a>Vista sin formato  
 La vista sin formato de la [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árbol es el árbol completo de <xref:System.Windows.Automation.AutomationElement> objetos para el que el escritorio es la raíz. La vista sin formato sigue estrechamente la estructura de programación nativa de una aplicación y es, por tanto, la vista más detallada disponible. También es la base sobre la que se crean las otras vistas del árbol. Dado que esta vista depende subyacente [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] framework, la vista sin formato de un [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] botón tendrá una vista sin formato diferente que una [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] botón.  
  
 La vista sin formato se obtiene mediante la búsqueda de elementos sin especificar propiedades o mediante el <xref:System.Windows.Automation.TreeWalker.RawViewWalker> para navegar por el árbol.  
  
<a name="uiautomation_control_view"></a>   
### <a name="control-view"></a>Vista de control  
 La vista de control de la [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árbol simplifica la tarea del producto de tecnología de asistencia de describir la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] para el usuario final y le ayuda a ese usuario final interactúe con la aplicación porque se asigna estrechamente a la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] estructura percibe un usuario final.  
  
 La vista de control es un subconjunto de la vista sin formato. Incluye todas [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elementos desde la vista sin formato que un usuario final entendería como interactivos o que contribuyen a la estructura lógica del control en el [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Ejemplos de [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elementos que contribuyen a la estructura lógica de la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], pero no son interactivos a sí mismos, son contenedores de elementos como los encabezados de vista de lista, barras de herramientas, menús y la barra de estado. En la vista de control no se verán los elementos no interactivos que se utilizan simplemente para fines decorativos o de diseño. Un ejemplo es un panel utilizado únicamente para organizar los controles en un cuadro de diálogo, pero no contiene ninguna información en sí. Los elementos no interactivos que se verán en la vista de control son gráficos con información y texto estático en un cuadro de diálogo. Los elementos no interactivos que se incluyen en la vista de control no pueden recibir el foco del teclado.  
  
 La vista de control se obtiene mediante la búsqueda de elementos que tengan la <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A> propiedad establecida en `true`, o mediante el <xref:System.Windows.Automation.TreeWalker.ControlViewWalker> para navegar por el árbol.  
  
<a name="uiautomation_content_view"></a>   
### <a name="content-view"></a>Vista de contenido  
 La vista de contenido de la [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árbol es un subconjunto de la vista de control. Contiene [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elementos que transmiten la información verdadera en una interfaz de usuario, incluidos [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] los elementos que pueden recibir el foco de teclado y texto que no es una etiqueta en un [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elemento. Por ejemplo, los valores de un cuadro combinado desplegable aparecerán en la vista de contenido porque representan la información que usa un usuario final. En la vista de contenido, un cuadro combinado y un cuadro de lista se representan como una colección de [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elementos donde se puede seleccionar uno, o quizás más de uno, el elemento. El hecho de que uno siempre esté abierto y otro pueda expandirse y contraerse es irrelevante en la vista de contenido, ya que está diseñada para mostrar los datos, o el contenido, que se muestran al usuario.  
  
 La vista de contenido se obtiene mediante la búsqueda de elementos que tengan la <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A> propiedad establecida en `true`, o mediante el <xref:System.Windows.Automation.TreeWalker.ContentViewWalker> para navegar por el árbol.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Automation.AutomationElement>  
 [Información general sobre la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-overview.md)
