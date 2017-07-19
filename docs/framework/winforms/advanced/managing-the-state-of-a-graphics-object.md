---
title: "Administrar el estado de un objeto Graphics | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "gráficos, recortar"
  - "gráficos, administrar estado"
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Administrar el estado de un objeto Graphics
La clase <xref:System.Drawing.Graphics> es la esencia de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  Para dibujar algo, hay que obtener un objeto <xref:System.Drawing.Graphics>, establecer sus propiedades y, después, llamar a sus métodos <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A> y similares.  
  
 En el siguiente ejemplo se llama al método <xref:System.Drawing.Graphics.DrawRectangle%2A> de un objeto <xref:System.Drawing.Graphics>.  El primer argumento pasado al método <xref:System.Drawing.Graphics.DrawRectangle%2A> es un objeto <xref:System.Drawing.Pen>.  
  
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
  
## Estado de los gráficos  
 Un objeto <xref:System.Drawing.Graphics> hace algo más que proporcionar métodos de dibujo, como <xref:System.Drawing.Graphics.DrawLine%2A> y <xref:System.Drawing.Graphics.DrawRectangle%2A>.  Un objeto <xref:System.Drawing.Graphics> también mantienen el estado de los gráficos, que se puede dividir en las siguientes categorías:  
  
-   Valores de calidad  
  
-   Transformaciones  
  
-   Región de recorte  
  
### Valores de calidad  
 Los objetos <xref:System.Drawing.Graphics> poseen varias propiedades que afectan a la calidad de los elementos que se dibujan.  Por ejemplo, se puede establecer la propiedad <xref:System.Drawing.Graphics.TextRenderingHint%2A> para que especifique el tipo de suavizado de contorno \(de haberlo\) aplicado al texto.  Otras propiedades que influyen en la calidad son <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A> y <xref:System.Drawing.Graphics.InterpolationMode%2A>.  
  
 En el siguiente ejemplo se dibujan dos elipses, una con el modo de suavizado establecido en <xref:System.Drawing.Drawing2D.SmoothingMode> y otra con el modo de suavizado establecido en <xref:System.Drawing.Drawing2D.SmoothingMode>:  
  
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
  
### Transformaciones  
 Un objeto <xref:System.Drawing.Graphics> mantiene dos transformaciones \(universal y de página\) que se aplican a todos los elementos dibujados por ese objeto <xref:System.Drawing.Graphics> en cuestión.  Las transformaciones afines se pueden almacenar en la transformación universal.  Las transformaciones afines incluyen el ajuste de escala, rotación, reflejo, inclinación y conversión.  La transformación de página se puede utilizar para ajustar la escala y para modificar unidades \(por ejemplo, de píxeles a pulgadas\).  Para obtener más información, vea [Sistemas de coordenadas y transformaciones](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).  
  
 En el siguiente ejemplo se establecen las transformaciones universal y de página de un objeto <xref:System.Drawing.Graphics>.  La transformación universal se establece en una rotación de 30 grados.  La transformación de página se establece de modo que las coordenadas pasadas al segundo método <xref:System.Drawing.Graphics.DrawEllipse%2A> se traten como milímetros en lugar de píxeles.  El código hace dos llamadas idénticas al método <xref:System.Drawing.Graphics.DrawEllipse%2A>.  La transformación universal se aplica a la primera llamada a <xref:System.Drawing.Graphics.DrawEllipse%2A>, mientras que se aplican las dos transformaciones \(universal y de página\) a la segunda llamada a <xref:System.Drawing.Graphics.DrawEllipse%2A>.  
  
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
  
 En la siguiente ilustración se muestran las dos elipses.  Observe que la rotación de 30 grados se sitúa alrededor del origen del sistema de coordenadas \(esquina superior izquierda del área del cliente\), y no en los centros de las elipses.  Observe asimismo que el ancho del lápiz 1 significa 1 píxel para la primera elipse y 1 milímetro para la segunda.  
  
 ![Óvalos](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")  
  
### Región de recorte  
 Un objeto <xref:System.Drawing.Graphics> mantiene una región de recorte que se aplica a todos los elementos dibujados por ese objeto <xref:System.Drawing.Graphics>.  Para establecer la región de recorte hay que llamar al método <xref:System.Drawing.Graphics.SetClip%2A>.  
  
 En el siguiente ejemplo se crea una región con forma de signo más mediante la unión de dos rectángulos.  Dicha región se designa como la región de recorte de un objeto <xref:System.Drawing.Graphics>.  Luego, el código dibuja dos líneas que se limitan al interior de la región de recorte.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](../../../../amples/snippets/visualbasic/VS_Snippets_Wpf/ToolBarOrient_snip/visualbasic/toolbargraphics/new.bmp Rectangle(50, 0, 50, 150))  
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
  
 En la siguiente ilustración se muestran las líneas recortadas.  
  
 ![Región de recorte limitada](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")  
  
## Vea también  
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Utilizar contenedores de gráficos anidados](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)