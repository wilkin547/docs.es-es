---
title: Tipos de sistemas de coordenadas
ms.date: 03/30/2017
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
ms.openlocfilehash: bbb0d4908d4a281499336d262c653d7b72f3ccdc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159811"
---
# <a name="types-of-coordinate-systems"></a><span data-ttu-id="6892c-102">Tipos de sistemas de coordenadas</span><span class="sxs-lookup"><span data-stu-id="6892c-102">Types of Coordinate Systems</span></span>
<span data-ttu-id="6892c-103">GDI+ utiliza tres espacios de coordenadas: World, Page y Device.</span><span class="sxs-lookup"><span data-stu-id="6892c-103">GDI+ uses three coordinate spaces: world, page, and device.</span></span> <span data-ttu-id="6892c-104">Las coordenadas universales son las coordenadas utilizadas para modelar un mundo gráfico determinado y son las coordenadas que se pasan a los métodos en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6892c-104">World coordinates are the coordinates used to model a particular graphic world and are the coordinates you pass to methods in the .NET Framework.</span></span> <span data-ttu-id="6892c-105">Las coordenadas de página hacen referencia al sistema de coordenadas utilizado por una superficie de dibujo, como un formulario o un control.</span><span class="sxs-lookup"><span data-stu-id="6892c-105">Page coordinates refer to the coordinate system used by a drawing surface, such as a form or control.</span></span> <span data-ttu-id="6892c-106">Las coordenadas del dispositivo son las coordenadas utilizadas por el dispositivo físico en el que se dibuja, como una pantalla o una hoja de papel.</span><span class="sxs-lookup"><span data-stu-id="6892c-106">Device coordinates are the coordinates used by the physical device being drawn on, such as a screen or sheet of paper.</span></span> <span data-ttu-id="6892c-107">Cuando se realiza la llamada `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, los puntos que se pasan al método <xref:System.Drawing.Graphics.DrawLine%2A>,`(0, 0)` y `(160, 80)`, se encuentran en el espacio de coordenadas del mundo.</span><span class="sxs-lookup"><span data-stu-id="6892c-107">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, the points that you pass to the <xref:System.Drawing.Graphics.DrawLine%2A> method—`(0, 0)` and `(160, 80)`—are in the world coordinate space.</span></span> <span data-ttu-id="6892c-108">Antes de que GDI+ pueda dibujar la línea en la pantalla, las coordenadas pasan a través de una secuencia de transformaciones.</span><span class="sxs-lookup"><span data-stu-id="6892c-108">Before GDI+ can draw the line on the screen, the coordinates pass through a sequence of transformations.</span></span> <span data-ttu-id="6892c-109">Una transformación, denominada transformación universal, convierte coordenadas universales en coordenadas de página y otra transformación, denominada transformación página, convierte las coordenadas de página en coordenadas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6892c-109">One transformation, called the world transformation, converts world coordinates to page coordinates, and another transformation, called the page transformation, converts page coordinates to device coordinates.</span></span>  
  
