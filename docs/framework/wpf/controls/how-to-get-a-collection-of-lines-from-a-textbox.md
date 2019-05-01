---
title: Procedimiento Obtener una colección de líneas de un control TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: b7b2f1c2e071388635fb50b1e3573fd7f44334dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052487"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a><span data-ttu-id="cef12-102">Procedimiento Obtener una colección de líneas de un control TextBox</span><span class="sxs-lookup"><span data-stu-id="cef12-102">How to: Get a Collection of Lines from a TextBox</span></span>
<span data-ttu-id="cef12-103">En este ejemplo se muestra cómo obtener una colección de líneas de texto de un <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="cef12-103">This example shows how to get a collection of lines of text from a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cef12-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cef12-104">Example</span></span>  
 <span data-ttu-id="cef12-105">El ejemplo siguiente muestra un método simple que toma un <xref:System.Windows.Controls.TextBox> como argumento y devuelve un <xref:System.Collections.Specialized.StringCollection> que contiene las líneas de texto en el **TextBox**.</span><span class="sxs-lookup"><span data-stu-id="cef12-105">The following example shows a simple method that takes a <xref:System.Windows.Controls.TextBox> as the argument, and returns a <xref:System.Collections.Specialized.StringCollection> containing the lines of text in the **TextBox**.</span></span>  <span data-ttu-id="cef12-106">El <xref:System.Windows.Controls.TextBox.LineCount%2A> propiedad se utiliza para determinar cuántas líneas están actualmente en el **TextBox**y el <xref:System.Windows.Controls.TextBox.GetLineText%2A> método, a continuación, se usa para extraer cada línea y agregarla a la colección de líneas.</span><span class="sxs-lookup"><span data-stu-id="cef12-106">The <xref:System.Windows.Controls.TextBox.LineCount%2A> property is used to determine how many lines are currently in the **TextBox**, and the <xref:System.Windows.Controls.TextBox.GetLineText%2A> method is then used to extract each line and add it to the collection of lines.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a><span data-ttu-id="cef12-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="cef12-107">See also</span></span>

- [<span data-ttu-id="cef12-108">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="cef12-108">TextBox Overview</span></span>](textbox-overview.md)
- <span data-ttu-id="cef12-109">[RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="cef12-109">[RichTextBox Overview](richtextbox-overview.md)</span></span>
