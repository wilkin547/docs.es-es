---
title: Filtrar Manipular elementos de contenido dinámico mediante la propiedad Inlines
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], manipulating through Inlines property
- documents [WPF], manipulating flow Content elements through Inlines property
- Inlines property [WPF], manipulating flow Content elements
- properties [WPF], Inlines [WPF], manipulating flow Content elements
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
ms.openlocfilehash: cfff958bb4c87e6bfecf2d280224cda233c31806
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186074"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-inlines-property"></a>Filtrar Manipular elementos de contenido dinámico mediante la propiedad Inlines
Estos ejemplos muestran algunas de las operaciones más comunes que se pueden realizar en elementos de contenido dinámico insertado (y los contenedores de tales elementos, tales como <xref:System.Windows.Controls.TextBlock>) a través de la **Inlines** propiedad. Esta propiedad se utiliza para agregar y quitar elementos de <xref:System.Windows.Documents.InlineCollection>. Flujo de contenido de elementos de esa característica un **Inlines** propiedad incluyen:  
  
-   <xref:System.Windows.Documents.Bold>  
  
-   <xref:System.Windows.Documents.Hyperlink>  
  
-   <xref:System.Windows.Documents.Italic>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Span>  
  
-   <xref:System.Windows.Documents.Underline>  
  
 Estos ejemplos se producen al usar <xref:System.Windows.Documents.Span> como el flujo de elemento de contenido, pero estas técnicas son aplicables a todos los elementos o controles que hospedan un <xref:System.Windows.Documents.InlineCollection> colección.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un nuevo <xref:System.Windows.Documents.Span> objeto y, a continuación, utiliza el **agregar** método para agregar texto dos series como elementos secundarios de contenido de la <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un nuevo <xref:System.Windows.Documents.Run> elemento y lo inserta al principio de la <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se obtiene el número de nivel superior <xref:System.Windows.Documents.Inline> elementos contenidos en el <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se elimina la última <xref:System.Windows.Documents.Inline> elemento en el <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo borra todo el contenido (<xref:System.Windows.Documents.Inline> elementos) desde el <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [Información general sobre documentos dinámicos](flow-document-overview.md)
- [Manipular un objeto FlowDocument mediante la propiedad Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Manipular las columnas de una tabla mediante la propiedad Columns](how-to-manipulate-table-columns-through-the-columns-property.md)
- [Manipular grupos de filas de una tabla mediante la propiedad RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
