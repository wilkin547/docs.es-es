---
title: Información general sobre ScrollViewer
description: Obtenga información sobre el control ScrollViewer, que permite desplazarse por el contenido de Windows Presentation Foundation aplicaciones. Vea ejemplos de uso.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], ScrollViewer
- ScrollViewer control [WPF], about ScrollViewer control
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
ms.openlocfilehash: 1ef680bb004315a2b523814714d5533535d044e5
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164637"
---
# <a name="scrollviewer-overview"></a>Información general sobre ScrollViewer
El contenido en una interfaz de usuario suele ser mayor que el área de presentación de la pantalla del equipo. El <xref:System.Windows.Controls.ScrollViewer> control proporciona una manera cómoda de habilitar el desplazamiento de contenido en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] las aplicaciones. En este tema se presenta el <xref:System.Windows.Controls.ScrollViewer> elemento y se proporcionan varios ejemplos de uso.  
  
<a name="what_is_a_scrollviewer_element"></a>
## <a name="the-scrollviewer-control"></a>Control ScrollViewer  
 Hay dos elementos predefinidos que permiten el desplazamiento en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones: <xref:System.Windows.Controls.Primitives.ScrollBar> y <xref:System.Windows.Controls.ScrollViewer> . El <xref:System.Windows.Controls.ScrollViewer> control encapsula los elementos horizontales y verticales <xref:System.Windows.Controls.Primitives.ScrollBar> y un contenedor de contenido (como un <xref:System.Windows.Controls.Panel> elemento) para mostrar otros elementos visibles en un área desplazable. Debe crear un objeto personalizado para poder usar el <xref:System.Windows.Controls.Primitives.ScrollBar> elemento para el desplazamiento de contenido. Sin embargo, puede usar el <xref:System.Windows.Controls.ScrollViewer> elemento por sí solo porque es un control compuesto que encapsula la <xref:System.Windows.Controls.Primitives.ScrollBar> funcionalidad.  
  
 El <xref:System.Windows.Controls.ScrollViewer> control responde a los comandos del mouse y del teclado, y define numerosos métodos con los que se va a desplazar el contenido mediante incrementos predeterminados. Puede usar el <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> evento para detectar un cambio en un <xref:System.Windows.Controls.ScrollViewer> Estado.  
  
 Un <xref:System.Windows.Controls.ScrollViewer> solo puede tener un elemento secundario, normalmente un <xref:System.Windows.Controls.Panel> elemento que puede hospedar una <xref:System.Windows.Controls.Panel.Children%2A> colección de elementos. La <xref:System.Windows.Controls.ContentPresenter.Content%2A> propiedad define el único elemento secundario de <xref:System.Windows.Controls.ScrollViewer> .  
  
<a name="scrollviewer_physical_vs_logical"></a>
## <a name="physical-vs-logical-scrolling"></a>Desplazamientos físicos y lógicos  
 El desplazamiento físico se utiliza para desplazar el contenido mediante incrementos físicos predeterminados, normalmente por un valor que se declara en píxeles. El desplazamiento lógico se utiliza para desplazarse al elemento siguiente del árbol lógico. El desplazamiento físico es el comportamiento de desplazamiento predeterminado para la mayoría de <xref:System.Windows.Controls.Panel> los elementos. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite ambos tipos de desplazamiento.  
  
#### <a name="the-iscrollinfo-interface"></a>Interfaz IScrollInfo  
 La <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaz representa la región de desplazamiento principal dentro de un <xref:System.Windows.Controls.ScrollViewer> control derivado de o. La interfaz define las propiedades y los métodos de desplazamiento que pueden ser implementados por <xref:System.Windows.Controls.Panel> elementos que requieren desplazamiento por unidad lógica, en lugar de por un incremento físico. Convertir una instancia de <xref:System.Windows.Controls.Primitives.IScrollInfo> en un derivado <xref:System.Windows.Controls.Panel> y, a continuación, utilizar sus métodos de desplazamiento proporciona una manera útil de desplazarse a la siguiente unidad lógica en una colección secundaria, en lugar de por incrementos de píxeles. De forma predeterminada, el <xref:System.Windows.Controls.ScrollViewer> control admite el desplazamiento por unidades físicas.  
  
 <xref:System.Windows.Controls.StackPanel>y <xref:System.Windows.Controls.VirtualizingStackPanel> ambos implementan <xref:System.Windows.Controls.Primitives.IScrollInfo> y admiten de forma nativa el desplazamiento lógico. En el caso de los controles de diseño que admiten de forma nativa el desplazamiento lógico, puede lograr el desplazamiento físico ajustando el <xref:System.Windows.Controls.Panel> elemento host en <xref:System.Windows.Controls.ScrollViewer> y estableciendo la <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> propiedad en `false` .  
  
 En el ejemplo de código siguiente se muestra cómo convertir una instancia de <xref:System.Windows.Controls.Primitives.IScrollInfo> en <xref:System.Windows.Controls.StackPanel> y utilizar los métodos de desplazamiento de contenido ( <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> y <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> ) definidos por la interfaz.  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>
## <a name="defining-and-using-a-scrollviewer-element"></a>Definir y utilizar un elemento ScrollViewer  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ScrollViewer> en una ventana de que contiene texto y un rectángulo. <xref:System.Windows.Controls.Primitives.ScrollBar>los elementos solo aparecen cuando son necesarios. Al cambiar el tamaño de la ventana, los <xref:System.Windows.Controls.Primitives.ScrollBar> elementos aparecen y desaparecen, debido a los valores actualizados de las <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> propiedades y.  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>
## <a name="styling-a-scrollviewer"></a>Aplicar estilos a ScrollViewer  
 Al igual que todos los controles de Windows Presentation Foundation, <xref:System.Windows.Controls.ScrollViewer> se puede aplicar un estilo a con el fin de cambiar el comportamiento de representación predeterminado del control. Para obtener información adicional sobre los estilos de control, consulte [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>
## <a name="paginating-documents"></a>Paginar documentos  
 Para el contenido del documento, una alternativa al desplazamiento es elegir un contenedor de documentos que admita la paginación. <xref:System.Windows.Documents.FlowDocument>es para documentos que están diseñados para hospedarse en un control de vista, como <xref:System.Windows.Controls.FlowDocumentPageViewer> , que admite la paginación de contenido en varias páginas, lo que evita la necesidad de desplazarse. <xref:System.Windows.Controls.DocumentViewer>proporciona una solución para ver <xref:System.Windows.Documents.FixedDocument> el contenido, que usa el desplazamiento tradicional para mostrar el contenido fuera del territorio del área de presentación.  
  
 Para más información sobre los formatos de documentos y opciones de presentación, consulte [Documents in WPF](../advanced/documents-in-wpf.md) (Documentos en WPF).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [Cómo: crear un visor de desplazamiento](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [Documentos en WPF](../advanced/documents-in-wpf.md)
- [Estilos y plantillas de ScrollBar](scrollbar-styles-and-templates.md)
- [Controles](../advanced/optimizing-performance-controls.md)
