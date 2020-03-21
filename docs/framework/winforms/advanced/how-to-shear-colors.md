---
title: 'Cómo: Recortar colores'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: 825e5a90ebb0d9df3b894ce7bd353e917b676939
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142399"
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="f8210-102">Cómo: Recortar colores</span><span class="sxs-lookup"><span data-stu-id="f8210-102">How to: Shear Colors</span></span>
<span data-ttu-id="f8210-103">El cizallamiento aumenta o disminuye un componente de color en una cantidad proporcional a otro componente de color.</span><span class="sxs-lookup"><span data-stu-id="f8210-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="f8210-104">Por ejemplo, considere la transformación en la que el componente rojo se incrementa en la mitad del valor del componente azul.</span><span class="sxs-lookup"><span data-stu-id="f8210-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="f8210-105">En tal transformación, el color (0,2, 0,5, 1) se convertiría en (0,7, 0,5, 1).</span><span class="sxs-lookup"><span data-stu-id="f8210-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="f8210-106">El nuevo componente rojo es 0,2 + (1/2)(1) a 0,7.</span><span class="sxs-lookup"><span data-stu-id="f8210-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8210-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8210-107">Example</span></span>  
 <span data-ttu-id="f8210-108">En el ejemplo <xref:System.Drawing.Image> siguiente se construye un objeto a partir del archivo ColorBars4.bmp.</span><span class="sxs-lookup"><span data-stu-id="f8210-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="f8210-109">A continuación, el código aplica la transformación de cizallamiento descrita en el párrafo anterior a cada píxel de la imagen.</span><span class="sxs-lookup"><span data-stu-id="f8210-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="f8210-110">La siguiente ilustración muestra la imagen original a la izquierda y la imagen cizallada a la derecha:</span><span class="sxs-lookup"><span data-stu-id="f8210-110">The following illustration shows the original image on the left and the sheared image on the right:</span></span>
  
 ![Dos cuadrados con rayas de colores lado a lado ilustrando la imagen original y la imagen cizallada.](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 <span data-ttu-id="f8210-112">En la tabla siguiente se enumeran los vectores de color de las cuatro barras antes y después de la transformación de cizallamiento.</span><span class="sxs-lookup"><span data-stu-id="f8210-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="f8210-113">Original</span><span class="sxs-lookup"><span data-stu-id="f8210-113">Original</span></span>|<span data-ttu-id="f8210-114">Esquilada</span><span class="sxs-lookup"><span data-stu-id="f8210-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="f8210-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="f8210-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="f8210-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="f8210-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="f8210-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="f8210-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="f8210-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="f8210-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="f8210-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="f8210-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="f8210-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="f8210-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="f8210-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="f8210-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="f8210-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="f8210-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f8210-123">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="f8210-123">Compiling the Code</span></span>  
 <span data-ttu-id="f8210-124">El ejemplo anterior está diseñado para su uso <xref:System.Windows.Forms.PaintEventArgs> `e`con formularios Windows Forms, y requiere , que es un parámetro del <xref:System.Windows.Forms.Control.Paint> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f8210-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="f8210-125">Reemplace `ColorBars.bmp` por un nombre de imagen y una ruta de acceso válidas en el sistema.</span><span class="sxs-lookup"><span data-stu-id="f8210-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8210-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f8210-126">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="f8210-127">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8210-127">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="f8210-128">Cambiar el color de las imágenes</span><span class="sxs-lookup"><span data-stu-id="f8210-128">Recoloring Images</span></span>](recoloring-images.md)
