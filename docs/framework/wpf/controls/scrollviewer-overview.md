---
title: "Informaci&#243;n general sobre ScrollViewer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "controles, ScrollViewer"
  - "ScrollViewer (control), acerca de ScrollViewer (control)"
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Informaci&#243;n general sobre ScrollViewer
El contenido de una interfaz de usuario suele ser mayor que el área de presentación de la pantalla de un equipo.  El control <xref:System.Windows.Controls.ScrollViewer> proporciona una manera cómoda de habilitar el desplazamiento del contenido en las aplicaciones de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  En este tema se presenta el elemento <xref:System.Windows.Controls.ScrollViewer> y se proporcionan varios ejemplos de su uso.  
  
 Este tema contiene las siguientes secciones:  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [Control ScrollViewer](#what_is_a_scrollviewer_element)  
  
-   [Desplazamiento físicoy lógico](#scrollviewer_physical_vs_logical)  
  
-   [Definir y utilizar un elemento ScrollViewer](#scrollviewer_markup_syntax_and_sample)  
  
-   [Aplicar estilos a un control ScrollViewer](#scrollviewer_styling_scrollviewer)  
  
-   [Paginar documentos](#scrollviewer_scroll_vs_paginate)  
  
-   [Related Topics](#seeAlsoToggle)  
  
<a name="what_is_a_scrollviewer_element"></a>   
## Control ScrollViewer  
 Existen dos elementos predefinidos que habilitan el desplazamiento en las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: <xref:System.Windows.Controls.Primitives.ScrollBar> y <xref:System.Windows.Controls.ScrollViewer>.  El control <xref:System.Windows.Controls.ScrollViewer> encapsula los elementos <xref:System.Windows.Controls.Primitives.ScrollBar> horizontales y verticales, así como un contenedor de contenido \(como un elemento <xref:System.Windows.Controls.Panel>\) para mostrar otros elementos visibles en un área desplazable.  Debe crear un objeto personalizado a fin de utilizar el elemento <xref:System.Windows.Controls.Primitives.ScrollBar> para el desplazamiento del contenido.  Sin embargo, puede utilizar el elemento <xref:System.Windows.Controls.ScrollViewer> por sí solo, porque es un control compuesto que encapsula la funcionalidad de <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
 El control <xref:System.Windows.Controls.ScrollViewer> responde a los comandos del mouse y del teclado, y define numerosos métodos con los que puede desplazarse el contenido en incrementos predeterminados.  El evento <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> puede utilizarse para detectar cambios en el estado de <xref:System.Windows.Controls.ScrollViewer>.  
  
 <xref:System.Windows.Controls.ScrollViewer> solo puede tener un elemento secundario, que normalmente es un elemento <xref:System.Windows.Controls.Panel> que puede hospedar una colección de elementos <xref:System.Windows.Controls.Panel.Children%2A>.  La propiedad <xref:System.Windows.Controls.ContentPresenter.Content%2A> define el único elemento secundario de <xref:System.Windows.Controls.ScrollViewer>.  
  
<a name="scrollviewer_physical_vs_logical"></a>   
## Desplazamiento físicoy lógico  
 El desplazamiento físico se utiliza para desplazar el contenido en un incremento físico predeterminado, que suele ser un valor declarado en píxeles.  El desplazamiento lógico se utiliza para desplazarse al elemento siguiente en el árbol lógico.  El desplazamiento físico es el comportamiento de desplazamiento predeterminado para la mayoría de los elementos <xref:System.Windows.Controls.Panel>.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite ambos tipos de desplazamiento.  
  
#### Interfaz IScrollInfo  
 La interfaz <xref:System.Windows.Controls.Primitives.IScrollInfo> representa el área de desplazamiento principal dentro de un control <xref:System.Windows.Controls.ScrollViewer> o derivado.  Esta interfaz define las propiedades de desplazamiento y los métodos implementados por los elementos <xref:System.Windows.Controls.Panel> que requieren el desplazamiento por unidades lógicas, no por incrementos físicos.  Convertir una instancia de <xref:System.Windows.Controls.Primitives.IScrollInfo> en un <xref:System.Windows.Controls.Panel> derivado y, a continuación, utilizar sus métodos de desplazamiento proporciona una manera útil de desplazarse hasta la unidad lógica siguiente en una colección secundaria, en lugar de hacerlo por incrementos en píxeles.  De manera predeterminada, el control <xref:System.Windows.Controls.ScrollViewer> admite el desplazamiento por unidades físicas.  
  
 <xref:System.Windows.Controls.StackPanel> y <xref:System.Windows.Controls.VirtualizingStackPanel> implementan <xref:System.Windows.Controls.Primitives.IScrollInfo> y admiten nativamente el desplazamiento lógico.  En los controles de diseño que admiten de manera nativa el desplazamiento lógico, puede conseguirse el desplazamiento físico si se ajusta el elemento <xref:System.Windows.Controls.Panel> host en un control <xref:System.Windows.Controls.ScrollViewer> y se establece la propiedad <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> en `false`.  
  
 En el ejemplo de código siguiente se muestra cómo convertir una instancia de <xref:System.Windows.Controls.Primitives.IScrollInfo> en un control <xref:System.Windows.Controls.StackPanel> y utilizar los métodos de desplazamiento del contenido \(<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> y <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>\) definidos por la interfaz.  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>   
## Definir y utilizar un elemento ScrollViewer  
 En el ejemplo siguiente se crea un objeto <xref:System.Windows.Controls.ScrollViewer> en una ventana que contiene texto y un rectángulo.  Los elementos <xref:System.Windows.Controls.Primitives.ScrollBar> solo aparecen cuando son necesarios.  Cuando se cambia el tamaño de la ventana, los elementos <xref:System.Windows.Controls.Primitives.ScrollBar> aparecen y desaparecen, ya que se actualizan los valores de las propiedades <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> y <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A>.  
  
 [!code-cpp[ScrollViewer#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xml[ScrollViewer#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>   
## Aplicar estilos a un control ScrollViewer  
 Al igual que todos los controles de Windows Presentation Foundation, pueden aplicarse estilos a <xref:System.Windows.Controls.ScrollViewer> para cambiar su comportamiento de representación predeterminado.  Para obtener información adicional sobre la aplicación de estilos a los controles, vea [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>   
## Paginar documentos  
 Para el contenido de los documentos, una alternativa al desplazamiento es elegir un contenedor de documento que admita la paginación.  <xref:System.Windows.Documents.FlowDocument> es para los documentos que están diseñados para ser hospedados en un control de visualización, como <xref:System.Windows.Controls.FlowDocumentPageViewer>, que permite paginar el contenido por varias páginas, evitando la necesidad de desplazarse.  <xref:System.Windows.Controls.DocumentViewer> proporciona una solución para ver contenido <xref:System.Windows.Documents.FixedDocument>, que usa el desplazamiento tradicional para mostrar el contenido fuera del dominio kerberos del área de presentación.  
  
 Para obtener información adicional sobre formatos de documentos y opciones de presentación, vea [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
## Vea también  
 <xref:System.Windows.Controls.ScrollViewer>   
 <xref:System.Windows.Controls.Primitives.ScrollBar>   
 <xref:System.Windows.Controls.Primitives.IScrollInfo>   
 [Create a Scroll Viewer](http://msdn.microsoft.com/es-es/c8e46af7-b417-441b-aa30-791cbdbd43ef)   
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Estilos y plantillas de ScrollBar](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)   
 [Controles](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)