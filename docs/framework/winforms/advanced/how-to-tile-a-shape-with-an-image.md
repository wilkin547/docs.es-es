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
ms.openlocfilehash: a906db44a548361df2822efa24d1dd1849cb5a24
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063740"
---
# <a name="how-to-tile-a-shape-with-an-image"></a><span data-ttu-id="3c454-102">Procedimiento para disponer una forma en mosaico con una imagen</span><span class="sxs-lookup"><span data-stu-id="3c454-102">How to: Tile a Shape with an Image</span></span>
<span data-ttu-id="3c454-103">Igual que los iconos se pueden colocar juntos para cubrir un piso, se pueden colocar imágenes rectangulares junto a la otra para rellenar una forma (mosaico).</span><span class="sxs-lookup"><span data-stu-id="3c454-103">Just as tiles can be placed next to each other to cover a floor, rectangular images can be placed next to each other to fill (tile) a shape.</span></span> <span data-ttu-id="3c454-104">El interior de una forma de mosaico, utilice un pincel de textura.</span><span class="sxs-lookup"><span data-stu-id="3c454-104">To tile the interior of a shape, use a texture brush.</span></span> <span data-ttu-id="3c454-105">Cuando se construye un <xref:System.Drawing.TextureBrush> de objetos, uno de los argumentos que pasa al constructor es un <xref:System.Drawing.Image> objeto.</span><span class="sxs-lookup"><span data-stu-id="3c454-105">When you construct a <xref:System.Drawing.TextureBrush> object, one of the arguments you pass to the constructor is an <xref:System.Drawing.Image> object.</span></span> <span data-ttu-id="3c454-106">Cuando se usa el pincel de textura para pintar el interior de una forma, la forma se rellena con las copias repetidas de esta imagen.</span><span class="sxs-lookup"><span data-stu-id="3c454-106">When you use the texture brush to paint the interior of a shape, the shape is filled with repeated copies of this image.</span></span>  
  
 <span data-ttu-id="3c454-107">La propiedad del modo de ajuste el <xref:System.Drawing.TextureBrush> objeto determina cómo se orienta la imagen cuando se repite en una cuadrícula rectangular.</span><span class="sxs-lookup"><span data-stu-id="3c454-107">The wrap mode property of the <xref:System.Drawing.TextureBrush> object determines how the image is oriented as it is repeated in a rectangular grid.</span></span> <span data-ttu-id="3c454-108">Puede realizar todos los iconos en la cuadrícula tienen la misma orientación o se puede voltear la imagen desde la posición de una cuadrícula a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="3c454-108">You can make all the tiles in the grid have the same orientation, or you can make the image flip from one grid position to the next.</span></span> <span data-ttu-id="3c454-109">El volteo puede ser horizontal, vertical o ambos.</span><span class="sxs-lookup"><span data-stu-id="3c454-109">The flipping can be horizontal, vertical, or both.</span></span> <span data-ttu-id="3c454-110">Los ejemplos siguientes muestran la disposición en mosaico con distintos tipos de volteo.</span><span class="sxs-lookup"><span data-stu-id="3c454-110">The following examples demonstrate tiling with different types of flipping.</span></span>  
  
### <a name="to-tile-an-image"></a><span data-ttu-id="3c454-111">Para una imagen en mosaico</span><span class="sxs-lookup"><span data-stu-id="3c454-111">To tile an image</span></span>  
  
- <span data-ttu-id="3c454-112">Este ejemplo utiliza la siguiente imagen de 75 × 75 para disponer en mosaico un rectángulo de 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="3c454-112">This example uses the following 75×75 image to tile a 200×200 rectangle.</span></span>  
  
 ![La imagen de icono que muestra una casa rojo y un árbol.](./media/how-to-tile-a-shape-with-an-image/rectangle-tile-200x200.gif)  
  
