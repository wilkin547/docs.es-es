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
ms.openlocfilehash: a3302d9c360b0918a1fce956af3e3aa14f29361b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212432"
---
# <a name="scrollviewer-overview"></a>Información general sobre ScrollViewer
El contenido en una interfaz de usuario suele ser mayor que el área de presentación de la pantalla del equipo. El <xref:System.Windows.Controls.ScrollViewer> control proporciona una manera cómoda para habilitar el desplazamiento del contenido en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicaciones. Este tema se presentan los <xref:System.Windows.Controls.ScrollViewer> elemento y se proporcionan varios ejemplos de uso.  
  
<a name="what_is_a_scrollviewer_element"></a>   
## <a name="the-scrollviewer-control"></a>Control ScrollViewer  
 Hay dos elementos predefinidos que habilitan el desplazamiento en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones: <xref:System.Windows.Controls.Primitives.ScrollBar> y <xref:System.Windows.Controls.ScrollViewer>. El <xref:System.Windows.Controls.ScrollViewer> control encapsula horizontal y vertical <xref:System.Windows.Controls.Primitives.ScrollBar> elementos y un contenedor de contenido (como un <xref:System.Windows.Controls.Panel> elemento) para mostrar otros elementos visibles en un área desplazable. Debe crear un objeto personalizado para poder usar el <xref:System.Windows.Controls.Primitives.ScrollBar> elemento para el desplazamiento de contenido. Sin embargo, puede usar el <xref:System.Windows.Controls.ScrollViewer> elemento por sí mismo, porque es una composición de control que encapsula <xref:System.Windows.Controls.Primitives.ScrollBar> funcionalidad.  
  
 El <xref:System.Windows.Controls.ScrollViewer> control responde a comandos del mouse y teclado y define varios métodos con los que se va a desplazar el contenido mediante incrementos predeterminados. Puede usar el <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> eventos para detectar un cambio en un <xref:System.Windows.Controls.ScrollViewer> estado.  
  
 Un <xref:System.Windows.Controls.ScrollViewer> sólo puede tener un elemento secundario, normalmente un <xref:System.Windows.Controls.Panel> elemento que puede hospedar un <xref:System.Windows.Controls.Panel.Children%2A> colección de elementos. El <xref:System.Windows.Controls.ContentPresenter.Content%2A> propiedad define el único elemento secundario de la <xref:System.Windows.Controls.ScrollViewer>.  
  
<a name="scrollviewer_physical_vs_logical"></a>   
## <a name="physical-vs-logical-scrolling"></a>Desplazamiento físico y lógico  
 El desplazamiento físico se utiliza para desplazar el contenido mediante incrementos físicos predeterminados, normalmente por un valor que se declara en píxeles. El desplazamiento lógico se utiliza para desplazarse al elemento siguiente del árbol lógico. El desplazamiento físico es el comportamiento de desplazamiento predeterminado para la mayoría <xref:System.Windows.Controls.Panel> elementos. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite ambos tipos de desplazamiento.  
  
#### <a name="the-iscrollinfo-interface"></a>Interfaz IScrollInfo  
 El <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaz representa la región desplazable principal dentro de un <xref:System.Windows.Controls.ScrollViewer> o control derivado. La interfaz define el desplazamiento de las propiedades y métodos que pueden ser implementados por <xref:System.Windows.Controls.Panel> elementos que requieren el desplazamiento por unidad lógica, en lugar de un incremento físico. Convertir una instancia de <xref:System.Windows.Controls.Primitives.IScrollInfo> a una derivada <xref:System.Windows.Controls.Panel> y, a continuación, utilizar sus métodos de desplazamiento proporciona una manera útil para desplazarse a la siguiente unidad lógica en una colección secundaria, en lugar de hacerlo por incrementos en píxeles. De forma predeterminada, el <xref:System.Windows.Controls.ScrollViewer> control admite el desplazamiento por unidades físicas.  
  
 <xref:System.Windows.Controls.StackPanel> y <xref:System.Windows.Controls.VirtualizingStackPanel> ambos implementan <xref:System.Windows.Controls.Primitives.IScrollInfo> y admiten de forma nativa el desplazamiento lógico. Para los controles de diseño que forma nativa compatibilidad con el desplazamiento lógico, puede conseguirse el desplazamiento físico ajustando el host <xref:System.Windows.Controls.Panel> elemento en un <xref:System.Windows.Controls.ScrollViewer> y estableciendo el <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> propiedad `false`.  
  
 En el ejemplo de código siguiente se muestra cómo convertir una instancia de <xref:System.Windows.Controls.Primitives.IScrollInfo> a un <xref:System.Windows.Controls.StackPanel> y usar los métodos de desplazamiento de contenido (<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> y <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>) definidos por la interfaz.  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>   
## <a name="defining-and-using-a-scrollviewer-element"></a>Definir y utilizar un elemento ScrollViewer  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ScrollViewer> en una ventana que contiene texto y un rectángulo. <xref:System.Windows.Controls.Primitives.ScrollBar> los elementos aparecen solo cuando son necesarios. Cuando cambia el tamaño de la ventana, el <xref:System.Windows.Controls.Primitives.ScrollBar> elementos aparecen y desaparecen, debido a los valores actualizados de la <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> y <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> propiedades.  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>   
## <a name="styling-a-scrollviewer"></a>Aplicar estilos a ScrollViewer  
 Al igual que todos los controles en Windows Presentation Foundation, el <xref:System.Windows.Controls.ScrollViewer> puede cambiar el estilo con el fin de cambiar el comportamiento de representación predeterminado del control. Para obtener información adicional sobre los estilos de control, consulte [Aplicar estilos y plantillas](styling-and-templating.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>   
## <a name="paginating-documents"></a>Paginar documentos  
 Para el contenido del documento, una alternativa al desplazamiento es elegir un contenedor de documentos que admita la paginación. <xref:System.Windows.Documents.FlowDocument> es para los documentos que están diseñados para ser hospedados en un control de visualización, como <xref:System.Windows.Controls.FlowDocumentPageViewer>, que permite paginar el contenido a través de varias páginas, evitando la necesidad de desplazarse. <xref:System.Windows.Controls.DocumentViewer> Proporciona una solución para su visualización <xref:System.Windows.Documents.FixedDocument> contenido, que usa el desplazamiento tradicional para mostrar contenido fuera del ámbito del área de visualización.  
  
 Para más información sobre los formatos de documentos y opciones de presentación, consulte [Documents in WPF](../advanced/documents-in-wpf.md) (Documentos en WPF).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [Cómo: Crear un visor de desplazamiento](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [Documentos en WPF](../advanced/documents-in-wpf.md)
- [ScrollBar Styles and Templates](scrollbar-styles-and-templates.md) (Estilos y plantillas de ScrollBar)
- [Controles](../advanced/optimizing-performance-controls.md)
