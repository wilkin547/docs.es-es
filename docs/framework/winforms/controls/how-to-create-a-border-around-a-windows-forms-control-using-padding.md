---
title: Filtrar para crear un borde alrededor de un control de formularios Windows Forms con relleno
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
ms.openlocfilehash: e3bbf43dbe45e675df172a6c3e1db16a3ba9caa8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124034"
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a>Filtrar para crear un borde alrededor de un control de formularios Windows Forms con relleno
En el ejemplo de código siguiente se muestra cómo crear un borde o describir en torno a un <xref:System.Windows.Forms.RichTextBox> control. El ejemplo establece el valor de un <xref:System.Windows.Forms.Panel> del control <xref:System.Windows.Forms.Padding> propiedad en 5 y establece el <xref:System.Windows.Forms.Control.Dock%2A> propiedad de un elemento secundario <xref:System.Windows.Forms.RichTextBox> el control a <xref:System.Windows.Forms.DockStyle.Fill>. El <xref:System.Windows.Forms.Control.BackColor%2A> de la <xref:System.Windows.Forms.Panel> control está establecido en <xref:System.Drawing.Color.Blue%2A>, que crea un borde azul alrededor del <xref:System.Windows.Forms.RichTextBox> control.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.Padding#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Padding>
- [Márgenes y relleno en controles de formularios Windows Forms](margin-and-padding-in-windows-forms-controls.md)
