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
ms.openlocfilehash: 4a50e8a10563fdc5e16ee2e2a46389e13b51e447
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548862"
---
# <a name="textelement-content-model-overview"></a>Información general sobre el modelo de contenido de TextElement
Esta información general de modelo de contenido describe el contenido compatible para un <xref:System.Windows.Documents.TextElement>. El <xref:System.Windows.Documents.Paragraph> clase es un tipo de <xref:System.Windows.Documents.TextElement>. Un modelo de contenido describe qué objetos o elementos se pueden contener en otros. Esta información general resume el modelo de contenido que se usa para los objetos derivados de <xref:System.Windows.Documents.TextElement>. Para obtener más información, consulte [Flow Document Overview](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
  
<a name="text_element_classes"></a>   
## <a name="content-model-diagram"></a>Diagrama del modelo de contenido  
 En el diagrama siguiente se resume el modelo de contenido para las clases derivadas de <xref:System.Windows.Documents.TextElement> , así como cómo otros no - `TextElement` las clases que se pueden integrar en este modelo.  
  
 ![Diagrama: Esquema de contención de contenido dinámico](../../../../docs/framework/wpf/advanced/media/flow-content-schema.png "Flow_Content_Schema")  
  
 Tal y como se puede ver en el diagrama anterior, los elementos secundarios permitidos para un elemento no necesariamente determina si una clase se deriva de la <xref:System.Windows.Documents.Block> clase o un <xref:System.Windows.Documents.Inline> clase. Por ejemplo, un <xref:System.Windows.Documents.Span> (un <xref:System.Windows.Documents.Inline>-clase derivada) solo puede tener <xref:System.Windows.Documents.Inline> elementos secundarios, pero un <xref:System.Windows.Documents.Figure> (también una <xref:System.Windows.Documents.Inline>-clase derivada) solo puede tener <xref:System.Windows.Documents.Block> los elementos secundarios. Por tanto, un diagrama es útil para determinar rápidamente qué elemento puede incluirse en otro. Por ejemplo, vamos a usar el diagrama para determinar cómo construir el contenido del flujo de un <xref:System.Windows.Controls.RichTextBox>.  
  
1.  A <xref:System.Windows.Controls.RichTextBox> debe contener una <xref:System.Windows.Documents.FlowDocument> que a su vez debe contener un <xref:System.Windows.Documents.Block>-objeto derivado. A continuación, se muestra el segmento correspondiente del diagrama anterior.  
  
     ![Diagrama: Reglas de contención de RichTextBox](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     Llegados a este punto, esta es la apariencia que podría tener el marcado.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2.  Según el diagrama, hay varios <xref:System.Windows.Documents.Block> elementos que puede elegir incluidos <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, y <xref:System.Windows.Documents.BlockUIContainer> (vea clases derivadas de bloque en el diagrama anterior). Supongamos que queremos un <xref:System.Windows.Documents.Table>. Según el diagrama anterior, un <xref:System.Windows.Documents.Table> contiene un <xref:System.Windows.Documents.TableRowGroup> que contiene <xref:System.Windows.Documents.TableRow> elementos, que contienen <xref:System.Windows.Documents.TableCell> elementos que contienen un <xref:System.Windows.Documents.Block>-objeto derivado. Éste es el segmento correspondiente para <xref:System.Windows.Documents.Table> tomado del diagrama anterior.  
  
     ![Diagrama: Esquema de elemento primario&#47;secundario para Table](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     A continuación, se muestra el marcado correspondiente.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3.  Una vez más, uno o varios <xref:System.Windows.Documents.Block> requieren debajo de los elementos de un <xref:System.Windows.Documents.TableCell>. Para facilitar el proceso, vamos a colocar texto dentro de la celda. Podemos hacer esto con un <xref:System.Windows.Documents.Paragraph> con un <xref:System.Windows.Documents.Run> elemento. Éste es el segmentos correspondientes del diagrama que muestra que un <xref:System.Windows.Documents.Paragraph> puede tardar un <xref:System.Windows.Documents.Inline> elemento y que un <xref:System.Windows.Documents.Run> (un <xref:System.Windows.Documents.Inline> elemento) solo se puede tomar el texto sin formato.  
  
     ![Diagrama: Esquema de elemento primario&#47;secundario para Paragraph](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![Diagrama: Esquema de elemento primario&#47;secundario para Run](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 A continuación se muestra el ejemplo completo en el marcado.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## <a name="working-with-textelement-content-programmatically"></a>Trabajar con contenido de TextElement mediante programación  
 El contenido de un <xref:System.Windows.Documents.TextElement> está formado por las colecciones de modo que manipular mediante programación el contenido de <xref:System.Windows.Documents.TextElement> objetos se realiza cuando se trabaja con estas colecciones. Hay tres colecciones diferentes utilizadas por <xref:System.Windows.Documents.TextElement> -las clases derivadas:  
  
-   <xref:System.Windows.Documents.InlineCollection>: Representa una colección de <xref:System.Windows.Documents.Inline> elementos. <xref:System.Windows.Documents.InlineCollection> define el contenido secundario permitido de la <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span>, y <xref:System.Windows.Controls.TextBlock> elementos.  
  
-   <xref:System.Windows.Documents.BlockCollection>: Representa una colección de <xref:System.Windows.Documents.Block> elementos. <xref:System.Windows.Documents.BlockCollection> define el contenido secundario permitido de los elementos <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater> y <xref:System.Windows.Documents.Figure>.  
  
-   <xref:System.Windows.Documents.ListItemCollection>: Un elemento de contenido dinámico que representa un elemento de contenido determinado en una ordenada o desordenada <xref:System.Windows.Documents.List>.  
  
 Puede manipular (Agregar o quitar elementos) de estas colecciones mediante las propiedades correspondientes de **elementos incorporados**, **bloques**, y **ListItems**. Los ejemplos siguientes muestran cómo manipular el contenido de un intervalo mediante el **elementos incorporados** propiedad.  
  
> [!NOTE]
>  El objeto Table usa varias colecciones para manipular su contenido, pero no se describen aquí. Para obtener más información, consulte [información general de la tabla](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
 En el ejemplo siguiente se crea un nuevo <xref:System.Windows.Documents.Span> objeto y, a continuación, utiliza el `Add` método para agregar dos texto se ejecuta como elementos de contenido secundarios de la <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 En el ejemplo siguiente se crea un nuevo <xref:System.Windows.Documents.Run> elemento y se inserta al principio de la <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 En el ejemplo siguiente se elimina el último <xref:System.Windows.Documents.Inline> elemento en el <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 En el ejemplo siguiente se borra todo el contenido (<xref:System.Windows.Documents.Inline> elementos) de la <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## <a name="types-that-share-this-content-model"></a>Tipos que comparten este modelo de contenido  
 Los siguientes tipos de heredan de la <xref:System.Windows.Documents.TextElement> clase y puede utilizarse para mostrar el contenido descrito en este artículo.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 Tenga en cuenta que esta lista incluye solo los tipos no abstractos distribuidos con el [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]. Puede usar otros tipos que heredan de <xref:System.Windows.Documents.TextElement>.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## <a name="types-that-can-contain-textelement-objects"></a>Tipos que pueden contener objetos TextElement  
 Vea [modelo de contenido de WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
## <a name="see-also"></a>Vea también  
 [Manipular un objeto FlowDocument mediante la propiedad Blocks](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [Manipular elementos de contenido dinámico mediante la propiedad Blocks](../../../../docs/framework/wpf/advanced/how-to-manipulate-flow-content-elements-through-the-blocks-property.md)  
 [Manipular un objeto FlowDocument mediante la propiedad Blocks](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [Manipular las columnas de una tabla mediante la propiedad Columns](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [Manipular grupos de filas de una tabla mediante la propiedad RowGroups](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
