---
title: Filtrar Enumerar las fuentes instaladas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: e56f06d6f7a762a1ef1ff85fa30751ea64f9f14b
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "58653748"
---
# <a name="how-to-enumerate-installed-fonts"></a>Filtrar Enumerar las fuentes instaladas
El <xref:System.Drawing.Text.InstalledFontCollection> clase hereda de la <xref:System.Drawing.Text.FontCollection> clase base abstracta. Puede usar un <xref:System.Drawing.Text.InstalledFontCollection> objeto para enumerar las fuentes instaladas en el equipo. El <xref:System.Drawing.Text.FontCollection.Families%2A> propiedad de un <xref:System.Drawing.Text.InstalledFontCollection> objeto es una matriz de <xref:System.Drawing.FontFamily> objetos.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente enumeran los nombres de todas las familias de fuentes instaladas en el equipo. El código recupera el <xref:System.Drawing.FontFamily.Name%2A> propiedad de cada uno <xref:System.Drawing.FontFamily> objeto en la matriz devuelta por la <xref:System.Drawing.Text.FontCollection.Families%2A> propiedad. Como se recuperan los nombres de familia, se concatenan para lista separada por comas de formulario. El <xref:System.Drawing.Graphics.DrawString%2A> método de la <xref:System.Drawing.Graphics> clase dibuja la lista separada por comas en un rectángulo.  
  
 Si ejecuta el código de ejemplo, el resultado será similar al que se muestra en la ilustración siguiente:  
  
 ![Captura de pantalla que muestra las familias de fuentes instaladas.](./media/how-to-enumerate-installed-fonts/list-installed-font-families.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>. Además, debe importar el <xref:System.Drawing.Text> espacio de nombres.  
  
## <a name="see-also"></a>Vea también
- [Utilizar fuentes y texto](using-fonts-and-text.md)
