---
title: "Cómo: Rotar colores"
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
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81b022011bd5613b8e956aa83482d2836508a4f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-rotate-colors"></a>Cómo: Rotar colores
Rotación en un espacio de colores de cuatro dimensiones es difícil de visualizar. Podemos facilitar la visualizar rotación decidido mantener uno de los componentes de color fijo. Supongamos que se decide mantener el componente alfa fijado en 1 (completamente opaco). A continuación, podemos visualizar un espacio de color tridimensional con ejes de rojos, verde y azules como se muestra en la siguiente ilustración.  
  
 ![Cambio de color](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")  
  
 Un color puede considerarse como un punto en un espacio 3D. Por ejemplo, el punto (1, 0, 0) en un espacio representa el color rojo y el punto (0, 1, 0) en un espacio representa el color verde.  
  
 En la siguiente ilustración se muestra lo que significa para rotar el color (1, 0, 0) a través de un ángulo de 60 grados en el plano rojo y verde. Rotación en un plano paralelo al plano rojo-verde puede considerarse como una rotación sobre el eje azul.  
  
 ![Cambio de color](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")  
  
 La ilustración siguiente muestra cómo inicializar una matriz de color para realizar rotaciones sobre cada uno de los tres ejes de coordenadas (rojo, verde, azul).  
  
 ![Cambio de color](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se toma una imagen que es un color (1, 0, 0,6) y se aplica una rotación de 60 grados sobre el eje azul. El ángulo de rotación se trazará en un plano paralelo al plano rojo y verde.  
  
 En la siguiente ilustración se muestra la imagen original a la izquierda y la imagen gira de color de la derecha.  
  
 ![Rotar colores](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")  
  
 En la siguiente ilustración muestra una visualización de la rotación de color realizada en el código siguiente.  
  
 ![Cambio de color](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")  
  
 [!code-csharp[System.Drawing.RotateColors#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos. Reemplace `RotationInput.bmp` con un nombre de archivo de imagen y la ruta de acceso válida en su sistema.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Cambiar el color de las imágenes](../../../../docs/framework/winforms/advanced/recoloring-images.md)
