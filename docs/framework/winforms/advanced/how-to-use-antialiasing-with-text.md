---
title: 'Cómo: Utilizar la función de suavizado de contorno con texto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
ms.openlocfilehash: 842c1fb0b73533fd2e87474b9e8cfa282eba2a70
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523115"
---
# <a name="how-to-use-antialiasing-with-text"></a>Cómo: Utilizar la función de suavizado de contorno con texto
*Suavizado de contorno* se refiere al suavizado de los bordes irregulares de gráficos y texto para mejorar su apariencia y legibilidad dibujados. Con los recursos administrados [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] clases, puede representar texto con suavizado de contorno de alta calidad, así como texto de menor calidad. Normalmente, una representación de calidad superior tarda más tiempo de procesamiento que una calidad inferior. Para establecer el nivel de calidad de texto, establezca la <xref:System.Drawing.Graphics.TextRenderingHint%2A> propiedad de un <xref:System.Drawing.Graphics> a uno de los elementos de la <xref:System.Drawing.Text.TextRenderingHint> (enumeración)  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se dibuja texto con dos configuraciones de calidad diferente.  
  
 En la siguiente ilustración se muestra el resultado del código de ejemplo.  
  
 ![Texto de las fuentes](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo de código anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
