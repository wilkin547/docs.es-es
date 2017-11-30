---
title: Administrar el estado de un objeto Graphics
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
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 438243d16d8031d99e27993cadb44fd58bbec0b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="managing-the-state-of-a-graphics-object"></a><span data-ttu-id="5d9c9-102">Administrar el estado de un objeto Graphics</span><span class="sxs-lookup"><span data-stu-id="5d9c9-102">Managing the State of a Graphics Object</span></span>
<span data-ttu-id="5d9c9-103">El <xref:System.Drawing.Graphics> clase es la esencia de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d9c9-103">The <xref:System.Drawing.Graphics> class is at the heart of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="5d9c9-104">Para dibujar cualquier cosa, obtendrá un <xref:System.Drawing.Graphics> objeto, establecer sus propiedades y llamar a sus métodos <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>etc.).</span><span class="sxs-lookup"><span data-stu-id="5d9c9-104">To draw anything, you obtain a <xref:System.Drawing.Graphics> object, set its properties, and call its methods <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, and the like).</span></span>  
  
 <span data-ttu-id="5d9c9-105">El ejemplo siguiente se llama el <xref:System.Drawing.Graphics.DrawRectangle%2A> método de una <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-105">The following example calls the <xref:System.Drawing.Graphics.DrawRectangle%2A> method of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="5d9c9-106">El primer argumento pasado a la <xref:System.Drawing.Graphics.DrawRectangle%2A> método es un <xref:System.Drawing.Pen> objeto.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-106">The first argument passed to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method is a <xref:System.Drawing.Pen> object.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue) ' Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  // Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100);  
```  
  
## <a name="graphics-state"></a><span data-ttu-id="5d9c9-107">Estado de los gráficos</span><span class="sxs-lookup"><span data-stu-id="5d9c9-107">Graphics State</span></span>  
 <span data-ttu-id="5d9c9-108">A <xref:System.Drawing.Graphics> objeto más de proporcionar métodos de dibujo, como <xref:System.Drawing.Graphics.DrawLine%2A> y <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-108">A <xref:System.Drawing.Graphics> object does more than provide drawing methods, such as <xref:System.Drawing.Graphics.DrawLine%2A> and <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span></span> <span data-ttu-id="5d9c9-109">Un <xref:System.Drawing.Graphics> objeto también mantiene el estado de los gráficos, que puede dividirse en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="5d9c9-109">A <xref:System.Drawing.Graphics> object also maintains graphics state, which can be divided into the following categories:</span></span>  
  
-   <span data-ttu-id="5d9c9-110">Configuración de calidad</span><span class="sxs-lookup"><span data-stu-id="5d9c9-110">Quality settings</span></span>  
  
-   <span data-ttu-id="5d9c9-111">Transformaciones</span><span class="sxs-lookup"><span data-stu-id="5d9c9-111">Transformations</span></span>  
  
-   <span data-ttu-id="5d9c9-112">Región de recorte</span><span class="sxs-lookup"><span data-stu-id="5d9c9-112">Clipping region</span></span>  
  
### <a name="quality-settings"></a><span data-ttu-id="5d9c9-113">Configuración de calidad</span><span class="sxs-lookup"><span data-stu-id="5d9c9-113">Quality Settings</span></span>  
 <span data-ttu-id="5d9c9-114">Un <xref:System.Drawing.Graphics> objeto tiene varias propiedades que afectan a la calidad de los elementos que se dibujan.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-114">A <xref:System.Drawing.Graphics> object has several properties that influence the quality of the items that are drawn.</span></span> <span data-ttu-id="5d9c9-115">Por ejemplo, puede establecer el <xref:System.Drawing.Graphics.TextRenderingHint%2A> propiedad para especificar el tipo de suavizado de contorno (si existe) que se aplica al texto.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-115">For example, you can set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property to specify the type of antialiasing (if any) applied to text.</span></span> <span data-ttu-id="5d9c9-116">Otras propiedades que influyen en la calidad son <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, y <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-116">Other properties that influence quality are <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, and <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span></span>  
  
 <span data-ttu-id="5d9c9-117">En el ejemplo siguiente se dibuja dos elipses, una con el modo de suavizado establecido en <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> y otra con el modo de suavizado establecido en <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span><span class="sxs-lookup"><span data-stu-id="5d9c9-117">The following example draws two ellipses, one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> and one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue)  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias  
graphics.DrawEllipse(pen, 0, 0, 200, 100)  
graphics.SmoothingMode = SmoothingMode.HighSpeed  
graphics.DrawEllipse(pen, 0, 150, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias;  
graphics.DrawEllipse(pen, 0, 0, 200, 100);  
graphics.SmoothingMode = SmoothingMode.HighSpeed;  
graphics.DrawEllipse(pen, 0, 150, 200, 100);  
```  
  
