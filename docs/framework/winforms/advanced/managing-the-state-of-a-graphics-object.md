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
# <a name="managing-the-state-of-a-graphics-object"></a>Administrar el estado de un objeto Graphics
La <xref:System.Drawing.Graphics> clase está en el corazón de GDI+. Para dibujar cualquier cosa, se obtiene <xref:System.Drawing.Graphics> un objeto, <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Graphics.DrawImage%2A>se <xref:System.Drawing.Graphics.DrawString%2A>establecen sus propiedades y se llaman a sus métodos , , , y similares).  
  
 En el ejemplo <xref:System.Drawing.Graphics.DrawRectangle%2A> siguiente <xref:System.Drawing.Graphics> se llama al método de un objeto. El primer argumento <xref:System.Drawing.Graphics.DrawRectangle%2A> pasado al <xref:System.Drawing.Pen> método es un objeto.  
  
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
  
## <a name="graphics-state"></a>Estado de gráficos  
 Un <xref:System.Drawing.Graphics> objeto hace más que proporcionar <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Graphics.DrawRectangle%2A>métodos de dibujo, como y . Un <xref:System.Drawing.Graphics> objeto también mantiene el estado de gráficos, que se puede dividir en las siguientes categorías:  
  
- Ajustes de calidad  
  
- Transformaciones  
  
- Región de recorte  
  
### <a name="quality-settings"></a>Ajustes de calidad  
 Un <xref:System.Drawing.Graphics> objeto tiene varias propiedades que influyen en la calidad de los elementos que se dibujan. Por ejemplo, puede <xref:System.Drawing.Graphics.TextRenderingHint%2A> establecer la propiedad para especificar el tipo de antialiasing (si existe) aplicado al texto. Otras propiedades que <xref:System.Drawing.Graphics.SmoothingMode%2A>influyen <xref:System.Drawing.Graphics.CompositingQuality%2A>en <xref:System.Drawing.Graphics.InterpolationMode%2A>la calidad son , <xref:System.Drawing.Graphics.CompositingMode%2A>, , y .  
  
 En el ejemplo siguiente se dibujan dos elipses, una con el modo de suavizado establecido en <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> y otra con el modo de suavizado establecido en <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:  
  
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
  
### <a name="transformations"></a>Transformaciones  
 Un <xref:System.Drawing.Graphics> objeto mantiene dos transformaciones (mundo y página) que <xref:System.Drawing.Graphics> se aplican a todos los elementos dibujados por ese objeto. Cualquier transformación afín se puede almacenar en la transformación del mundo. Las transformaciones afines incluyen escalar, rotar, reflejar, sesgar y traducir. La transformación de página se puede utilizar para escalar y cambiar unidades (por ejemplo, píxeles a pulgadas). Para obtener más información, consulte [Sistemas de coordenadas y transformaciones](coordinate-systems-and-transformations.md).  
  
 En el ejemplo siguiente se establecen <xref:System.Drawing.Graphics> las transformaciones de mundo y página de un objeto. La transformación mundial se establece en una rotación de 30 grados. La transformación de página se establece de <xref:System.Drawing.Graphics.DrawEllipse%2A> modo que las coordenadas pasadas a la segunda se traten como milímetros en lugar de píxeles. El código realiza dos <xref:System.Drawing.Graphics.DrawEllipse%2A> llamadas idénticas al método. La transformación del mundo <xref:System.Drawing.Graphics.DrawEllipse%2A> se aplica a la primera llamada y ambas <xref:System.Drawing.Graphics.DrawEllipse%2A> transformaciones (mundo y página) se aplican a la segunda llamada.  
  
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
  
 En la ilustración siguiente se muestran las dos elipses. Tenga en cuenta que la rotación de 30 grados es sobre el origen del sistema de coordenadas (esquina superior izquierda del área de cliente), no sobre los centros de las elipses. Tenga en cuenta también que el ancho del lápiz de 1 significa 1 píxel para la primera elipse y 1 milímetro para la segunda elipse.  
  
 ![Ilustración que muestra dos elipses: rotación y anchura del lápiz.](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a>Región de Recorte  
 Un <xref:System.Drawing.Graphics> objeto mantiene una región de recorte que <xref:System.Drawing.Graphics> se aplica a todos los elementos dibujados por ese objeto. Puede establecer la región de <xref:System.Drawing.Graphics.SetClip%2A> recorte llamando al método.  
  
 En el ejemplo siguiente se crea una región con forma de signo más formando la unión de dos rectángulos. Esa región se designa <xref:System.Drawing.Graphics> como la región de recorte de un objeto. A continuación, el código dibuja dos líneas que están restringidas al interior de la región de recorte.  
  
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
  
 La siguiente ilustración muestra las líneas recortadas:  
  
 ![Diagrama que muestra la región de clip limitada.](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a>Consulte también

- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Utilizar contenedores de gráficos anidados](using-nested-graphics-containers.md)
