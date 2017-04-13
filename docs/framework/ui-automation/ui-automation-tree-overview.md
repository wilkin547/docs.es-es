---
title: "Informaci&#243;n general sobre el &#225;rbol de la UI Automation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "árbol de automatización"
  - "Automatización de la interfaz de usuario, árbol"
ms.assetid: 03b98058-bdb3-47a0-8ff7-45e6cdf67166
caps.latest.revision: 25
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 25
---
# Informaci&#243;n general sobre el &#225;rbol de la UI Automation
> [!NOTE]
>  Esta documentación está dirigida a desarrolladores de .NET Framework que quieran usar los recursos administrados [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clases definidas en el <xref:System.Windows.Automation> espacio de nombres. Para obtener la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Navegar por los productos de tecnología de asistencia y los scripts de prueba el [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árbol para reunir información sobre la [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] y sus elementos.  
  
 Dentro de la [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] existe árbol es un elemento raíz (<xref:System.Windows.Automation.AutomationElement.RootElement%2A>) que representa el escritorio actual y cuyos elementos secundarios representan ventanas de la aplicación. Cada uno de estos elementos secundarios puede contener elementos que representan partes de [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] como menús, botones, barras de herramientas y cuadros de lista. A su vez, estos elementos pueden contener elementos, como elementos de lista.  
  
 El [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árbol no es una estructura fija y casi nunca se presenta en su totalidad, ya que podría contener miles de elementos. Partes de él se crean conforme se necesitan y pueden experimentar cambios a medida que se agregan, mueven o quitan elementos.  
  
 Los proveedores de UI Automation admiten el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] mediante la implementación de navegación entre los elementos dentro de un fragmento, que consta de una raíz (normalmente hospedada en una ventana) y un subárbol. Sin embargo, a los proveedores no les afecta la navegación de un control a otro. Esto es administrado por el [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] principal, utilizando la información de los proveedores de ventana predeterminado.  
  
<a name="uiautomation_tree_view"></a>   
## <a name="views-of-the-automation-tree"></a>Vistas del árbol de Automation  
 El [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árbol puede filtrarse para crear vistas que contienen sólo los <xref:System.Windows.Automation.AutomationElement> objetos relevantes para un cliente determinado. Este enfoque permite a los clientes personalizar la estructura presentada a través de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] a sus necesidades concretas.  
  
 El cliente tiene dos maneras de personalizar la vista: mediante ámbito y mediante filtrado. El ámbito consiste en definir el alcance de la vista, a partir de un elemento base: por ejemplo, la aplicación podría querer buscar únicamente los elementos secundarios directos del escritorio o todos los descendientes de una ventana de aplicación. El filtrado implica definir los tipos de elementos que deben incluirse en la vista.  
  
 Proveedores de automatización de la interfaz de usuario admiten el filtrado definiendo propiedades en los elementos, incluidos el <xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty> y <xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty> propiedades.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]proporciona tres vistas predeterminadas. Estas vistas se definen mediante el tipo de filtrado realizado; el ámbito de cualquier vista lo define la aplicación. Además, la aplicación puede aplicar otros filtros en las propiedades; por ejemplo, para incluir únicamente controles habilitados en una vista de control.  
  
<a name="uiautomation_raw_view"></a>   
### <a name="raw-view"></a>Vista sin formato  
 La vista sin formato de la [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árbol es el árbol completo de <xref:System.Windows.Automation.AutomationElement> objetos para los que la raíz es el escritorio. La vista sin formato sigue estrechamente la estructura de programación nativa de una aplicación y es, por tanto, la vista más detallada disponible. También es la base sobre la que se crean las otras vistas del árbol. Porque depende de esta vista subyacente [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] framework, la vista sin formato de un [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] botón tendrá una vista diferente sin procesar de un [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] botón.  
  
 La vista sin formato se obtiene mediante la búsqueda de elementos sin especificar las propiedades o mediante la <xref:System.Windows.Automation.TreeWalker.RawViewWalker> para navegar en el árbol.  
  
<a name="uiautomation_control_view"></a>   
### <a name="control-view"></a>Vista de control  
 La vista de control de la [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árbol simplifica la tarea del producto de tecnología de asistencia de describir la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] para el usuario final y le ayuda a ese usuario final interactuar con la aplicación porque se asigna estrechamente a la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] estructura percibida el usuario final.  
  
 La vista de control es un subconjunto de la vista sin formato. Todos los incluye [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elementos de la vista sin formato que un usuario final entendería como interactivos o contribuyentes a la estructura lógica del control en el [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Ejemplos de [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elementos que contribuyen a la estructura lógica de la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], pero no son interactivos a sí mismos, son contenedores de elementos, como encabezados de vista de lista, barras de herramientas, menús y la barra de estado. En la vista de control no se verán los elementos no interactivos que se utilizan simplemente para fines decorativos o de diseño. Un ejemplo es un panel utilizado únicamente para organizar los controles en un cuadro de diálogo, pero no contiene ninguna información en sí. Los elementos no interactivos que se verán en la vista de control son gráficos con información y texto estático en un cuadro de diálogo. Los elementos no interactivos que se incluyen en la vista de control no pueden recibir el foco del teclado.  
  
 La vista de control se obtiene mediante la búsqueda de elementos que tienen la <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A> propiedad establecida en `true`, o mediante la <xref:System.Windows.Automation.TreeWalker.ControlViewWalker> para navegar en el árbol.  
  
<a name="uiautomation_content_view"></a>   
### <a name="content-view"></a>Vista de contenido  
 La vista de contenido de la [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árbol es un subconjunto de la vista de control. Contiene [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elementos que transmiten la información en true en una interfaz de usuario, incluyendo [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elementos que pueden recibir el foco de teclado y texto que no es una etiqueta en un [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elemento. Por ejemplo, los valores de un cuadro combinado desplegable aparecerán en la vista de contenido porque representan la información que usa un usuario final. En la vista de contenido, un cuadro combinado y el cuadro de lista son ambos representados como una colección de [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elementos donde puede seleccionar uno o más que un elemento. El hecho de que uno siempre esté abierto y otro pueda expandirse y contraerse es irrelevante en la vista de contenido, ya que está diseñada para mostrar los datos, o el contenido, que se muestran al usuario.  
  
 La vista de contenido se obtiene mediante la búsqueda de elementos que tienen la <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A> propiedad establecida en `true`, o mediante la <xref:System.Windows.Automation.TreeWalker.ContentViewWalker> para navegar en el árbol.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Automation.AutomationElement>   
 [Información general sobre la automatización de interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-overview.md)