- <span data-ttu-id="3c454-114">La siguiente ilustración muestra cómo se coloca en mosaico el rectángulo con la imagen.</span><span class="sxs-lookup"><span data-stu-id="3c454-114">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="3c454-115">Tenga en cuenta que todos los iconos tienen la misma orientación; No hay ningún giro.</span><span class="sxs-lookup"><span data-stu-id="3c454-115">Note that all tiles have the same orientation; there is no flipping.</span></span>  
  
 ![Un rectángulo en mosaico con la imagen con la orientación de la misma para todos los iconos.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-no-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a><span data-ttu-id="3c454-117">Para voltear una imagen horizontalmente durante la disposición en mosaico</span><span class="sxs-lookup"><span data-stu-id="3c454-117">To flip an image horizontally while tiling</span></span>  
  
- <span data-ttu-id="3c454-118">Este ejemplo utiliza la misma imagen de 75 × 75 para rellenar un rectángulo de 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="3c454-118">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="3c454-119">El modo de ajuste se establece en la imagen se voltea horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="3c454-119">The wrap mode is set to flip the image horizontally.</span></span> <span data-ttu-id="3c454-120">La siguiente ilustración muestra cómo se coloca en mosaico el rectángulo con la imagen.</span><span class="sxs-lookup"><span data-stu-id="3c454-120">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="3c454-121">Tenga en cuenta que, al desplazarse de un mosaico a la siguiente en una fila determinada, la imagen se voltea horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="3c454-121">Note that as you move from one tile to the next in a given row, the image is flipped horizontally.</span></span>  
  
 ![Un rectángulo en mosaico con la imagen se voltea horizontalmente.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a><span data-ttu-id="3c454-123">Para voltear una imagen verticalmente al mosaico</span><span class="sxs-lookup"><span data-stu-id="3c454-123">To flip an image vertically while tiling</span></span>  
  
- <span data-ttu-id="3c454-124">Este ejemplo utiliza la misma imagen de 75 × 75 para rellenar un rectángulo de 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="3c454-124">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="3c454-125">El modo de ajuste se establece en la imagen se voltea verticalmente.</span><span class="sxs-lookup"><span data-stu-id="3c454-125">The wrap mode is set to flip the image vertically.</span></span>  
  
     [!code-csharp[System.Drawing.UsingABrush#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a><span data-ttu-id="3c454-126">Para voltear una imagen horizontal y verticalmente durante la disposición en mosaico</span><span class="sxs-lookup"><span data-stu-id="3c454-126">To flip an image horizontally and vertically while tiling</span></span>  
  
- <span data-ttu-id="3c454-127">Este ejemplo utiliza la misma imagen de 75 × 75 para disponer en mosaico un rectángulo de 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="3c454-127">This example uses the same 75×75 image to tile a 200×200 rectangle.</span></span> <span data-ttu-id="3c454-128">Se establece el modo de ajuste se voltea la imagen horizontal y verticalmente.</span><span class="sxs-lookup"><span data-stu-id="3c454-128">The wrap mode is set to flip the image both horizontally and vertically.</span></span> <span data-ttu-id="3c454-129">La siguiente ilustración muestra cómo el rectángulo se coloca en mosaico la imagen.</span><span class="sxs-lookup"><span data-stu-id="3c454-129">The following illustration shows how the rectangle is tiled by the image.</span></span> <span data-ttu-id="3c454-130">Tenga en cuenta que, al desplazarse de un mosaico a la siguiente en una fila determinada, la imagen se voltea horizontalmente y al mover de un mosaico a la siguiente en una columna determinada, la imagen se voltea verticalmente.</span><span class="sxs-lookup"><span data-stu-id="3c454-130">Note that as you move from one tile to the next in a given row, the image is flipped horizontally, and as you move from one tile to the next in a given column, the image is flipped vertically.</span></span>  
  
 ![Un rectángulo en mosaico con la imagen se voltea horizontalmente y verticalmente.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-vertical-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="3c454-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c454-132">See also</span></span>

- [<span data-ttu-id="3c454-133">Utilizar un pincel para rellenar formas</span><span class="sxs-lookup"><span data-stu-id="3c454-133">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
