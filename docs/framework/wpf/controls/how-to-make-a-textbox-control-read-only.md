---
title: Procedimiento Hacer que un control TextBox sea de sólo lectura
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 1e9d333f22099d9593e58b4087f185b2988215ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517180"
---
# <a name="how-to-make-a-textbox-control-read-only"></a><span data-ttu-id="18fe6-102">Procedimiento Hacer que un control TextBox sea de sólo lectura</span><span class="sxs-lookup"><span data-stu-id="18fe6-102">How to: Make a TextBox Control Read-Only</span></span>
<span data-ttu-id="18fe6-103">En este ejemplo se muestra cómo configurar un <xref:System.Windows.Controls.TextBox> control no permitir la entrada del usuario o la modificación.</span><span class="sxs-lookup"><span data-stu-id="18fe6-103">This example shows how to configure a <xref:System.Windows.Controls.TextBox> control to not allow user input or modification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18fe6-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="18fe6-104">Example</span></span>  
 <span data-ttu-id="18fe6-105">Para evitar que los usuarios modifiquen el contenido de un <xref:System.Windows.Controls.TextBox> , establezca el <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> atributo **true**.</span><span class="sxs-lookup"><span data-stu-id="18fe6-105">To prevent users from modifying the contents of a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <span data-ttu-id="18fe6-106">El <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> atributo afecta a los proporcionados por el usuario sólo; no afecta al texto establecido el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] descripción de un <xref:System.Windows.Controls.TextBox> control o texto establecido mediante programación a través del <xref:System.Windows.Controls.TextBox.Text%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="18fe6-106">The <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute affects user input only; it does not affect text set in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] description of a <xref:System.Windows.Controls.TextBox> control, or text set programmatically through the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="18fe6-107">El valor predeterminado de <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> es **false**.</span><span class="sxs-lookup"><span data-stu-id="18fe6-107">The default value of <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> is **false**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18fe6-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="18fe6-108">See also</span></span>
- [<span data-ttu-id="18fe6-109">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="18fe6-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
- <span data-ttu-id="18fe6-110">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="18fe6-110">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md)</span></span>
