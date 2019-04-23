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
ms.openlocfilehash: 8fc92bf84def50bed54a054ae634a8a08c8835c2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212458"
---
# <a name="managing-the-state-of-a-graphics-object"></a><span data-ttu-id="326be-102">Administrar el estado de un objeto Graphics</span><span class="sxs-lookup"><span data-stu-id="326be-102">Managing the State of a Graphics Object</span></span>
<span data-ttu-id="326be-103">El <xref:System.Drawing.Graphics> clase es la esencia de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="326be-103">The <xref:System.Drawing.Graphics> class is at the heart of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="326be-104">Para dibujar algo, obtendrá un <xref:System.Drawing.Graphics> objeto, establecer sus propiedades y llamar a sus métodos <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>etc.).</span><span class="sxs-lookup"><span data-stu-id="326be-104">To draw anything, you obtain a <xref:System.Drawing.Graphics> object, set its properties, and call its methods <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, and the like).</span></span>  
  
 <span data-ttu-id="326be-105">El ejemplo siguiente se llama el <xref:System.Drawing.Graphics.DrawRectangle%2A> método de un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="326be-105">The following example calls the <xref:System.Drawing.Graphics.DrawRectangle%2A> method of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="326be-106">El primer argumento pasado a la <xref:System.Drawing.Graphics.DrawRectangle%2A> método es un <xref:System.Drawing.Pen> objeto.</span><span class="sxs-lookup"><span data-stu-id="326be-106">The first argument passed to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method is a <xref:System.Drawing.Pen> object.</span></span>  
  
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
  
## <a name="graphics-state"></a><span data-ttu-id="326be-107">Estado de gráficos</span><span class="sxs-lookup"><span data-stu-id="326be-107">Graphics State</span></span>  
 <span data-ttu-id="326be-108">Un <xref:System.Drawing.Graphics> objeto más de proporcionar métodos de dibujo, como <xref:System.Drawing.Graphics.DrawLine%2A> y <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span><span class="sxs-lookup"><span data-stu-id="326be-108">A <xref:System.Drawing.Graphics> object does more than provide drawing methods, such as <xref:System.Drawing.Graphics.DrawLine%2A> and <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span></span> <span data-ttu-id="326be-109">Un <xref:System.Drawing.Graphics> objeto también mantiene el estado de los gráficos, que puede dividirse en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="326be-109">A <xref:System.Drawing.Graphics> object also maintains graphics state, which can be divided into the following categories:</span></span>  
  
-   <span data-ttu-id="326be-110">Configuración de calidad</span><span class="sxs-lookup"><span data-stu-id="326be-110">Quality settings</span></span>  
  
-   <span data-ttu-id="326be-111">Transformaciones</span><span class="sxs-lookup"><span data-stu-id="326be-111">Transformations</span></span>  
  
-   <span data-ttu-id="326be-112">Región de recorte</span><span class="sxs-lookup"><span data-stu-id="326be-112">Clipping region</span></span>  
  
### <a name="quality-settings"></a><span data-ttu-id="326be-113">Configuración de calidad</span><span class="sxs-lookup"><span data-stu-id="326be-113">Quality Settings</span></span>  
 <span data-ttu-id="326be-114">Un <xref:System.Drawing.Graphics> objeto tiene varias propiedades que afectan a la calidad de los elementos que se dibujan.</span><span class="sxs-lookup"><span data-stu-id="326be-114">A <xref:System.Drawing.Graphics> object has several properties that influence the quality of the items that are drawn.</span></span> <span data-ttu-id="326be-115">Por ejemplo, puede establecer el <xref:System.Drawing.Graphics.TextRenderingHint%2A> propiedad para especificar el tipo de suavizado de contorno (si existe) aplicado al texto.</span><span class="sxs-lookup"><span data-stu-id="326be-115">For example, you can set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property to specify the type of antialiasing (if any) applied to text.</span></span> <span data-ttu-id="326be-116">Otras propiedades que influyen en la calidad son <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, y <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="326be-116">Other properties that influence quality are <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, and <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span></span>  
  
 <span data-ttu-id="326be-117">En el ejemplo siguiente se dibuja dos elipses, uno con el modo suavizado establecido en <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> y otro con el modo suavizado establecido en <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span><span class="sxs-lookup"><span data-stu-id="326be-117">The following example draws two ellipses, one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> and one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span></span>  
  
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
  
