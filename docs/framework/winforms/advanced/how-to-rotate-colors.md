---
title: 'Cómo: Rotar colores'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 8d2717dd7b819e963126072279b361fda02188bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111340"
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="ca9b0-102">Cómo: Rotar colores</span><span class="sxs-lookup"><span data-stu-id="ca9b0-102">How to: Rotate Colors</span></span>
<span data-ttu-id="ca9b0-103">La rotación en un espacio de color de cuatro dimensiones es difícil de visualizar.</span><span class="sxs-lookup"><span data-stu-id="ca9b0-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="ca9b0-104">Podemos facilitar la visualización de la rotación aceptando mantener uno de los componentes de color fijos.</span><span class="sxs-lookup"><span data-stu-id="ca9b0-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="ca9b0-105">Supongamos que estamos de acuerdo en mantener el componente alfa fijo en 1 (totalmente opaco).</span><span class="sxs-lookup"><span data-stu-id="ca9b0-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="ca9b0-106">A continuación, podemos visualizar un espacio de color tridimensional con ejes rojos, verdes y azules, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="ca9b0-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 ![Ilustración que muestra la rotación con ejes rojos, verdes y azules.](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 <span data-ttu-id="ca9b0-108">Un color se puede considerar como un punto en el espacio 3D.</span><span class="sxs-lookup"><span data-stu-id="ca9b0-108">A color can be thought of as a point in 3D space.</span></span> <span data-ttu-id="ca9b0-109">Por ejemplo, el punto (1, 0, 0) en el espacio representa el color rojo y el punto (0, 1, 0) en el espacio representa el color verde.</span><span class="sxs-lookup"><span data-stu-id="ca9b0-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="ca9b0-110">La siguiente ilustración muestra lo que significa girar el color (1, 0, 0) a través de un ángulo de 60 grados en el plano rojo-verde.</span><span class="sxs-lookup"><span data-stu-id="ca9b0-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="ca9b0-111">La rotación en un plano paralelo al plano rojo-verde se puede considerar como rotación sobre el eje azul.</span><span class="sxs-lookup"><span data-stu-id="ca9b0-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 ![Ilustración que muestra la rotación sobre el eje azul.](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 <span data-ttu-id="ca9b0-113">En la ilustración siguiente se muestra cómo inicializar una matriz de colorpara realizar rotaciones sobre cada uno de los tres ejes de coordenadas (rojo, verde, azul):</span><span class="sxs-lookup"><span data-stu-id="ca9b0-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue):</span></span>  
  
 ![Inicializar una matriz de color para realizar rotaciones de unos tres ejes.](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a><span data-ttu-id="ca9b0-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca9b0-115">Example</span></span>  
 <span data-ttu-id="ca9b0-116">En el ejemplo siguiente se toma una imagen de un color (1, 0, 0,6) y se aplica una rotación de 60 grados sobre el eje azul.</span><span class="sxs-lookup"><span data-stu-id="ca9b0-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="ca9b0-117">El ángulo de rotación se barre en un plano paralelo al plano rojo-verde.</span><span class="sxs-lookup"><span data-stu-id="ca9b0-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="ca9b0-118">La siguiente ilustración muestra la imagen original a la izquierda y la imagen girada en color a la derecha:</span><span class="sxs-lookup"><span data-stu-id="ca9b0-118">The following illustration shows the original image on the left and the color-rotated image on the right:</span></span>  
  
 ![Ilustración que muestra la imagen original y la imagen rotada en color.](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 <span data-ttu-id="ca9b0-120">En la ilustración siguiente se muestra una visualización de la rotación de color realizada en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ca9b0-120">The following illustration shows a visualization of the color rotation performed in the following code:</span></span>
  
 ![Ilustración que muestra la visualización de la rotación de color.](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ca9b0-122">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="ca9b0-122">Compiling the Code</span></span>  
 <span data-ttu-id="ca9b0-123">El ejemplo anterior está diseñado para su uso <xref:System.Windows.Forms.PaintEventArgs> `e`con formularios Windows Forms, y requiere , que es un parámetro del <xref:System.Windows.Forms.Control.Paint> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="ca9b0-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="ca9b0-124">Reemplace `RotationInput.bmp` por un nombre de archivo de imagen y una ruta válida en el sistema.</span><span class="sxs-lookup"><span data-stu-id="ca9b0-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca9b0-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca9b0-125">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="ca9b0-126">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ca9b0-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="ca9b0-127">Cambiar el color de las imágenes</span><span class="sxs-lookup"><span data-stu-id="ca9b0-127">Recoloring Images</span></span>](recoloring-images.md)
