---
title: "Cómo: Rotar colores"
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
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81b022011bd5613b8e956aa83482d2836508a4f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="1c178-102">Cómo: Rotar colores</span><span class="sxs-lookup"><span data-stu-id="1c178-102">How to: Rotate Colors</span></span>
<span data-ttu-id="1c178-103">Rotación en un espacio de colores de cuatro dimensiones es difícil de visualizar.</span><span class="sxs-lookup"><span data-stu-id="1c178-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="1c178-104">Podemos facilitar la visualizar rotación decidido mantener uno de los componentes de color fijo.</span><span class="sxs-lookup"><span data-stu-id="1c178-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="1c178-105">Supongamos que se decide mantener el componente alfa fijado en 1 (completamente opaco).</span><span class="sxs-lookup"><span data-stu-id="1c178-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="1c178-106">A continuación, podemos visualizar un espacio de color tridimensional con ejes de rojos, verde y azules como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="1c178-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="1c178-107">![Cambio de color](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")</span><span class="sxs-lookup"><span data-stu-id="1c178-107">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")</span></span>  
  
 <span data-ttu-id="1c178-108">Un color puede considerarse como un punto en un espacio 3D.</span><span class="sxs-lookup"><span data-stu-id="1c178-108">A color can be thought of as a point in 3-D space.</span></span> <span data-ttu-id="1c178-109">Por ejemplo, el punto (1, 0, 0) en un espacio representa el color rojo y el punto (0, 1, 0) en un espacio representa el color verde.</span><span class="sxs-lookup"><span data-stu-id="1c178-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="1c178-110">En la siguiente ilustración se muestra lo que significa para rotar el color (1, 0, 0) a través de un ángulo de 60 grados en el plano rojo y verde.</span><span class="sxs-lookup"><span data-stu-id="1c178-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="1c178-111">Rotación en un plano paralelo al plano rojo-verde puede considerarse como una rotación sobre el eje azul.</span><span class="sxs-lookup"><span data-stu-id="1c178-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 <span data-ttu-id="1c178-112">![Cambio de color](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")</span><span class="sxs-lookup"><span data-stu-id="1c178-112">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")</span></span>  
  
 <span data-ttu-id="1c178-113">La ilustración siguiente muestra cómo inicializar una matriz de color para realizar rotaciones sobre cada uno de los tres ejes de coordenadas (rojo, verde, azul).</span><span class="sxs-lookup"><span data-stu-id="1c178-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue).</span></span>  
  
 <span data-ttu-id="1c178-114">![Cambio de color](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")</span><span class="sxs-lookup"><span data-stu-id="1c178-114">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c178-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c178-115">Example</span></span>  
 <span data-ttu-id="1c178-116">En el ejemplo siguiente se toma una imagen que es un color (1, 0, 0,6) y se aplica una rotación de 60 grados sobre el eje azul.</span><span class="sxs-lookup"><span data-stu-id="1c178-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="1c178-117">El ángulo de rotación se trazará en un plano paralelo al plano rojo y verde.</span><span class="sxs-lookup"><span data-stu-id="1c178-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="1c178-118">En la siguiente ilustración se muestra la imagen original a la izquierda y la imagen gira de color de la derecha.</span><span class="sxs-lookup"><span data-stu-id="1c178-118">The following illustration shows the original image on the left and the color-rotated image on the right.</span></span>  
  
 <span data-ttu-id="1c178-119">![Rotar colores](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")</span><span class="sxs-lookup"><span data-stu-id="1c178-119">![Rotate Colors](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")</span></span>  
  
 <span data-ttu-id="1c178-120">En la siguiente ilustración muestra una visualización de la rotación de color realizada en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="1c178-120">The following illustration shows a visualization of the color rotation performed in the following code.</span></span>  
  
 <span data-ttu-id="1c178-121">![Cambio de color](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")</span><span class="sxs-lookup"><span data-stu-id="1c178-121">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")</span></span>  
  
 [!code-csharp[System.Drawing.RotateColors#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1c178-122">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="1c178-122">Compiling the Code</span></span>  
 <span data-ttu-id="1c178-123">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="1c178-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="1c178-124">Reemplace `RotationInput.bmp` con un nombre de archivo de imagen y la ruta de acceso válida en su sistema.</span><span class="sxs-lookup"><span data-stu-id="1c178-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c178-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c178-125">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="1c178-126">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1c178-126">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="1c178-127">Cambiar el color de las imágenes</span><span class="sxs-lookup"><span data-stu-id="1c178-127">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
