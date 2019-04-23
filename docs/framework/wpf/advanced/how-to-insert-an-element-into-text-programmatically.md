---
title: Procedimiento Insertar un elemento en texto mediante programación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Text Animation sample [WPF]
- elements [WPF], inserting into text
- inserting elements into text [WPF]
- TextPointer objects [WPF]
- text [WPF], inserting elements
ms.assetid: 97bd950a-25ac-4e42-a311-94b6420d4136
ms.openlocfilehash: ea9850c8490ec37032d4565c6b3375e3116d4313
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169590"
---
# <a name="how-to-insert-an-element-into-text-programmatically"></a><span data-ttu-id="1b083-102">Procedimiento Insertar un elemento en texto mediante programación</span><span class="sxs-lookup"><span data-stu-id="1b083-102">How to: Insert an Element Into Text Programmatically</span></span>
<span data-ttu-id="1b083-103">El ejemplo siguiente muestra cómo utilizar dos <xref:System.Windows.Documents.TextPointer> objetos para especificar un intervalo de texto que se aplicará un <xref:System.Windows.Documents.Span> elemento.</span><span class="sxs-lookup"><span data-stu-id="1b083-103">The following example shows how to use two <xref:System.Windows.Documents.TextPointer> objects to specify a range within text to apply a <xref:System.Windows.Documents.Span> element to.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b083-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b083-104">Example</span></span>  
 [!code-csharp[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/CSharp/InsertInlineIntoTextExample.cs#insertinlineintotextexamplewholepage)]
 [!code-vb[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/VisualBasic/InsertInlineIntoTextExample.vb#insertinlineintotextexamplewholepage)]  
  
 <span data-ttu-id="1b083-105">En la ilustración siguiente se muestra el aspecto de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1b083-105">The illustration below shows what this example looks like.</span></span>  
  
 <span data-ttu-id="1b083-106">![Elemento Span aplicado a un intervalo de texto](./media/flow-insertelementintotextprogrammatically.png "Flow_InsertElementIntoTextProgrammatically")</span><span class="sxs-lookup"><span data-stu-id="1b083-106">![A Span element applied to a range of text](./media/flow-insertelementintotextprogrammatically.png "Flow_InsertElementIntoTextProgrammatically")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b083-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b083-107">See also</span></span>

- [<span data-ttu-id="1b083-108">Información general sobre documentos dinámicos</span><span class="sxs-lookup"><span data-stu-id="1b083-108">Flow Document Overview</span></span>](flow-document-overview.md)
