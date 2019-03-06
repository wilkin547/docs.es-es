---
title: Procedimiento Guardar, cargar e imprimir contenido de un control RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- saving RichTextBox controls [WPF]
- printing RichTextBox controls [WPF]
- loading RichTextBox controls [WPF]
- RichTextBox control [WPF], saving
- RichTextBox control [WPF], printing
- RichTextBox control [WPF], loading
ms.assetid: ffb113d3-c68a-47ca-8ac0-882283f38326
ms.openlocfilehash: bcb368ababaac15dd92b11e43c22dfb705a7c0b3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365742"
---
# <a name="how-to-save-load-and-print-richtextbox-content"></a><span data-ttu-id="affb2-102">Filtrar Guardar, cargar e imprimir contenido de un control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="affb2-102">How to: Save, Load, and Print RichTextBox Content</span></span>
<span data-ttu-id="affb2-103">El ejemplo siguiente muestra cómo guardar el contenido de un <xref:System.Windows.Controls.RichTextBox> en un archivo, cargar ese contenido de nuevo en el <xref:System.Windows.Controls.RichTextBox>e imprimir el contenido.</span><span class="sxs-lookup"><span data-stu-id="affb2-103">The following example shows how to save content of a <xref:System.Windows.Controls.RichTextBox> to a file, load that content back into the <xref:System.Windows.Controls.RichTextBox>, and print the contents.</span></span>  
  
## <a name="example"></a><span data-ttu-id="affb2-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="affb2-104">Example</span></span>  
 <span data-ttu-id="affb2-105">A continuación, se muestra el marcado para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="affb2-105">Below is the markup for the example.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="affb2-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="affb2-106">Example</span></span>  
 <span data-ttu-id="affb2-107">A continuación, se muestra el código subyacente para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="affb2-107">Below is the code behind for the example.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="affb2-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="affb2-108">See also</span></span>
- <span data-ttu-id="affb2-109">[RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="affb2-109">[RichTextBox Overview](richtextbox-overview.md)</span></span>
- [<span data-ttu-id="affb2-110">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="affb2-110">TextBox Overview</span></span>](textbox-overview.md)