### <a name="transformations"></a><span data-ttu-id="326be-118">Transformaciones</span><span class="sxs-lookup"><span data-stu-id="326be-118">Transformations</span></span>  
 <span data-ttu-id="326be-119">Un <xref:System.Drawing.Graphics> objeto mantiene dos transformaciones (universal y página) que se aplican a todos los elementos dibujados por el que <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="326be-119">A <xref:System.Drawing.Graphics> object maintains two transformations (world and page) that are applied to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="326be-120">Las transformaciones afines se pueden almacenar en la transformación universal.</span><span class="sxs-lookup"><span data-stu-id="326be-120">Any affine transformation can be stored in the world transformation.</span></span> <span data-ttu-id="326be-121">Transformaciones afines incluyen escalar, girar, reflejar, sesgar y traducir.</span><span class="sxs-lookup"><span data-stu-id="326be-121">Affine transformations include scaling, rotating, reflecting, skewing, and translating.</span></span> <span data-ttu-id="326be-122">La transformación de página puede utilizarse para escalar y cambiar las unidades (por ejemplo, píxeles y pulgadas).</span><span class="sxs-lookup"><span data-stu-id="326be-122">The page transformation can be used for scaling and for changing units (for example, pixels to inches).</span></span> <span data-ttu-id="326be-123">Para obtener más información, consulte [sistemas de coordenadas y transformaciones](coordinate-systems-and-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="326be-123">For more information, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
 <span data-ttu-id="326be-124">El ejemplo siguiente establece las transformaciones universal y de página de un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="326be-124">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="326be-125">La transformación universal se establece en una rotación de 30 grados.</span><span class="sxs-lookup"><span data-stu-id="326be-125">The world transformation is set to a 30-degree rotation.</span></span> <span data-ttu-id="326be-126">La transformación de página se establece para que las coordenadas que se pasan a la segunda <xref:System.Drawing.Graphics.DrawEllipse%2A> se tratará como milímetros en lugar de píxeles.</span><span class="sxs-lookup"><span data-stu-id="326be-126">The page transformation is set so that the coordinates passed to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> will be treated as millimeters instead of pixels.</span></span> <span data-ttu-id="326be-127">El código hace dos llamadas idénticas a la <xref:System.Drawing.Graphics.DrawEllipse%2A> método.</span><span class="sxs-lookup"><span data-stu-id="326be-127">The code makes two identical calls to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="326be-128">La transformación universal se aplica a la primera <xref:System.Drawing.Graphics.DrawEllipse%2A> llamada y ambas transformaciones (universal y página) se aplican a la segunda <xref:System.Drawing.Graphics.DrawEllipse%2A> llamar.</span><span class="sxs-lookup"><span data-stu-id="326be-128">The world transformation is applied to the first <xref:System.Drawing.Graphics.DrawEllipse%2A> call, and both transformations (world and page) are applied to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> call.</span></span>  
  
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
  
 <span data-ttu-id="326be-129">La siguiente ilustración muestra las dos elipses.</span><span class="sxs-lookup"><span data-stu-id="326be-129">The following illustration shows the two ellipses.</span></span> <span data-ttu-id="326be-130">Tenga en cuenta que la rotación de 30 grados sobre el origen del sistema de coordenadas (esquina superior izquierda del área de cliente), pero no los centros de los puntos suspensivos.</span><span class="sxs-lookup"><span data-stu-id="326be-130">Note that the 30-degree rotation is about the origin of the coordinate system (upper-left corner of the client area), not about the centers of the ellipses.</span></span> <span data-ttu-id="326be-131">Tenga en cuenta también que el ancho del lápiz de 1 significa 1 píxel de la primera elipse y 1 milímetro para la segunda.</span><span class="sxs-lookup"><span data-stu-id="326be-131">Also note that the pen width of 1 means 1 pixel for the first ellipse and 1 millimeter for the second ellipse.</span></span>  
  
 ![Ilustración que muestra dos elipses: ancho de rotación y el lápiz.](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a><span data-ttu-id="326be-133">Región de recorte</span><span class="sxs-lookup"><span data-stu-id="326be-133">Clipping Region</span></span>  
 <span data-ttu-id="326be-134">Un <xref:System.Drawing.Graphics> objeto mantiene una región de recorte que se aplica a todos los elementos dibujados por el que <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="326be-134">A <xref:System.Drawing.Graphics> object maintains a clipping region that applies to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="326be-135">Puede establecer la región de recorte mediante una llamada a la <xref:System.Drawing.Graphics.SetClip%2A> método.</span><span class="sxs-lookup"><span data-stu-id="326be-135">You can set the clipping region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
 <span data-ttu-id="326be-136">El ejemplo siguiente crea una región en forma más mediante la unión de dos rectángulos.</span><span class="sxs-lookup"><span data-stu-id="326be-136">The following example creates a plus-shaped region by forming the union of two rectangles.</span></span> <span data-ttu-id="326be-137">Dicha región se designa como la región de recorte de un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="326be-137">That region is designated as the clipping region of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="326be-138">A continuación, el código dibuja dos líneas que están restringidas al interior de la región de recorte.</span><span class="sxs-lookup"><span data-stu-id="326be-138">Then the code draws two lines that are restricted to the interior of the clipping region.</span></span>  
  
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
  
 <span data-ttu-id="326be-139">La siguiente ilustración muestra las líneas recortadas:</span><span class="sxs-lookup"><span data-stu-id="326be-139">The following illustration shows the clipped lines:</span></span>  
  
 ![Diagrama que muestra la región de recorte limitada.](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a><span data-ttu-id="326be-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="326be-141">See also</span></span>

- [<span data-ttu-id="326be-142">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="326be-142">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="326be-143">Utilizar contenedores de gráficos anidados</span><span class="sxs-lookup"><span data-stu-id="326be-143">Using Nested Graphics Containers</span></span>](using-nested-graphics-containers.md)
