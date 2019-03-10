---
title: Procedimiento Crear un degradado lineal
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
ms.openlocfilehash: e47707d040cd7bf67008fab33ac482706963ce39
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725251"
---
# <a name="how-to-create-a-linear-gradient"></a><span data-ttu-id="bdc6e-102">Procedimiento Crear un degradado lineal</span><span class="sxs-lookup"><span data-stu-id="bdc6e-102">How to: Create a Linear Gradient</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="bdc6e-103">proporciona degradados lineales horizontales, verticales y diagonales.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-103">provides horizontal, vertical, and diagonal linear gradients.</span></span> <span data-ttu-id="bdc6e-104">De forma predeterminada, el color de un degradado lineal cambia de manera uniforme.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-104">By default, the color in a linear gradient changes uniformly.</span></span> <span data-ttu-id="bdc6e-105">Sin embargo, puede personalizar un degradado lineal por lo que cambia el color de manera no uniforme.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-105">However, you can customize a linear gradient so that the color changes in a non-uniform fashion.</span></span>  
  
 <span data-ttu-id="bdc6e-106">El siguiente ejemplo rellena una línea, una elipse y un rectángulo con un pincel de degradado lineal horizontal.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-106">The following example fills a line, an ellipse, and a rectangle with a horizontal linear gradient brush.</span></span>  
  
 <span data-ttu-id="bdc6e-107">El <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor recibe cuatro argumentos: dos puntos y dos colores.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-107">The <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor receives four arguments: two points and two colors.</span></span> <span data-ttu-id="bdc6e-108">El primer punto (0, 10) está asociado con el primer color (rojo) y el segundo punto (200, 10) está asociado con el segundo color (azul).</span><span class="sxs-lookup"><span data-stu-id="bdc6e-108">The first point (0, 10) is associated with the first color (red), and the second point (200, 10) is associated with the second color (blue).</span></span> <span data-ttu-id="bdc6e-109">Como cabría esperar, la línea dibujada en (0, 10) a (200, 10) cambia gradualmente de rojo a azul.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-109">As you would expect, the line drawn from (0, 10) to (200, 10) changes gradually from red to blue.</span></span>  
  
 <span data-ttu-id="bdc6e-110">El 10s en los puntos (50, 10) y (200, 10) no son importantes.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-110">The 10s in the points (50, 10) and (200, 10) are not important.</span></span> <span data-ttu-id="bdc6e-111">Lo importante es que los dos puntos tengan la misma segunda coordenada: la línea conectándolos es horizontal.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-111">What is important is that the two points have the same second coordinate — the line connecting them is horizontal.</span></span> <span data-ttu-id="bdc6e-112">Los puntos suspensivos y el rectángulo también cambian gradualmente de rojo a azul como la coordenada horizontal va de 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-112">The ellipse and the rectangle also change gradually from red to blue as the horizontal coordinate goes from 0 to 200.</span></span>  
  
 <span data-ttu-id="bdc6e-113">La siguiente ilustración muestra la línea, la elipse y el rectángulo.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-113">The following illustration shows the line, the ellipse, and the rectangle.</span></span> <span data-ttu-id="bdc6e-114">Tenga en cuenta que el degradado de color se repite a medida que aumenta la coordenada horizontal por encima de 200.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-114">Note that the color gradient repeats itself as the horizontal coordinate increases beyond 200.</span></span>  
  
 <span data-ttu-id="bdc6e-115">![Degradado lineal](./media/cslineargradient1.png "cslineargradient1")</span><span class="sxs-lookup"><span data-stu-id="bdc6e-115">![Linear Gradient](./media/cslineargradient1.png "cslineargradient1")</span></span>  
  
### <a name="to-use-horizontal-linear-gradients"></a><span data-ttu-id="bdc6e-116">Usar degradados lineales horizontales</span><span class="sxs-lookup"><span data-stu-id="bdc6e-116">To use horizontal linear gradients</span></span>  
  
-   <span data-ttu-id="bdc6e-117">Pase el azul opaco opaco y rojo como el tercer y cuarto argumentos, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-117">Pass in the opaque red and opaque blue as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 <span data-ttu-id="bdc6e-118">En el ejemplo anterior, los componentes de color linealmente cambian cuando alterna de una coordenada horizontal de 0 a una coordenada horizontal de 200.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-118">In the preceding example, the color components change linearly as you move from a horizontal coordinate of 0 to a horizontal coordinate of 200.</span></span> <span data-ttu-id="bdc6e-119">Por ejemplo, un punto cuya primera coordenada está comprendido entre 0 y 200 tendrá un componente azul que está comprendido entre 0 y 255.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-119">For example, a point whose first coordinate is halfway between 0 and 200 will have a blue component that is halfway between 0 and 255.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="bdc6e-120">permite ajustar la manera en que un color varía en función de uno de los bordes de un degradado a otro.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-120">allows you to adjust the way a color varies from one edge of a gradient to the other.</span></span> <span data-ttu-id="bdc6e-121">Suponga que desea crear un pincel de degradado que cambia de color negro a rojo según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-121">Suppose you want to create a gradient brush that changes from black to red according to the following table.</span></span>  
  
