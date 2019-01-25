---
title: Procedimiento Enumerar las fuentes instaladas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: 0124d2bdd8b9c60dc2bf2508348044d76a2c7eb4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602239"
---
# <a name="how-to-enumerate-installed-fonts"></a>Procedimiento Enumerar las fuentes instaladas
El <xref:System.Drawing.Text.InstalledFontCollection> clase hereda de la <xref:System.Drawing.Text.FontCollection> clase base abstracta. Puede usar un <xref:System.Drawing.Text.InstalledFontCollection> objeto para enumerar las fuentes instaladas en el equipo. El <xref:System.Drawing.Text.FontCollection.Families%2A> propiedad de un <xref:System.Drawing.Text.InstalledFontCollection> objeto es una matriz de <xref:System.Drawing.FontFamily> objetos.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente enumeran los nombres de todas las familias de fuentes instaladas en el equipo. El código recupera el <xref:System.Drawing.FontFamily.Name%2A> propiedad de cada uno <xref:System.Drawing.FontFamily> objeto en la matriz devuelta por la <xref:System.Drawing.Text.FontCollection.Families%2A> propiedad. Como se recuperan los nombres de familia, se concatenan para lista separada por comas de formulario. El <xref:System.Drawing.Graphics.DrawString%2A> método de la <xref:System.Drawing.Graphics> clase dibuja la lista separada por comas en un rectángulo.  
  
 Si ejecuta el código de ejemplo, el resultado será similar al que se muestra en la siguiente ilustración.  
  
 ![Las fuentes instaladas](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>. Además, debe importar el <xref:System.Drawing.Text> espacio de nombres.  
  
## <a name="see-also"></a>Vea también
- [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
