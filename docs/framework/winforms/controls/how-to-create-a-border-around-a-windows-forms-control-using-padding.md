---
title: Procedimiento Crear un borde alrededor de un formulario Windows Forms con relleno de Control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins
- controls [Windows Forms], Margin property
- padding [Windows Forms], Windows Forms
- controls [Windows Forms], Padding property
- controls [Windows Forms], outlining
- Padding property [Windows Forms]
- margins [Windows Forms], Windows Forms
- Margin property [Windows Forms]
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
ms.openlocfilehash: 26d5dd086828df94c1ea0808d2f72723344b0702
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614659"
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a><span data-ttu-id="e8542-102">Procedimiento Crear un borde alrededor de un formulario Windows Forms con relleno de Control</span><span class="sxs-lookup"><span data-stu-id="e8542-102">How to: Create a Border Around a Windows Forms Control Using Padding</span></span>
<span data-ttu-id="e8542-103">En el ejemplo de código siguiente se muestra cómo crear un borde o describir en torno a un <xref:System.Windows.Forms.RichTextBox> control.</span><span class="sxs-lookup"><span data-stu-id="e8542-103">The following code example demonstrates how to create a border or outline around a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="e8542-104">El ejemplo establece el valor de un <xref:System.Windows.Forms.Panel> del control <xref:System.Windows.Forms.Padding> propiedad en 5 y establece el <xref:System.Windows.Forms.Control.Dock%2A> propiedad de un elemento secundario <xref:System.Windows.Forms.RichTextBox> el control a <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="e8542-104">The example sets the value of a <xref:System.Windows.Forms.Panel> control’s <xref:System.Windows.Forms.Padding> property to 5 and sets the <xref:System.Windows.Forms.Control.Dock%2A> property of a child <xref:System.Windows.Forms.RichTextBox> control to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="e8542-105">El <xref:System.Windows.Forms.Control.BackColor%2A> de la <xref:System.Windows.Forms.Panel> control está establecido en <xref:System.Drawing.Color.Blue%2A>, que crea un borde azul alrededor del <xref:System.Windows.Forms.RichTextBox> control.</span><span class="sxs-lookup"><span data-stu-id="e8542-105">The <xref:System.Windows.Forms.Control.BackColor%2A> of the <xref:System.Windows.Forms.Panel> control is set to <xref:System.Drawing.Color.Blue%2A>, which creates a blue border around the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8542-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e8542-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Padding#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e8542-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8542-107">See also</span></span>
- <xref:System.Windows.Forms.Padding>
- [<span data-ttu-id="e8542-108">Márgenes y relleno en controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e8542-108">Margin and Padding in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)
