---
title: 'Cómo: Utilizar una matriz de color para transformar un color único'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
ms.openlocfilehash: 741259fcf853c82dfd13b43edc92e50d8767887b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527409"
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a>Cómo: Utilizar una matriz de color para transformar un color único
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona el <xref:System.Drawing.Image> y <xref:System.Drawing.Bitmap> clases para almacenar y manipular imágenes. <xref:System.Drawing.Image> y <xref:System.Drawing.Bitmap> objetos almacenan el color de cada píxel como un número de 32 bits: 8 bits para cada color rojo, verde, azul y alfa. Cada uno de los cuatro componentes es un número comprendido entre 0 y 255, donde 0 representa ninguna intensidad y que representa la intensidad máxima de 255. El componente alfa especifica la transparencia del color: 0 es totalmente transparente, y 255 es completamente opaco.  
  
 Un vector de color es una tupla de 4 del formulario (rojo, verde, azul, alfa). Por ejemplo, el vector de color (0, 255, 0, 255) representa un color opaco que no tiene ningún color rojo o azul, pero tiene verde con intensidad total.  
  
 Otra convención para representar los colores emplea el número 1 para la intensidad total. Mediante esta convención, el color descrito en el párrafo anterior se representarán mediante el vector (0, 1, 0, 1). [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] utiliza la convención 1 como intensidad total cuando realiza las transformaciones de color.  
  
 Puede aplicar transformaciones lineales (rotación, escala y similares) a los vectores de color multiplicando los vectores de color por una matriz de 4 x 4. Sin embargo, no se puede utilizar una matriz de 4 x 4 para realizar una conversión (no lineal). Si agrega una quinta coordenada ficticia (por ejemplo, el número 1) a cada uno de los vectores de color, puede usar una matriz de 5 x 5 para aplicar cualquier combinación de conversiones y transformaciones lineales. Una transformación que se compone de una transformación lineal seguida de una traducción se denomina una transformación afín.  
  
 Por ejemplo, imagine que desea empezar con el color (0.2, 0.0, 0.4, 1.0) y se aplican las siguientes transformaciones:  
  
1.  Duplique el componente rojo  
  
2.  Agregue 0.2 a los componentes rojos, verde y azules  
  
 La siguiente multiplicación de matrices realizará el par de transformaciones en el orden indicado.  
  
 ![Cambio de color](../../../../docs/framework/winforms/advanced/media/recoloring01.gif "recoloring01")  
  
 Los elementos de una matriz de color se indizan (basado en cero) por fila y, a continuación, la columna. Por ejemplo, la entrada en la quinta fila y la tercera columna de la matriz m. se indica mediante M [4] [2].  
  
 La matriz de identidad de 5 × 5 (se muestra en la siguiente ilustración) tiene números 1 en la diagonal y 0 en los demás lugares. Si multiplica un vector de color por la matriz de identidad, el vector de color no cambia. Una manera cómoda para formar la matriz de una transformación de color es empezar con la matriz de identidad y realizar un pequeño cambio que se produzca la transformación deseada.  
  
 ![Cambio de color](../../../../docs/framework/winforms/advanced/media/recoloring02.gif "recoloring02")  
  
 Para obtener una explicación más detallada de las matrices y las transformaciones, consulte [sistemas de coordenadas y transformaciones](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se toma una imagen de un color (0.2, 0.0, 0.4, 1.0) y se aplica la transformación descrita en los párrafos anteriores.  
  
 En la siguiente ilustración se muestra la imagen original a la izquierda y la imagen transformada a la derecha.  
  
 ![Colores](../../../../docs/framework/winforms/advanced/media/colortrans1.png "colortrans1")  
  
 El código en el ejemplo siguiente utiliza los siguientes pasos para realizar el cambio de color:  
  
1.  Inicializar un <xref:System.Drawing.Imaging.ColorMatrix> objeto.  
  
2.  Crear un <xref:System.Drawing.Imaging.ImageAttributes> objeto y pasar la <xref:System.Drawing.Imaging.ColorMatrix> el objeto a la <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> método de la <xref:System.Drawing.Imaging.ImageAttributes> objeto.  
  
3.  Pasar el <xref:System.Drawing.Imaging.ImageAttributes> el objeto a la <xref:System.Drawing.Graphics.DrawImage%2A> método de una <xref:System.Drawing.Graphics> objeto.  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también  
 [Cambiar el color de las imágenes](../../../../docs/framework/winforms/advanced/recoloring-images.md)  
 [Sistemas de coordenadas y transformaciones](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)
