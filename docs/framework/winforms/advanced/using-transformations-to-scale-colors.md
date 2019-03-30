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
ms.openlocfilehash: 9255dd4adba19bfef1332e5e3dfa463ee96f43f0
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "58653995"
---
# <a name="using-transformations-to-scale-colors"></a><span data-ttu-id="bd3f2-102">Utilizar transformaciones para ajustar la escala de los colores</span><span class="sxs-lookup"><span data-stu-id="bd3f2-102">Using Transformations to Scale Colors</span></span>
<span data-ttu-id="bd3f2-103">Una transformación de escala multiplica uno o varios de los cuatro componentes de color por un número.</span><span class="sxs-lookup"><span data-stu-id="bd3f2-103">A scaling transformation multiplies one or more of the four color components by a number.</span></span> <span data-ttu-id="bd3f2-104">En la siguiente tabla figuran las entradas de la matriz de color que representan el escalado.</span><span class="sxs-lookup"><span data-stu-id="bd3f2-104">The color matrix entries that represent scaling are given in the following table.</span></span>  
  
|<span data-ttu-id="bd3f2-105">Componente escalar</span><span class="sxs-lookup"><span data-stu-id="bd3f2-105">Component to be scaled</span></span>|<span data-ttu-id="bd3f2-106">Entrada de matriz</span><span class="sxs-lookup"><span data-stu-id="bd3f2-106">Matrix entry</span></span>|  
|----------------------------|------------------|  
|<span data-ttu-id="bd3f2-107">Rojo</span><span class="sxs-lookup"><span data-stu-id="bd3f2-107">Red</span></span>|<span data-ttu-id="bd3f2-108">[0][0]</span><span class="sxs-lookup"><span data-stu-id="bd3f2-108">[0][0]</span></span>|  
|<span data-ttu-id="bd3f2-109">Verde</span><span class="sxs-lookup"><span data-stu-id="bd3f2-109">Green</span></span>|<span data-ttu-id="bd3f2-110">[1][1]</span><span class="sxs-lookup"><span data-stu-id="bd3f2-110">[1][1]</span></span>|  
|<span data-ttu-id="bd3f2-111">Azul</span><span class="sxs-lookup"><span data-stu-id="bd3f2-111">Blue</span></span>|<span data-ttu-id="bd3f2-112">[2][2]</span><span class="sxs-lookup"><span data-stu-id="bd3f2-112">[2][2]</span></span>|  
|<span data-ttu-id="bd3f2-113">Alpha</span><span class="sxs-lookup"><span data-stu-id="bd3f2-113">Alpha</span></span>|<span data-ttu-id="bd3f2-114">[3][3]</span><span class="sxs-lookup"><span data-stu-id="bd3f2-114">[3][3]</span></span>|  
  
## <a name="scaling-one-color"></a><span data-ttu-id="bd3f2-115">Una escala de Color</span><span class="sxs-lookup"><span data-stu-id="bd3f2-115">Scaling One Color</span></span>  
 <span data-ttu-id="bd3f2-116">En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto a partir del archivo ColorBars2.bmp.</span><span class="sxs-lookup"><span data-stu-id="bd3f2-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="bd3f2-117">A continuación, el código ajusta el componente azul de cada píxel de la imagen en un factor de 2.</span><span class="sxs-lookup"><span data-stu-id="bd3f2-117">Then the code scales the blue component of each pixel in the image by a factor of 2.</span></span> <span data-ttu-id="bd3f2-118">Se dibuja la imagen original junto con la imagen transformada.</span><span class="sxs-lookup"><span data-stu-id="bd3f2-118">The original image is drawn alongside the transformed image.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 <span data-ttu-id="bd3f2-119">La siguiente ilustración muestra la imagen original a la izquierda y la imagen de la derecha:</span><span class="sxs-lookup"><span data-stu-id="bd3f2-119">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![Captura de pantalla que compara los colores originales y se escalan.](./media/using-transformations-to-scale-colors/four-bar-scale-one-color.png)  
  
 <span data-ttu-id="bd3f2-121">En la tabla siguiente se enumera los vectores de color de las cuatro barras antes y después de ajustar el azul.</span><span class="sxs-lookup"><span data-stu-id="bd3f2-121">The following table lists the color vectors for the four bars before and after the blue scaling.</span></span> <span data-ttu-id="bd3f2-122">Tenga en cuenta que el componente azul de la cuarta barra de color pasó de 0,8 a 0,6.</span><span class="sxs-lookup"><span data-stu-id="bd3f2-122">Note that the blue component in the fourth color bar went from 0.8 to 0.6.</span></span> <span data-ttu-id="bd3f2-123">Eso es porque [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] conserva sólo la parte fraccionaria del resultado.</span><span class="sxs-lookup"><span data-stu-id="bd3f2-123">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] retains only the fractional part of the result.</span></span> <span data-ttu-id="bd3f2-124">Por ejemplo, (2)(0.8) = 1.6, y la parte fraccionaria de 1,6 es 0,6.</span><span class="sxs-lookup"><span data-stu-id="bd3f2-124">For example, (2)(0.8) = 1.6, and the fractional part of 1.6 is 0.6.</span></span> <span data-ttu-id="bd3f2-125">Conservar solo la parte fraccionaria garantiza que el resultado es siempre en el intervalo [0, 1].</span><span class="sxs-lookup"><span data-stu-id="bd3f2-125">Retaining only the fractional part ensures that the result is always in the interval [0, 1].</span></span>  
  
