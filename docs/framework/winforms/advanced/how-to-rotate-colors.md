---
title: Procedimiento Rotar colores
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: cb3824d8a5a5674b83124301dbfbd5a3ba60effa
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720623"
---
# <a name="how-to-rotate-colors"></a>Filtrar Rotar colores
Es difícil visualizar la rotación en un espacio de colores de cuatro dimensiones. Podemos lo hacemos más fácil visualizar la rotación mediante decidido mantener uno de los componentes de color fijo. Supongamos que estamos de acuerdo mantener el componente alfa en 1 (completamente opaco). A continuación, podemos visualizar un espacio tridimensional de color con ejes de rojos, verde y azules como se muestra en la siguiente ilustración.  
  
 ![Cambiar el color de](./media/recoloring03.gif "recoloring03")  
  
 Un color puede considerarse como un punto en el espacio 3D. Por ejemplo, el punto (1, 0, 0) en el espacio representa el color rojo y el punto (0, 1, 0) en el espacio representa el color verde.  
  
 En la siguiente ilustración se muestra lo que significa girar el color (1, 0, 0) a través de un ángulo de 60 grados en el plano de color rojo verde. Rotación en un plano paralelo al plano de color rojo verde puede considerarse como la rotación sobre el eje azul.  
  
 ![Cambiar el color de](./media/recoloring04.gif "recoloring04")  
  
 La siguiente ilustración muestra cómo inicializar una matriz de colores para llevar a cabo las rotaciones sobre cada uno de los tres ejes de coordenadas (rojo, verde, azul).  
  
 ![Cambiar el color de](./media/recoloring05.gif "recoloring05")  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente toma una imagen que es un color (1, 0, 0,6) y se aplica un giro de 60 grados sobre el eje azul. El ángulo de rotación se trazará en un plano paralelo al plano de color rojo verde.  
  
 La siguiente ilustración muestra la imagen original a la izquierda y la imagen gira de color de la derecha.  
  
 ![Rotar colores](./media/colortrans5.png "colortrans5")  
  
 La siguiente ilustración muestra una visualización de la rotación de color realizada en el código siguiente.  
  
 ![Cambiar el color de](./media/recoloring06.gif "recoloring06")  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>. Reemplace `RotationInput.bmp` con un nombre de archivo de imagen y la ruta de acceso válida en su sistema.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Cambiar el color de las imágenes](recoloring-images.md)
