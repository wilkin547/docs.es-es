---
title: Filtrar para sesgar colores
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: bb5f9043ea5bdd25e984d73d3640c80f599714e6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826397"
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="0546d-102">Filtrar para sesgar colores</span><span class="sxs-lookup"><span data-stu-id="0546d-102">How to: Shear Colors</span></span>
<span data-ttu-id="0546d-103">Distorsión aumenta o disminuye un componente de color en una cantidad proporcional a otro componente de color.</span><span class="sxs-lookup"><span data-stu-id="0546d-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="0546d-104">Por ejemplo, considere la posibilidad de la transformación donde el componente rojo se incrementa por la mitad del valor del componente azul.</span><span class="sxs-lookup"><span data-stu-id="0546d-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="0546d-105">En este tipo de transformación, el color (0.2, 0.5, 1) se convertiría en (0,7, 0,5, 1).</span><span class="sxs-lookup"><span data-stu-id="0546d-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="0546d-106">El nuevo componente rojo es 0,2 + (1/2)(1) = 0,7.</span><span class="sxs-lookup"><span data-stu-id="0546d-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0546d-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0546d-107">Example</span></span>  
 <span data-ttu-id="0546d-108">En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto desde el archivo ColorBars4.bmp.</span><span class="sxs-lookup"><span data-stu-id="0546d-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="0546d-109">A continuación, el código aplica la transformación de recorte que se describe en el párrafo anterior a cada píxel de la imagen.</span><span class="sxs-lookup"><span data-stu-id="0546d-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="0546d-110">La siguiente ilustración muestra la imagen original a la izquierda y la imagen recortada de la derecha:</span><span class="sxs-lookup"><span data-stu-id="0546d-110">The following illustration shows the original image on the left and the sheared image on the right:</span></span> 
  
 ![Dos cuadrados con barras de colores por en paralelo que ilustra la imagen original y la imagen recortada.](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 <span data-ttu-id="0546d-112">En la tabla siguiente se enumera los vectores de color de las cuatro barras antes y después de la transformación de recorte.</span><span class="sxs-lookup"><span data-stu-id="0546d-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="0546d-113">Original</span><span class="sxs-lookup"><span data-stu-id="0546d-113">Original</span></span>|<span data-ttu-id="0546d-114">Recorta</span><span class="sxs-lookup"><span data-stu-id="0546d-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="0546d-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="0546d-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="0546d-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="0546d-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="0546d-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="0546d-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="0546d-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="0546d-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="0546d-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="0546d-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="0546d-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="0546d-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="0546d-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="0546d-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="0546d-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="0546d-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0546d-123">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="0546d-123">Compiling the Code</span></span>  
 <span data-ttu-id="0546d-124">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="0546d-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="0546d-125">Reemplace `ColorBars.bmp` con un nombre de la imagen y la ruta de acceso válida en su sistema.</span><span class="sxs-lookup"><span data-stu-id="0546d-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0546d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="0546d-126">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="0546d-127">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0546d-127">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="0546d-128">Cambiar el color de las imágenes</span><span class="sxs-lookup"><span data-stu-id="0546d-128">Recoloring Images</span></span>](recoloring-images.md)
