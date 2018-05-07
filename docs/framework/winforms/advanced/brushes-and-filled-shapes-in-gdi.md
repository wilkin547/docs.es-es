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
ms.openlocfilehash: 9475518a5f0422e0eac1ec521088071bb4d1c885
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="brushes-and-filled-shapes-in-gdi"></a>Pinceles y formas rellenas en GDI+
Una forma cerrada, como un rectángulo o una elipse, consta de un esquema y un interior. El contorno se dibuja con un lápiz y el interior se rellena con un pincel. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona varias clases de pincel para rellenar el interior de las formas cerradas: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, y <xref:System.Drawing.Drawing2D.PathGradientBrush>. Todas estas clases heredan de la <xref:System.Drawing.Brush> clase. La ilustración siguiente muestra un rectángulo relleno con un pincel sólido y una elipse rellena con un pincel de trama.  
  
 ![Formas con relleno](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.gif "Aboutgdip02_art17")  
  
## <a name="solid-brushes"></a>Pinceles sólidos  
 Para rellenar una forma cerrada, necesita una instancia de la <xref:System.Drawing.Graphics> clase y un <xref:System.Drawing.Brush>. La instancia de la <xref:System.Drawing.Graphics> clase proporciona métodos, como <xref:System.Drawing.Graphics.FillRectangle%2A> y <xref:System.Drawing.Graphics.FillEllipse%2A>y <xref:System.Drawing.Brush> almacena los atributos de relleno, como el color y la trama. El <xref:System.Drawing.Brush> se pasa como uno de los argumentos para el método de relleno. En el ejemplo de código siguiente se muestra cómo rellenar una elipse con un color rojo sólido.  
  
 [!code-csharp[LinesCurvesAndShapes#121](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  En el ejemplo anterior, el pincel es de tipo <xref:System.Drawing.SolidBrush>, que hereda de <xref:System.Drawing.Brush>.  
  
## <a name="hatch-brushes"></a>Pinceles de trama  
 Cuando se rellena una forma con un pincel de trama, especifica un color de primer plano, un color de fondo y un estilo de trama. El color de primer plano es el color de la trama.  
  
 [!code-csharp[LinesCurvesAndShapes#122](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona más de 50 estilos de trama; los tres estilos que se muestra en la siguiente ilustración son <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, y <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.  
  
 ![Formas con relleno](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.gif "Aboutgdip02_art18")  
  
## <a name="texture-brushes"></a>Pinceles de textura  
 Con un pincel de textura, puede rellenar una forma con un patrón almacenado en un mapa de bits. Por ejemplo, suponga que en la siguiente imagen se almacena en un archivo de disco denominado `MyTexture.bmp`.  
  
 ![Rellenar formas](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.gif "Aboutgdip02_Art19")  
  
 En el ejemplo de código siguiente se muestra cómo rellenar una elipse repitiendo la imagen almacenada en `MyTexture.bmp`.  
  
 [!code-csharp[LinesCurvesAndShapes#123](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 En la siguiente ilustración se muestra la elipse rellena.  
  
 ![Rellenar formas](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.gif "AboutGdip02_Art20")  
  
## <a name="gradient-brushes"></a>Pinceles degradados  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona dos tipos de pinceles degradados: lineal y ruta de acceso. Puede utilizar un pincel de degradado lineal para rellenar una forma con colores que cambian gradualmente a medida que se desplaza a través de la forma horizontal, vertical o diagonalmente. En el ejemplo de código siguiente se muestra cómo rellenar una elipse con un pincel degradado horizontal que cambia de azul a verde conforme mueve desde el borde izquierdo de la elipse al borde derecho.  
  
 [!code-csharp[LinesCurvesAndShapes#124](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 En la siguiente ilustración se muestra la elipse rellena.  
  
 ![Rellenar formas](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.gif "AboutGdip02_Art21")  
  
 Un pincel de degradado de trazado puede configurarse para cambiar color a medida que se desplaza desde el centro de una forma hacia el borde.  
  
 ![Rellenar formas](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.gif "AboutGdip02_Art22")  
  
 Pinceles degradados de ruta de acceso son bastante flexibles. El pincel de degradado que se usa para rellenar el triángulo situado en la siguiente ilustración cambia gradualmente de rojo en el centro a cada uno de tres colores diferentes en los vértices.  
  
 ![Rellenar formas](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.gif "AboutGdip02_Art23")  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Dibujar un rectángulo relleno en Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-rectangle-on-a-windows-form.md)  
 [Dibujar una elipse rellena en Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-ellipse-on-a-windows-form.md)