|<span data-ttu-id="bdc6e-122">Coordenada horizontal</span><span class="sxs-lookup"><span data-stu-id="bdc6e-122">Horizontal coordinate</span></span>|<span data-ttu-id="bdc6e-123">Componentes RGB</span><span class="sxs-lookup"><span data-stu-id="bdc6e-123">RGB components</span></span>|  
|---------------------------|--------------------|  
|<span data-ttu-id="bdc6e-124">0</span><span class="sxs-lookup"><span data-stu-id="bdc6e-124">0</span></span>|<span data-ttu-id="bdc6e-125">(0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="bdc6e-125">(0, 0, 0)</span></span>|  
|<span data-ttu-id="bdc6e-126">40</span><span class="sxs-lookup"><span data-stu-id="bdc6e-126">40</span></span>|<span data-ttu-id="bdc6e-127">(128, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="bdc6e-127">(128, 0, 0)</span></span>|  
|<span data-ttu-id="bdc6e-128">200</span><span class="sxs-lookup"><span data-stu-id="bdc6e-128">200</span></span>|<span data-ttu-id="bdc6e-129">(255, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="bdc6e-129">(255, 0, 0)</span></span>|  
  
 <span data-ttu-id="bdc6e-130">Tenga en cuenta que el componente rojo a media intensidad cuando la coordenada horizontal es sólo el 20 por ciento de la manera de 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-130">Note that the red component is at half intensity when the horizontal coordinate is only 20 percent of the way from 0 to 200.</span></span>  
  
 <span data-ttu-id="bdc6e-131">El ejemplo siguiente se establece la <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> propiedad de un <xref:System.Drawing.Drawing2D.LinearGradientBrush> objeto para asociar tres intensidades relativas a tres posiciones relativas.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-131">The following example sets the <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> property of a <xref:System.Drawing.Drawing2D.LinearGradientBrush> object to associate three relative intensities with three relative positions.</span></span> <span data-ttu-id="bdc6e-132">Como se muestra en la tabla anterior, una intensidad relativa de 0,5 está asociada con una posición relativa de 0,2.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-132">As in the preceding table, a relative intensity of 0.5 is associated with a relative position of 0.2.</span></span> <span data-ttu-id="bdc6e-133">El código rellena una elipse y un rectángulo con el pincel de degradado.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-133">The code fills an ellipse and a rectangle with the gradient brush.</span></span>  
  
 <span data-ttu-id="bdc6e-134">La siguiente ilustración muestra la elipse resultante y el rectángulo.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-134">The following illustration shows the resulting ellipse and rectangle.</span></span>  
  
 <span data-ttu-id="bdc6e-135">![Degradado lineal](./media/cslineargradient2.png "cslineargradient2")</span><span class="sxs-lookup"><span data-stu-id="bdc6e-135">![Linear Gradient](./media/cslineargradient2.png "cslineargradient2")</span></span>  
  
### <a name="to-customize-linear-gradients"></a><span data-ttu-id="bdc6e-136">Para personalizar degradados lineales</span><span class="sxs-lookup"><span data-stu-id="bdc6e-136">To customize linear gradients</span></span>  
  
-   <span data-ttu-id="bdc6e-137">Pase el rojo opaco opaco y negro como el tercer y cuarto argumentos, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-137">Pass in the opaque black and opaque red as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 <span data-ttu-id="bdc6e-138">Los degradados en los ejemplos anteriores han sido horizontales; es decir, el color cambia gradualmente conforme se desplaza por cualquier línea horizontal.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-138">The gradients in the preceding examples have been horizontal; that is, the color changes gradually as you move along any horizontal line.</span></span> <span data-ttu-id="bdc6e-139">También puede definir degradados verticales y diagonales.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-139">You can also define vertical gradients and diagonal gradients.</span></span>  
  
 <span data-ttu-id="bdc6e-140">El siguiente ejemplo pasa a los puntos (0, 0) y (200, 100) a un <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-140">The following example passes the points (0, 0) and (200, 100) to a <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="bdc6e-141">Está asociado el color azul (0, 0), y se asocia el color verde (200, 100).</span><span class="sxs-lookup"><span data-stu-id="bdc6e-141">The color blue is associated with (0, 0), and the color green is associated with (200, 100).</span></span> <span data-ttu-id="bdc6e-142">Una línea (con el ancho del lápiz 10) y una elipse se rellenan con el pincel de degradado lineal.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-142">A line (with pen width 10) and an ellipse are filled with the linear gradient brush.</span></span>  
  
 <span data-ttu-id="bdc6e-143">La siguiente ilustración muestra la línea y la elipse.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-143">The following illustration shows the line and the ellipse.</span></span> <span data-ttu-id="bdc6e-144">Tenga en cuenta que el color de la elipse cambia gradualmente conforme se desplaza por cualquier línea es parecida a la línea que atraviesa (0, 0) y (200, 100).</span><span class="sxs-lookup"><span data-stu-id="bdc6e-144">Note that the color in the ellipse changes gradually as you move along any line that is parallel to the line passing through (0, 0) and (200, 100).</span></span>  
  
 <span data-ttu-id="bdc6e-145">![Degradado lineal](./media/cslineargradient3.png "cslineargradient3")</span><span class="sxs-lookup"><span data-stu-id="bdc6e-145">![Linear Gradient](./media/cslineargradient3.png "cslineargradient3")</span></span>  
  
### <a name="to-create-diagonal-linear-gradients"></a><span data-ttu-id="bdc6e-146">Para crear degradados lineales diagonales</span><span class="sxs-lookup"><span data-stu-id="bdc6e-146">To create diagonal linear gradients</span></span>  
  
-   <span data-ttu-id="bdc6e-147">Pase el verde opaco opaco y azul como el tercer y cuarto argumentos, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="bdc6e-147">Pass in the opaque blue and opaque green as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="bdc6e-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdc6e-148">See also</span></span>
- [<span data-ttu-id="bdc6e-149">Utilizar un pincel degradado para rellenar formas</span><span class="sxs-lookup"><span data-stu-id="bdc6e-149">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
- [<span data-ttu-id="bdc6e-150">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bdc6e-150">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
