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
# <a name="how-to-rotate-colors"></a><span data-ttu-id="b91e3-102">Filtrar Rotar colores</span><span class="sxs-lookup"><span data-stu-id="b91e3-102">How to: Rotate Colors</span></span>
<span data-ttu-id="b91e3-103">Es difícil visualizar la rotación en un espacio de colores de cuatro dimensiones.</span><span class="sxs-lookup"><span data-stu-id="b91e3-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="b91e3-104">Podemos lo hacemos más fácil visualizar la rotación mediante decidido mantener uno de los componentes de color fijo.</span><span class="sxs-lookup"><span data-stu-id="b91e3-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="b91e3-105">Supongamos que estamos de acuerdo mantener el componente alfa en 1 (completamente opaco).</span><span class="sxs-lookup"><span data-stu-id="b91e3-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="b91e3-106">A continuación, podemos visualizar un espacio tridimensional de color con ejes de rojos, verde y azules como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="b91e3-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="b91e3-107">![Cambiar el color de](./media/recoloring03.gif "recoloring03")</span><span class="sxs-lookup"><span data-stu-id="b91e3-107">![Recoloring](./media/recoloring03.gif "recoloring03")</span></span>  
  
 <span data-ttu-id="b91e3-108">Un color puede considerarse como un punto en el espacio 3D.</span><span class="sxs-lookup"><span data-stu-id="b91e3-108">A color can be thought of as a point in 3-D space.</span></span> <span data-ttu-id="b91e3-109">Por ejemplo, el punto (1, 0, 0) en el espacio representa el color rojo y el punto (0, 1, 0) en el espacio representa el color verde.</span><span class="sxs-lookup"><span data-stu-id="b91e3-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="b91e3-110">En la siguiente ilustración se muestra lo que significa girar el color (1, 0, 0) a través de un ángulo de 60 grados en el plano de color rojo verde.</span><span class="sxs-lookup"><span data-stu-id="b91e3-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="b91e3-111">Rotación en un plano paralelo al plano de color rojo verde puede considerarse como la rotación sobre el eje azul.</span><span class="sxs-lookup"><span data-stu-id="b91e3-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 <span data-ttu-id="b91e3-112">![Cambiar el color de](./media/recoloring04.gif "recoloring04")</span><span class="sxs-lookup"><span data-stu-id="b91e3-112">![Recoloring](./media/recoloring04.gif "recoloring04")</span></span>  
  
 <span data-ttu-id="b91e3-113">La siguiente ilustración muestra cómo inicializar una matriz de colores para llevar a cabo las rotaciones sobre cada uno de los tres ejes de coordenadas (rojo, verde, azul).</span><span class="sxs-lookup"><span data-stu-id="b91e3-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue).</span></span>  
  
 <span data-ttu-id="b91e3-114">![Cambiar el color de](./media/recoloring05.gif "recoloring05")</span><span class="sxs-lookup"><span data-stu-id="b91e3-114">![Recoloring](./media/recoloring05.gif "recoloring05")</span></span>  
  
## <a name="example"></a><span data-ttu-id="b91e3-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b91e3-115">Example</span></span>  
 <span data-ttu-id="b91e3-116">El ejemplo siguiente toma una imagen que es un color (1, 0, 0,6) y se aplica un giro de 60 grados sobre el eje azul.</span><span class="sxs-lookup"><span data-stu-id="b91e3-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="b91e3-117">El ángulo de rotación se trazará en un plano paralelo al plano de color rojo verde.</span><span class="sxs-lookup"><span data-stu-id="b91e3-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="b91e3-118">La siguiente ilustración muestra la imagen original a la izquierda y la imagen gira de color de la derecha.</span><span class="sxs-lookup"><span data-stu-id="b91e3-118">The following illustration shows the original image on the left and the color-rotated image on the right.</span></span>  
  
 <span data-ttu-id="b91e3-119">![Rotar colores](./media/colortrans5.png "colortrans5")</span><span class="sxs-lookup"><span data-stu-id="b91e3-119">![Rotate Colors](./media/colortrans5.png "colortrans5")</span></span>  
  
 <span data-ttu-id="b91e3-120">La siguiente ilustración muestra una visualización de la rotación de color realizada en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="b91e3-120">The following illustration shows a visualization of the color rotation performed in the following code.</span></span>  
  
 <span data-ttu-id="b91e3-121">![Cambiar el color de](./media/recoloring06.gif "recoloring06")</span><span class="sxs-lookup"><span data-stu-id="b91e3-121">![Recoloring](./media/recoloring06.gif "recoloring06")</span></span>  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b91e3-122">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b91e3-122">Compiling the Code</span></span>  
 <span data-ttu-id="b91e3-123">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="b91e3-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="b91e3-124">Reemplace `RotationInput.bmp` con un nombre de archivo de imagen y la ruta de acceso válida en su sistema.</span><span class="sxs-lookup"><span data-stu-id="b91e3-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b91e3-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b91e3-125">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="b91e3-126">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b91e3-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="b91e3-127">Cambiar el color de las imágenes</span><span class="sxs-lookup"><span data-stu-id="b91e3-127">Recoloring Images</span></span>](recoloring-images.md)
