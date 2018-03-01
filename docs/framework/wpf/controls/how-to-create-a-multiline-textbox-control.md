---
title: "Cómo: Crear un control TextBox multilínea"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2a6885a594e5fcd747f85dedf1afbd39ec644717
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-multiline-textbox-control"></a><span data-ttu-id="36af5-102">Cómo: Crear un control TextBox multilínea</span><span class="sxs-lookup"><span data-stu-id="36af5-102">How to: Create a Multiline TextBox Control</span></span>
<span data-ttu-id="36af5-103">Este ejemplo muestra cómo usar [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para definir un <xref:System.Windows.Controls.TextBox> control que se expande automáticamente para alojar varias líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="36af5-103">This example shows how to use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.TextBox> control that will automatically expand to accommodate multiple lines of text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36af5-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="36af5-104">Example</span></span>  
 <span data-ttu-id="36af5-105">Establecer el <xref:System.Windows.Controls.TextBox.TextWrapping%2A> atribuir a **ajustar** hará que el texto escrito ajustar en una nueva línea cuando el borde de la <xref:System.Windows.Controls.TextBox> control se alcanza, expanda automáticamente la <xref:System.Windows.Controls.TextBox> control debe incluir el espacio para una nueva línea, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="36af5-105">Setting the <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attribute to **Wrap** will cause entered text to wrap to a new line when the edge of the <xref:System.Windows.Controls.TextBox> control is reached, automatically expanding the <xref:System.Windows.Controls.TextBox> control to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="36af5-106">Establecer el <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> atribuir a **true** provoca una nueva línea insertará cuando se presiona la tecla ENTRAR, se expande automáticamente una vez más la <xref:System.Windows.Controls.TextBox> incluir espacio para una nueva línea, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="36af5-106">Setting the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> attribute to **true** causes a new line to be inserted when the RETURN key is pressed, once again automatically expanding the <xref:System.Windows.Controls.TextBox> to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="36af5-107">El <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> atributo agrega una barra de desplazamiento a la <xref:System.Windows.Controls.TextBox>, de modo que el contenido de la <xref:System.Windows.Controls.TextBox> puede desplazarse a través de if el <xref:System.Windows.Controls.TextBox> se expande más allá del tamaño del marco o la ventana que lo incluye.</span><span class="sxs-lookup"><span data-stu-id="36af5-107">The <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attribute adds a scroll bar to the <xref:System.Windows.Controls.TextBox>, so that the contents of the <xref:System.Windows.Controls.TextBox> can be scrolled through if the <xref:System.Windows.Controls.TextBox> expands beyond the size of the frame or window that encloses it.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="36af5-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="36af5-108">See Also</span></span>  
 <xref:System.Windows.TextWrapping>  
 [<span data-ttu-id="36af5-109">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="36af5-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 <span data-ttu-id="36af5-110">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="36af5-110">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md)</span></span>
