---
title: Pinceles y formas rellenas en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [Windows Forms], GDI+
- filled shapes [Windows Forms], GDI+
- shapes [Windows Forms], GDI+
- GDI+, brushes
- GDI+, filled shapes
- gradient brushes
- brushes [Windows Forms], gradient
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
ms.openlocfilehash: 45ef0b5920e43300e047d363149ea10a7833477b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912232"
---
# <a name="brushes-and-filled-shapes-in-gdi"></a><span data-ttu-id="032a2-102">Pinceles y formas rellenas en GDI+</span><span class="sxs-lookup"><span data-stu-id="032a2-102">Brushes and Filled Shapes in GDI+</span></span>
<span data-ttu-id="032a2-103">Una forma cerrada, como un rectángulo o una elipse, consta de un contorno y un interior.</span><span class="sxs-lookup"><span data-stu-id="032a2-103">A closed shape, such as a rectangle or an ellipse, consists of an outline and an interior.</span></span> <span data-ttu-id="032a2-104">El contorno se dibuja con un lápiz y el interior se rellena con un pincel.</span><span class="sxs-lookup"><span data-stu-id="032a2-104">The outline is drawn with a pen and the interior is filled with a brush.</span></span> <span data-ttu-id="032a2-105">GDI+ proporciona varias clases de pincel para rellenar el interior de las <xref:System.Drawing.SolidBrush>formas <xref:System.Drawing.Drawing2D.HatchBrush>cerradas <xref:System.Drawing.TextureBrush>: <xref:System.Drawing.Drawing2D.LinearGradientBrush>,, <xref:System.Drawing.Drawing2D.PathGradientBrush>, y.</span><span class="sxs-lookup"><span data-stu-id="032a2-105">GDI+ provides several brush classes for filling the interiors of closed shapes: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, and <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span></span> <span data-ttu-id="032a2-106">Todas estas clases heredan de la <xref:System.Drawing.Brush> clase.</span><span class="sxs-lookup"><span data-stu-id="032a2-106">All of these classes inherit from the <xref:System.Drawing.Brush> class.</span></span> <span data-ttu-id="032a2-107">En la ilustración siguiente se muestra un rectángulo relleno con un pincel sólido y una elipse rellena con un pincel de trama.</span><span class="sxs-lookup"><span data-stu-id="032a2-107">The following illustration shows a rectangle filled with a solid brush and an ellipse filled with a hatch brush.</span></span>  
  
 <span data-ttu-id="032a2-108">![Formas] rellenas (./media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span><span class="sxs-lookup"><span data-stu-id="032a2-108">![Filled Shapes](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span></span>  
  
## <a name="solid-brushes"></a><span data-ttu-id="032a2-109">Pinceles sólidos</span><span class="sxs-lookup"><span data-stu-id="032a2-109">Solid Brushes</span></span>  
 <span data-ttu-id="032a2-110">Para rellenar una forma cerrada, se necesita una instancia <xref:System.Drawing.Graphics> de la clase <xref:System.Drawing.Brush>y un.</span><span class="sxs-lookup"><span data-stu-id="032a2-110">To fill a closed shape, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Brush>.</span></span> <span data-ttu-id="032a2-111">La instancia de la <xref:System.Drawing.Graphics> clase proporciona métodos, <xref:System.Drawing.Graphics.FillRectangle%2A> como y <xref:System.Drawing.Graphics.FillEllipse%2A>, y almacena los <xref:System.Drawing.Brush> atributos del relleno, como el color y el patrón.</span><span class="sxs-lookup"><span data-stu-id="032a2-111">The instance of the <xref:System.Drawing.Graphics> class provides methods, such as <xref:System.Drawing.Graphics.FillRectangle%2A> and <xref:System.Drawing.Graphics.FillEllipse%2A>, and the <xref:System.Drawing.Brush> stores attributes of the fill, such as color and pattern.</span></span> <span data-ttu-id="032a2-112"><xref:System.Drawing.Brush> Se pasa como uno de los argumentos al método Fill.</span><span class="sxs-lookup"><span data-stu-id="032a2-112">The <xref:System.Drawing.Brush> is passed as one of the arguments to the fill method.</span></span> <span data-ttu-id="032a2-113">En el ejemplo de código siguiente se muestra cómo rellenar una elipse con un color rojo sólido.</span><span class="sxs-lookup"><span data-stu-id="032a2-113">The following code example shows how to fill an ellipse with a solid red color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#121](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
> <span data-ttu-id="032a2-114">En el ejemplo anterior, el pincel es de tipo <xref:System.Drawing.SolidBrush>, que hereda de. <xref:System.Drawing.Brush></span><span class="sxs-lookup"><span data-stu-id="032a2-114">In the preceding example, the brush is of type <xref:System.Drawing.SolidBrush>, which inherits from <xref:System.Drawing.Brush>.</span></span>  
  
## <a name="hatch-brushes"></a><span data-ttu-id="032a2-115">Pinceles de trama</span><span class="sxs-lookup"><span data-stu-id="032a2-115">Hatch Brushes</span></span>  
 <span data-ttu-id="032a2-116">Al rellenar una forma con un pincel de trama, se especifica un color de primer plano, un color de fondo y un estilo de trama.</span><span class="sxs-lookup"><span data-stu-id="032a2-116">When you fill a shape with a hatch brush, you specify a foreground color, a background color, and a hatch style.</span></span> <span data-ttu-id="032a2-117">El color de primer plano es el color del sombreado.</span><span class="sxs-lookup"><span data-stu-id="032a2-117">The foreground color is the color of the hatching.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#122](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 <span data-ttu-id="032a2-118">GDI+ proporciona más de 50 estilos de trama; los tres estilos que se muestran en la siguiente <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>ilustración <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>son, <xref:System.Drawing.Drawing2D.HatchStyle.Cross>y.</span><span class="sxs-lookup"><span data-stu-id="032a2-118">GDI+ provides more than 50 hatch styles; the three styles shown in the following illustration are <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, and <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span></span>  
  
 <span data-ttu-id="032a2-119">![Formas] rellenas (./media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span><span class="sxs-lookup"><span data-stu-id="032a2-119">![Filled Shapes](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span></span>  
  
## <a name="texture-brushes"></a><span data-ttu-id="032a2-120">Pinceles de textura</span><span class="sxs-lookup"><span data-stu-id="032a2-120">Texture Brushes</span></span>  
 <span data-ttu-id="032a2-121">Con un pincel de textura, puede rellenar una forma con un patrón almacenado en un mapa de bits.</span><span class="sxs-lookup"><span data-stu-id="032a2-121">With a texture brush, you can fill a shape with a pattern stored in a bitmap.</span></span> <span data-ttu-id="032a2-122">Por ejemplo, supongamos que la siguiente imagen se almacena en un `MyTexture.bmp`archivo de disco denominado.</span><span class="sxs-lookup"><span data-stu-id="032a2-122">For example, suppose the following picture is stored in a disk file named `MyTexture.bmp`.</span></span>  
  
 <span data-ttu-id="032a2-123">![Forma rellena](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span><span class="sxs-lookup"><span data-stu-id="032a2-123">![Filled Shape](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span></span>  
  
 <span data-ttu-id="032a2-124">En el ejemplo de código siguiente se muestra cómo rellenar una elipse repitiendo `MyTexture.bmp`la imagen almacenada en.</span><span class="sxs-lookup"><span data-stu-id="032a2-124">The following code example shows how to fill an ellipse by repeating the picture stored in `MyTexture.bmp`.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#123](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 <span data-ttu-id="032a2-125">En la ilustración siguiente se muestra la elipse rellenada.</span><span class="sxs-lookup"><span data-stu-id="032a2-125">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="032a2-126">![Forma rellena](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span><span class="sxs-lookup"><span data-stu-id="032a2-126">![Filled Shape](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span></span>  
  
## <a name="gradient-brushes"></a><span data-ttu-id="032a2-127">Pinceles de degradado</span><span class="sxs-lookup"><span data-stu-id="032a2-127">Gradient Brushes</span></span>  
 <span data-ttu-id="032a2-128">GDI+ proporciona dos tipos de pinceles de degradado: lineal y path.</span><span class="sxs-lookup"><span data-stu-id="032a2-128">GDI+ provides two kinds of gradient brushes: linear and path.</span></span> <span data-ttu-id="032a2-129">Puede usar un pincel de degradado lineal para rellenar una forma con un color que cambie gradualmente a medida que se desplaza por la forma horizontal, vertical o diagonalmente.</span><span class="sxs-lookup"><span data-stu-id="032a2-129">You can use a linear gradient brush to fill a shape with color that changes gradually as you move across the shape horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="032a2-130">En el ejemplo de código siguiente se muestra cómo rellenar una elipse con un pincel de degradado horizontal que cambia de azul a verde a medida que se desplaza desde el borde izquierdo de la elipse hasta el borde derecho.</span><span class="sxs-lookup"><span data-stu-id="032a2-130">The following code example shows how to fill an ellipse with a horizontal gradient brush that changes from blue to green as you move from the left edge of the ellipse to the right edge.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#124](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 <span data-ttu-id="032a2-131">En la ilustración siguiente se muestra la elipse rellenada.</span><span class="sxs-lookup"><span data-stu-id="032a2-131">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="032a2-132">![Forma rellena](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span><span class="sxs-lookup"><span data-stu-id="032a2-132">![Filled Shape](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span></span>  
  
 <span data-ttu-id="032a2-133">Un pincel de degradado de trazado puede configurarse para cambiar el color a medida que se desplaza desde el centro de una forma hacia el borde.</span><span class="sxs-lookup"><span data-stu-id="032a2-133">A path gradient brush can be configured to change color as you move from the center of a shape toward the edge.</span></span>  
  
 <span data-ttu-id="032a2-134">![Forma rellena](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span><span class="sxs-lookup"><span data-stu-id="032a2-134">![Filled Shape](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span></span>  
  
 <span data-ttu-id="032a2-135">Los pinceles de degradado de trazado son bastante flexibles.</span><span class="sxs-lookup"><span data-stu-id="032a2-135">Path gradient brushes are quite flexible.</span></span> <span data-ttu-id="032a2-136">El pincel de degradado que se usa para rellenar el triángulo de la siguiente ilustración cambia gradualmente de rojo en el centro a cada uno de tres colores diferentes en los vértices.</span><span class="sxs-lookup"><span data-stu-id="032a2-136">The gradient brush used to fill the triangle in the following illustration changes gradually from red at the center to each of three different colors at the vertices.</span></span>  
  
 <span data-ttu-id="032a2-137">![Forma rellena](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span><span class="sxs-lookup"><span data-stu-id="032a2-137">![Filled Shape](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="032a2-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="032a2-138">See also</span></span>

- <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>
- <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="032a2-139">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="032a2-139">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="032a2-140">Cómo: Dibujar un rectángulo relleno en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="032a2-140">How to: Draw a Filled Rectangle on a Windows Form</span></span>](how-to-draw-a-filled-rectangle-on-a-windows-form.md)
- [<span data-ttu-id="032a2-141">Procedimientos: Dibujar una elipse rellena en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="032a2-141">How to: Draw a Filled Ellipse on a Windows Form</span></span>](how-to-draw-a-filled-ellipse-on-a-windows-form.md)
