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
ms.openlocfilehash: 683b5966f993ac3a69c8bf7c1233b6df3d65e19a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115315"
---
# <a name="brushes-and-filled-shapes-in-gdi"></a><span data-ttu-id="207dc-102">Pinceles y formas rellenas en GDI+</span><span class="sxs-lookup"><span data-stu-id="207dc-102">Brushes and Filled Shapes in GDI+</span></span>
<span data-ttu-id="207dc-103">Una forma cerrada, como un rectángulo o una elipse, consta de un esquema y un interior.</span><span class="sxs-lookup"><span data-stu-id="207dc-103">A closed shape, such as a rectangle or an ellipse, consists of an outline and an interior.</span></span> <span data-ttu-id="207dc-104">El contorno se dibuja con un lápiz y el interior se rellena con un pincel.</span><span class="sxs-lookup"><span data-stu-id="207dc-104">The outline is drawn with a pen and the interior is filled with a brush.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="207dc-105">proporciona varias clases de pincel para rellenar los interiores de formas cerradas: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, y <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="207dc-105">provides several brush classes for filling the interiors of closed shapes: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, and <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span></span> <span data-ttu-id="207dc-106">Todas estas clases heredan de la <xref:System.Drawing.Brush> clase.</span><span class="sxs-lookup"><span data-stu-id="207dc-106">All of these classes inherit from the <xref:System.Drawing.Brush> class.</span></span> <span data-ttu-id="207dc-107">La siguiente ilustración se muestra un rectángulo relleno con un pincel sólido y una elipse rellena con un pincel de trama.</span><span class="sxs-lookup"><span data-stu-id="207dc-107">The following illustration shows a rectangle filled with a solid brush and an ellipse filled with a hatch brush.</span></span>  
  
 <span data-ttu-id="207dc-108">![Rellenar formas](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span><span class="sxs-lookup"><span data-stu-id="207dc-108">![Filled Shapes](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span></span>  
  
## <a name="solid-brushes"></a><span data-ttu-id="207dc-109">Pinceles sólidos</span><span class="sxs-lookup"><span data-stu-id="207dc-109">Solid Brushes</span></span>  
 <span data-ttu-id="207dc-110">Para rellenar una forma cerrada, se necesita una instancia de la <xref:System.Drawing.Graphics> clase y un <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="207dc-110">To fill a closed shape, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Brush>.</span></span> <span data-ttu-id="207dc-111">La instancia de la <xref:System.Drawing.Graphics> clase proporciona métodos, como <xref:System.Drawing.Graphics.FillRectangle%2A> y <xref:System.Drawing.Graphics.FillEllipse%2A>y el <xref:System.Drawing.Brush> almacena atributos de relleno, como el color y el patrón.</span><span class="sxs-lookup"><span data-stu-id="207dc-111">The instance of the <xref:System.Drawing.Graphics> class provides methods, such as <xref:System.Drawing.Graphics.FillRectangle%2A> and <xref:System.Drawing.Graphics.FillEllipse%2A>, and the <xref:System.Drawing.Brush> stores attributes of the fill, such as color and pattern.</span></span> <span data-ttu-id="207dc-112">El <xref:System.Drawing.Brush> se pasa como uno de los argumentos del método de relleno.</span><span class="sxs-lookup"><span data-stu-id="207dc-112">The <xref:System.Drawing.Brush> is passed as one of the arguments to the fill method.</span></span> <span data-ttu-id="207dc-113">El ejemplo de código siguiente muestra cómo rellenar una elipse con un color rojo sólido.</span><span class="sxs-lookup"><span data-stu-id="207dc-113">The following code example shows how to fill an ellipse with a solid red color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#121](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  <span data-ttu-id="207dc-114">En el ejemplo anterior, el pincel es de tipo <xref:System.Drawing.SolidBrush>, que hereda de <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="207dc-114">In the preceding example, the brush is of type <xref:System.Drawing.SolidBrush>, which inherits from <xref:System.Drawing.Brush>.</span></span>  
  
## <a name="hatch-brushes"></a><span data-ttu-id="207dc-115">Pinceles de trama</span><span class="sxs-lookup"><span data-stu-id="207dc-115">Hatch Brushes</span></span>  
 <span data-ttu-id="207dc-116">Al rellenar una forma con un pincel de trama, especifique un color de primer plano, un color de fondo y un estilo de trama.</span><span class="sxs-lookup"><span data-stu-id="207dc-116">When you fill a shape with a hatch brush, you specify a foreground color, a background color, and a hatch style.</span></span> <span data-ttu-id="207dc-117">El color de primer plano es el color de la sombreado.</span><span class="sxs-lookup"><span data-stu-id="207dc-117">The foreground color is the color of the hatching.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#122](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="207dc-118">proporciona más de 50 estilos de sombreado; los tres estilos que se muestra en la siguiente ilustración son <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, y <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span><span class="sxs-lookup"><span data-stu-id="207dc-118">provides more than 50 hatch styles; the three styles shown in the following illustration are <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, and <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span></span>  
  
 <span data-ttu-id="207dc-119">![Rellenar formas](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span><span class="sxs-lookup"><span data-stu-id="207dc-119">![Filled Shapes](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span></span>  
  
## <a name="texture-brushes"></a><span data-ttu-id="207dc-120">Pinceles de textura</span><span class="sxs-lookup"><span data-stu-id="207dc-120">Texture Brushes</span></span>  
 <span data-ttu-id="207dc-121">Con un pincel de textura, puede rellenar una forma con un modelo almacenado en un mapa de bits.</span><span class="sxs-lookup"><span data-stu-id="207dc-121">With a texture brush, you can fill a shape with a pattern stored in a bitmap.</span></span> <span data-ttu-id="207dc-122">Por ejemplo, suponga la siguiente imagen se almacena en un archivo de disco denominado `MyTexture.bmp`.</span><span class="sxs-lookup"><span data-stu-id="207dc-122">For example, suppose the following picture is stored in a disk file named `MyTexture.bmp`.</span></span>  
  
 <span data-ttu-id="207dc-123">![Rellena de forma](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span><span class="sxs-lookup"><span data-stu-id="207dc-123">![Filled Shape](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span></span>  
  
 <span data-ttu-id="207dc-124">El ejemplo de código siguiente muestra cómo rellenar una elipse repitiendo la imagen almacenada en `MyTexture.bmp`.</span><span class="sxs-lookup"><span data-stu-id="207dc-124">The following code example shows how to fill an ellipse by repeating the picture stored in `MyTexture.bmp`.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#123](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 <span data-ttu-id="207dc-125">La siguiente ilustración muestra la elipse rellena.</span><span class="sxs-lookup"><span data-stu-id="207dc-125">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="207dc-126">![Rellena de forma](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span><span class="sxs-lookup"><span data-stu-id="207dc-126">![Filled Shape](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span></span>  
  
## <a name="gradient-brushes"></a><span data-ttu-id="207dc-127">Pinceles de degradado</span><span class="sxs-lookup"><span data-stu-id="207dc-127">Gradient Brushes</span></span>  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="207dc-128">proporciona dos tipos de pinceles de degradado: lineal y ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="207dc-128">provides two kinds of gradient brushes: linear and path.</span></span> <span data-ttu-id="207dc-129">Puede utilizar un pincel de degradado lineal para rellenar una forma con un color que cambia gradualmente al desplazarse a través de la forma horizontal, vertical o diagonalmente.</span><span class="sxs-lookup"><span data-stu-id="207dc-129">You can use a linear gradient brush to fill a shape with color that changes gradually as you move across the shape horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="207dc-130">El ejemplo de código siguiente muestra cómo rellenar una elipse con un pincel de degradado horizontal que cambia de azul a verde a medida que se desplaza desde el borde izquierdo de la elipse hasta el borde derecho.</span><span class="sxs-lookup"><span data-stu-id="207dc-130">The following code example shows how to fill an ellipse with a horizontal gradient brush that changes from blue to green as you move from the left edge of the ellipse to the right edge.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#124](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 <span data-ttu-id="207dc-131">La siguiente ilustración muestra la elipse rellena.</span><span class="sxs-lookup"><span data-stu-id="207dc-131">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="207dc-132">![Rellena de forma](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span><span class="sxs-lookup"><span data-stu-id="207dc-132">![Filled Shape](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span></span>  
  
 <span data-ttu-id="207dc-133">Un pincel de degradado de la ruta de acceso puede configurarse para cambiar el color al desplazarse desde el centro de una forma hacia el borde.</span><span class="sxs-lookup"><span data-stu-id="207dc-133">A path gradient brush can be configured to change color as you move from the center of a shape toward the edge.</span></span>  
  
 <span data-ttu-id="207dc-134">![Rellena de forma](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span><span class="sxs-lookup"><span data-stu-id="207dc-134">![Filled Shape](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span></span>  
  
 <span data-ttu-id="207dc-135">Pinceles de degradado de trazado son bastante flexibles.</span><span class="sxs-lookup"><span data-stu-id="207dc-135">Path gradient brushes are quite flexible.</span></span> <span data-ttu-id="207dc-136">El pincel de degradado que se usa para rellenar el triángulo situado en la siguiente ilustración cambia gradualmente de rojo en el centro a cada uno de tres colores distintos en los vértices.</span><span class="sxs-lookup"><span data-stu-id="207dc-136">The gradient brush used to fill the triangle in the following illustration changes gradually from red at the center to each of three different colors at the vertices.</span></span>  
  
 <span data-ttu-id="207dc-137">![Rellena de forma](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span><span class="sxs-lookup"><span data-stu-id="207dc-137">![Filled Shape](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="207dc-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="207dc-138">See also</span></span>

- <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>
- <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="207dc-139">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="207dc-139">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="207dc-140">Cómo: Dibujar un rectángulo relleno en un formulario de Windows</span><span class="sxs-lookup"><span data-stu-id="207dc-140">How to: Draw a Filled Rectangle on a Windows Form</span></span>](how-to-draw-a-filled-rectangle-on-a-windows-form.md)
- [<span data-ttu-id="207dc-141">Cómo: Dibujar una elipse con relleno en un formulario de Windows</span><span class="sxs-lookup"><span data-stu-id="207dc-141">How to: Draw a Filled Ellipse on a Windows Form</span></span>](how-to-draw-a-filled-ellipse-on-a-windows-form.md)