|<span data-ttu-id="bd3f2-126">Original</span><span class="sxs-lookup"><span data-stu-id="bd3f2-126">Original</span></span>|<span data-ttu-id="bd3f2-127">Escalar</span><span class="sxs-lookup"><span data-stu-id="bd3f2-127">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="bd3f2-128">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="bd3f2-128">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="bd3f2-129">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="bd3f2-129">(0.4, 0.4, 0.8, 1)</span></span>|  
|<span data-ttu-id="bd3f2-130">(0.4, 0.2, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="bd3f2-130">(0.4, 0.2, 0.2, 1)</span></span>|<span data-ttu-id="bd3f2-131">(0.4, 0.2, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="bd3f2-131">(0.4, 0.2, 0.4, 1)</span></span>|  
|<span data-ttu-id="bd3f2-132">(0.2, 0.4, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="bd3f2-132">(0.2, 0.4, 0.2, 1)</span></span>|<span data-ttu-id="bd3f2-133">(0.2, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="bd3f2-133">(0.2, 0.4, 0.4, 1)</span></span>|  
|<span data-ttu-id="bd3f2-134">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="bd3f2-134">(0.4, 0.4, 0.8, 1)</span></span>|<span data-ttu-id="bd3f2-135">(0.4, 0.4, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="bd3f2-135">(0.4, 0.4, 0.6, 1)</span></span>|  
  
## <a name="scaling-multiple-colors"></a><span data-ttu-id="bd3f2-136">Escalado de varios colores</span><span class="sxs-lookup"><span data-stu-id="bd3f2-136">Scaling Multiple Colors</span></span>  
 <span data-ttu-id="bd3f2-137">En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto a partir del archivo ColorBars2.bmp.</span><span class="sxs-lookup"><span data-stu-id="bd3f2-137">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="bd3f2-138">A continuación, el código ajusta los componentes rojos, verde y azules de cada píxel de la imagen.</span><span class="sxs-lookup"><span data-stu-id="bd3f2-138">Then the code scales the red, green, and blue components of each pixel in the image.</span></span> <span data-ttu-id="bd3f2-139">Los componentes rojos se reducen a 25 por ciento, se escalan los componentes verde 35 por ciento y se escalan los componentes azules 50 por ciento.</span><span class="sxs-lookup"><span data-stu-id="bd3f2-139">The red components are scaled down 25 percent, the green components are scaled down 35 percent, and the blue components are scaled down 50 percent.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 <span data-ttu-id="bd3f2-140">La siguiente ilustración muestra la imagen original a la izquierda y la imagen de la derecha:</span><span class="sxs-lookup"><span data-stu-id="bd3f2-140">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![Captura de pantalla que compara los colores originales y se escalan.](./media/using-transformations-to-scale-colors/four-bar-scale-multiple-colors.png)  
  
 <span data-ttu-id="bd3f2-142">En la tabla siguiente se enumera los vectores de color de las cuatro barras antes y después de la escala de color rojo, verde y azul.</span><span class="sxs-lookup"><span data-stu-id="bd3f2-142">The following table lists the color vectors for the four bars before and after the red, green and blue scaling.</span></span>  
  
|<span data-ttu-id="bd3f2-143">Original</span><span class="sxs-lookup"><span data-stu-id="bd3f2-143">Original</span></span>|<span data-ttu-id="bd3f2-144">Escalar</span><span class="sxs-lookup"><span data-stu-id="bd3f2-144">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="bd3f2-145">(0.6, 0.6, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="bd3f2-145">(0.6, 0.6, 0.6, 1)</span></span>|<span data-ttu-id="bd3f2-146">(0.45, 0.39, 0.3, 1)</span><span class="sxs-lookup"><span data-stu-id="bd3f2-146">(0.45, 0.39, 0.3, 1)</span></span>|  
|<span data-ttu-id="bd3f2-147">(0, 1, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="bd3f2-147">(0, 1, 1, 1)</span></span>|<span data-ttu-id="bd3f2-148">(0, 0.65, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="bd3f2-148">(0, 0.65, 0.5, 1)</span></span>|  
|<span data-ttu-id="bd3f2-149">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="bd3f2-149">(1, 1, 0, 1)</span></span>|<span data-ttu-id="bd3f2-150">(0.75, 0.65, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="bd3f2-150">(0.75, 0.65, 0, 1)</span></span>|  
|<span data-ttu-id="bd3f2-151">(1, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="bd3f2-151">(1, 0, 1, 1)</span></span>|<span data-ttu-id="bd3f2-152">(0.75, 0, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="bd3f2-152">(0.75, 0, 0.5, 1)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd3f2-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd3f2-153">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="bd3f2-154">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bd3f2-154">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="bd3f2-155">Cambiar el color de las imágenes</span><span class="sxs-lookup"><span data-stu-id="bd3f2-155">Recoloring Images</span></span>](recoloring-images.md)
