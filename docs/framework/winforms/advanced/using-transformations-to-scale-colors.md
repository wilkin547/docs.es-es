---
title: Utilizar transformaciones para ajustar la escala de los colores
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
ms.openlocfilehash: 6cfe90cef42086672990c45c99961db3d29c3ff3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525972"
---
# <a name="using-transformations-to-scale-colors"></a><span data-ttu-id="6dac4-102">Utilizar transformaciones para ajustar la escala de los colores</span><span class="sxs-lookup"><span data-stu-id="6dac4-102">Using Transformations to Scale Colors</span></span>
<span data-ttu-id="6dac4-103">Una transformación de escala multiplica uno o varios de los cuatro componentes de color por un número.</span><span class="sxs-lookup"><span data-stu-id="6dac4-103">A scaling transformation multiplies one or more of the four color components by a number.</span></span> <span data-ttu-id="6dac4-104">Las entradas de la matriz de color que representan el ajuste de escala se proporcionan en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6dac4-104">The color matrix entries that represent scaling are given in the following table.</span></span>  
  
|<span data-ttu-id="6dac4-105">Componente escalar</span><span class="sxs-lookup"><span data-stu-id="6dac4-105">Component to be scaled</span></span>|<span data-ttu-id="6dac4-106">Entrada de matriz</span><span class="sxs-lookup"><span data-stu-id="6dac4-106">Matrix entry</span></span>|  
|----------------------------|------------------|  
|<span data-ttu-id="6dac4-107">Rojo</span><span class="sxs-lookup"><span data-stu-id="6dac4-107">Red</span></span>|<span data-ttu-id="6dac4-108">[0][0]</span><span class="sxs-lookup"><span data-stu-id="6dac4-108">[0][0]</span></span>|  
|<span data-ttu-id="6dac4-109">Verde</span><span class="sxs-lookup"><span data-stu-id="6dac4-109">Green</span></span>|<span data-ttu-id="6dac4-110">[1][1]</span><span class="sxs-lookup"><span data-stu-id="6dac4-110">[1][1]</span></span>|  
|<span data-ttu-id="6dac4-111">Azul</span><span class="sxs-lookup"><span data-stu-id="6dac4-111">Blue</span></span>|<span data-ttu-id="6dac4-112">[2][2]</span><span class="sxs-lookup"><span data-stu-id="6dac4-112">[2][2]</span></span>|  
|<span data-ttu-id="6dac4-113">Alpha</span><span class="sxs-lookup"><span data-stu-id="6dac4-113">Alpha</span></span>|<span data-ttu-id="6dac4-114">[3][3]</span><span class="sxs-lookup"><span data-stu-id="6dac4-114">[3][3]</span></span>|  
  
## <a name="scaling-one-color"></a><span data-ttu-id="6dac4-115">Ajuste de escala en un Color</span><span class="sxs-lookup"><span data-stu-id="6dac4-115">Scaling One Color</span></span>  
 <span data-ttu-id="6dac4-116">En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto a partir del archivo ColorBars2.bmp.</span><span class="sxs-lookup"><span data-stu-id="6dac4-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="6dac4-117">A continuación, el código ajusta el componente azul de cada píxel de la imagen en un factor de 2.</span><span class="sxs-lookup"><span data-stu-id="6dac4-117">Then the code scales the blue component of each pixel in the image by a factor of 2.</span></span> <span data-ttu-id="6dac4-118">Se dibuja la imagen original junto con la imagen transformada.</span><span class="sxs-lookup"><span data-stu-id="6dac4-118">The original image is drawn alongside the transformed image.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 <span data-ttu-id="6dac4-119">En la siguiente ilustración se muestra la imagen original a la izquierda y la imagen escalada a la derecha.</span><span class="sxs-lookup"><span data-stu-id="6dac4-119">The following illustration shows the original image on the left and the scaled image on the right.</span></span>  
  
 <span data-ttu-id="6dac4-120">![Escala de colores](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")</span><span class="sxs-lookup"><span data-stu-id="6dac4-120">![Scale Colors](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")</span></span>  
  
 <span data-ttu-id="6dac4-121">En la tabla siguiente se recogen los vectores de color de las cuatro barras antes y después de ajustar el azul.</span><span class="sxs-lookup"><span data-stu-id="6dac4-121">The following table lists the color vectors for the four bars before and after the blue scaling.</span></span> <span data-ttu-id="6dac4-122">Tenga en cuenta que el componente azul de la cuarta barra de color pasó de 0,8 a 0,6.</span><span class="sxs-lookup"><span data-stu-id="6dac4-122">Note that the blue component in the fourth color bar went from 0.8 to 0.6.</span></span> <span data-ttu-id="6dac4-123">Esto es así porque [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] conserva solo la parte fraccionaria del resultado.</span><span class="sxs-lookup"><span data-stu-id="6dac4-123">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] retains only the fractional part of the result.</span></span> <span data-ttu-id="6dac4-124">Por ejemplo, (2)(0.8) = 1.6, y la parte fraccionaria de 1,6 es 0,6.</span><span class="sxs-lookup"><span data-stu-id="6dac4-124">For example, (2)(0.8) = 1.6, and the fractional part of 1.6 is 0.6.</span></span> <span data-ttu-id="6dac4-125">Conserva solo la parte fraccionaria, se garantiza que el resultado está siempre en el intervalo [0, 1].</span><span class="sxs-lookup"><span data-stu-id="6dac4-125">Retaining only the fractional part ensures that the result is always in the interval [0, 1].</span></span>  
  
