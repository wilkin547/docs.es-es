---
title: Procedimiento Obtener una colección de líneas de un control TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: a63470c6f0db72340f482bf638910685aa3f461f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561769"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a><span data-ttu-id="5eee2-102">Procedimiento Obtener una colección de líneas de un control TextBox</span><span class="sxs-lookup"><span data-stu-id="5eee2-102">How to: Get a Collection of Lines from a TextBox</span></span>
<span data-ttu-id="5eee2-103">En este ejemplo se muestra cómo obtener una colección de líneas de texto de un <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="5eee2-103">This example shows how to get a collection of lines of text from a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5eee2-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5eee2-104">Example</span></span>  
 <span data-ttu-id="5eee2-105">El ejemplo siguiente muestra un método simple que toma un <xref:System.Windows.Controls.TextBox> como argumento y devuelve un <xref:System.Collections.Specialized.StringCollection> que contiene las líneas de texto en el **TextBox**.</span><span class="sxs-lookup"><span data-stu-id="5eee2-105">The following example shows a simple method that takes a <xref:System.Windows.Controls.TextBox> as the argument, and returns a <xref:System.Collections.Specialized.StringCollection> containing the lines of text in the **TextBox**.</span></span>  <span data-ttu-id="5eee2-106">El <xref:System.Windows.Controls.TextBox.LineCount%2A> propiedad se utiliza para determinar cuántas líneas están actualmente en el **TextBox**y el <xref:System.Windows.Controls.TextBox.GetLineText%2A> método, a continuación, se usa para extraer cada línea y agregarla a la colección de líneas.</span><span class="sxs-lookup"><span data-stu-id="5eee2-106">The <xref:System.Windows.Controls.TextBox.LineCount%2A> property is used to determine how many lines are currently in the **TextBox**, and the <xref:System.Windows.Controls.TextBox.GetLineText%2A> method is then used to extract each line and add it to the collection of lines.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a><span data-ttu-id="5eee2-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="5eee2-107">See also</span></span>
- [<span data-ttu-id="5eee2-108">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="5eee2-108">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
- <span data-ttu-id="5eee2-109">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="5eee2-109">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md)</span></span>
