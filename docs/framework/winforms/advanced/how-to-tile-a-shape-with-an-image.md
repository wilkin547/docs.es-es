---
title: Procedimiento para disponer una forma en mosaico con una imagen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
ms.openlocfilehash: ad7b8737a63028e533cadfa6db56b063eb943f22
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59221543"
---
# <a name="how-to-tile-a-shape-with-an-image"></a>Procedimiento para disponer una forma en mosaico con una imagen
Igual que los iconos se pueden colocar juntos para cubrir un piso, se pueden colocar imágenes rectangulares junto a la otra para rellenar una forma (mosaico). El interior de una forma de mosaico, utilice un pincel de textura. Cuando se construye un <xref:System.Drawing.TextureBrush> de objetos, uno de los argumentos que pasa al constructor es un <xref:System.Drawing.Image> objeto. Cuando se usa el pincel de textura para pintar el interior de una forma, la forma se rellena con las copias repetidas de esta imagen.  
  
 La propiedad del modo de ajuste el <xref:System.Drawing.TextureBrush> objeto determina cómo se orienta la imagen cuando se repite en una cuadrícula rectangular. Puede realizar todos los iconos en la cuadrícula tienen la misma orientación o se puede voltear la imagen desde la posición de una cuadrícula a la siguiente. El volteo puede ser horizontal, vertical o ambos. Los ejemplos siguientes muestran la disposición en mosaico con distintos tipos de volteo.  
  
### <a name="to-tile-an-image"></a>Para una imagen en mosaico  
  
-   Este ejemplo utiliza la siguiente imagen de 75 × 75 para disponer en mosaico un rectángulo de 200 × 200.  
  
 ![Icono 1](./media/tile1.gif "tile1")  
  
-   La siguiente ilustración muestra cómo se coloca en mosaico el rectángulo con la imagen. Tenga en cuenta que todos los iconos tienen la misma orientación; No hay ningún giro.  
  
 ![Icono 2](./media/tile2.gif "tile2")  
  
 [!code-csharp[System.Drawing.UsingABrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a>Para voltear una imagen horizontalmente durante la disposición en mosaico  
  
-   Este ejemplo utiliza la misma imagen de 75 × 75 para rellenar un rectángulo de 200 × 200. El modo de ajuste se establece en la imagen se voltea horizontalmente. La siguiente ilustración muestra cómo se coloca en mosaico el rectángulo con la imagen. Tenga en cuenta que, al desplazarse de un mosaico a la siguiente en una fila determinada, la imagen se voltea horizontalmente.  
  
 ![Icono 3](./media/tile3.gif "tile3")  
  
 [!code-csharp[System.Drawing.UsingABrush#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a>Para voltear una imagen verticalmente al mosaico  
  
-   Este ejemplo utiliza la misma imagen de 75 × 75 para rellenar un rectángulo de 200 × 200. El modo de ajuste se establece en la imagen se voltea verticalmente.  
  
     [!code-csharp[System.Drawing.UsingABrush#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a>Para voltear una imagen horizontal y verticalmente durante la disposición en mosaico  
  
-   Este ejemplo utiliza la misma imagen de 75 × 75 para disponer en mosaico un rectángulo de 200 × 200. Se establece el modo de ajuste se voltea la imagen horizontal y verticalmente. La siguiente ilustración muestra cómo el rectángulo se coloca en mosaico la imagen. Tenga en cuenta que, al desplazarse de un mosaico a la siguiente en una fila determinada, la imagen se voltea horizontalmente y al mover de un mosaico a la siguiente en una columna determinada, la imagen se voltea verticalmente.  
  
 ![Icono 5](./media/tile5.gif "tile5")  
  
 [!code-csharp[System.Drawing.UsingABrush#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>Vea también

- [Utilizar un pincel para rellenar formas](using-a-brush-to-fill-shapes.md)
