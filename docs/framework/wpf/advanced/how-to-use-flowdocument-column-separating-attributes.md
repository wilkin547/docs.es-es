---
title: 'Cómo: Usar atributos de separación de columnas de FlowDocument'
ms.date: 03/30/2017
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
ms.openlocfilehash: 678e01a35c286ea03f0385291d64f2f900f068c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543776"
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a>Cómo: Usar atributos de separación de columnas de FlowDocument
Este ejemplo muestra cómo utilizar las características de separación de columnas de una <xref:System.Windows.Documents.FlowDocument>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un <xref:System.Windows.Documents.FlowDocument>y establece la <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, y <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> atributos.  El <xref:System.Windows.Documents.FlowDocument> contiene un párrafo único de contenido de ejemplo.  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 La ilustración siguiente muestra los efectos de la <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, y <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> atributos en un representado <xref:System.Windows.Documents.FlowDocument>.  
  
 ![Captura de pantalla: FlowDocument dentro de columna](../../../../docs/framework/wpf/advanced/media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")
