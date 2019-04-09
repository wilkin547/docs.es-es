---
title: Filtrar Crear un control TextBox multilínea
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: 29fb4c9498fe163c36e71680242d3ef8cf98c089
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181173"
---
# <a name="how-to-create-a-multiline-textbox-control"></a><span data-ttu-id="a3c3a-102">Filtrar Crear un control TextBox multilínea</span><span class="sxs-lookup"><span data-stu-id="a3c3a-102">How to: Create a Multiline TextBox Control</span></span>
<span data-ttu-id="a3c3a-103">En este ejemplo se muestra cómo usar [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para definir un <xref:System.Windows.Controls.TextBox> control que se expandirá automáticamente para alojar varias líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-103">This example shows how to use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.TextBox> control that will automatically expand to accommodate multiple lines of text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3c3a-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3c3a-104">Example</span></span>  
 <span data-ttu-id="a3c3a-105">Establecer el <xref:System.Windows.Controls.TextBox.TextWrapping%2A> atribuir a **ajustar** hará que el texto especificado se ajuste a una nueva línea cuando el borde de la <xref:System.Windows.Controls.TextBox> se alcanza el control, se expande automáticamente el <xref:System.Windows.Controls.TextBox> control para incluir espacio para una nueva línea, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-105">Setting the <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attribute to **Wrap** will cause entered text to wrap to a new line when the edge of the <xref:System.Windows.Controls.TextBox> control is reached, automatically expanding the <xref:System.Windows.Controls.TextBox> control to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="a3c3a-106">Establecer el <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> atributo **true** provoca una nueva línea va a insertar cuando se presiona la tecla ENTRAR, se expande automáticamente una vez más la <xref:System.Windows.Controls.TextBox> para incluir espacio para una nueva línea, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-106">Setting the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> attribute to **true** causes a new line to be inserted when the RETURN key is pressed, once again automatically expanding the <xref:System.Windows.Controls.TextBox> to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="a3c3a-107">El <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> atributo agrega una barra de desplazamiento a la <xref:System.Windows.Controls.TextBox>, de modo que el contenido de la <xref:System.Windows.Controls.TextBox> se puede desplazar y si el <xref:System.Windows.Controls.TextBox> se expande más allá del tamaño del marco o la ventana que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="a3c3a-107">The <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attribute adds a scroll bar to the <xref:System.Windows.Controls.TextBox>, so that the contents of the <xref:System.Windows.Controls.TextBox> can be scrolled through if the <xref:System.Windows.Controls.TextBox> expands beyond the size of the frame or window that encloses it.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="a3c3a-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3c3a-108">See also</span></span>

- <xref:System.Windows.TextWrapping>
- [<span data-ttu-id="a3c3a-109">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="a3c3a-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="a3c3a-110">Información general sobre el control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="a3c3a-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
