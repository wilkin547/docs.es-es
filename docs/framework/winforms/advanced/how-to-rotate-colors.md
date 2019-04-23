---
title: Procedimiento para rotar colores
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 241d2824fc2d87a0505eb6e790c865bfa7d8ef90
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175544"
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="f2fb4-102">Procedimiento para rotar colores</span><span class="sxs-lookup"><span data-stu-id="f2fb4-102">How to: Rotate Colors</span></span>
<span data-ttu-id="f2fb4-103">Es difícil visualizar la rotación en un espacio de colores de cuatro dimensiones.</span><span class="sxs-lookup"><span data-stu-id="f2fb4-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="f2fb4-104">Podemos lo hacemos más fácil visualizar la rotación mediante decidido mantener uno de los componentes de color fijo.</span><span class="sxs-lookup"><span data-stu-id="f2fb4-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="f2fb4-105">Supongamos que estamos de acuerdo mantener el componente alfa en 1 (completamente opaco).</span><span class="sxs-lookup"><span data-stu-id="f2fb4-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="f2fb4-106">A continuación, podemos visualizar un espacio tridimensional de color con ejes de rojos, verde y azules como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="f2fb4-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 ![Ilustración que muestra la rotación con ejes de rojos, verde y azules.](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 <span data-ttu-id="f2fb4-108">Un color puede considerarse como un punto en el espacio 3D.</span><span class="sxs-lookup"><span data-stu-id="f2fb4-108">A color can be thought of as a point in 3-D space.</span></span> <span data-ttu-id="f2fb4-109">Por ejemplo, el punto (1, 0, 0) en el espacio representa el color rojo y el punto (0, 1, 0) en el espacio representa el color verde.</span><span class="sxs-lookup"><span data-stu-id="f2fb4-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="f2fb4-110">En la siguiente ilustración se muestra lo que significa girar el color (1, 0, 0) a través de un ángulo de 60 grados en el plano de color rojo verde.</span><span class="sxs-lookup"><span data-stu-id="f2fb4-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="f2fb4-111">Rotación en un plano paralelo al plano de color rojo verde puede considerarse como la rotación sobre el eje azul.</span><span class="sxs-lookup"><span data-stu-id="f2fb4-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 ![Ilustración que muestra la rotación sobre el eje azul.](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 <span data-ttu-id="f2fb4-113">La siguiente ilustración muestra cómo inicializar una matriz de colores para llevar a cabo las rotaciones sobre cada uno de los tres ejes de coordenadas (rojo, verde, azul):</span><span class="sxs-lookup"><span data-stu-id="f2fb4-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue):</span></span>  
  
 ![Inicializar una matriz de colores para llevar a cabo las rotaciones de los tres ejes.](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a><span data-ttu-id="f2fb4-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2fb4-115">Example</span></span>  
 <span data-ttu-id="f2fb4-116">El ejemplo siguiente toma una imagen que es un color (1, 0, 0,6) y se aplica un giro de 60 grados sobre el eje azul.</span><span class="sxs-lookup"><span data-stu-id="f2fb4-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="f2fb4-117">El ángulo de rotación se trazará en un plano paralelo al plano de color rojo verde.</span><span class="sxs-lookup"><span data-stu-id="f2fb4-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="f2fb4-118">La siguiente ilustración muestra la imagen original a la izquierda y la imagen gira de color de la derecha:</span><span class="sxs-lookup"><span data-stu-id="f2fb4-118">The following illustration shows the original image on the left and the color-rotated image on the right:</span></span>  
  
 ![Ilustración que muestra la imagen original y la imagen de rotación de colores.](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 <span data-ttu-id="f2fb4-120">La siguiente ilustración muestra una visualización de la rotación de color realizada en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2fb4-120">The following illustration shows a visualization of the color rotation performed in the following code:</span></span>
  
 ![Ilustración que muestra la visualización de la rotación de color.](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f2fb4-122">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="f2fb4-122">Compiling the Code</span></span>  
 <span data-ttu-id="f2fb4-123">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="f2fb4-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="f2fb4-124">Reemplace `RotationInput.bmp` con un nombre de archivo de imagen y la ruta de acceso válida en su sistema.</span><span class="sxs-lookup"><span data-stu-id="f2fb4-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2fb4-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2fb4-125">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="f2fb4-126">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f2fb4-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="f2fb4-127">Cambiar el color de las imágenes</span><span class="sxs-lookup"><span data-stu-id="f2fb4-127">Recoloring Images</span></span>](recoloring-images.md)