## <a name="transforms-and-coordinate-systems"></a><span data-ttu-id="6892c-110">Transformaciones y sistemas de coordenadas</span><span class="sxs-lookup"><span data-stu-id="6892c-110">Transforms and Coordinate Systems</span></span>  
 <span data-ttu-id="6892c-111">Supongamos que desea trabajar con un sistema de coordenadas que tiene su origen en el cuerpo del área cliente en lugar de en la esquina superior izquierda.</span><span class="sxs-lookup"><span data-stu-id="6892c-111">Suppose you want to work with a coordinate system that has its origin in the body of the client area rather than the upper-left corner.</span></span> <span data-ttu-id="6892c-112">Por ejemplo, Imagine que desea que el origen sea 100 píxeles desde el borde izquierdo del área cliente y 50 píxeles desde la parte superior del área cliente.</span><span class="sxs-lookup"><span data-stu-id="6892c-112">Say, for example, that you want the origin to be 100 pixels from the left edge of the client area and 50 pixels from the top of the client area.</span></span> <span data-ttu-id="6892c-113">En la ilustración siguiente se muestra este tipo de sistema de coordenadas.</span><span class="sxs-lookup"><span data-stu-id="6892c-113">The following illustration shows such a coordinate system.</span></span>  
  
 <span data-ttu-id="6892c-114">![Sistema de coordenadas](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span><span class="sxs-lookup"><span data-stu-id="6892c-114">![Coordinate System](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span></span>  
  
 <span data-ttu-id="6892c-115">Cuando realice la llamada `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, obtendrá la línea que se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="6892c-115">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, you get the line shown in the following illustration.</span></span>  
  
 <span data-ttu-id="6892c-116">![Sistema de coordenadas](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span><span class="sxs-lookup"><span data-stu-id="6892c-116">![Coordinate System](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span></span>  
  
 <span data-ttu-id="6892c-117">Las coordenadas de los extremos de la línea en los tres espacios de coordenadas son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="6892c-117">The coordinates of the endpoints of your line in the three coordinate spaces are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6892c-118">WWPN</span><span class="sxs-lookup"><span data-stu-id="6892c-118">World</span></span>|<span data-ttu-id="6892c-119">(0,0) a (160, 80)</span><span class="sxs-lookup"><span data-stu-id="6892c-119">(0, 0) to (160, 80)</span></span>|  
|<span data-ttu-id="6892c-120">Página</span><span class="sxs-lookup"><span data-stu-id="6892c-120">Page</span></span>|<span data-ttu-id="6892c-121">(100, 50) a (260, 130)</span><span class="sxs-lookup"><span data-stu-id="6892c-121">(100, 50) to (260, 130)</span></span>|  
|<span data-ttu-id="6892c-122">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="6892c-122">Device</span></span>|<span data-ttu-id="6892c-123">(100, 50) a (260, 130)</span><span class="sxs-lookup"><span data-stu-id="6892c-123">(100, 50) to (260, 130)</span></span>|  
  
 <span data-ttu-id="6892c-124">Tenga en cuenta que el espacio de coordenadas de la página tiene su origen en la esquina superior izquierda del área cliente; siempre será el caso.</span><span class="sxs-lookup"><span data-stu-id="6892c-124">Note that the page coordinate space has its origin at the upper-left corner of the client area; this will always be the case.</span></span> <span data-ttu-id="6892c-125">Tenga en cuenta también que, dado que la unidad de medida es el píxel, las coordenadas del dispositivo son las mismas que las coordenadas de la página.</span><span class="sxs-lookup"><span data-stu-id="6892c-125">Also note that because the unit of measure is the pixel, the device coordinates are the same as the page coordinates.</span></span> <span data-ttu-id="6892c-126">Si establece la unidad de medida en un valor distinto de píxeles (por ejemplo, pulgadas), las coordenadas del dispositivo serán diferentes de las coordenadas de la página.</span><span class="sxs-lookup"><span data-stu-id="6892c-126">If you set the unit of measure to something other than pixels (for example, inches), then the device coordinates will be different from the page coordinates.</span></span>  
  
 <span data-ttu-id="6892c-127">La transformación universal, que asigna coordenadas universales a coordenadas de página, se mantiene en la propiedad <xref:System.Drawing.Graphics.Transform%2A> de la clase <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="6892c-127">The world transformation, which maps world coordinates to page coordinates, is held in the <xref:System.Drawing.Graphics.Transform%2A> property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="6892c-128">En el ejemplo anterior, la transformación universal es una traducción de 100 unidades en la dirección x y 50 unidades en la dirección y.</span><span class="sxs-lookup"><span data-stu-id="6892c-128">In the preceding example, the world transformation is a translation 100 units in the x direction and 50 units in the y direction.</span></span> <span data-ttu-id="6892c-129">En el ejemplo siguiente se establece la transformación universal de un objeto <xref:System.Drawing.Graphics> y, a continuación, se usa ese objeto <xref:System.Drawing.Graphics> para dibujar la línea que se muestra en la ilustración anterior:</span><span class="sxs-lookup"><span data-stu-id="6892c-129">The following example sets the world transformation of a <xref:System.Drawing.Graphics> object and then uses that <xref:System.Drawing.Graphics> object to draw the line shown in the preceding figure:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 <span data-ttu-id="6892c-130">La página asigna coordenadas de página a coordenadas del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6892c-130">The page transformation maps page coordinates to device coordinates.</span></span> <span data-ttu-id="6892c-131">La clase <xref:System.Drawing.Graphics> proporciona las propiedades <xref:System.Drawing.Graphics.PageUnit%2A> y <xref:System.Drawing.Graphics.PageScale%2A> para manipular la transformación de página.</span><span class="sxs-lookup"><span data-stu-id="6892c-131">The <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.PageUnit%2A> and <xref:System.Drawing.Graphics.PageScale%2A> properties for manipulating the page transformation.</span></span> <span data-ttu-id="6892c-132">La clase <xref:System.Drawing.Graphics> también proporciona dos propiedades de solo lectura, <xref:System.Drawing.Graphics.DpiX%2A> y <xref:System.Drawing.Graphics.DpiY%2A>, para examinar los puntos verticales y horizontales por pulgada del dispositivo de pantalla.</span><span class="sxs-lookup"><span data-stu-id="6892c-132">The <xref:System.Drawing.Graphics> class also provides two read-only properties, <xref:System.Drawing.Graphics.DpiX%2A> and <xref:System.Drawing.Graphics.DpiY%2A>, for examining the horizontal and vertical dots per inch of the display device.</span></span>  
  
 <span data-ttu-id="6892c-133">Puede utilizar la propiedad <xref:System.Drawing.Graphics.PageUnit%2A> de la clase <xref:System.Drawing.Graphics> para especificar una unidad de medida distinta del píxel.</span><span class="sxs-lookup"><span data-stu-id="6892c-133">You can use the <xref:System.Drawing.Graphics.PageUnit%2A> property of the <xref:System.Drawing.Graphics> class to specify a unit of measure other than the pixel.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6892c-134">No se puede establecer la propiedad <xref:System.Drawing.Graphics.PageUnit%2A> en <xref:System.Drawing.GraphicsUnit.World>, ya que no es una unidad física y producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="6892c-134">You cannot set the <xref:System.Drawing.Graphics.PageUnit%2A> property to <xref:System.Drawing.GraphicsUnit.World>, as this is not a physical unit and will cause an exception.</span></span>  
  
 <span data-ttu-id="6892c-135">En el ejemplo siguiente se dibuja una línea de (0,0) a (2, 1), donde el punto (2, 1) es 2 pulgadas a la derecha y 1 pulgada hacia abajo desde el punto (0,0):</span><span class="sxs-lookup"><span data-stu-id="6892c-135">The following example draws a line from (0, 0) to (2, 1), where the point (2, 1) is 2 inches to the right and 1 inch down from the point (0, 0):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
> <span data-ttu-id="6892c-136">Si no especifica un ancho de lápiz al crear el lápiz, el ejemplo anterior dibujará una línea de ancho de una pulgada.</span><span class="sxs-lookup"><span data-stu-id="6892c-136">If you don't specify a pen width when you construct your pen, the preceding example will draw a line that is one inch wide.</span></span> <span data-ttu-id="6892c-137">Puede especificar el ancho del lápiz en el segundo argumento del constructor <xref:System.Drawing.Pen>:</span><span class="sxs-lookup"><span data-stu-id="6892c-137">You can specify the pen width in the second argument to the <xref:System.Drawing.Pen> constructor:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 <span data-ttu-id="6892c-138">Si damos por hecho que el dispositivo de pantalla tiene 96 puntos por pulgada en la dirección horizontal y 96 puntos por pulgada en la dirección vertical, los extremos de la línea del ejemplo anterior tienen las coordenadas siguientes en los tres espacios de coordenadas:</span><span class="sxs-lookup"><span data-stu-id="6892c-138">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6892c-139">WWPN</span><span class="sxs-lookup"><span data-stu-id="6892c-139">World</span></span>|<span data-ttu-id="6892c-140">(0,0) a (2, 1)</span><span class="sxs-lookup"><span data-stu-id="6892c-140">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="6892c-141">Página</span><span class="sxs-lookup"><span data-stu-id="6892c-141">Page</span></span>|<span data-ttu-id="6892c-142">(0,0) a (2, 1)</span><span class="sxs-lookup"><span data-stu-id="6892c-142">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="6892c-143">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="6892c-143">Device</span></span>|<span data-ttu-id="6892c-144">(0,0) a (192, 96)</span><span class="sxs-lookup"><span data-stu-id="6892c-144">(0, 0) to (192, 96)</span></span>|  
  
 <span data-ttu-id="6892c-145">Tenga en cuenta que, dado que el origen del espacio de coordenadas del mundo está en la esquina superior izquierda del área cliente, las coordenadas de la página son las mismas que las coordenadas del mundo.</span><span class="sxs-lookup"><span data-stu-id="6892c-145">Note that because the origin of the world coordinate space is at the upper-left corner of the client area, the page coordinates are the same as the world coordinates.</span></span>  
  
 <span data-ttu-id="6892c-146">Puede combinar las transformaciones de página y el mundo para lograr una gran variedad de efectos.</span><span class="sxs-lookup"><span data-stu-id="6892c-146">You can combine the world and page transformations to achieve a variety of effects.</span></span> <span data-ttu-id="6892c-147">Por ejemplo, supongamos que desea usar pulgadas como unidad de medida y desea que el origen del sistema de coordenadas sea 2 pulgadas desde el borde izquierdo del área de cliente y 1/2 de la pulgada desde la parte superior del área cliente.</span><span class="sxs-lookup"><span data-stu-id="6892c-147">For example, suppose you want to use inches as the unit of measure and you want the origin of your coordinate system to be 2 inches from the left edge of the client area and 1/2 inch from the top of the client area.</span></span> <span data-ttu-id="6892c-148">En el ejemplo siguiente se establecen las transformaciones mundo y página de un objeto <xref:System.Drawing.Graphics> y, a continuación, se dibuja una línea de (0,0) a (2, 1):</span><span class="sxs-lookup"><span data-stu-id="6892c-148">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object and then draws a line from (0, 0) to (2, 1):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 <span data-ttu-id="6892c-149">En la ilustración siguiente se muestra la línea y el sistema de coordenadas.</span><span class="sxs-lookup"><span data-stu-id="6892c-149">The following illustration shows the line and coordinate system.</span></span>  
  
 <span data-ttu-id="6892c-150">![Sistema de coordenadas](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span><span class="sxs-lookup"><span data-stu-id="6892c-150">![Coordinate System](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span></span>  
  
 <span data-ttu-id="6892c-151">Si damos por hecho que el dispositivo de pantalla tiene 96 puntos por pulgada en la dirección horizontal y 96 puntos por pulgada en la dirección vertical, los extremos de la línea del ejemplo anterior tienen las coordenadas siguientes en los tres espacios de coordenadas:</span><span class="sxs-lookup"><span data-stu-id="6892c-151">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6892c-152">WWPN</span><span class="sxs-lookup"><span data-stu-id="6892c-152">World</span></span>|<span data-ttu-id="6892c-153">(0,0) a (2, 1)</span><span class="sxs-lookup"><span data-stu-id="6892c-153">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="6892c-154">Página</span><span class="sxs-lookup"><span data-stu-id="6892c-154">Page</span></span>|<span data-ttu-id="6892c-155">(2, 0,5) a (4, 1,5)</span><span class="sxs-lookup"><span data-stu-id="6892c-155">(2, 0.5) to (4, 1.5)</span></span>|  
|<span data-ttu-id="6892c-156">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="6892c-156">Device</span></span>|<span data-ttu-id="6892c-157">(192, 48) a (384, 144)</span><span class="sxs-lookup"><span data-stu-id="6892c-157">(192, 48) to (384, 144)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6892c-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="6892c-158">See also</span></span>

- [<span data-ttu-id="6892c-159">Sistemas de coordenadas y transformaciones</span><span class="sxs-lookup"><span data-stu-id="6892c-159">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="6892c-160">Representación matricial de transformaciones</span><span class="sxs-lookup"><span data-stu-id="6892c-160">Matrix Representation of Transformations</span></span>](matrix-representation-of-transformations.md)
