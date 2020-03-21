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
ms.openlocfilehash: 2ff0f134ea3174f7f034d47446aab782e2141916
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186982"
---
# <a name="scrollviewer-overview"></a>Información general sobre ScrollViewer
El contenido en una interfaz de usuario suele ser mayor que el área de presentación de la pantalla del equipo. El <xref:System.Windows.Controls.ScrollViewer> control proporciona una manera cómoda de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] habilitar el desplazamiento de contenido en las aplicaciones. En este tema <xref:System.Windows.Controls.ScrollViewer> se presenta el elemento y se proporcionan varios ejemplos de uso.  
  
<a name="what_is_a_scrollviewer_element"></a>
## <a name="the-scrollviewer-control"></a>Control ScrollViewer  
 Hay dos elementos predefinidos que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permiten <xref:System.Windows.Controls.Primitives.ScrollBar> <xref:System.Windows.Controls.ScrollViewer>el desplazamiento en aplicaciones: y . El <xref:System.Windows.Controls.ScrollViewer> control encapsula elementos horizontales y <xref:System.Windows.Controls.Primitives.ScrollBar> verticales <xref:System.Windows.Controls.Panel> y un contenedor de contenido (como un elemento) para mostrar otros elementos visibles en un área desplazable. Debe crear un objeto personalizado para <xref:System.Windows.Controls.Primitives.ScrollBar> poder utilizar el elemento para el desplazamiento de contenido. Sin embargo, <xref:System.Windows.Controls.ScrollViewer> puede usar el elemento por sí <xref:System.Windows.Controls.Primitives.ScrollBar> mismo porque es un control compuesto que encapsula la funcionalidad.  
  
 El <xref:System.Windows.Controls.ScrollViewer> control responde a los comandos del mouse y del teclado, y define numerosos métodos con los que desplazar el contenido por incrementos predeterminados. Puede usar <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> el evento para detectar <xref:System.Windows.Controls.ScrollViewer> un cambio en un estado.  
  
 A <xref:System.Windows.Controls.ScrollViewer> solo puede tener un <xref:System.Windows.Controls.Panel> elemento secundario, <xref:System.Windows.Controls.Panel.Children%2A> normalmente un elemento que puede hospedar una colección de elementos. La <xref:System.Windows.Controls.ContentPresenter.Content%2A> propiedad define el <xref:System.Windows.Controls.ScrollViewer>único elemento secundario de la .  
  
<a name="scrollviewer_physical_vs_logical"></a>
## <a name="physical-vs-logical-scrolling"></a>Desplazamiento físico frente a desplazamiento lógico  
 El desplazamiento físico se utiliza para desplazar el contenido mediante incrementos físicos predeterminados, normalmente por un valor que se declara en píxeles. El desplazamiento lógico se utiliza para desplazarse al elemento siguiente del árbol lógico. El desplazamiento físico es el <xref:System.Windows.Controls.Panel> comportamiento de desplazamiento predeterminado para la mayoría de los elementos. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite ambos tipos de desplazamiento.  
  
#### <a name="the-iscrollinfo-interface"></a>Interfaz IScrollInfo  
 La <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaz representa la región <xref:System.Windows.Controls.ScrollViewer> de desplazamiento principal dentro de un control o derivado. La interfaz define propiedades de desplazamiento y <xref:System.Windows.Controls.Panel> métodos que se pueden implementar mediante elementos que requieren desplazamiento por unidad lógica, en lugar de por un incremento físico. Convertir una <xref:System.Windows.Controls.Primitives.IScrollInfo> instancia de <xref:System.Windows.Controls.Panel> un derivado y, a continuación, usar sus métodos de desplazamiento proporciona una manera útil de desplazarse a la siguiente unidad lógica en una colección secundaria, en lugar de por incremento de píxel. De forma <xref:System.Windows.Controls.ScrollViewer> predeterminada, el control admite el desplazamiento por unidades físicas.  
  
 <xref:System.Windows.Controls.StackPanel>y <xref:System.Windows.Controls.VirtualizingStackPanel> tanto <xref:System.Windows.Controls.Primitives.IScrollInfo> implementar como admitir de forma nativa el desplazamiento lógico. Para los controles de diseño que admiten de forma nativa el <xref:System.Windows.Controls.Panel> desplazamiento <xref:System.Windows.Controls.ScrollViewer> lógico, <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> todavía `false`puede lograr el desplazamiento físico ajustando el elemento host en a y estableciendo la propiedad en .  
  
 En el ejemplo de código siguiente <xref:System.Windows.Controls.Primitives.IScrollInfo> se <xref:System.Windows.Controls.StackPanel> muestra cómo convertir una<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>instancia de a y utilizar métodos de desplazamiento de contenido ( y ) definidos por la interfaz.  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>
## <a name="defining-and-using-a-scrollviewer-element"></a>Definir y utilizar un elemento ScrollViewer  
 En el ejemplo <xref:System.Windows.Controls.ScrollViewer> siguiente se crea una ventana en una ventana que contiene texto y un rectángulo. <xref:System.Windows.Controls.Primitives.ScrollBar>los elementos aparecen sólo cuando son necesarios. Al cambiar el tamaño <xref:System.Windows.Controls.Primitives.ScrollBar> de la ventana, los elementos aparecen y desaparecen, debido a los valores actualizados de las <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> propiedades y. <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A>  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>
## <a name="styling-a-scrollviewer"></a>Aplicar estilos a ScrollViewer  
 Al igual que todos los <xref:System.Windows.Controls.ScrollViewer> controles de Windows Presentation Foundation, se puede aplicar estilo para cambiar el comportamiento de representación predeterminado del control. Para obtener información adicional sobre los estilos de control, consulte [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>
## <a name="paginating-documents"></a>Paginar documentos  
 Para el contenido del documento, una alternativa al desplazamiento es elegir un contenedor de documentos que admita la paginación. <xref:System.Windows.Documents.FlowDocument>es para documentos que están diseñados para <xref:System.Windows.Controls.FlowDocumentPageViewer>hospedarse dentro de un control de visualización, como , que admite la paginación de contenido en varias páginas, lo que impide la necesidad de desplazamiento. <xref:System.Windows.Controls.DocumentViewer>proporciona una solución para ver <xref:System.Windows.Documents.FixedDocument> el contenido, que utiliza el desplazamiento tradicional para mostrar contenido fuera del ámbito del área de visualización.  
  
 Para más información sobre los formatos de documentos y opciones de presentación, consulte [Documents in WPF](../advanced/documents-in-wpf.md) (Documentos en WPF).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [Cómo: Crear un visor de desplazamiento](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [Documentos en WPF](../advanced/documents-in-wpf.md)
- [ScrollBar Styles and Templates](scrollbar-styles-and-templates.md) (Estilos y plantillas de ScrollBar)
- [Controles](../advanced/optimizing-performance-controls.md)