### <a name="transformations"></a><span data-ttu-id="5d9c9-118">Transformaciones</span><span class="sxs-lookup"><span data-stu-id="5d9c9-118">Transformations</span></span>  
 <span data-ttu-id="5d9c9-119">A <xref:System.Drawing.Graphics> objeto mantiene dos transformaciones (universal y página) que se aplican a todos los elementos dibujados por esa <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-119">A <xref:System.Drawing.Graphics> object maintains two transformations (world and page) that are applied to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="5d9c9-120">Las transformaciones afines se pueden almacenar en la transformación universal.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-120">Any affine transformation can be stored in the world transformation.</span></span> <span data-ttu-id="5d9c9-121">Transformaciones afines incluyen escalar, girar, reflejar, sesgar y traducir.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-121">Affine transformations include scaling, rotating, reflecting, skewing, and translating.</span></span> <span data-ttu-id="5d9c9-122">La transformación de página se puede utilizar para ajustar la escala y para modificar unidades (por ejemplo, píxeles a pulgadas).</span><span class="sxs-lookup"><span data-stu-id="5d9c9-122">The page transformation can be used for scaling and for changing units (for example, pixels to inches).</span></span> <span data-ttu-id="5d9c9-123">Para obtener más información, consulte [sistemas de coordenadas y transformaciones](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="5d9c9-123">For more information, see [Coordinate Systems and Transformations](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).</span></span>  
  
 <span data-ttu-id="5d9c9-124">En el ejemplo siguiente se establece las transformaciones universal y de página de un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-124">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="5d9c9-125">La transformación universal se establece en una rotación de 30 grados.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-125">The world transformation is set to a 30-degree rotation.</span></span> <span data-ttu-id="5d9c9-126">La transformación de página se establece para que las coordenadas se pasan a la segunda <xref:System.Drawing.Graphics.DrawEllipse%2A> se tratará como milímetros en lugar de píxeles.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-126">The page transformation is set so that the coordinates passed to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> will be treated as millimeters instead of pixels.</span></span> <span data-ttu-id="5d9c9-127">El código hace dos llamadas idénticas a las <xref:System.Drawing.Graphics.DrawEllipse%2A> método.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-127">The code makes two identical calls to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="5d9c9-128">La transformación universal se aplica a la primera <xref:System.Drawing.Graphics.DrawEllipse%2A> llamada y ambas transformaciones (universal y página) se aplican a la segunda <xref:System.Drawing.Graphics.DrawEllipse%2A> llamar.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-128">The world transformation is applied to the first <xref:System.Drawing.Graphics.DrawEllipse%2A> call, and both transformations (world and page) are applied to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> call.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Red)  
  
graphics.ResetTransform()  
graphics.RotateTransform(30) ' world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
graphics.PageUnit = GraphicsUnit.Millimeter ' page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Red);   
  
