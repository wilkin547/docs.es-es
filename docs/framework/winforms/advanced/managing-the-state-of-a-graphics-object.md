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
ms.openlocfilehash: ce645133af35271fe1de969621907c53183d9a54
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505597"
---
# <a name="managing-the-state-of-a-graphics-object"></a>Administrar el estado de un objeto Graphics
La <xref:System.Drawing.Graphics> clase es la esencia de GDI +. Para dibujar algo, obtendrá un <xref:System.Drawing.Graphics> objeto, establecer sus propiedades y llamar a sus métodos <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>etc.).  
  
 El ejemplo siguiente se llama el <xref:System.Drawing.Graphics.DrawRectangle%2A> método de un <xref:System.Drawing.Graphics> objeto. El primer argumento pasado a la <xref:System.Drawing.Graphics.DrawRectangle%2A> método es un <xref:System.Drawing.Pen> objeto.  
  
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
 Un <xref:System.Drawing.Graphics> objeto más de proporcionar métodos de dibujo, como <xref:System.Drawing.Graphics.DrawLine%2A> y <xref:System.Drawing.Graphics.DrawRectangle%2A>. Un <xref:System.Drawing.Graphics> objeto también mantiene el estado de los gráficos, que puede dividirse en las siguientes categorías:  
  
- Configuración de calidad  
  
- Transformaciones  
  
- Región de recorte  
  
### <a name="quality-settings"></a>Configuración de calidad  
 Un <xref:System.Drawing.Graphics> objeto tiene varias propiedades que afectan a la calidad de los elementos que se dibujan. Por ejemplo, puede establecer el <xref:System.Drawing.Graphics.TextRenderingHint%2A> propiedad para especificar el tipo de suavizado de contorno (si existe) aplicado al texto. Otras propiedades que influyen en la calidad son <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, y <xref:System.Drawing.Graphics.InterpolationMode%2A>.  
  
 En el ejemplo siguiente se dibuja dos elipses, uno con el modo suavizado establecido en <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> y otro con el modo suavizado establecido en <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:  
  
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
 Un <xref:System.Drawing.Graphics> objeto mantiene dos transformaciones (universal y página) que se aplican a todos los elementos dibujados por el que <xref:System.Drawing.Graphics> objeto. Las transformaciones afines se pueden almacenar en la transformación universal. Transformaciones afines incluyen escalar, girar, reflejar, sesgar y traducir. La transformación de página puede utilizarse para escalar y cambiar las unidades (por ejemplo, píxeles y pulgadas). Para obtener más información, consulte [sistemas de coordenadas y transformaciones](coordinate-systems-and-transformations.md).  
  
 El ejemplo siguiente establece las transformaciones universal y de página de un <xref:System.Drawing.Graphics> objeto. La transformación universal se establece en una rotación de 30 grados. La transformación de página se establece para que las coordenadas que se pasan a la segunda <xref:System.Drawing.Graphics.DrawEllipse%2A> se tratará como milímetros en lugar de píxeles. El código hace dos llamadas idénticas a la <xref:System.Drawing.Graphics.DrawEllipse%2A> método. La transformación universal se aplica a la primera <xref:System.Drawing.Graphics.DrawEllipse%2A> llamada y ambas transformaciones (universal y página) se aplican a la segunda <xref:System.Drawing.Graphics.DrawEllipse%2A> llamar.  
  
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
  
 La siguiente ilustración muestra las dos elipses. Tenga en cuenta que la rotación de 30 grados sobre el origen del sistema de coordenadas (esquina superior izquierda del área de cliente), pero no los centros de los puntos suspensivos. Tenga en cuenta también que el ancho del lápiz de 1 significa 1 píxel de la primera elipse y 1 milímetro para la segunda.  
  
 ![Ilustración que muestra dos elipses: ancho de rotación y el lápiz.](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a>Región de recorte  
 Un <xref:System.Drawing.Graphics> objeto mantiene una región de recorte que se aplica a todos los elementos dibujados por el que <xref:System.Drawing.Graphics> objeto. Puede establecer la región de recorte mediante una llamada a la <xref:System.Drawing.Graphics.SetClip%2A> método.  
  
 El ejemplo siguiente crea una región en forma más mediante la unión de dos rectángulos. Dicha región se designa como la región de recorte de un <xref:System.Drawing.Graphics> objeto. A continuación, el código dibuja dos líneas que están restringidas al interior de la región de recorte.  
  
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
  
 ![Diagrama que muestra la región de recorte limitada.](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a>Vea también

- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Utilizar contenedores de gráficos anidados](using-nested-graphics-containers.md)
