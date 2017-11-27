---
title: Tipos de sistemas de coordenadas
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
- transformations [Windows Forms], page
- unit of measure
- world coordinate system
- page coordinate system
- page transformation
- device coordinate system
- world transformation
- coordinate systems
- transformations [Windows Forms], world
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: be89584ee8e7a82c405bf8664bfad18ced6d989a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="types-of-coordinate-systems"></a><span data-ttu-id="be8c7-102">Tipos de sistemas de coordenadas</span><span class="sxs-lookup"><span data-stu-id="be8c7-102">Types of Coordinate Systems</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="be8c7-103">utiliza tres espacios de coordenadas: universales, de página y de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="be8c7-103"> uses three coordinate spaces: world, page, and device.</span></span> <span data-ttu-id="be8c7-104">Coordenadas universales son las coordenadas utilizadas para modelar un mundo gráfico determinado y las coordenadas que se pasan a los métodos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="be8c7-104">World coordinates are the coordinates used to model a particular graphic world and are the coordinates you pass to methods in the .NET Framework.</span></span> <span data-ttu-id="be8c7-105">Las coordenadas de página hacen referencia al sistema de coordenadas utilizado por una superficie de dibujo, como un formulario o control.</span><span class="sxs-lookup"><span data-stu-id="be8c7-105">Page coordinates refer to the coordinate system used by a drawing surface, such as a form or control.</span></span> <span data-ttu-id="be8c7-106">Coordenadas de dispositivo son las utilizadas por el dispositivo físico que se dibuja, como una pantalla o una hoja de papel.</span><span class="sxs-lookup"><span data-stu-id="be8c7-106">Device coordinates are the coordinates used by the physical device being drawn on, such as a screen or sheet of paper.</span></span> <span data-ttu-id="be8c7-107">Cuando realiza la llamada `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, lo que se pasa a la <xref:System.Drawing.Graphics.DrawLine%2A> método:`(0, 0)` y `(160, 80)`: están en el espacio de coordenadas universales.</span><span class="sxs-lookup"><span data-stu-id="be8c7-107">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, the points that you pass to the <xref:System.Drawing.Graphics.DrawLine%2A> method—`(0, 0)` and `(160, 80)`—are in the world coordinate space.</span></span> <span data-ttu-id="be8c7-108">Antes de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] puede dibujar la línea en la pantalla, las coordenadas tienen que pasar a través de una secuencia de transformaciones.</span><span class="sxs-lookup"><span data-stu-id="be8c7-108">Before [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can draw the line on the screen, the coordinates pass through a sequence of transformations.</span></span> <span data-ttu-id="be8c7-109">Una transformación, llamada a la transformación universal, convierte las coordenadas universales en coordenadas de página y otra transformación, llamado a la transformación de página, convierte las coordenadas de página en coordenadas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="be8c7-109">One transformation, called the world transformation, converts world coordinates to page coordinates, and another transformation, called the page transformation, converts page coordinates to device coordinates.</span></span>  
  
## <a name="transforms-and-coordinate-systems"></a><span data-ttu-id="be8c7-110">Sistemas de coordenadas y transformaciones</span><span class="sxs-lookup"><span data-stu-id="be8c7-110">Transforms and Coordinate Systems</span></span>  
 <span data-ttu-id="be8c7-111">Imagine que desea trabajar con un sistema de coordenadas que tiene su origen en el cuerpo del área de cliente en lugar de la esquina superior izquierda.</span><span class="sxs-lookup"><span data-stu-id="be8c7-111">Suppose you want to work with a coordinate system that has its origin in the body of the client area rather than the upper-left corner.</span></span> <span data-ttu-id="be8c7-112">Por ejemplo, supongamos que desea que el origen sea 100 píxeles desde el borde izquierdo del área cliente y 50 píxeles desde la parte superior del área cliente.</span><span class="sxs-lookup"><span data-stu-id="be8c7-112">Say, for example, that you want the origin to be 100 pixels from the left edge of the client area and 50 pixels from the top of the client area.</span></span> <span data-ttu-id="be8c7-113">En la siguiente ilustración muestra un sistema de coordenadas de este tipo.</span><span class="sxs-lookup"><span data-stu-id="be8c7-113">The following illustration shows such a coordinate system.</span></span>  
  
 <span data-ttu-id="be8c7-114">![Sistema de coordenadas](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art01.gif "AboutGdip05_art01")</span><span class="sxs-lookup"><span data-stu-id="be8c7-114">![Coordinate System](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art01.gif "AboutGdip05_art01")</span></span>  
  
 <span data-ttu-id="be8c7-115">Cuando realiza la llamada `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, obtendrá la línea que se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="be8c7-115">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, you get the line shown in the following illustration.</span></span>  
  
 <span data-ttu-id="be8c7-116">![Sistema de coordenadas](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art02.gif "AboutGdip05_art02")</span><span class="sxs-lookup"><span data-stu-id="be8c7-116">![Coordinate System](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art02.gif "AboutGdip05_art02")</span></span>  
  
 <span data-ttu-id="be8c7-117">Las coordenadas de los extremos de la línea en los tres espacios de coordenadas son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="be8c7-117">The coordinates of the endpoints of your line in the three coordinate spaces are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be8c7-118">World</span><span class="sxs-lookup"><span data-stu-id="be8c7-118">World</span></span>|<span data-ttu-id="be8c7-119">(0, 0) a (160, 80)</span><span class="sxs-lookup"><span data-stu-id="be8c7-119">(0, 0) to (160, 80)</span></span>|  
