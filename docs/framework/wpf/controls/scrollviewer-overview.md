---
title: Información general sobre ScrollViewer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], ScrollViewer
- ScrollViewer control [WPF], about ScrollViewer control
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
ms.openlocfilehash: 993f3c861cbead88df3503eb01f18e5d1f69e2d8
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458438"
---
# <a name="scrollviewer-overview"></a>Información general sobre ScrollViewer
El contenido en una interfaz de usuario suele ser mayor que el área de presentación de la pantalla del equipo. El control <xref:System.Windows.Controls.ScrollViewer> proporciona una manera cómoda de habilitar el desplazamiento de contenido en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicaciones. En este tema se presenta el elemento <xref:System.Windows.Controls.ScrollViewer> y se proporcionan varios ejemplos de uso.  
  
<a name="what_is_a_scrollviewer_element"></a>   
## <a name="the-scrollviewer-control"></a>Control ScrollViewer  
 Hay dos elementos predefinidos que permiten el desplazamiento en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones: <xref:System.Windows.Controls.Primitives.ScrollBar> y <xref:System.Windows.Controls.ScrollViewer>. El control <xref:System.Windows.Controls.ScrollViewer> encapsula los elementos de <xref:System.Windows.Controls.Primitives.ScrollBar> horizontal y vertical y un contenedor de contenido (por ejemplo, un elemento <xref:System.Windows.Controls.Panel>) para mostrar otros elementos visibles en un área desplazable. Debe crear un objeto personalizado para poder usar el elemento <xref:System.Windows.Controls.Primitives.ScrollBar> para el desplazamiento de contenido. Sin embargo, puede usar el elemento <xref:System.Windows.Controls.ScrollViewer> por sí solo porque es un control compuesto que encapsula <xref:System.Windows.Controls.Primitives.ScrollBar> funcionalidad.  
  
 El control <xref:System.Windows.Controls.ScrollViewer> responde a los comandos del mouse y del teclado, y define numerosos métodos con los que se va a desplazar el contenido mediante incrementos predeterminados. Puede usar el evento <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> para detectar un cambio en un estado de <xref:System.Windows.Controls.ScrollViewer>.  
  
 Un <xref:System.Windows.Controls.ScrollViewer> solo puede tener un elemento secundario, normalmente un elemento <xref:System.Windows.Controls.Panel> que puede hospedar una colección <xref:System.Windows.Controls.Panel.Children%2A> de elementos. La propiedad <xref:System.Windows.Controls.ContentPresenter.Content%2A> define el único elemento secundario del <xref:System.Windows.Controls.ScrollViewer>.  
  
<a name="scrollviewer_physical_vs_logical"></a>   
## <a name="physical-vs-logical-scrolling"></a>Desplazamientos físicos y lógicos  
 El desplazamiento físico se utiliza para desplazar el contenido mediante incrementos físicos predeterminados, normalmente por un valor que se declara en píxeles. El desplazamiento lógico se utiliza para desplazarse al elemento siguiente del árbol lógico. El desplazamiento físico es el comportamiento de desplazamiento predeterminado para la mayoría de los elementos de <xref:System.Windows.Controls.Panel>. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite ambos tipos de desplazamiento.  
  
#### <a name="the-iscrollinfo-interface"></a>Interfaz IScrollInfo  
 La interfaz <xref:System.Windows.Controls.Primitives.IScrollInfo> representa la región de desplazamiento principal dentro de un <xref:System.Windows.Controls.ScrollViewer> o control derivado. La interfaz define las propiedades y los métodos de desplazamiento que pueden ser implementados por <xref:System.Windows.Controls.Panel> elementos que requieren desplazamiento por unidad lógica, en lugar de por un incremento físico. Convertir una instancia de <xref:System.Windows.Controls.Primitives.IScrollInfo> en un <xref:System.Windows.Controls.Panel> derivado y, a continuación, usar sus métodos de desplazamiento proporciona una manera útil de desplazarse a la siguiente unidad lógica en una colección secundaria, en lugar de por incrementos de píxeles. De forma predeterminada, el control <xref:System.Windows.Controls.ScrollViewer> admite el desplazamiento por unidades físicas.  
  
 <xref:System.Windows.Controls.StackPanel> y <xref:System.Windows.Controls.VirtualizingStackPanel> implementan <xref:System.Windows.Controls.Primitives.IScrollInfo> y admiten de forma nativa el desplazamiento lógico. En el caso de los controles de diseño que admiten de forma nativa el desplazamiento lógico, puede lograr el desplazamiento físico ajustando el elemento <xref:System.Windows.Controls.Panel> del host en un <xref:System.Windows.Controls.ScrollViewer> y estableciendo la propiedad <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> en `false`.  
  
 En el ejemplo de código siguiente se muestra cómo convertir una instancia de <xref:System.Windows.Controls.Primitives.IScrollInfo> en un <xref:System.Windows.Controls.StackPanel> y utilizar los métodos de desplazamiento de contenido (<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> y <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>) definidos por la interfaz.  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>   
## <a name="defining-and-using-a-scrollviewer-element"></a>Definir y utilizar un elemento ScrollViewer  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ScrollViewer> en una ventana que contiene texto y un rectángulo. <xref:System.Windows.Controls.Primitives.ScrollBar> elementos solo aparecen cuando son necesarios. Al cambiar el tamaño de la ventana, los elementos <xref:System.Windows.Controls.Primitives.ScrollBar> aparecen y desaparecen, debido a los valores actualizados de las propiedades <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> y <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A>.  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>   
## <a name="styling-a-scrollviewer"></a>Aplicar estilos a ScrollViewer  
 Al igual que todos los controles de Windows Presentation Foundation, se puede aplicar estilo al <xref:System.Windows.Controls.ScrollViewer> para cambiar el comportamiento de representación predeterminado del control. Para obtener información adicional sobre los estilos de control, consulte [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>   
## <a name="paginating-documents"></a>Paginar documentos  
 Para el contenido del documento, una alternativa al desplazamiento es elegir un contenedor de documentos que admita la paginación. <xref:System.Windows.Documents.FlowDocument> es para documentos que están diseñados para hospedarse en un control de vista, como <xref:System.Windows.Controls.FlowDocumentPageViewer>, que admite la paginación de contenido en varias páginas, lo que evita la necesidad de desplazarse. <xref:System.Windows.Controls.DocumentViewer> proporciona una solución para ver <xref:System.Windows.Documents.FixedDocument> contenido, que usa el desplazamiento tradicional para mostrar el contenido fuera del territorio del área de presentación.  
  
 Para más información sobre los formatos de documentos y opciones de presentación, consulte [Documents in WPF](../advanced/documents-in-wpf.md) (Documentos en WPF).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [Cómo: crear un visor de desplazamiento](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [Documentos en WPF](../advanced/documents-in-wpf.md)
- [ScrollBar Styles and Templates](scrollbar-styles-and-templates.md) (Estilos y plantillas de ScrollBar)
- [Controles](../advanced/optimizing-performance-controls.md)
