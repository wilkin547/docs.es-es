---
title: Administrar el estado de un objeto Graphics
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
ms.openlocfilehash: d1e7e6eac775ca779fb68605adcc9bc2b9915e49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182454"
---
# <a name="managing-the-state-of-a-graphics-object"></a><span data-ttu-id="5694d-102">Administrar el estado de un objeto Graphics</span><span class="sxs-lookup"><span data-stu-id="5694d-102">Managing the State of a Graphics Object</span></span>
<span data-ttu-id="5694d-103">La <xref:System.Drawing.Graphics> clase está en el corazón de GDI+.</span><span class="sxs-lookup"><span data-stu-id="5694d-103">The <xref:System.Drawing.Graphics> class is at the heart of GDI+.</span></span> <span data-ttu-id="5694d-104">Para dibujar cualquier cosa, se obtiene <xref:System.Drawing.Graphics> un objeto, <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Graphics.DrawImage%2A>se <xref:System.Drawing.Graphics.DrawString%2A>establecen sus propiedades y se llaman a sus métodos , , , y similares).</span><span class="sxs-lookup"><span data-stu-id="5694d-104">To draw anything, you obtain a <xref:System.Drawing.Graphics> object, set its properties, and call its methods <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, and the like).</span></span>  
  
 <span data-ttu-id="5694d-105">En el ejemplo <xref:System.Drawing.Graphics.DrawRectangle%2A> siguiente <xref:System.Drawing.Graphics> se llama al método de un objeto.</span><span class="sxs-lookup"><span data-stu-id="5694d-105">The following example calls the <xref:System.Drawing.Graphics.DrawRectangle%2A> method of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="5694d-106">El primer argumento <xref:System.Drawing.Graphics.DrawRectangle%2A> pasado al <xref:System.Drawing.Pen> método es un objeto.</span><span class="sxs-lookup"><span data-stu-id="5694d-106">The first argument passed to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method is a <xref:System.Drawing.Pen> object.</span></span>  
  
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
  
## <a name="graphics-state"></a><span data-ttu-id="5694d-107">Estado de gráficos</span><span class="sxs-lookup"><span data-stu-id="5694d-107">Graphics State</span></span>  
 <span data-ttu-id="5694d-108">Un <xref:System.Drawing.Graphics> objeto hace más que proporcionar <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Graphics.DrawRectangle%2A>métodos de dibujo, como y .</span><span class="sxs-lookup"><span data-stu-id="5694d-108">A <xref:System.Drawing.Graphics> object does more than provide drawing methods, such as <xref:System.Drawing.Graphics.DrawLine%2A> and <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span></span> <span data-ttu-id="5694d-109">Un <xref:System.Drawing.Graphics> objeto también mantiene el estado de gráficos, que se puede dividir en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="5694d-109">A <xref:System.Drawing.Graphics> object also maintains graphics state, which can be divided into the following categories:</span></span>  
  
- <span data-ttu-id="5694d-110">Ajustes de calidad</span><span class="sxs-lookup"><span data-stu-id="5694d-110">Quality settings</span></span>  
  
- <span data-ttu-id="5694d-111">Transformaciones</span><span class="sxs-lookup"><span data-stu-id="5694d-111">Transformations</span></span>  
  
- <span data-ttu-id="5694d-112">Región de recorte</span><span class="sxs-lookup"><span data-stu-id="5694d-112">Clipping region</span></span>  
  
