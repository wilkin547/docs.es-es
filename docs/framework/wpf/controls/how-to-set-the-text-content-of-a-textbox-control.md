---
title: 'Cómo: Establecer el contenido de texto de un control TextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: 37d636a5e35e9c52ca35ae558b60b5f32d63cabe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551731"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="17afe-102">Cómo: Establecer el contenido de texto de un control TextBox</span><span class="sxs-lookup"><span data-stu-id="17afe-102">How to: Set the Text Content of a TextBox Control</span></span>
<span data-ttu-id="17afe-103">Este ejemplo muestra cómo utilizar el <xref:System.Windows.Controls.TextBox.Text%2A> propiedad que se va a establecer el contenido de texto inicial de un <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="17afe-103">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 <span data-ttu-id="17afe-104">**Tenga en cuenta** aunque el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] podría utilizar la versión del ejemplo la `<TextBox.Text>` etiquetas alrededor del texto de cada botón <xref:System.Windows.Controls.TextBox> contenido, no es necesario porque el <xref:System.Windows.Controls.TextBox> se aplica el <xref:System.Windows.Markup.ContentPropertyAttribute> atribuir a la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="17afe-104">**Note** Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="17afe-105">Para obtener más información, consulte [información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="17afe-105">For more information, see [XAML Overview (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="17afe-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17afe-106">Example</span></span>  
 [!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]  
  
## <a name="example"></a><span data-ttu-id="17afe-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17afe-107">Example</span></span>  
 [!code-csharp[TextBox_MiscCode#_TextBoxSetText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
 [!code-vb[TextBox_MiscCode#_TextBoxSetText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]  
  
## <a name="see-also"></a><span data-ttu-id="17afe-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="17afe-108">See Also</span></span>  
 [<span data-ttu-id="17afe-109">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="17afe-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 <span data-ttu-id="17afe-110">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="17afe-110">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md)</span></span>
