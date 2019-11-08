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
ms.openlocfilehash: acd67dd870c6912eddc368bf674804d98dba2db8
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740757"
---
# <a name="textelement-content-model-overview"></a>Información general sobre el modelo de contenido de TextElement
Esta información general sobre el modelo de contenido describe el contenido admitido para una <xref:System.Windows.Documents.TextElement>. La clase <xref:System.Windows.Documents.Paragraph> es un tipo de <xref:System.Windows.Documents.TextElement>. Un modelo de contenido describe qué objetos o elementos se pueden contener en otros. En esta información general se resume el modelo de contenido que se usa para los objetos derivados de <xref:System.Windows.Documents.TextElement>. Para obtener más información, vea [información general sobre documentos dinámicos](flow-document-overview.md).  

<a name="text_element_classes"></a>   
## <a name="content-model-diagram"></a>Diagrama del modelo de contenido  
 En el diagrama siguiente se resume el modelo de contenido para las clases derivadas de <xref:System.Windows.Documents.TextElement> así como el modo en que otras clases que no son de `TextElement` encajan en este modelo.  
  
 ![Diagrama: esquema de contención de contenido dinámico](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 Como se puede observar en el diagrama anterior, los elementos secundarios permitidos para un elemento no se determinan necesariamente si una clase se deriva de la clase <xref:System.Windows.Documents.Block> o de una clase <xref:System.Windows.Documents.Inline>. Por ejemplo, un <xref:System.Windows.Documents.Span> (una clase derivada de <xref:System.Windows.Documents.Inline>) solo puede tener <xref:System.Windows.Documents.Inline> elementos secundarios, pero una <xref:System.Windows.Documents.Figure> (también una clase derivada de <xref:System.Windows.Documents.Inline>) solo puede tener <xref:System.Windows.Documents.Block> elementos secundarios. Por tanto, un diagrama es útil para determinar rápidamente qué elemento puede incluirse en otro. Por ejemplo, vamos a usar el diagrama para determinar cómo construir el contenido dinámico de un <xref:System.Windows.Controls.RichTextBox>.  
  
1. Un <xref:System.Windows.Controls.RichTextBox> debe contener un <xref:System.Windows.Documents.FlowDocument> que a su vez debe contener un objeto derivado de <xref:System.Windows.Documents.Block>. A continuación, se muestra el segmento correspondiente del diagrama anterior.  
  
     ![Diagrama: reglas de contención de RichTextBox](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     Llegados a este punto, esta es la apariencia que podría tener el marcado.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2. Según el diagrama, hay varios elementos de <xref:System.Windows.Documents.Block> entre los que puede elegir, entre los que se incluyen <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>y <xref:System.Windows.Documents.BlockUIContainer> (vea clases derivadas del bloque en el diagrama anterior). Supongamos que queremos un <xref:System.Windows.Documents.Table>. Según el diagrama anterior, un <xref:System.Windows.Documents.Table> contiene un <xref:System.Windows.Documents.TableRowGroup> que contiene elementos <xref:System.Windows.Documents.TableRow>, que contienen <xref:System.Windows.Documents.TableCell> elementos que contienen un objeto derivado de <xref:System.Windows.Documents.Block>. El siguiente es el segmento correspondiente para <xref:System.Windows.Documents.Table> tomado del diagrama anterior.  
  
     ![Diagrama: esquema&#47;de elementos primarios y secundarios para la tabla](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     A continuación, se muestra el marcado correspondiente.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3. De nuevo, se requieren uno o varios elementos <xref:System.Windows.Documents.Block> bajo un <xref:System.Windows.Documents.TableCell>. Para facilitar el proceso, vamos a colocar texto dentro de la celda. Para ello, se puede usar un <xref:System.Windows.Documents.Paragraph> con un elemento <xref:System.Windows.Documents.Run>. A continuación se muestran los segmentos correspondientes del diagrama que muestra que un <xref:System.Windows.Documents.Paragraph> puede tomar un <xref:System.Windows.Documents.Inline> elemento y que un <xref:System.Windows.Documents.Run> (un elemento <xref:System.Windows.Documents.Inline>) solo puede tomar texto sin formato.  
  
     ![Diagrama: esquema&#47;de elementos primarios y secundarios para el párrafo](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![Diagrama: esquema&#47;de elementos primarios y secundarios para ejecutar](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 A continuación se muestra el ejemplo completo en el marcado.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## <a name="working-with-textelement-content-programmatically"></a>Trabajar con contenido de TextElement mediante programación  
 El contenido de un <xref:System.Windows.Documents.TextElement> se compone de colecciones y, por lo tanto, la manipulación mediante programación del contenido de <xref:System.Windows.Documents.TextElement> objetos se realiza mediante el trabajo con estas colecciones. Existen tres colecciones diferentes que utilizan las clases derivadas de <xref:System.Windows.Documents.TextElement>:  
  
- <xref:System.Windows.Documents.InlineCollection>: representa una colección de elementos <xref:System.Windows.Documents.Inline>. <xref:System.Windows.Documents.InlineCollection> define el contenido secundario permitido de los elementos <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span> y <xref:System.Windows.Controls.TextBlock>.  
  
- <xref:System.Windows.Documents.BlockCollection>: representa una colección de elementos <xref:System.Windows.Documents.Block>. <xref:System.Windows.Documents.BlockCollection> define el contenido secundario permitido de los elementos <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater> y <xref:System.Windows.Documents.Figure>.  
  
- <xref:System.Windows.Documents.ListItemCollection>: un elemento de contenido dinámico que representa un elemento de contenido determinado en una <xref:System.Windows.Documents.List>ordenada o sin ordenar.  
  
 Puede manipular (agregar o quitar elementos) de estas colecciones usando las propiedades respectivas de **Inlines**, **Blocks**y **ListItems**. En los siguientes ejemplos se muestra cómo manipular el contenido de un intervalo mediante la propiedad **Inlines** .  
  
> [!NOTE]
> El objeto Table usa varias colecciones para manipular su contenido, pero no se describen aquí. Para obtener más información, vea [información general sobre tablas](table-overview.md).  
  
 En el ejemplo siguiente se crea un nuevo objeto <xref:System.Windows.Documents.Span> y, a continuación, se usa el método `Add` para agregar dos ejecuciones de texto como elementos secundarios de contenido de la <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 En el ejemplo siguiente se crea un nuevo elemento <xref:System.Windows.Documents.Run> y se inserta al principio de la <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 En el ejemplo siguiente se elimina el último elemento <xref:System.Windows.Documents.Inline> del <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 En el siguiente ejemplo se borra todo el contenido (elementos<xref:System.Windows.Documents.Inline>) del <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## <a name="types-that-share-this-content-model"></a>Tipos que comparten este modelo de contenido  
 Los siguientes tipos heredan de la clase <xref:System.Windows.Documents.TextElement> y se pueden usar para mostrar el contenido descrito en esta información general.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table><xref:System.Windows.Documents.Underline>.  
  
 Tenga en cuenta que esta lista solo incluye tipos no abstractos distribuidos con el Windows SDK. Puede usar otros tipos que heredan de <xref:System.Windows.Documents.TextElement>.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## <a name="types-that-can-contain-textelement-objects"></a>Tipos que pueden contener objetos TextElement  
 Vea [modelo de contenido de WPF](../controls/wpf-content-model.md).  
  
## <a name="see-also"></a>Vea también

- [Manipular un objeto FlowDocument mediante la propiedad Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Manipular elementos de contenido dinámico mediante la propiedad Blocks](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [Manipular un objeto FlowDocument mediante la propiedad Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Manipular las columnas de una tabla mediante la propiedad Columns](how-to-manipulate-table-columns-through-the-columns-property.md)
- [Manipular grupos de filas de una tabla mediante la propiedad RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