### <a name="quality-settings"></a><span data-ttu-id="5694d-113">Ajustes de calidad</span><span class="sxs-lookup"><span data-stu-id="5694d-113">Quality Settings</span></span>  
 <span data-ttu-id="5694d-114">Un <xref:System.Drawing.Graphics> objeto tiene varias propiedades que influyen en la calidad de los elementos que se dibujan.</span><span class="sxs-lookup"><span data-stu-id="5694d-114">A <xref:System.Drawing.Graphics> object has several properties that influence the quality of the items that are drawn.</span></span> <span data-ttu-id="5694d-115">Por ejemplo, puede <xref:System.Drawing.Graphics.TextRenderingHint%2A> establecer la propiedad para especificar el tipo de antialiasing (si existe) aplicado al texto.</span><span class="sxs-lookup"><span data-stu-id="5694d-115">For example, you can set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property to specify the type of antialiasing (if any) applied to text.</span></span> <span data-ttu-id="5694d-116">Otras propiedades que <xref:System.Drawing.Graphics.SmoothingMode%2A>influyen <xref:System.Drawing.Graphics.CompositingQuality%2A>en <xref:System.Drawing.Graphics.InterpolationMode%2A>la calidad son , <xref:System.Drawing.Graphics.CompositingMode%2A>, , y .</span><span class="sxs-lookup"><span data-stu-id="5694d-116">Other properties that influence quality are <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, and <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span></span>  
  
 <span data-ttu-id="5694d-117">En el ejemplo siguiente se dibujan dos elipses, una con el modo de suavizado establecido en <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> y otra con el modo de suavizado establecido en <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span><span class="sxs-lookup"><span data-stu-id="5694d-117">The following example draws two ellipses, one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> and one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span></span>  
  
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
  
