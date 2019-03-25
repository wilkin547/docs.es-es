---
title: Filtrar Usar atributos de separación de columnas de FlowDocument
ms.date: 03/30/2017
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
ms.openlocfilehash: 27491b21da587fa198061ba52d8daed5d3f28de3
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410906"
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a>Procedimiento Usar atributos de separación de columnas de FlowDocument
En este ejemplo se muestra cómo usar las características de separación de columnas de una <xref:System.Windows.Documents.FlowDocument>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un <xref:System.Windows.Documents.FlowDocument>y establece el <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, y <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> atributos.  El <xref:System.Windows.Documents.FlowDocument> contiene un único párrafo de contenido de ejemplo.  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 En la siguiente ilustración se muestra los efectos de la <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, y <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> atributos en un representado <xref:System.Windows.Documents.FlowDocument>.  
  
 ![Captura de pantalla que muestra el atributo FlowDocument dentro de columna.](./media/how-to-use-flowdocument-column-separating-attributes/flowdocument-intra-column.png)
