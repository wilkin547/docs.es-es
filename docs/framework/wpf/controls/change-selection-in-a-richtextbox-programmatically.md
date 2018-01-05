---
title: "Cambiar mediante programación la selección en un control RichTextBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- changing selections in a text box [WPF]
- changing selections in a RichTextBox [WPF]
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f645a5719425742ba02f8f9056ca788fd6fdb931
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="change-selection-in-a-richtextbox-programmatically"></a><span data-ttu-id="4aa76-102">Cambiar mediante programación la selección en un control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="4aa76-102">Change Selection in a RichTextBox Programmatically</span></span>
<span data-ttu-id="4aa76-103">Este ejemplo muestra cómo cambiar mediante programación la selección actual en un <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="4aa76-103">This example shows how to programmatically change the current selection in a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="4aa76-104">Esta selección es el mismo, como si el usuario hubiera seleccionado el contenido mediante la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="4aa76-104">This selection is the same as if the user had selected the content by using the user interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4aa76-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4aa76-105">Example</span></span>  
 <span data-ttu-id="4aa76-106">El siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] código describe un conjunto con nombre <xref:System.Windows.Controls.RichTextBox> control con contenido simple.</span><span class="sxs-lookup"><span data-stu-id="4aa76-106">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="4aa76-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4aa76-107">Example</span></span>  
 <span data-ttu-id="4aa76-108">El siguiente código selecciona mediante programación un texto arbitrario cuando el usuario hace clic dentro de la <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="4aa76-108">The following code programmatically selects some arbitrary text when the user clicks inside the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="4aa76-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="4aa76-109">See Also</span></span>  
 <span data-ttu-id="4aa76-110">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="4aa76-110">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md)</span></span>  
 [<span data-ttu-id="4aa76-111">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="4aa76-111">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