|<span data-ttu-id="6dac4-126">Original</span><span class="sxs-lookup"><span data-stu-id="6dac4-126">Original</span></span>|<span data-ttu-id="6dac4-127">Escalar</span><span class="sxs-lookup"><span data-stu-id="6dac4-127">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="6dac4-128">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="6dac4-128">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="6dac4-129">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="6dac4-129">(0.4, 0.4, 0.8, 1)</span></span>|  
|<span data-ttu-id="6dac4-130">(0.4, 0.2, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="6dac4-130">(0.4, 0.2, 0.2, 1)</span></span>|<span data-ttu-id="6dac4-131">(0.4, 0.2, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="6dac4-131">(0.4, 0.2, 0.4, 1)</span></span>|  
|<span data-ttu-id="6dac4-132">(0.2, 0.4, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="6dac4-132">(0.2, 0.4, 0.2, 1)</span></span>|<span data-ttu-id="6dac4-133">(0.2, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="6dac4-133">(0.2, 0.4, 0.4, 1)</span></span>|  
|<span data-ttu-id="6dac4-134">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="6dac4-134">(0.4, 0.4, 0.8, 1)</span></span>|<span data-ttu-id="6dac4-135">(0.4, 0.4, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="6dac4-135">(0.4, 0.4, 0.6, 1)</span></span>|  
  
## <a name="scaling-multiple-colors"></a><span data-ttu-id="6dac4-136">Ajuste de escala en varios colores</span><span class="sxs-lookup"><span data-stu-id="6dac4-136">Scaling Multiple Colors</span></span>  
 <span data-ttu-id="6dac4-137">En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto a partir del archivo ColorBars2.bmp.</span><span class="sxs-lookup"><span data-stu-id="6dac4-137">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="6dac4-138">A continuación, el código ajusta los componentes rojos, verde y azules de cada píxel de la imagen.</span><span class="sxs-lookup"><span data-stu-id="6dac4-138">Then the code scales the red, green, and blue components of each pixel in the image.</span></span> <span data-ttu-id="6dac4-139">Los componentes rojos son reducidos de 25 por ciento, se escalan los componentes verde hacia abajo un 35% y los componentes de color azules son reducidos 50 por ciento.</span><span class="sxs-lookup"><span data-stu-id="6dac4-139">The red components are scaled down 25 percent, the green components are scaled down 35 percent, and the blue components are scaled down 50 percent.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 <span data-ttu-id="6dac4-140">En la siguiente ilustración se muestra la imagen original a la izquierda y la imagen escalada a la derecha.</span><span class="sxs-lookup"><span data-stu-id="6dac4-140">The following illustration shows the original image on the left and the scaled image on the right.</span></span>  
  
 <span data-ttu-id="6dac4-141">![Escala de colores](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")</span><span class="sxs-lookup"><span data-stu-id="6dac4-141">![Scale Colors](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")</span></span>  
  
 <span data-ttu-id="6dac4-142">En la tabla siguiente se enumera los vectores de color de las cuatro barras antes y después de la escala de color rojo, verde y azul.</span><span class="sxs-lookup"><span data-stu-id="6dac4-142">The following table lists the color vectors for the four bars before and after the red, green and blue scaling.</span></span>  
  
|<span data-ttu-id="6dac4-143">Original</span><span class="sxs-lookup"><span data-stu-id="6dac4-143">Original</span></span>|<span data-ttu-id="6dac4-144">Escalar</span><span class="sxs-lookup"><span data-stu-id="6dac4-144">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="6dac4-145">(0.6, 0.6, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="6dac4-145">(0.6, 0.6, 0.6, 1)</span></span>|<span data-ttu-id="6dac4-146">(0.45, 0.39, 0.3, 1)</span><span class="sxs-lookup"><span data-stu-id="6dac4-146">(0.45, 0.39, 0.3, 1)</span></span>|  
|<span data-ttu-id="6dac4-147">(0, 1, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="6dac4-147">(0, 1, 1, 1)</span></span>|<span data-ttu-id="6dac4-148">(0, 0.65, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="6dac4-148">(0, 0.65, 0.5, 1)</span></span>|  
|<span data-ttu-id="6dac4-149">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="6dac4-149">(1, 1, 0, 1)</span></span>|<span data-ttu-id="6dac4-150">(0.75, 0.65, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="6dac4-150">(0.75, 0.65, 0, 1)</span></span>|  
|<span data-ttu-id="6dac4-151">(1, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="6dac4-151">(1, 0, 1, 1)</span></span>|<span data-ttu-id="6dac4-152">(0.75, 0, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="6dac4-152">(0.75, 0, 0.5, 1)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6dac4-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="6dac4-153">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="6dac4-154">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6dac4-154">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="6dac4-155">Cambiar el color de las imágenes</span><span class="sxs-lookup"><span data-stu-id="6dac4-155">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
