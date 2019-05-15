---
title: Procedimiento para convertir colores de imágenes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: fb9ec30c06740214b8dc6b65d32eba4e2920c89b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592934"
---
# <a name="how-to-translate-image-colors"></a>Procedimiento para convertir colores de imágenes
Una traducción, agrega un valor a uno o varios de los cuatro componentes de color. En la siguiente tabla figuran las entradas de la matriz de color que representan las traducciones.  
  
|Componente que se deben traducir|Entrada de matriz|  
|--------------------------------|------------------|  
|Rojo|[4][0]|  
|Verde|[4][1]|  
|Azul|[4][2]|  
|Alpha|[4][3]|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto a partir del archivo ColorBars.bmp. A continuación, el código agrega 0,75 al componente rojo de cada píxel de la imagen. Se dibuja la imagen original junto con la imagen transformada.  
  
 La siguiente ilustración muestra la imagen original a la izquierda y la imagen transformada de la derecha:  
  
 ![Captura de pantalla de la imagen original y transformada.](./media/how-to-translate-image-colors/original-image-translate-colors.png)  
  
 En la tabla siguiente se enumera los vectores de color de las cuatro barras antes y después de la traducción de color rojo. Tenga en cuenta que dado que el valor máximo para un componente de color es 1, el componente rojo de la segunda fila no cambia. (De forma similar, el valor mínimo de un componente de color es 0).  
  
|Original|Texto traducido al|  
|--------------|----------------|  
|Negro (0, 0, 0, 1)|(0.75, 0, 0, 1)|  
|Rojo (1, 0, 0, 1)|(1, 0, 0, 1)|  
|Verde (0, 1, 0, 1)|(0.75, 1, 0, 1)|  
|Azul (0, 0, 1, 1)|(0.75, 0, 1, 1)|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos. Reemplace `ColorBars.bmp` con un nombre de archivo de imagen y la ruta de acceso que son válidos en el sistema.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Cambiar el color de las imágenes](recoloring-images.md)
