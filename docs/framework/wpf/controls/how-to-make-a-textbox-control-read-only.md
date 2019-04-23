---
title: Procedimiento Hacer que un control TextBox sea de solo lectura
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 7f24458eb98bd669d59f15c49d1d9e3beb6833b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229841"
---
# <a name="how-to-make-a-textbox-control-read-only"></a><span data-ttu-id="39eed-102">Procedimiento Hacer que un control TextBox sea de solo lectura</span><span class="sxs-lookup"><span data-stu-id="39eed-102">How to: Make a TextBox Control Read-Only</span></span>
<span data-ttu-id="39eed-103">En este ejemplo se muestra cómo configurar un <xref:System.Windows.Controls.TextBox> control no permitir la entrada del usuario o la modificación.</span><span class="sxs-lookup"><span data-stu-id="39eed-103">This example shows how to configure a <xref:System.Windows.Controls.TextBox> control to not allow user input or modification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39eed-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="39eed-104">Example</span></span>  
 <span data-ttu-id="39eed-105">Para evitar que los usuarios modifiquen el contenido de un <xref:System.Windows.Controls.TextBox> , establezca el <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> atributo **true**.</span><span class="sxs-lookup"><span data-stu-id="39eed-105">To prevent users from modifying the contents of a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <span data-ttu-id="39eed-106">El <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> atributo afecta a los proporcionados por el usuario sólo; no afecta al texto establecido el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] descripción de un <xref:System.Windows.Controls.TextBox> control o texto establecido mediante programación a través del <xref:System.Windows.Controls.TextBox.Text%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="39eed-106">The <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute affects user input only; it does not affect text set in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] description of a <xref:System.Windows.Controls.TextBox> control, or text set programmatically through the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="39eed-107">El valor predeterminado de <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> es **false**.</span><span class="sxs-lookup"><span data-stu-id="39eed-107">The default value of <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> is **false**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39eed-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="39eed-108">See also</span></span>

- [<span data-ttu-id="39eed-109">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="39eed-109">TextBox Overview</span></span>](textbox-overview.md)
- <span data-ttu-id="39eed-110">[RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="39eed-110">[RichTextBox Overview](richtextbox-overview.md)</span></span>
