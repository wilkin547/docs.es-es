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
# <a name="how-to-use-flowdocument-column-separating-attributes"></a><span data-ttu-id="9dce0-102">Cómo: Usar atributos de separación de columnas de FlowDocument</span><span class="sxs-lookup"><span data-stu-id="9dce0-102">How to: Use FlowDocument Column-Separating Attributes</span></span>
<span data-ttu-id="9dce0-103">Este ejemplo muestra cómo utilizar las características de separación de columnas de una <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="9dce0-103">This example shows how to use the column-separating features of a <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dce0-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9dce0-104">Example</span></span>  
 <span data-ttu-id="9dce0-105">En el ejemplo siguiente se define un <xref:System.Windows.Documents.FlowDocument>y establece la <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, y <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> atributos.</span><span class="sxs-lookup"><span data-stu-id="9dce0-105">The following example defines a <xref:System.Windows.Documents.FlowDocument>, and sets the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes.</span></span>  <span data-ttu-id="9dce0-106">El <xref:System.Windows.Documents.FlowDocument> contiene un párrafo único de contenido de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9dce0-106">The <xref:System.Windows.Documents.FlowDocument> contains a single paragraph of sample content.</span></span>  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 <span data-ttu-id="9dce0-107">La ilustración siguiente muestra los efectos de la <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, y <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> atributos en un representado <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="9dce0-107">The following figure shows the effects of the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes in a rendered <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="9dce0-108">![Captura de pantalla: FlowDocument dentro de columna](../../../../docs/framework/wpf/advanced/media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")</span><span class="sxs-lookup"><span data-stu-id="9dce0-108">![Screenshot: FlowDocument Intra Column](../../../../docs/framework/wpf/advanced/media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")</span></span>
