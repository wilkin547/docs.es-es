---
title: Procedimiento para rellenar una forma con una textura de imagen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: 42c456137f84c6fa657ba5a09727eae052a45376
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911686"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a><span data-ttu-id="b65d5-102">Procedimiento para rellenar una forma con una textura de imagen</span><span class="sxs-lookup"><span data-stu-id="b65d5-102">How to: Fill a Shape with an Image Texture</span></span>
<span data-ttu-id="b65d5-103">Puede rellenar una forma cerrada con una textura mediante la <xref:System.Drawing.Image> clase y la <xref:System.Drawing.TextureBrush> clase.</span><span class="sxs-lookup"><span data-stu-id="b65d5-103">You can fill a closed shape with a texture by using the <xref:System.Drawing.Image> class and the <xref:System.Drawing.TextureBrush> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b65d5-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b65d5-104">Example</span></span>  
 <span data-ttu-id="b65d5-105">En el ejemplo siguiente se rellena una elipse con una imagen.</span><span class="sxs-lookup"><span data-stu-id="b65d5-105">The following example fills an ellipse with an image.</span></span> <span data-ttu-id="b65d5-106">El código crea un <xref:System.Drawing.Image> objeto y, a continuación, pasa la dirección de ese <xref:System.Drawing.Image> objeto como un argumento a <xref:System.Drawing.TextureBrush.%23ctor%2A> un constructor.</span><span class="sxs-lookup"><span data-stu-id="b65d5-106">The code constructs an <xref:System.Drawing.Image> object, and then passes the address of that <xref:System.Drawing.Image> object as an argument to a <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="b65d5-107">La tercera instrucción escala la imagen y la cuarta instrucción rellena la elipse con copias repetidas de la imagen escalada.</span><span class="sxs-lookup"><span data-stu-id="b65d5-107">The third statement scales the image, and the fourth statement fills the ellipse with repeated copies of the scaled image.</span></span>  
  
 <span data-ttu-id="b65d5-108">En el código siguiente, la <xref:System.Drawing.TextureBrush.Transform%2A> propiedad contiene la transformación que se aplica a la imagen antes de dibujarse.</span><span class="sxs-lookup"><span data-stu-id="b65d5-108">In the following code, the <xref:System.Drawing.TextureBrush.Transform%2A> property contains the transformation that is applied to the image before it is drawn.</span></span> <span data-ttu-id="b65d5-109">Supongamos que la imagen original tiene un ancho de 640 píxeles y un alto de 480 píxeles.</span><span class="sxs-lookup"><span data-stu-id="b65d5-109">Assume that the original image has a width of 640 pixels and a height of 480 pixels.</span></span> <span data-ttu-id="b65d5-110">La transformación reduce la imagen a 75 × 75 estableciendo los valores de escalado horizontal y vertical.</span><span class="sxs-lookup"><span data-stu-id="b65d5-110">The transform shrinks the image to 75×75 by setting the horizontal and vertical scaling values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b65d5-111">En el ejemplo siguiente, el tamaño de la imagen es 75 × 75 y el tamaño de la elipse es 150 × 250.</span><span class="sxs-lookup"><span data-stu-id="b65d5-111">In the following example, the image size is 75×75, and the ellipse size is 150×250.</span></span> <span data-ttu-id="b65d5-112">Dado que la imagen es más pequeña que la elipse que está rellenando, la elipse se coloca en mosaico con la imagen.</span><span class="sxs-lookup"><span data-stu-id="b65d5-112">Because the image is smaller than the ellipse it is filling, the ellipse is tiled with the image.</span></span> <span data-ttu-id="b65d5-113">La disposición en mosaico significa que la imagen se repite horizontal y verticalmente hasta que se alcanza el límite de la forma.</span><span class="sxs-lookup"><span data-stu-id="b65d5-113">Tiling means that the image is repeated horizontally and vertically until the boundary of the shape is reached.</span></span> <span data-ttu-id="b65d5-114">Para obtener más información acerca de la [disposición en mosaico, consulte Cómo: Colocar una forma en mosaico con](how-to-tile-a-shape-with-an-image.md)una imagen.</span><span class="sxs-lookup"><span data-stu-id="b65d5-114">For more information about tiling, see [How to: Tile a Shape with an Image](how-to-tile-a-shape-with-an-image.md).</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b65d5-115">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b65d5-115">Compiling the Code</span></span>  
 <span data-ttu-id="b65d5-116">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que <xref:System.Windows.Forms.Control.Paint> es un parámetro del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="b65d5-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b65d5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b65d5-117">See also</span></span>

- [<span data-ttu-id="b65d5-118">Utilizar un pincel para rellenar formas</span><span class="sxs-lookup"><span data-stu-id="b65d5-118">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
