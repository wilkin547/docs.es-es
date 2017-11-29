---
title: "Cómo: Disponer una forma en mosaico con una imagen"
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
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f825371d3849e96ace627e660fd7c59bd290185
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-tile-a-shape-with-an-image"></a>Cómo: Disponer una forma en mosaico con una imagen
Tal y como se pueden colocar iconos junto a la otra para cubrir una planta, se pueden colocar rectangulares imágenes junto a la otra para rellenar una forma (mosaico). El interior de una forma de mosaico, utilice un pincel de textura. Al construir un <xref:System.Drawing.TextureBrush> objeto, uno de los argumentos que se pasan al constructor es un <xref:System.Drawing.Image> objeto. Cuando se usa el pincel de textura para pintar el interior de una forma, la forma se rellena con las copias repetidas de esta imagen.  
  
 La propiedad del modo de ajuste de la <xref:System.Drawing.TextureBrush> objeto determina cómo se orienta la imagen cuando se repite en una cuadrícula rectangular. Puede realizar todos los iconos en la cuadrícula tienen la misma orientación o hacer que la imagen Voltear desde la posición de una cuadrícula a la siguiente. El volteo puede ser horizontal, vertical, o ambos. Los ejemplos siguientes muestran la disposición en mosaico con distintos tipos de volteo.  
  
### <a name="to-tile-an-image"></a>Para mostrar una imagen en mosaico  
  
-   Este ejemplo utiliza la siguiente imagen de 75 × 75 para disponer en mosaico un rectángulo de 200 × 200.  
  
 ![Icono 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")  
  
-   La ilustración siguiente muestra cómo se coloca en mosaico el rectángulo con la imagen. Tenga en cuenta que todas las piezas tienen la misma orientación; No hay ningún voltear.  
  
 ![Icono 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a>Para voltear una imagen horizontalmente al mosaico  
  
-   Este ejemplo utiliza la misma imagen de 75 × 75 para rellenar un rectángulo de 200 × 200. El modo de ajuste se establece en Voltear la imagen horizontalmente. La ilustración siguiente muestra cómo se coloca en mosaico el rectángulo con la imagen. Tenga en cuenta que, al pasar de un mosaico a la siguiente en una fila determinada, la imagen se voltean horizontalmente.  
  
 ![Icono 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a>Para voltear una imagen verticalmente al mosaico  
  
-   Este ejemplo utiliza la misma imagen de 75 × 75 para rellenar un rectángulo de 200 × 200. El modo de ajuste se establece en Voltear la imagen verticalmente.  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a>Para voltear una imagen horizontalmente y verticalmente al organizarla en mosaico  
  
-   Este ejemplo utiliza la misma imagen de 75 × 75 para disponer en mosaico un rectángulo de 200 × 200. Se establece el modo de ajuste para voltear la imagen horizontal y verticalmente. La ilustración siguiente muestra cómo se coloca en mosaico el rectángulo con la imagen. Tenga en cuenta que, al pasar de un mosaico a la siguiente en una fila determinada, la imagen se voltea horizontalmente y al pasar de un mosaico a la siguiente en una columna determinada, la imagen se voltea verticalmente.  
  
 ![Icono 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>Vea también  
 [Utilizar un pincel para rellenar formas](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
