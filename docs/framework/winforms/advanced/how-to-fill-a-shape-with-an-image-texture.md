---
title: "Cómo: Rellenar una forma con una textura de imagen"
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
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c20562cade6917a3426fe04861a05c4b6b0bd543
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a><span data-ttu-id="d5c78-102">Cómo: Rellenar una forma con una textura de imagen</span><span class="sxs-lookup"><span data-stu-id="d5c78-102">How to: Fill a Shape with an Image Texture</span></span>
<span data-ttu-id="d5c78-103">Puede rellenar una forma cerrada con una textura utilizando la <xref:System.Drawing.Image> clase y la <xref:System.Drawing.TextureBrush> clase.</span><span class="sxs-lookup"><span data-stu-id="d5c78-103">You can fill a closed shape with a texture by using the <xref:System.Drawing.Image> class and the <xref:System.Drawing.TextureBrush> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5c78-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5c78-104">Example</span></span>  
 <span data-ttu-id="d5c78-105">En el ejemplo siguiente se rellena una elipse con una imagen.</span><span class="sxs-lookup"><span data-stu-id="d5c78-105">The following example fills an ellipse with an image.</span></span> <span data-ttu-id="d5c78-106">El código construye una <xref:System.Drawing.Image> objeto y, a continuación, pasa la dirección de ese <xref:System.Drawing.Image> objeto como argumento a un <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="d5c78-106">The code constructs an <xref:System.Drawing.Image> object, and then passes the address of that <xref:System.Drawing.Image> object as an argument to a <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="d5c78-107">La tercera instrucción escala la imagen y la cuarta rellena la elipse con las copias repetidas de la imagen escalada.</span><span class="sxs-lookup"><span data-stu-id="d5c78-107">The third statement scales the image, and the fourth statement fills the ellipse with repeated copies of the scaled image.</span></span>  
  
 <span data-ttu-id="d5c78-108">En el código siguiente, la <xref:System.Drawing.TextureBrush.Transform%2A> propiedad contiene la transformación que se aplica a la imagen antes de dibujarlo.</span><span class="sxs-lookup"><span data-stu-id="d5c78-108">In the following code, the <xref:System.Drawing.TextureBrush.Transform%2A> property contains the transformation that is applied to the image before it is drawn.</span></span> <span data-ttu-id="d5c78-109">Suponga que la imagen original tiene un ancho de 640 píxeles y un alto de 480 píxeles.</span><span class="sxs-lookup"><span data-stu-id="d5c78-109">Assume that the original image has a width of 640 pixels and a height of 480 pixels.</span></span> <span data-ttu-id="d5c78-110">La transformación reduce la imagen a 75 × 75 estableciendo los valores de escalado horizontales y verticales.</span><span class="sxs-lookup"><span data-stu-id="d5c78-110">The transform shrinks the image to 75×75 by setting the horizontal and vertical scaling values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5c78-111">En el ejemplo siguiente, el tamaño de la imagen es de 75 × 75 y el tamaño de la elipse es de 150 × 250.</span><span class="sxs-lookup"><span data-stu-id="d5c78-111">In the following example, the image size is 75×75, and the ellipse size is 150×250.</span></span> <span data-ttu-id="d5c78-112">Dado que la imagen es más pequeña que la elipse que va a rellenar, la elipse se coloca en mosaico con la imagen.</span><span class="sxs-lookup"><span data-stu-id="d5c78-112">Because the image is smaller than the ellipse it is filling, the ellipse is tiled with the image.</span></span> <span data-ttu-id="d5c78-113">Se alcanzó la disposición en mosaico, que la imagen se repite horizontal y verticalmente hasta que el límite de la forma.</span><span class="sxs-lookup"><span data-stu-id="d5c78-113">Tiling means that the image is repeated horizontally and vertically until the boundary of the shape is reached.</span></span> <span data-ttu-id="d5c78-114">Para obtener más información acerca de la segmentación, consulte [Cómo: colocar en mosaico una forma con una imagen](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).</span><span class="sxs-lookup"><span data-stu-id="d5c78-114">For more information about tiling, see [How to: Tile a Shape with an Image](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d5c78-115">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d5c78-115">Compiling the Code</span></span>  
 <span data-ttu-id="d5c78-116">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="d5c78-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5c78-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5c78-117">See Also</span></span>  
 [<span data-ttu-id="d5c78-118">Utilizar un pincel para rellenar formas</span><span class="sxs-lookup"><span data-stu-id="d5c78-118">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
