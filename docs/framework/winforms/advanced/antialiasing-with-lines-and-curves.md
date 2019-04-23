---
title: Suavizado de contorno con líneas y curvas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
ms.openlocfilehash: cbc9033f18f1ab255862c8f8e2891aa9b68cf8d6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078503"
---
# <a name="antialiasing-with-lines-and-curves"></a><span data-ttu-id="d1c76-102">Suavizado de contorno con líneas y curvas</span><span class="sxs-lookup"><span data-stu-id="d1c76-102">Antialiasing with Lines and Curves</span></span>
<span data-ttu-id="d1c76-103">Cuando usas [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] para dibujar una línea, se proporcionan el punto de partida y el punto final de la línea, pero no tendrá que proporcionar toda la información sobre los píxeles individuales en la línea.</span><span class="sxs-lookup"><span data-stu-id="d1c76-103">When you use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to draw a line, you provide the starting point and ending point of the line, but you do not have to provide any information about the individual pixels on the line.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="d1c76-104">funciona junto con el software de controlador de vídeo para determinar qué píxeles se activará para mostrar la línea en un dispositivo de presentación determinado.</span><span class="sxs-lookup"><span data-stu-id="d1c76-104">works in conjunction with the display driver software to determine which pixels will be turned on to show the line on a particular display device.</span></span>  
  
