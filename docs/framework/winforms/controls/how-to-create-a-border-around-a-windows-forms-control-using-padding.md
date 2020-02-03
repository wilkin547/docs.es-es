---
title: Crear borde alrededor de un control mediante relleno
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
ms.openlocfilehash: 114186ab5784cf892cb01e9fe2648ce22cecc4b7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742187"
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a><span data-ttu-id="57dfd-102">Cómo: Crear un borde alrededor de un control de formularios Windows Forms con relleno</span><span class="sxs-lookup"><span data-stu-id="57dfd-102">How to: Create a Border Around a Windows Forms Control Using Padding</span></span>
<span data-ttu-id="57dfd-103">En el ejemplo de código siguiente se muestra cómo crear un borde o un contorno alrededor de un control de <xref:System.Windows.Forms.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="57dfd-103">The following code example demonstrates how to create a border or outline around a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="57dfd-104">En el ejemplo se establece el valor de la propiedad <xref:System.Windows.Forms.Padding> de un control <xref:System.Windows.Forms.Panel> en 5 y se establece la propiedad <xref:System.Windows.Forms.Control.Dock%2A> de un control <xref:System.Windows.Forms.RichTextBox> secundario en <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="57dfd-104">The example sets the value of a <xref:System.Windows.Forms.Panel> control’s <xref:System.Windows.Forms.Padding> property to 5 and sets the <xref:System.Windows.Forms.Control.Dock%2A> property of a child <xref:System.Windows.Forms.RichTextBox> control to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="57dfd-105">El <xref:System.Windows.Forms.Control.BackColor%2A> del control <xref:System.Windows.Forms.Panel> se establece en <xref:System.Drawing.Color.Blue%2A>, que crea un borde azul alrededor del control <xref:System.Windows.Forms.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="57dfd-105">The <xref:System.Windows.Forms.Control.BackColor%2A> of the <xref:System.Windows.Forms.Panel> control is set to <xref:System.Drawing.Color.Blue%2A>, which creates a blue border around the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57dfd-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57dfd-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Padding#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="57dfd-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57dfd-107">See also</span></span>

- <xref:System.Windows.Forms.Padding>
- [<span data-ttu-id="57dfd-108">Márgenes y relleno en controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="57dfd-108">Margin and Padding in Windows Forms Controls</span></span>](margin-and-padding-in-windows-forms-controls.md)
