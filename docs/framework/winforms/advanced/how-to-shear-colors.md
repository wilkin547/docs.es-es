---
title: "Cómo: Recortar colores"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35f89bb5d87ef58c5ecda7be4cb9fb41da08e8a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-shear-colors"></a>Cómo: Recortar colores
Distorsionar aumenta o disminuye un componente de color en una cantidad proporcional a otro componente de color. Por ejemplo, puede usar la transformación que aumenta el componente rojo en mitad del valor del componente azul. En este tipo de transformación, el color (0.2, 0.5, 1) se volverían (0,7, 0,5, 1). El nuevo componente rojo es 0,2 + (1/2)(1) = 0,7.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto desde el archivo ColorBars4.bmp. A continuación, el código aplica la transformación de recorte descrita en el párrafo anterior a cada píxel de la imagen.  
  
 En la siguiente ilustración se muestra la imagen original a la izquierda y la imagen sesgada a la derecha.  
  
 ![Sesgar colores](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")  
  
 En la tabla siguiente se enumera los vectores de color de las cuatro barras antes y después de la transformación de recorte.  
  
|Original|Deforma|  
|--------------|-------------|  
|(0, 0, 1, 1)|(0.5, 0, 1, 1)|  
|(0.5, 1, 0.5, 1)|(0.75, 1, 0.5, 1)|  
|(1, 1, 0, 1)|(1, 1, 0, 1)|  
|(0.4, 0.4, 0.4, 1)|(0.6, 0.4, 0.4, 1)|  
  
 [!code-csharp[System.Drawing.Misc3#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>. Reemplace `ColorBars.bmp` con un nombre de la imagen y la ruta de acceso válida en su sistema.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Cambiar el color de las imágenes](../../../../docs/framework/winforms/advanced/recoloring-images.md)