### <a name="transformations"></a><span data-ttu-id="5694d-118">Transformaciones</span><span class="sxs-lookup"><span data-stu-id="5694d-118">Transformations</span></span>  
 <span data-ttu-id="5694d-119">Un <xref:System.Drawing.Graphics> objeto mantiene dos transformaciones (mundo y página) que <xref:System.Drawing.Graphics> se aplican a todos los elementos dibujados por ese objeto.</span><span class="sxs-lookup"><span data-stu-id="5694d-119">A <xref:System.Drawing.Graphics> object maintains two transformations (world and page) that are applied to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="5694d-120">Cualquier transformación afín se puede almacenar en la transformación del mundo.</span><span class="sxs-lookup"><span data-stu-id="5694d-120">Any affine transformation can be stored in the world transformation.</span></span> <span data-ttu-id="5694d-121">Las transformaciones afines incluyen escalar, rotar, reflejar, sesgar y traducir.</span><span class="sxs-lookup"><span data-stu-id="5694d-121">Affine transformations include scaling, rotating, reflecting, skewing, and translating.</span></span> <span data-ttu-id="5694d-122">La transformación de página se puede utilizar para escalar y cambiar unidades (por ejemplo, píxeles a pulgadas).</span><span class="sxs-lookup"><span data-stu-id="5694d-122">The page transformation can be used for scaling and for changing units (for example, pixels to inches).</span></span> <span data-ttu-id="5694d-123">Para obtener más información, consulte [Sistemas de coordenadas y transformaciones](coordinate-systems-and-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="5694d-123">For more information, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
 <span data-ttu-id="5694d-124">En el ejemplo siguiente se establecen <xref:System.Drawing.Graphics> las transformaciones de mundo y página de un objeto.</span><span class="sxs-lookup"><span data-stu-id="5694d-124">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="5694d-125">La transformación mundial se establece en una rotación de 30 grados.</span><span class="sxs-lookup"><span data-stu-id="5694d-125">The world transformation is set to a 30-degree rotation.</span></span> <span data-ttu-id="5694d-126">La transformación de página se establece de <xref:System.Drawing.Graphics.DrawEllipse%2A> modo que las coordenadas pasadas a la segunda se traten como milímetros en lugar de píxeles.</span><span class="sxs-lookup"><span data-stu-id="5694d-126">The page transformation is set so that the coordinates passed to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> will be treated as millimeters instead of pixels.</span></span> <span data-ttu-id="5694d-127">El código realiza dos <xref:System.Drawing.Graphics.DrawEllipse%2A> llamadas idénticas al método.</span><span class="sxs-lookup"><span data-stu-id="5694d-127">The code makes two identical calls to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="5694d-128">La transformación del mundo <xref:System.Drawing.Graphics.DrawEllipse%2A> se aplica a la primera llamada y ambas <xref:System.Drawing.Graphics.DrawEllipse%2A> transformaciones (mundo y página) se aplican a la segunda llamada.</span><span class="sxs-lookup"><span data-stu-id="5694d-128">The world transformation is applied to the first <xref:System.Drawing.Graphics.DrawEllipse%2A> call, and both transformations (world and page) are applied to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> call.</span></span>  
  
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
  
 <span data-ttu-id="5694d-129">En la ilustración siguiente se muestran las dos elipses.</span><span class="sxs-lookup"><span data-stu-id="5694d-129">The following illustration shows the two ellipses.</span></span> <span data-ttu-id="5694d-130">Tenga en cuenta que la rotación de 30 grados es sobre el origen del sistema de coordenadas (esquina superior izquierda del área de cliente), no sobre los centros de las elipses.</span><span class="sxs-lookup"><span data-stu-id="5694d-130">Note that the 30-degree rotation is about the origin of the coordinate system (upper-left corner of the client area), not about the centers of the ellipses.</span></span> <span data-ttu-id="5694d-131">Tenga en cuenta también que el ancho del lápiz de 1 significa 1 píxel para la primera elipse y 1 milímetro para la segunda elipse.</span><span class="sxs-lookup"><span data-stu-id="5694d-131">Also note that the pen width of 1 means 1 pixel for the first ellipse and 1 millimeter for the second ellipse.</span></span>  
  
 ![Ilustración que muestra dos elipses: rotación y anchura del lápiz.](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a><span data-ttu-id="5694d-133">Región de Recorte</span><span class="sxs-lookup"><span data-stu-id="5694d-133">Clipping Region</span></span>  
 <span data-ttu-id="5694d-134">Un <xref:System.Drawing.Graphics> objeto mantiene una región de recorte que <xref:System.Drawing.Graphics> se aplica a todos los elementos dibujados por ese objeto.</span><span class="sxs-lookup"><span data-stu-id="5694d-134">A <xref:System.Drawing.Graphics> object maintains a clipping region that applies to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="5694d-135">Puede establecer la región de <xref:System.Drawing.Graphics.SetClip%2A> recorte llamando al método.</span><span class="sxs-lookup"><span data-stu-id="5694d-135">You can set the clipping region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
 <span data-ttu-id="5694d-136">En el ejemplo siguiente se crea una región con forma de signo más formando la unión de dos rectángulos.</span><span class="sxs-lookup"><span data-stu-id="5694d-136">The following example creates a plus-shaped region by forming the union of two rectangles.</span></span> <span data-ttu-id="5694d-137">Esa región se designa <xref:System.Drawing.Graphics> como la región de recorte de un objeto.</span><span class="sxs-lookup"><span data-stu-id="5694d-137">That region is designated as the clipping region of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="5694d-138">A continuación, el código dibuja dos líneas que están restringidas al interior de la región de recorte.</span><span class="sxs-lookup"><span data-stu-id="5694d-138">Then the code draws two lines that are restricted to the interior of the clipping region.</span></span>  
  
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
  
 <span data-ttu-id="5694d-139">La siguiente ilustración muestra las líneas recortadas:</span><span class="sxs-lookup"><span data-stu-id="5694d-139">The following illustration shows the clipped lines:</span></span>  
  
 ![Diagrama que muestra la región de clip limitada.](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a><span data-ttu-id="5694d-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5694d-141">See also</span></span>

- [<span data-ttu-id="5694d-142">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5694d-142">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="5694d-143">Utilizar contenedores de gráficos anidados</span><span class="sxs-lookup"><span data-stu-id="5694d-143">Using Nested Graphics Containers</span></span>](using-nested-graphics-containers.md)
