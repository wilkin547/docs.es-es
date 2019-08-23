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
ms.openlocfilehash: 45ef0b5920e43300e047d363149ea10a7833477b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912232"
---
# <a name="brushes-and-filled-shapes-in-gdi"></a>Pinceles y formas rellenas en GDI+
Una forma cerrada, como un rectángulo o una elipse, consta de un contorno y un interior. El contorno se dibuja con un lápiz y el interior se rellena con un pincel. GDI+ proporciona varias clases de pincel para rellenar el interior de las <xref:System.Drawing.SolidBrush>formas <xref:System.Drawing.Drawing2D.HatchBrush>cerradas <xref:System.Drawing.TextureBrush>: <xref:System.Drawing.Drawing2D.LinearGradientBrush>,, <xref:System.Drawing.Drawing2D.PathGradientBrush>, y. Todas estas clases heredan de la <xref:System.Drawing.Brush> clase. En la ilustración siguiente se muestra un rectángulo relleno con un pincel sólido y una elipse rellena con un pincel de trama.  
  
 ![Formas] rellenas (./media/aboutgdip02-art17.gif "Aboutgdip02_art17")  
  
## <a name="solid-brushes"></a>Pinceles sólidos  
 Para rellenar una forma cerrada, se necesita una instancia <xref:System.Drawing.Graphics> de la clase <xref:System.Drawing.Brush>y un. La instancia de la <xref:System.Drawing.Graphics> clase proporciona métodos, <xref:System.Drawing.Graphics.FillRectangle%2A> como y <xref:System.Drawing.Graphics.FillEllipse%2A>, y almacena los <xref:System.Drawing.Brush> atributos del relleno, como el color y el patrón. <xref:System.Drawing.Brush> Se pasa como uno de los argumentos al método Fill. En el ejemplo de código siguiente se muestra cómo rellenar una elipse con un color rojo sólido.  
  
 [!code-csharp[LinesCurvesAndShapes#121](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
> En el ejemplo anterior, el pincel es de tipo <xref:System.Drawing.SolidBrush>, que hereda de. <xref:System.Drawing.Brush>  
  
## <a name="hatch-brushes"></a>Pinceles de trama  
 Al rellenar una forma con un pincel de trama, se especifica un color de primer plano, un color de fondo y un estilo de trama. El color de primer plano es el color del sombreado.  
  
 [!code-csharp[LinesCurvesAndShapes#122](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 GDI+ proporciona más de 50 estilos de trama; los tres estilos que se muestran en la siguiente <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>ilustración <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>son, <xref:System.Drawing.Drawing2D.HatchStyle.Cross>y.  
  
 ![Formas] rellenas (./media/aboutgdip02-art18.gif "Aboutgdip02_art18")  
  
## <a name="texture-brushes"></a>Pinceles de textura  
 Con un pincel de textura, puede rellenar una forma con un patrón almacenado en un mapa de bits. Por ejemplo, supongamos que la siguiente imagen se almacena en un `MyTexture.bmp`archivo de disco denominado.  
  
 ![Forma rellena](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")  
  
 En el ejemplo de código siguiente se muestra cómo rellenar una elipse repitiendo `MyTexture.bmp`la imagen almacenada en.  
  
 [!code-csharp[LinesCurvesAndShapes#123](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 En la ilustración siguiente se muestra la elipse rellenada.  
  
 ![Forma rellena](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")  
  
## <a name="gradient-brushes"></a>Pinceles de degradado  
 GDI+ proporciona dos tipos de pinceles de degradado: lineal y path. Puede usar un pincel de degradado lineal para rellenar una forma con un color que cambie gradualmente a medida que se desplaza por la forma horizontal, vertical o diagonalmente. En el ejemplo de código siguiente se muestra cómo rellenar una elipse con un pincel de degradado horizontal que cambia de azul a verde a medida que se desplaza desde el borde izquierdo de la elipse hasta el borde derecho.  
  
 [!code-csharp[LinesCurvesAndShapes#124](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 En la ilustración siguiente se muestra la elipse rellenada.  
  
 ![Forma rellena](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")  
  
 Un pincel de degradado de trazado puede configurarse para cambiar el color a medida que se desplaza desde el centro de una forma hacia el borde.  
  
 ![Forma rellena](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")  
  
 Los pinceles de degradado de trazado son bastante flexibles. El pincel de degradado que se usa para rellenar el triángulo de la siguiente ilustración cambia gradualmente de rojo en el centro a cada uno de tres colores diferentes en los vértices.  
  
 ![Forma rellena](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>
- <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [Líneas, curvas y formas](lines-curves-and-shapes.md)
- [Cómo: Dibujar un rectángulo relleno en Windows Forms](how-to-draw-a-filled-rectangle-on-a-windows-form.md)
- [Procedimientos: Dibujar una elipse rellena en Windows Forms](how-to-draw-a-filled-ellipse-on-a-windows-form.md)
