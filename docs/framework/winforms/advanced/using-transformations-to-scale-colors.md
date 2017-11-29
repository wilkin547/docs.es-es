---
title: Utilizar transformaciones para ajustar la escala de los colores
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
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a4584b74cd7a394f7dd04d0cfba150b907ca7c82
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="using-transformations-to-scale-colors"></a>Utilizar transformaciones para ajustar la escala de los colores
Una transformación de escala multiplica uno o varios de los cuatro componentes de color por un número. Las entradas de la matriz de color que representan el ajuste de escala se proporcionan en la tabla siguiente.  
  
|Componente escalar|Entrada de matriz|  
|----------------------------|------------------|  
|Rojo|[0][0]|  
|Verde|[1][1]|  
|Azul|[2][2]|  
|Alpha|[3][3]|  
  
## <a name="scaling-one-color"></a>Ajuste de escala en un Color  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto a partir del archivo ColorBars2.bmp. A continuación, el código ajusta el componente azul de cada píxel de la imagen en un factor de 2. Se dibuja la imagen original junto con la imagen transformada.  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 En la siguiente ilustración se muestra la imagen original a la izquierda y la imagen escalada a la derecha.  
  
 ![Escala de colores](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")  
  
 En la tabla siguiente se recogen los vectores de color de las cuatro barras antes y después de ajustar el azul. Tenga en cuenta que el componente azul de la cuarta barra de color pasó de 0,8 a 0,6. Esto es así porque [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] conserva solo la parte fraccionaria del resultado. Por ejemplo, (2)(0.8) = 1.6, y la parte fraccionaria de 1,6 es 0,6. Conserva solo la parte fraccionaria, se garantiza que el resultado está siempre en el intervalo [0, 1].  
  
|Original|Escalar|  
|--------------|------------|  
|(0.4, 0.4, 0.4, 1)|(0.4, 0.4, 0.8, 1)|  
|(0.4, 0.2, 0.2, 1)|(0.4, 0.2, 0.4, 1)|  
|(0.2, 0.4, 0.2, 1)|(0.2, 0.4, 0.4, 1)|  
|(0.4, 0.4, 0.8, 1)|(0.4, 0.4, 0.6, 1)|  
  
## <a name="scaling-multiple-colors"></a>Ajuste de escala en varios colores  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto a partir del archivo ColorBars2.bmp. A continuación, el código ajusta los componentes rojos, verde y azules de cada píxel de la imagen. Los componentes rojos son reducidos de 25 por ciento, se escalan los componentes verde hacia abajo un 35% y los componentes de color azules son reducidos 50 por ciento.  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 En la siguiente ilustración se muestra la imagen original a la izquierda y la imagen escalada a la derecha.  
  
 ![Escala de colores](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")  
  
 En la tabla siguiente se enumera los vectores de color de las cuatro barras antes y después de la escala de color rojo, verde y azul.  
  
|Original|Escalar|  
|--------------|------------|  
|(0.6, 0.6, 0.6, 1)|(0.45, 0.39, 0.3, 1)|  
|(0, 1, 1, 1)|(0, 0.65, 0.5, 1)|  
|(1, 1, 0, 1)|(0.75, 0.65, 0, 1)|  
|(1, 0, 1, 1)|(0.75, 0, 0.5, 1)|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Cambiar el color de las imágenes](../../../../docs/framework/winforms/advanced/recoloring-images.md)
