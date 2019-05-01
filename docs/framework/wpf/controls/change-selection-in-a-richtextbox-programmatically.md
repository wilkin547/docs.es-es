---
title: Cambiar mediante programación la selección en un control RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- changing selections in a text box [WPF]
- changing selections in a RichTextBox [WPF]
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
ms.openlocfilehash: b8acfe7cde1fe5dae96cd6324f75c5b146be9ec9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62001720"
---
# <a name="change-selection-in-a-richtextbox-programmatically"></a><span data-ttu-id="4e9d5-102">Cambiar mediante programación la selección en un control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="4e9d5-102">Change Selection in a RichTextBox Programmatically</span></span>
<span data-ttu-id="4e9d5-103">En este ejemplo se muestra cómo cambiar mediante programación la selección actual en un <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="4e9d5-103">This example shows how to programmatically change the current selection in a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="4e9d5-104">Esta selección es el mismo como si el usuario hubiera seleccionado el contenido mediante el uso de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="4e9d5-104">This selection is the same as if the user had selected the content by using the user interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e9d5-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e9d5-105">Example</span></span>  
 <span data-ttu-id="4e9d5-106">La siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] código describe una con nombre <xref:System.Windows.Controls.RichTextBox> control con contenido simple.</span><span class="sxs-lookup"><span data-stu-id="4e9d5-106">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="4e9d5-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e9d5-107">Example</span></span>  
 <span data-ttu-id="4e9d5-108">El siguiente código selecciona mediante programación un texto arbitrario cuando el usuario hace clic dentro del <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="4e9d5-108">The following code programmatically selects some arbitrary text when the user clicks inside the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="4e9d5-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e9d5-109">See also</span></span>

- <span data-ttu-id="4e9d5-110">[RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="4e9d5-110">[RichTextBox Overview](richtextbox-overview.md)</span></span>
- [<span data-ttu-id="4e9d5-111">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="4e9d5-111">TextBox Overview</span></span>](textbox-overview.md)
