---
title: Información general sobre el modelo de contenido de TextElement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], flow documents
- TextElement content model [WPF]
- flow content elements [WPF], TextElement content model
ms.assetid: d0a7791c-b090-438c-812f-b9d009d83ee9
ms.openlocfilehash: ecb9441bc63eae41cfbbadf3bf81b0e5392bd0cb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125125"
---
# <a name="textelement-content-model-overview"></a>Información general sobre el modelo de contenido de TextElement
Esta introducción del modelo de contenido describe el contenido compatible con un <xref:System.Windows.Documents.TextElement>. El <xref:System.Windows.Documents.Paragraph> clase es un tipo de <xref:System.Windows.Documents.TextElement>. Un modelo de contenido describe qué objetos o elementos se pueden contener en otros. Esta información general resume el modelo de contenido que se usa para los objetos derivados de <xref:System.Windows.Documents.TextElement>. Para obtener más información, consulte [Flow Document Overview](flow-document-overview.md).  

<a name="text_element_classes"></a>   
## <a name="content-model-diagram"></a>Diagrama del modelo de contenido  
 El diagrama siguiente resume el modelo de contenido para las clases derivadas de <xref:System.Windows.Documents.TextElement> , así como cómo otros que no sean de `TextElement` clases encajan en este modelo.  
  
 ![Diagrama: Esquema de contención de contenido dinámico](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 Como puede verse en el diagrama anterior, los elementos secundarios de un elemento no vienen determinados necesariamente por si una clase se deriva el <xref:System.Windows.Documents.Block> clase o un <xref:System.Windows.Documents.Inline> clase. Por ejemplo, un <xref:System.Windows.Documents.Span> (un <xref:System.Windows.Documents.Inline>-clase derivada) solo puede tener <xref:System.Windows.Documents.Inline> elementos secundarios, pero un <xref:System.Windows.Documents.Figure> (también una <xref:System.Windows.Documents.Inline>-clase derivada) solo puede tener <xref:System.Windows.Documents.Block> elementos secundarios. Por tanto, un diagrama es útil para determinar rápidamente qué elemento puede incluirse en otro. Por ejemplo, vamos a usar el diagrama para determinar cómo construir el contenido dinámico de un <xref:System.Windows.Controls.RichTextBox>.  
  
1.  Un <xref:System.Windows.Controls.RichTextBox> debe contener un <xref:System.Windows.Documents.FlowDocument> que a su vez debe contener un <xref:System.Windows.Documents.Block>-objeto derivado. A continuación, se muestra el segmento correspondiente del diagrama anterior.  
  
     ![Diagrama: Las reglas de contención de RichTextBox](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     Llegados a este punto, esta es la apariencia que podría tener el marcado.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2.  Según el diagrama, hay varios <xref:System.Windows.Documents.Block> elementos para elegir, que incluyen <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, y <xref:System.Windows.Documents.BlockUIContainer> (vea las clases derivadas de Block en el diagrama anterior). Supongamos que queremos un <xref:System.Windows.Documents.Table>. Según el diagrama anterior, un <xref:System.Windows.Documents.Table> contiene un <xref:System.Windows.Documents.TableRowGroup> que contiene <xref:System.Windows.Documents.TableRow> elementos, que contienen <xref:System.Windows.Documents.TableCell> elementos que contienen un <xref:System.Windows.Documents.Block>-objeto derivado. El siguiente es el segmento correspondiente para <xref:System.Windows.Documents.Table> tomado del diagrama anterior.  
  
     ![Diagrama: Elemento primario&#47;esquema secundario para tabla](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     A continuación, se muestra el marcado correspondiente.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3.  Nuevamente, uno o varios <xref:System.Windows.Documents.Block> se requieren los elementos debajo de un <xref:System.Windows.Documents.TableCell>. Para facilitar el proceso, vamos a colocar texto dentro de la celda. Esto se logra mediante un <xref:System.Windows.Documents.Paragraph> con un <xref:System.Windows.Documents.Run> elemento. El siguiente es los segmentos correspondientes del diagrama que demuestran que un <xref:System.Windows.Documents.Paragraph> puede tardar un <xref:System.Windows.Documents.Inline> elemento y que un <xref:System.Windows.Documents.Run> (un <xref:System.Windows.Documents.Inline> elemento) sólo puede aceptar texto sin formato.  
  
     ![Diagrama: Elemento primario&#47;esquema secundario para párrafo](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![Diagrama: Elemento primario&#47;esquema secundario para ejecución](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 A continuación se muestra el ejemplo completo en el marcado.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## <a name="working-with-textelement-content-programmatically"></a>Trabajar con contenido de TextElement mediante programación  
 El contenido de un <xref:System.Windows.Documents.TextElement> está formado por las colecciones de modo que manipular mediante programación el contenido de <xref:System.Windows.Documents.TextElement> objetos se realiza cuando se trabaja con estas colecciones. Hay tres colecciones diferentes usadas por <xref:System.Windows.Documents.TextElement> -las clases derivadas:  
  
-   <xref:System.Windows.Documents.InlineCollection>: Representa una colección de elementos <xref:System.Windows.Documents.Inline>. <xref:System.Windows.Documents.InlineCollection> define el contenido secundario permitido de la <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span>, y <xref:System.Windows.Controls.TextBlock> elementos.  
  
-   <xref:System.Windows.Documents.BlockCollection>: Representa una colección de elementos <xref:System.Windows.Documents.Block>. <xref:System.Windows.Documents.BlockCollection> define el contenido secundario permitido de la <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater>, y <xref:System.Windows.Documents.Figure> elementos.  
  
-   <xref:System.Windows.Documents.ListItemCollection>: Un elemento de contenido dinámico que representa un elemento de contenido determinado en un ordenada o desordenada <xref:System.Windows.Documents.List>.  
  
 Puede manipular (Agregar o quitar elementos) de estas colecciones mediante las propiedades respectivas de **Inlines**, **bloques**, y **ListItems**. Los ejemplos siguientes muestran cómo manipular el contenido de un objeto Span mediante la **Inlines** propiedad.  
  
> [!NOTE]
>  El objeto Table usa varias colecciones para manipular su contenido, pero no se describen aquí. Para obtener más información, consulte [información general sobre tablas](table-overview.md).  
  
 En el ejemplo siguiente se crea un nuevo <xref:System.Windows.Documents.Span> objeto y, a continuación, utiliza el `Add` método para agregar texto dos series como elementos secundarios de contenido de la <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 En el ejemplo siguiente se crea un nuevo <xref:System.Windows.Documents.Run> elemento y lo inserta al principio de la <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 En el ejemplo siguiente se elimina la última <xref:System.Windows.Documents.Inline> elemento en el <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 El siguiente ejemplo borra todo el contenido (<xref:System.Windows.Documents.Inline> elementos) desde el <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## <a name="types-that-share-this-content-model"></a>Tipos que comparten este modelo de contenido  
 Los tipos siguientes heredan de la <xref:System.Windows.Documents.TextElement> clase y se pueden usar para mostrar el contenido descrito en esta introducción.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 Tenga en cuenta que esta lista incluye solo los tipos no abstractos distribuidos con el [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]. Puede usar otros tipos que heredan de <xref:System.Windows.Documents.TextElement>.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## <a name="types-that-can-contain-textelement-objects"></a>Tipos que pueden contener objetos TextElement  
 Consulte [modelo de contenido de WPF](../controls/wpf-content-model.md).  
  
## <a name="see-also"></a>Vea también

- [Manipular un objeto FlowDocument mediante la propiedad Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Manipular elementos de contenido dinámico mediante la propiedad Blocks](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [Manipular un objeto FlowDocument mediante la propiedad Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Manipular las columnas de una tabla mediante la propiedad Columns](how-to-manipulate-table-columns-through-the-columns-property.md)
- [Manipular grupos de filas de una tabla mediante la propiedad RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