|<span data-ttu-id="be8c7-120">Página</span><span class="sxs-lookup"><span data-stu-id="be8c7-120">Page</span></span>|<span data-ttu-id="be8c7-121">(100, 50) a (260, 130)</span><span class="sxs-lookup"><span data-stu-id="be8c7-121">(100, 50) to (260, 130)</span></span>|  
|<span data-ttu-id="be8c7-122">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="be8c7-122">Device</span></span>|<span data-ttu-id="be8c7-123">(100, 50) a (260, 130)</span><span class="sxs-lookup"><span data-stu-id="be8c7-123">(100, 50) to (260, 130)</span></span>|  
  
 <span data-ttu-id="be8c7-124">Tenga en cuenta que el espacio de coordenadas de página tiene su origen en la esquina superior izquierda del área de cliente; Esto siempre será el caso.</span><span class="sxs-lookup"><span data-stu-id="be8c7-124">Note that the page coordinate space has its origin at the upper-left corner of the client area; this will always be the case.</span></span> <span data-ttu-id="be8c7-125">Tenga en cuenta que, dado que la unidad de medida es el píxel, las coordenadas de dispositivo son los mismos que las coordenadas de página.</span><span class="sxs-lookup"><span data-stu-id="be8c7-125">Also note that because the unit of measure is the pixel, the device coordinates are the same as the page coordinates.</span></span> <span data-ttu-id="be8c7-126">Si establece la unidad de medida en un valor distinto de píxeles (por ejemplo, pulgadas), las coordenadas del dispositivo será diferentes de las coordenadas de página.</span><span class="sxs-lookup"><span data-stu-id="be8c7-126">If you set the unit of measure to something other than pixels (for example, inches), then the device coordinates will be different from the page coordinates.</span></span>  
  
 <span data-ttu-id="be8c7-127">La transformación universal, que asigna las coordenadas universales en coordenadas de página, se mantiene en el <xref:System.Drawing.Graphics.Transform%2A> propiedad de la <xref:System.Drawing.Graphics> clase.</span><span class="sxs-lookup"><span data-stu-id="be8c7-127">The world transformation, which maps world coordinates to page coordinates, is held in the <xref:System.Drawing.Graphics.Transform%2A> property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="be8c7-128">En el ejemplo anterior, la transformación universal es una conversión de 100 unidades en la dirección del eje x y de 50 unidades en la dirección del eje y.</span><span class="sxs-lookup"><span data-stu-id="be8c7-128">In the preceding example, the world transformation is a translation 100 units in the x direction and 50 units in the y direction.</span></span> <span data-ttu-id="be8c7-129">En el ejemplo siguiente se establece la transformación universal de un <xref:System.Drawing.Graphics> objeto y, a continuación, usa <xref:System.Drawing.Graphics> objeto que se va a dibujar la línea que se muestra en la ilustración anterior:</span><span class="sxs-lookup"><span data-stu-id="be8c7-129">The following example sets the world transformation of a <xref:System.Drawing.Graphics> object and then uses that <xref:System.Drawing.Graphics> object to draw the line shown in the preceding figure:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 <span data-ttu-id="be8c7-130">La transformación de página asigna las coordenadas de página en coordenadas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="be8c7-130">The page transformation maps page coordinates to device coordinates.</span></span> <span data-ttu-id="be8c7-131">El <xref:System.Drawing.Graphics> clase proporciona el <xref:System.Drawing.Graphics.PageUnit%2A> y <xref:System.Drawing.Graphics.PageScale%2A> propiedades para manipular la transformación de página.</span><span class="sxs-lookup"><span data-stu-id="be8c7-131">The <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.PageUnit%2A> and <xref:System.Drawing.Graphics.PageScale%2A> properties for manipulating the page transformation.</span></span> <span data-ttu-id="be8c7-132">El <xref:System.Drawing.Graphics> clase también proporciona dos propiedades de solo lectura, <xref:System.Drawing.Graphics.DpiX%2A> y <xref:System.Drawing.Graphics.DpiY%2A>, para examinar los puntos horizontales y verticales por pulgada del dispositivo de pantalla.</span><span class="sxs-lookup"><span data-stu-id="be8c7-132">The <xref:System.Drawing.Graphics> class also provides two read-only properties, <xref:System.Drawing.Graphics.DpiX%2A> and <xref:System.Drawing.Graphics.DpiY%2A>, for examining the horizontal and vertical dots per inch of the display device.</span></span>  
  
 <span data-ttu-id="be8c7-133">Puede usar el <xref:System.Drawing.Graphics.PageUnit%2A> propiedad de la <xref:System.Drawing.Graphics> clase para especificar una unidad de medida distinta del píxel.</span><span class="sxs-lookup"><span data-stu-id="be8c7-133">You can use the <xref:System.Drawing.Graphics.PageUnit%2A> property of the <xref:System.Drawing.Graphics> class to specify a unit of measure other than the pixel.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be8c7-134">No se puede establecer la <xref:System.Drawing.Graphics.PageUnit%2A> propiedad <xref:System.Drawing.GraphicsUnit.World>, ya que esto no es una unidad física y producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="be8c7-134">You cannot set the <xref:System.Drawing.Graphics.PageUnit%2A> property to <xref:System.Drawing.GraphicsUnit.World>, as this is not a physical unit and will cause an exception.</span></span>  
  
 <span data-ttu-id="be8c7-135">En el ejemplo siguiente se dibuja una línea de (0, 0) a (2, 1), donde el punto (2, 1) es de 2 pulgadas a la derecha y 1 pulgada hacia abajo desde el punto (0, 0):</span><span class="sxs-lookup"><span data-stu-id="be8c7-135">The following example draws a line from (0, 0) to (2, 1), where the point (2, 1) is 2 inches to the right and 1 inch down from the point (0, 0):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  <span data-ttu-id="be8c7-136">Si no se especifica un ancho de lápiz al construir el lápiz, el ejemplo anterior dibujará una línea de una pulgada de ancho.</span><span class="sxs-lookup"><span data-stu-id="be8c7-136">If you don't specify a pen width when you construct your pen, the preceding example will draw a line that is one inch wide.</span></span> <span data-ttu-id="be8c7-137">Puede especificar el ancho del lápiz en el segundo argumento para el <xref:System.Drawing.Pen> constructor:</span><span class="sxs-lookup"><span data-stu-id="be8c7-137">You can specify the pen width in the second argument to the <xref:System.Drawing.Pen> constructor:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 <span data-ttu-id="be8c7-138">Si suponemos que el dispositivo de pantalla tiene 96 puntos por pulgada en dirección horizontal y 96 puntos por pulgada en dirección vertical, los extremos de la línea en el ejemplo anterior tienen las siguientes coordenadas en los tres espacios de coordenadas:</span><span class="sxs-lookup"><span data-stu-id="be8c7-138">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be8c7-139">World</span><span class="sxs-lookup"><span data-stu-id="be8c7-139">World</span></span>|<span data-ttu-id="be8c7-140">(0, 0) a (2, 1)</span><span class="sxs-lookup"><span data-stu-id="be8c7-140">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="be8c7-141">Página</span><span class="sxs-lookup"><span data-stu-id="be8c7-141">Page</span></span>|<span data-ttu-id="be8c7-142">(0, 0) a (2, 1)</span><span class="sxs-lookup"><span data-stu-id="be8c7-142">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="be8c7-143">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="be8c7-143">Device</span></span>|<span data-ttu-id="be8c7-144">(0, 0, a (192, 96)</span><span class="sxs-lookup"><span data-stu-id="be8c7-144">(0, 0, to (192, 96)</span></span>|  
  
 <span data-ttu-id="be8c7-145">Tenga en cuenta que, dado que es el origen del espacio de coordenadas universales en la esquina superior izquierda del área de cliente, las coordenadas de página son los mismos que las coordenadas universales.</span><span class="sxs-lookup"><span data-stu-id="be8c7-145">Note that because the origin of the world coordinate space is at the upper-left corner of the client area, the page coordinates are the same as the world coordinates.</span></span>  
  
 <span data-ttu-id="be8c7-146">Puede combinar las transformaciones universal y de página para lograr una gran variedad de efectos.</span><span class="sxs-lookup"><span data-stu-id="be8c7-146">You can combine the world and page transformations to achieve a variety of effects.</span></span> <span data-ttu-id="be8c7-147">Por ejemplo, suponga que desea usar pulgadas como unidad de medida y se desea que el origen de su sistema de coordenadas como 2 pulgadas desde el borde izquierdo del área cliente y 1/2 pulgada desde la parte superior del área cliente.</span><span class="sxs-lookup"><span data-stu-id="be8c7-147">For example, suppose you want to use inches as the unit of measure and you want the origin of your coordinate system to be 2 inches from the left edge of the client area and 1/2 inch from the top of the client area.</span></span> <span data-ttu-id="be8c7-148">En el ejemplo siguiente se establece las transformaciones universal y de página de un <xref:System.Drawing.Graphics> de objeto y, a continuación, se dibuja una línea de (0, 0) a (2, 1):</span><span class="sxs-lookup"><span data-stu-id="be8c7-148">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object and then draws a line from (0, 0) to (2, 1):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 <span data-ttu-id="be8c7-149">En la siguiente ilustración muestra la línea y el sistema de coordenadas.</span><span class="sxs-lookup"><span data-stu-id="be8c7-149">The following illustration shows the line and coordinate system.</span></span>  
  
 <span data-ttu-id="be8c7-150">![Sistema de coordenadas](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art03.gif "AboutGdip05_art03")</span><span class="sxs-lookup"><span data-stu-id="be8c7-150">![Coordinate System](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art03.gif "AboutGdip05_art03")</span></span>  
  
 <span data-ttu-id="be8c7-151">Si suponemos que el dispositivo de pantalla tiene 96 puntos por pulgada en dirección horizontal y 96 puntos por pulgada en dirección vertical, los extremos de la línea en el ejemplo anterior tienen las siguientes coordenadas en los tres espacios de coordenadas:</span><span class="sxs-lookup"><span data-stu-id="be8c7-151">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be8c7-152">World</span><span class="sxs-lookup"><span data-stu-id="be8c7-152">World</span></span>|<span data-ttu-id="be8c7-153">(0, 0) a (2, 1)</span><span class="sxs-lookup"><span data-stu-id="be8c7-153">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="be8c7-154">Página</span><span class="sxs-lookup"><span data-stu-id="be8c7-154">Page</span></span>|<span data-ttu-id="be8c7-155">(2, 0,5) a (4, 1.5)</span><span class="sxs-lookup"><span data-stu-id="be8c7-155">(2, 0.5) to (4, 1.5)</span></span>|  
|<span data-ttu-id="be8c7-156">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="be8c7-156">Device</span></span>|<span data-ttu-id="be8c7-157">(192, 48) a (384, 144)</span><span class="sxs-lookup"><span data-stu-id="be8c7-157">(192, 48) to (384, 144)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be8c7-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="be8c7-158">See Also</span></span>  
 [<span data-ttu-id="be8c7-159">Sistemas de coordenadas y transformaciones</span><span class="sxs-lookup"><span data-stu-id="be8c7-159">Coordinate Systems and Transformations</span></span>](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [<span data-ttu-id="be8c7-160">Representación matricial de transformaciones</span><span class="sxs-lookup"><span data-stu-id="be8c7-160">Matrix Representation of Transformations</span></span>](../../../../docs/framework/winforms/advanced/matrix-representation-of-transformations.md)