graphics.ResetTransform();  
graphics.RotateTransform(30);                    // world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
graphics.PageUnit = GraphicsUnit.Millimeter;     // page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
```  
  
 <span data-ttu-id="5d9c9-129">En la siguiente ilustración se muestra las dos elipses.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-129">The following illustration shows the two ellipses.</span></span> <span data-ttu-id="5d9c9-130">Tenga en cuenta que la rotación de 30 grados alrededor del origen del sistema de coordenadas (esquina superior izquierda del área de cliente), pero no los centros de los puntos suspensivos.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-130">Note that the 30-degree rotation is about the origin of the coordinate system (upper-left corner of the client area), not about the centers of the ellipses.</span></span> <span data-ttu-id="5d9c9-131">Tenga en cuenta también que el ancho del lápiz 1 significa 1 píxel para la primera elipse y 1 milímetro para la segunda elipse.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-131">Also note that the pen width of 1 means 1 pixel for the first ellipse and 1 millimeter for the second ellipse.</span></span>  
  
 <span data-ttu-id="5d9c9-132">![Óvalos](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")</span><span class="sxs-lookup"><span data-stu-id="5d9c9-132">![Ovals](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")</span></span>  
  
### <a name="clipping-region"></a><span data-ttu-id="5d9c9-133">Región de recorte</span><span class="sxs-lookup"><span data-stu-id="5d9c9-133">Clipping Region</span></span>  
 <span data-ttu-id="5d9c9-134">A <xref:System.Drawing.Graphics> objeto mantiene una región de recorte que se aplica a todos los elementos dibujados por esa <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-134">A <xref:System.Drawing.Graphics> object maintains a clipping region that applies to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="5d9c9-135">Puede establecer la región de recorte mediante una llamada a la <xref:System.Drawing.Graphics.SetClip%2A> método.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-135">You can set the clipping region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
 <span data-ttu-id="5d9c9-136">En el ejemplo siguiente se crea una región con forma de signo más mediante la unión de dos rectángulos.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-136">The following example creates a plus-shaped region by forming the union of two rectangles.</span></span> <span data-ttu-id="5d9c9-137">Dicha región se designa como la región de recorte de un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-137">That region is designated as the clipping region of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="5d9c9-138">A continuación, el código dibuja dos líneas que están restringidas al interior de la región de recorte.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-138">Then the code draws two lines that are restricted to the interior of the clipping region.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](New Rectangle(50, 0, 50, 150))  
[region].Union(New Rectangle(0, 50, 150, 50))  
graphics.FillRegion(brush, [region])  
  
' Set the clipping region.  
graphics.SetClip([region], CombineMode.Replace)  
  
' Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160)  
graphics.DrawLine(pen, 40, 20, 190, 150)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
  
// Opaque red, width 5  
Pen pen = new Pen(Color.Red, 5);    
  
// Opaque aqua  
SolidBrush brush = new SolidBrush(Color.FromArgb(255, 180, 255, 255));    
  
// Create a plus-shaped region by forming the union of two rectangles.  
Region region = new Region(new Rectangle(50, 0, 50, 150));  
region.Union(new Rectangle(0, 50, 150, 50));  
graphics.FillRegion(brush, region);  
  
// Set the clipping region.  
graphics.SetClip(region, CombineMode.Replace);  
  
// Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160);  
graphics.DrawLine(pen, 40, 20, 190, 150);  
```  
  
 <span data-ttu-id="5d9c9-139">En la siguiente ilustración se muestra las líneas recortadas.</span><span class="sxs-lookup"><span data-stu-id="5d9c9-139">The following illustration shows the clipped lines.</span></span>  
  
 <span data-ttu-id="5d9c9-140">![Limita la región de recorte](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")</span><span class="sxs-lookup"><span data-stu-id="5d9c9-140">![Limited Clip Region](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d9c9-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d9c9-141">See Also</span></span>  
 [<span data-ttu-id="5d9c9-142">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5d9c9-142">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="5d9c9-143">Utilizar contenedores de gráficos anidados</span><span class="sxs-lookup"><span data-stu-id="5d9c9-143">Using Nested Graphics Containers</span></span>](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)
