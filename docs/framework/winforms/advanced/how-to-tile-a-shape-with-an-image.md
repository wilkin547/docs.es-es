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
# <a name="how-to-tile-a-shape-with-an-image"></a><span data-ttu-id="b3f7d-102">Cómo: Disponer una forma en mosaico con una imagen</span><span class="sxs-lookup"><span data-stu-id="b3f7d-102">How to: Tile a Shape with an Image</span></span>
<span data-ttu-id="b3f7d-103">Tal y como se pueden colocar iconos junto a la otra para cubrir una planta, se pueden colocar rectangulares imágenes junto a la otra para rellenar una forma (mosaico).</span><span class="sxs-lookup"><span data-stu-id="b3f7d-103">Just as tiles can be placed next to each other to cover a floor, rectangular images can be placed next to each other to fill (tile) a shape.</span></span> <span data-ttu-id="b3f7d-104">El interior de una forma de mosaico, utilice un pincel de textura.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-104">To tile the interior of a shape, use a texture brush.</span></span> <span data-ttu-id="b3f7d-105">Al construir un <xref:System.Drawing.TextureBrush> objeto, uno de los argumentos que se pasan al constructor es un <xref:System.Drawing.Image> objeto.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-105">When you construct a <xref:System.Drawing.TextureBrush> object, one of the arguments you pass to the constructor is an <xref:System.Drawing.Image> object.</span></span> <span data-ttu-id="b3f7d-106">Cuando se usa el pincel de textura para pintar el interior de una forma, la forma se rellena con las copias repetidas de esta imagen.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-106">When you use the texture brush to paint the interior of a shape, the shape is filled with repeated copies of this image.</span></span>  
  
 <span data-ttu-id="b3f7d-107">La propiedad del modo de ajuste de la <xref:System.Drawing.TextureBrush> objeto determina cómo se orienta la imagen cuando se repite en una cuadrícula rectangular.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-107">The wrap mode property of the <xref:System.Drawing.TextureBrush> object determines how the image is oriented as it is repeated in a rectangular grid.</span></span> <span data-ttu-id="b3f7d-108">Puede realizar todos los iconos en la cuadrícula tienen la misma orientación o hacer que la imagen Voltear desde la posición de una cuadrícula a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-108">You can make all the tiles in the grid have the same orientation, or you can make the image flip from one grid position to the next.</span></span> <span data-ttu-id="b3f7d-109">El volteo puede ser horizontal, vertical, o ambos.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-109">The flipping can be horizontal, vertical, or both.</span></span> <span data-ttu-id="b3f7d-110">Los ejemplos siguientes muestran la disposición en mosaico con distintos tipos de volteo.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-110">The following examples demonstrate tiling with different types of flipping.</span></span>  
  
### <a name="to-tile-an-image"></a><span data-ttu-id="b3f7d-111">Para mostrar una imagen en mosaico</span><span class="sxs-lookup"><span data-stu-id="b3f7d-111">To tile an image</span></span>  
  
-   <span data-ttu-id="b3f7d-112">Este ejemplo utiliza la siguiente imagen de 75 × 75 para disponer en mosaico un rectángulo de 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-112">This example uses the following 75×75 image to tile a 200×200 rectangle.</span></span>  
  
 <span data-ttu-id="b3f7d-113">![Icono 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span><span class="sxs-lookup"><span data-stu-id="b3f7d-113">![Tile 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span></span>  
  
-   <span data-ttu-id="b3f7d-114">La ilustración siguiente muestra cómo se coloca en mosaico el rectángulo con la imagen.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-114">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="b3f7d-115">Tenga en cuenta que todas las piezas tienen la misma orientación; No hay ningún voltear.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-115">Note that all tiles have the same orientation; there is no flipping.</span></span>  
  
 <span data-ttu-id="b3f7d-116">![Icono 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span><span class="sxs-lookup"><span data-stu-id="b3f7d-116">![Tile 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a><span data-ttu-id="b3f7d-117">Para voltear una imagen horizontalmente al mosaico</span><span class="sxs-lookup"><span data-stu-id="b3f7d-117">To flip an image horizontally while tiling</span></span>  
  
-   <span data-ttu-id="b3f7d-118">Este ejemplo utiliza la misma imagen de 75 × 75 para rellenar un rectángulo de 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-118">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="b3f7d-119">El modo de ajuste se establece en Voltear la imagen horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-119">The wrap mode is set to flip the image horizontally.</span></span> <span data-ttu-id="b3f7d-120">La ilustración siguiente muestra cómo se coloca en mosaico el rectángulo con la imagen.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-120">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="b3f7d-121">Tenga en cuenta que, al pasar de un mosaico a la siguiente en una fila determinada, la imagen se voltean horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-121">Note that as you move from one tile to the next in a given row, the image is flipped horizontally.</span></span>  
  
 <span data-ttu-id="b3f7d-122">![Icono 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span><span class="sxs-lookup"><span data-stu-id="b3f7d-122">![Tile 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a><span data-ttu-id="b3f7d-123">Para voltear una imagen verticalmente al mosaico</span><span class="sxs-lookup"><span data-stu-id="b3f7d-123">To flip an image vertically while tiling</span></span>  
  
-   <span data-ttu-id="b3f7d-124">Este ejemplo utiliza la misma imagen de 75 × 75 para rellenar un rectángulo de 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-124">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="b3f7d-125">El modo de ajuste se establece en Voltear la imagen verticalmente.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-125">The wrap mode is set to flip the image vertically.</span></span>  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a><span data-ttu-id="b3f7d-126">Para voltear una imagen horizontalmente y verticalmente al organizarla en mosaico</span><span class="sxs-lookup"><span data-stu-id="b3f7d-126">To flip an image horizontally and vertically while tiling</span></span>  
  
-   <span data-ttu-id="b3f7d-127">Este ejemplo utiliza la misma imagen de 75 × 75 para disponer en mosaico un rectángulo de 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-127">This example uses the same 75×75 image to tile a 200×200 rectangle.</span></span> <span data-ttu-id="b3f7d-128">Se establece el modo de ajuste para voltear la imagen horizontal y verticalmente.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-128">The wrap mode is set to flip the image both horizontally and vertically.</span></span> <span data-ttu-id="b3f7d-129">La ilustración siguiente muestra cómo se coloca en mosaico el rectángulo con la imagen.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-129">The following illustration shows how the rectangle is tiled by the image.</span></span> <span data-ttu-id="b3f7d-130">Tenga en cuenta que, al pasar de un mosaico a la siguiente en una fila determinada, la imagen se voltea horizontalmente y al pasar de un mosaico a la siguiente en una columna determinada, la imagen se voltea verticalmente.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-130">Note that as you move from one tile to the next in a given row, the image is flipped horizontally, and as you move from one tile to the next in a given column, the image is flipped vertically.</span></span>  
  
 <span data-ttu-id="b3f7d-131">![Icono 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span><span class="sxs-lookup"><span data-stu-id="b3f7d-131">![Tile 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="b3f7d-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3f7d-132">See Also</span></span>  
 [<span data-ttu-id="b3f7d-133">Utilizar un pincel para rellenar formas</span><span class="sxs-lookup"><span data-stu-id="b3f7d-133">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
