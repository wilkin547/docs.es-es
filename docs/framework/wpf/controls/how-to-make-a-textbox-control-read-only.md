---
title: "Cómo: Hacer que un control TextBox sea de sólo lectura"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3d3acf1e5065633f9f4c75f24780230525b01ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-a-textbox-control-read-only"></a><span data-ttu-id="55e43-102">Cómo: Hacer que un control TextBox sea de sólo lectura</span><span class="sxs-lookup"><span data-stu-id="55e43-102">How to: Make a TextBox Control Read-Only</span></span>
<span data-ttu-id="55e43-103">Este ejemplo muestra cómo configurar un <xref:System.Windows.Controls.TextBox> control no permitir la intervención del usuario o la modificación.</span><span class="sxs-lookup"><span data-stu-id="55e43-103">This example shows how to configure a <xref:System.Windows.Controls.TextBox> control to not allow user input or modification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55e43-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="55e43-104">Example</span></span>  
 <span data-ttu-id="55e43-105">Para impedir que los usuarios modifiquen el contenido de un <xref:System.Windows.Controls.TextBox> de control, establezca la <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> atribuir a **true**.</span><span class="sxs-lookup"><span data-stu-id="55e43-105">To prevent users from modifying the contents of a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <span data-ttu-id="55e43-106">El <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> atributo afecta a los proporcionados por el usuario sólo; no afecta al texto establecido el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] descripción de un <xref:System.Windows.Controls.TextBox> control ni al texto establecido mediante programación a través del <xref:System.Windows.Controls.TextBox.Text%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="55e43-106">The <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute affects user input only; it does not affect text set in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] description of a <xref:System.Windows.Controls.TextBox> control, or text set programmatically through the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="55e43-107">El valor predeterminado de <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> es **false**.</span><span class="sxs-lookup"><span data-stu-id="55e43-107">The default value of <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> is **false**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55e43-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="55e43-108">See Also</span></span>  
 [<span data-ttu-id="55e43-109">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="55e43-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 <span data-ttu-id="55e43-110">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="55e43-110">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md)</span></span>
