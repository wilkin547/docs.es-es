---
title: Filtrar Extraer el contenido de texto de un control RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], extracting
- RichTextBox control [WPF], extracting text content
- content [WPF], extracting
- extracting text content [WPF]
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
ms.openlocfilehash: 220da59ec893528c99014e9ec95fb185c461b291
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086122"
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a><span data-ttu-id="823aa-102">Filtrar Extraer el contenido de texto de un control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="823aa-102">How to: Extract the Text Content from a RichTextBox</span></span>
<span data-ttu-id="823aa-103">En este ejemplo se muestra cómo extraer el contenido de un <xref:System.Windows.Controls.RichTextBox> como texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="823aa-103">This example shows how to extract the contents of a <xref:System.Windows.Controls.RichTextBox> as plain text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="823aa-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="823aa-104">Example</span></span>  
 <span data-ttu-id="823aa-105">La siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] código describe una con nombre <xref:System.Windows.Controls.RichTextBox> control con contenido simple.</span><span class="sxs-lookup"><span data-stu-id="823aa-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a><span data-ttu-id="823aa-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="823aa-106">Example</span></span>  
 <span data-ttu-id="823aa-107">El código siguiente implementa un método que toma un <xref:System.Windows.Controls.RichTextBox> como un argumento y devuelve una cadena que representa el contenido de texto sin formato de la <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="823aa-107">The following code implements a method that takes a <xref:System.Windows.Controls.RichTextBox> as an argument, and returns a string representing the plain text contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="823aa-108">El método crea un nuevo <xref:System.Windows.Documents.TextRange> desde el contenido de la <xref:System.Windows.Controls.RichTextBox>, usando la <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> y <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> para indicar el intervalo del contenido para extraer.</span><span class="sxs-lookup"><span data-stu-id="823aa-108">The method creates a new <xref:System.Windows.Documents.TextRange> from the contents of the <xref:System.Windows.Controls.RichTextBox>, using the <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> to indicate the range of the contents to extract.</span></span>  <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> <span data-ttu-id="823aa-109">y <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> devuelven propiedades de cada una <xref:System.Windows.Documents.TextPointer>y son accesibles en FlowDocument subyacente que representa el contenido de la <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="823aa-109">and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> properties each return a <xref:System.Windows.Documents.TextPointer>, and are accessible on the underlying FlowDocument that represents the contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  <xref:System.Windows.Documents.TextRange> <span data-ttu-id="823aa-110">Proporciona una propiedad de texto, que devuelve las partes de texto sin formato de la <xref:System.Windows.Documents.TextRange> como una cadena.</span><span class="sxs-lookup"><span data-stu-id="823aa-110">provides a Text property, which returns the plain text portions of the <xref:System.Windows.Documents.TextRange> as a string.</span></span>  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a><span data-ttu-id="823aa-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="823aa-111">See also</span></span>

- [<span data-ttu-id="823aa-112">Información general sobre el control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="823aa-112">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="823aa-113">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="823aa-113">TextBox Overview</span></span>](textbox-overview.md)
