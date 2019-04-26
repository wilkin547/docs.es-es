---
title: Procedimiento Establecer el contenido de texto de un control TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: da91e27b804d649f5b8010bc9d7c074425be26f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024149"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="8781e-102">Procedimiento Establecer el contenido de texto de un control TextBox</span><span class="sxs-lookup"><span data-stu-id="8781e-102">How to: Set the Text Content of a TextBox Control</span></span>
<span data-ttu-id="8781e-103">En este ejemplo se muestra cómo usar el <xref:System.Windows.Controls.TextBox.Text%2A> propiedad para establecer el contenido inicial del texto de un <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="8781e-103">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 <span data-ttu-id="8781e-104">**Tenga en cuenta** aunque el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] podría usar la versión del ejemplo el `<TextBox.Text>` etiquetas alrededor del texto de cada botón <xref:System.Windows.Controls.TextBox> contenido, no es necesario porque el <xref:System.Windows.Controls.TextBox> se aplica el <xref:System.Windows.Markup.ContentPropertyAttribute> atributo a la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="8781e-104">**Note** Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="8781e-105">Para obtener más información, consulte [información general sobre XAML (WPF)](../advanced/xaml-overview-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="8781e-105">For more information, see [XAML Overview (WPF)](../advanced/xaml-overview-wpf.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8781e-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8781e-106">Example</span></span>  
 [!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]  
  
## <a name="example"></a><span data-ttu-id="8781e-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8781e-107">Example</span></span>  
 [!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
 [!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]  
  
## <a name="see-also"></a><span data-ttu-id="8781e-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="8781e-108">See also</span></span>

- [<span data-ttu-id="8781e-109">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="8781e-109">TextBox Overview</span></span>](textbox-overview.md)
- <span data-ttu-id="8781e-110">[RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="8781e-110">[RichTextBox Overview](richtextbox-overview.md)</span></span>
