---
title: Filtrar Usa suavizado de contorno con texto
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
ms.openlocfilehash: b0dc3cf5cff9cf3e163478861ec55a05427ad6ce
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718576"
---
# <a name="how-to-use-antialiasing-with-text"></a>Procedimiento Usa suavizado de contorno con texto
*Suavizado de contorno* hace referencia al suavizado de los bordes escalonados de dibujados gráficos y texto para mejorar su apariencia y legibilidad. Con el administrado [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] clases, puede representar texto con suavizado de contorno de alta calidad, así como texto de menor calidad. Normalmente, una representación de mayor calidad toma más tiempo de procesamiento que una calidad inferior. Para establecer el nivel de calidad de texto, establezca el <xref:System.Drawing.Graphics.TextRenderingHint%2A> propiedad de un <xref:System.Drawing.Graphics> a uno de los elementos de la <xref:System.Drawing.Text.TextRenderingHint> (enumeración)  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se dibuja texto con dos configuraciones de calidad diferente.  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
 
 La siguiente ilustración muestra la salida del código de ejemplo:  
  
 ![Fonts Text](./media/fontstext10.png "FontsText10")  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo de código anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también
- [Utilizar fuentes y texto](using-fonts-and-text.md)
