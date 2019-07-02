---
title: Líneas y rellenos con mezcla alfa
ms.date: 03/30/2017
helpviewer_keywords:
- lines [Windows Forms], adding transparency
- examples [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with lines
- alpha blending
- lines [Windows Forms], alpha blending
- fills [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with fills
- shapes [Windows Forms], adding transparency
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
ms.openlocfilehash: 66061341ee6539e2172c537a0b2a6ec9ff87565c
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506111"
---
# <a name="alpha-blending-lines-and-fills"></a><span data-ttu-id="572ea-102">Líneas y rellenos con mezcla alfa</span><span class="sxs-lookup"><span data-stu-id="572ea-102">Alpha Blending Lines and Fills</span></span>
<span data-ttu-id="572ea-103">En GDI +, un color es un valor de 32 bits con 8 bits para alfa, rojo, verde y azul.</span><span class="sxs-lookup"><span data-stu-id="572ea-103">In GDI+, a color is a 32-bit value with 8 bits each for alpha, red, green, and blue.</span></span> <span data-ttu-id="572ea-104">El valor alfa indica la transparencia del color, la extensión a la que el color se mezcla con el color de fondo.</span><span class="sxs-lookup"><span data-stu-id="572ea-104">The alpha value indicates the transparency of the color — the extent to which the color is blended with the background color.</span></span> <span data-ttu-id="572ea-105">Intervalo de valores alfa de 0 a 255, donde 0 representa un color completamente transparente, y 255 representa un color completamente opaco.</span><span class="sxs-lookup"><span data-stu-id="572ea-105">Alpha values range from 0 through 255, where 0 represents a fully transparent color, and 255 represents a fully opaque color.</span></span>  
  
 <span data-ttu-id="572ea-106">Combinación alfa es una mezcla de píxel a píxel de datos de origen y de fondo de color.</span><span class="sxs-lookup"><span data-stu-id="572ea-106">Alpha blending is a pixel-by-pixel blending of source and background color data.</span></span> <span data-ttu-id="572ea-107">Cada uno de los tres componentes (rojo, verde, azul) de un color de origen dado se mezcla con el componente correspondiente del color de fondo según la siguiente fórmula:</span><span class="sxs-lookup"><span data-stu-id="572ea-107">Each of the three components (red, green, blue) of a given source color is blended with the corresponding component of the background color according to the following formula:</span></span>  
  
 <span data-ttu-id="572ea-108">displayColor = sourceColor × alfa / 255 + backgroundColor × (alfa de 255 –) / 255</span><span class="sxs-lookup"><span data-stu-id="572ea-108">displayColor = sourceColor × alpha / 255 + backgroundColor × (255 – alpha) / 255</span></span>  
  
 <span data-ttu-id="572ea-109">Por ejemplo, supongamos que el componente rojo del color de origen es 150 y el componente rojo del color de fondo es 100.</span><span class="sxs-lookup"><span data-stu-id="572ea-109">For example, suppose the red component of the source color is 150 and the red component of the background color is 100.</span></span> <span data-ttu-id="572ea-110">Si el valor alfa es 200, el componente rojo del color resultante se calcula como sigue:</span><span class="sxs-lookup"><span data-stu-id="572ea-110">If the alpha value is 200, the red component of the resultant color is calculated as follows:</span></span>  
  
 <span data-ttu-id="572ea-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span><span class="sxs-lookup"><span data-stu-id="572ea-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="572ea-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="572ea-112">In This Section</span></span>  
 [<span data-ttu-id="572ea-113">Cómo: Dibujar líneas opacas y semitransparentes</span><span class="sxs-lookup"><span data-stu-id="572ea-113">How to: Draw Opaque and Semitransparent Lines</span></span>](how-to-draw-opaque-and-semitransparent-lines.md)  
 <span data-ttu-id="572ea-114">Se muestra cómo dibujar líneas con mezcla alfa.</span><span class="sxs-lookup"><span data-stu-id="572ea-114">Shows how to draw alpha-blended lines.</span></span>  
  
 [<span data-ttu-id="572ea-115">Cómo: Dibujar con pinceles opacos y semitransparentes</span><span class="sxs-lookup"><span data-stu-id="572ea-115">How to: Draw with Opaque and Semitransparent Brushes</span></span>](how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 <span data-ttu-id="572ea-116">Explica cómo realizar la mezcla alfa con pinceles.</span><span class="sxs-lookup"><span data-stu-id="572ea-116">Explains how to alpha-blend with brushes.</span></span>  
  
 [<span data-ttu-id="572ea-117">Cómo: Usar el modo de composición para controlar la mezcla alfa</span><span class="sxs-lookup"><span data-stu-id="572ea-117">How to: Use Compositing Mode to Control Alpha Blending</span></span>](how-to-use-compositing-mode-to-control-alpha-blending.md)  
 <span data-ttu-id="572ea-118">Describe cómo controlar la combinación alfa usando <xref:System.Drawing.Drawing2D.CompositingMode>.</span><span class="sxs-lookup"><span data-stu-id="572ea-118">Describes how to control alpha blending using <xref:System.Drawing.Drawing2D.CompositingMode>.</span></span>  
  
 [<span data-ttu-id="572ea-119">Cómo: Use una matriz de colores para establecer valores alfabéticos en imágenes</span><span class="sxs-lookup"><span data-stu-id="572ea-119">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>](how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 <span data-ttu-id="572ea-120">Explica cómo utilizar un <xref:System.Drawing.Imaging.ColorMatrix> objeto para controlar la mezcla alfa.</span><span class="sxs-lookup"><span data-stu-id="572ea-120">Explains how to use a <xref:System.Drawing.Imaging.ColorMatrix> object to control alpha blending.</span></span>
