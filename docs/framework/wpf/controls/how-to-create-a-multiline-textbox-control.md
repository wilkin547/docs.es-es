---
title: 'Cómo: Crear un control TextBox multilínea'
description: Obtenga información sobre cómo usar XAML para definir un control de cuadro de texto que se expande para alojar varias líneas de texto en una aplicación Windows Presentation Foundation.
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: 0a88d4d768884df135afddb491431650b9ba2d24
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166250"
---
# <a name="how-to-create-a-multiline-textbox-control"></a><span data-ttu-id="f457c-103">Cómo: Crear un control TextBox multilínea</span><span class="sxs-lookup"><span data-stu-id="f457c-103">How to: Create a Multiline TextBox Control</span></span>
<span data-ttu-id="f457c-104">En este ejemplo se muestra cómo usar [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para definir un <xref:System.Windows.Controls.TextBox> control que se expandirá automáticamente para alojar varias líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="f457c-104">This example shows how to use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.TextBox> control that will automatically expand to accommodate multiple lines of text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f457c-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f457c-105">Example</span></span>  
 <span data-ttu-id="f457c-106">Al establecer el <xref:System.Windows.Controls.TextBox.TextWrapping%2A> atributo en **Wrap** , el texto escrito se ajustará a una nueva línea cuando se alcance el borde del <xref:System.Windows.Controls.TextBox> control, expandiendo automáticamente el <xref:System.Windows.Controls.TextBox> control para que incluya espacio para una nueva línea, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="f457c-106">Setting the <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attribute to **Wrap** will cause entered text to wrap to a new line when the edge of the <xref:System.Windows.Controls.TextBox> control is reached, automatically expanding the <xref:System.Windows.Controls.TextBox> control to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="f457c-107"><xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A>Si se establece el atributo en **true** , se insertará una nueva línea cuando se presione la tecla entrar; de esta forma, se expandirá automáticamente el <xref:System.Windows.Controls.TextBox> para incluir el espacio para una nueva línea, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="f457c-107">Setting the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> attribute to **true** causes a new line to be inserted when the RETURN key is pressed, once again automatically expanding the <xref:System.Windows.Controls.TextBox> to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="f457c-108">El <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> atributo agrega una barra de desplazamiento a <xref:System.Windows.Controls.TextBox> , de modo que el contenido de <xref:System.Windows.Controls.TextBox> se puede desplazar a través de si el objeto se <xref:System.Windows.Controls.TextBox> expande más allá del tamaño del marco o de la ventana que lo incluye.</span><span class="sxs-lookup"><span data-stu-id="f457c-108">The <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attribute adds a scroll bar to the <xref:System.Windows.Controls.TextBox>, so that the contents of the <xref:System.Windows.Controls.TextBox> can be scrolled through if the <xref:System.Windows.Controls.TextBox> expands beyond the size of the frame or window that encloses it.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="f457c-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="f457c-109">See also</span></span>

- <xref:System.Windows.TextWrapping>
- [<span data-ttu-id="f457c-110">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="f457c-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="f457c-111">Información general sobre el control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="f457c-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
