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
ms.openlocfilehash: 632ed329173d134495a424b34ca7c71e402607bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182484"
---
# <a name="how-to-use-antialiasing-with-text"></a>Cómo: Utilizar la función de suavizado de contorno con texto
*Antialiasing* se refiere al suavizado de bordes irregulares de gráficos dibujados y texto para mejorar su apariencia o legibilidad. Con las clases GDI+GDI+ administradas, puede representar texto antialiased de alta calidad, así como texto de menor calidad. Normalmente, el renderizado de mayor calidad requiere más tiempo de procesamiento que el renderizado de menor calidad. Para establecer el nivel de <xref:System.Drawing.Graphics.TextRenderingHint%2A> calidad <xref:System.Drawing.Graphics> del texto, establezca <xref:System.Drawing.Text.TextRenderingHint> la propiedad de a en uno de los elementos de la enumeración  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se dibuja texto con dos configuraciones de calidad diferentes.  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  

 La siguiente ilustración muestra la salida del código de ejemplo:  
  
 ![Captura de pantalla que muestra texto con dos configuraciones de calidad diferentes.](./media/how-to-use-antialiasing-with-text/antialiasing-text-quality-settings.png)  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo de código anterior está diseñado para su <xref:System.Windows.Forms.PaintEventArgs> `e`uso con formularios <xref:System.Windows.Forms.PaintEventHandler>Windows Forms y requiere , que es un parámetro de .  
  
## <a name="see-also"></a>Consulte también

- [Utilizar fuentes y texto](using-fonts-and-text.md)
