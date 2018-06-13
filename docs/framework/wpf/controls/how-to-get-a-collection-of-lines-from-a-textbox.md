---
title: 'Cómo: Obtener una colección de líneas de un control TextBox'
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: 64187527da3cfb97343e2036338822d479dd997a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552745"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a><span data-ttu-id="88a9f-102">Cómo: Obtener una colección de líneas de un control TextBox</span><span class="sxs-lookup"><span data-stu-id="88a9f-102">How to: Get a Collection of Lines from a TextBox</span></span>
<span data-ttu-id="88a9f-103">Este ejemplo muestra cómo obtener una colección de líneas de texto de un <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="88a9f-103">This example shows how to get a collection of lines of text from a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88a9f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88a9f-104">Example</span></span>  
 <span data-ttu-id="88a9f-105">En el ejemplo siguiente se muestra un método simple que toma un <xref:System.Windows.Controls.TextBox> como argumento y devuelve un <xref:System.Collections.Specialized.StringCollection> que contiene las líneas de texto en el **cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="88a9f-105">The following example shows a simple method that takes a <xref:System.Windows.Controls.TextBox> as the argument, and returns a <xref:System.Collections.Specialized.StringCollection> containing the lines of text in the **TextBox**.</span></span>  <span data-ttu-id="88a9f-106">El <xref:System.Windows.Controls.TextBox.LineCount%2A> propiedad se utiliza para determinar el número de líneas que está actualmente en el **cuadro de texto**y el <xref:System.Windows.Controls.TextBox.GetLineText%2A> , a continuación, se utiliza el método para extraer cada línea y agregarla a la colección de líneas.</span><span class="sxs-lookup"><span data-stu-id="88a9f-106">The <xref:System.Windows.Controls.TextBox.LineCount%2A> property is used to determine how many lines are currently in the **TextBox**, and the <xref:System.Windows.Controls.TextBox.GetLineText%2A> method is then used to extract each line and add it to the collection of lines.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a><span data-ttu-id="88a9f-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="88a9f-107">See Also</span></span>  
 [<span data-ttu-id="88a9f-108">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="88a9f-108">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 <span data-ttu-id="88a9f-109">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="88a9f-109">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md)</span></span>
