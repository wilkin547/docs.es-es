---
title: 'Cómo: Rotar colores'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 8d2717dd7b819e963126072279b361fda02188bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111340"
---
# <a name="how-to-rotate-colors"></a>Cómo: Rotar colores
La rotación en un espacio de color de cuatro dimensiones es difícil de visualizar. Podemos facilitar la visualización de la rotación aceptando mantener uno de los componentes de color fijos. Supongamos que estamos de acuerdo en mantener el componente alfa fijo en 1 (totalmente opaco). A continuación, podemos visualizar un espacio de color tridimensional con ejes rojos, verdes y azules, como se muestra en la siguiente ilustración.  
  
 ![Ilustración que muestra la rotación con ejes rojos, verdes y azules.](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 Un color se puede considerar como un punto en el espacio 3D. Por ejemplo, el punto (1, 0, 0) en el espacio representa el color rojo y el punto (0, 1, 0) en el espacio representa el color verde.  
  
 La siguiente ilustración muestra lo que significa girar el color (1, 0, 0) a través de un ángulo de 60 grados en el plano rojo-verde. La rotación en un plano paralelo al plano rojo-verde se puede considerar como rotación sobre el eje azul.  
  
 ![Ilustración que muestra la rotación sobre el eje azul.](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 En la ilustración siguiente se muestra cómo inicializar una matriz de colorpara realizar rotaciones sobre cada uno de los tres ejes de coordenadas (rojo, verde, azul):  
  
 ![Inicializar una matriz de color para realizar rotaciones de unos tres ejes.](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se toma una imagen de un color (1, 0, 0,6) y se aplica una rotación de 60 grados sobre el eje azul. El ángulo de rotación se barre en un plano paralelo al plano rojo-verde.  
  
 La siguiente ilustración muestra la imagen original a la izquierda y la imagen girada en color a la derecha:  
  
 ![Ilustración que muestra la imagen original y la imagen rotada en color.](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 En la ilustración siguiente se muestra una visualización de la rotación de color realizada en el código siguiente:
  
 ![Ilustración que muestra la visualización de la rotación de color.](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso <xref:System.Windows.Forms.PaintEventArgs> `e`con formularios Windows Forms, y requiere , que es un parámetro del <xref:System.Windows.Forms.Control.Paint> controlador de eventos. Reemplace `RotationInput.bmp` por un nombre de archivo de imagen y una ruta válida en el sistema.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Cambiar el color de las imágenes](recoloring-images.md)