## <a name="aliasing"></a><span data-ttu-id="d1c76-105">Creación de alias</span><span class="sxs-lookup"><span data-stu-id="d1c76-105">Aliasing</span></span>  
 <span data-ttu-id="d1c76-106">Considere la posibilidad de la línea recta de color rojo que va desde el punto (4, 2) al punto (16, 10).</span><span class="sxs-lookup"><span data-stu-id="d1c76-106">Consider the straight red line that goes from the point (4, 2) to the point (16, 10).</span></span> <span data-ttu-id="d1c76-107">Suponga que el sistema de coordenadas tiene su origen en la esquina superior izquierda y que la unidad de medida es el píxel.</span><span class="sxs-lookup"><span data-stu-id="d1c76-107">Assume the coordinate system has its origin in the upper-left corner and that the unit of measure is the pixel.</span></span> <span data-ttu-id="d1c76-108">También se supone que el eje x apunta hacia la derecha y el eje y apunta hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="d1c76-108">Also assume that the x-axis points to the right and the y-axis points down.</span></span> <span data-ttu-id="d1c76-109">La siguiente ilustración muestra una vista ampliada de la línea roja dibujada en un fondo de varios colores.</span><span class="sxs-lookup"><span data-stu-id="d1c76-109">The following illustration shows an enlarged view of the red line drawn on a multicolored background.</span></span>  
  
 <span data-ttu-id="d1c76-110">![Línea, sin suavizado de contorno](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span><span class="sxs-lookup"><span data-stu-id="d1c76-110">![Line, no antialiasing](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span></span>  
  
 <span data-ttu-id="d1c76-111">Los píxeles rojos utilizados para representar la línea son opacos.</span><span class="sxs-lookup"><span data-stu-id="d1c76-111">The red pixels used to render the line are opaque.</span></span> <span data-ttu-id="d1c76-112">No hay ningún píxel parcialmente transparente en la línea.</span><span class="sxs-lookup"><span data-stu-id="d1c76-112">There are no partially transparent pixels in the line.</span></span> <span data-ttu-id="d1c76-113">Este tipo de representación de línea le da la línea de una apariencia escalonada y la línea es bastante similar a una escalera.</span><span class="sxs-lookup"><span data-stu-id="d1c76-113">This type of line rendering gives the line a jagged appearance, and the line looks somewhat like a staircase.</span></span> <span data-ttu-id="d1c76-114">Esta técnica de representar una línea con una escalera se denomina "aliasing"; la escalera es un alias de la línea teórica.</span><span class="sxs-lookup"><span data-stu-id="d1c76-114">This technique of representing a line with a staircase is called aliasing; the staircase is an alias for the theoretical line.</span></span>  
  
## <a name="antialiasing"></a><span data-ttu-id="d1c76-115">suavizado de contorno</span><span class="sxs-lookup"><span data-stu-id="d1c76-115">Antialiasing</span></span>  
 <span data-ttu-id="d1c76-116">Una técnica más sofisticada para representar una línea implica el uso de píxeles parcialmente transparentes junto con píxeles opacos.</span><span class="sxs-lookup"><span data-stu-id="d1c76-116">A more sophisticated technique for rendering a line involves using partially transparent pixels along with opaque pixels.</span></span> <span data-ttu-id="d1c76-117">Los píxeles se establecen en rojo puro o en cierta mezcla de rojo y el color de fondo, dependiendo de cómo cerrar son a la línea.</span><span class="sxs-lookup"><span data-stu-id="d1c76-117">Pixels are set to pure red, or to some blend of red and the background color, depending on how close they are to the line.</span></span> <span data-ttu-id="d1c76-118">Este tipo de representación se denomina suavizado de contorno y da como resultado una línea que el ojo humano percibe como más suave.</span><span class="sxs-lookup"><span data-stu-id="d1c76-118">This type of rendering is called antialiasing and results in a line that the human eye perceives as more smooth.</span></span> <span data-ttu-id="d1c76-119">La siguiente ilustración muestra cómo ciertos píxeles se mezclan con el fondo para generar una línea con suavizado de contorno.</span><span class="sxs-lookup"><span data-stu-id="d1c76-119">The following illustration shows how certain pixels are blended with the background to produce an antialiased line.</span></span>  
  
 <span data-ttu-id="d1c76-120">![Suavizado de contorno de una línea](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span><span class="sxs-lookup"><span data-stu-id="d1c76-120">![Antialiasing a Line](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span></span>  
  
 <span data-ttu-id="d1c76-121">Suavizado de contorno, también llamado suavizado, también puede aplicarse a las curvas.</span><span class="sxs-lookup"><span data-stu-id="d1c76-121">Antialiasing, also called smoothing, can also be applied to curves.</span></span> <span data-ttu-id="d1c76-122">La siguiente ilustración muestra una vista ampliada de una elipse suavizada.</span><span class="sxs-lookup"><span data-stu-id="d1c76-122">The following illustration shows an enlarged view of a smoothed ellipse.</span></span>  
  
 <span data-ttu-id="d1c76-123">![Suavizado de contorno curvas](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span><span class="sxs-lookup"><span data-stu-id="d1c76-123">![Antialiasing Curves](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span></span>  
  
 <span data-ttu-id="d1c76-124">La siguiente ilustración muestra la misma elipse en su tamaño real, una vez sin suavizado de contorno y otra vez con suavizado de contorno.</span><span class="sxs-lookup"><span data-stu-id="d1c76-124">The following illustration shows the same ellipse in its actual size, once without antialiasing and once with antialiasing.</span></span>  
  
 <span data-ttu-id="d1c76-125">![Ejemplo de suavizado de contorno](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span><span class="sxs-lookup"><span data-stu-id="d1c76-125">![Antialiasing example](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span></span>  
  
 <span data-ttu-id="d1c76-126">Para dibujar líneas y curvas que utilizan el suavizado de contorno, cree una instancia de la <xref:System.Drawing.Graphics> clase y establezca su <xref:System.Drawing.Graphics.SmoothingMode%2A> propiedad <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> o <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span><span class="sxs-lookup"><span data-stu-id="d1c76-126">To draw lines and curves that use antialiasing, create an instance of the <xref:System.Drawing.Graphics> class and set its <xref:System.Drawing.Graphics.SmoothingMode%2A> property to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> or <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span></span> <span data-ttu-id="d1c76-127">A continuación, llame a uno de los métodos de dibujo de ese mismo <xref:System.Drawing.Graphics> clase.</span><span class="sxs-lookup"><span data-stu-id="d1c76-127">Then call one of the drawing methods of that same <xref:System.Drawing.Graphics> class.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#81](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a><span data-ttu-id="d1c76-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1c76-128">See also</span></span>

- <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>
- [<span data-ttu-id="d1c76-129">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="d1c76-129">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="d1c76-130">Cómo: Usa suavizado de contorno con texto</span><span class="sxs-lookup"><span data-stu-id="d1c76-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)
