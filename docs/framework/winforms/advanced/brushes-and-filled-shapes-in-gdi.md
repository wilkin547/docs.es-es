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
ms.openlocfilehash: fc6d6857e912ba14fca382eb49373655004534d5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720948"
---
# <a name="brushes-and-filled-shapes-in-gdi"></a>Pinceles y formas rellenas en GDI+
Una forma cerrada, como un rectángulo o una elipse, consta de un esquema y un interior. El contorno se dibuja con un lápiz y el interior se rellena con un pincel. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona varias clases de pincel para rellenar los interiores de formas cerradas: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, y <xref:System.Drawing.Drawing2D.PathGradientBrush>. Todas estas clases heredan de la <xref:System.Drawing.Brush> clase. La siguiente ilustración se muestra un rectángulo relleno con un pincel sólido y una elipse rellena con un pincel de trama.  
  
 ![Rellenar formas](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")  
  
## <a name="solid-brushes"></a>Pinceles sólidos  
 Para rellenar una forma cerrada, se necesita una instancia de la <xref:System.Drawing.Graphics> clase y un <xref:System.Drawing.Brush>. La instancia de la <xref:System.Drawing.Graphics> clase proporciona métodos, como <xref:System.Drawing.Graphics.FillRectangle%2A> y <xref:System.Drawing.Graphics.FillEllipse%2A>y el <xref:System.Drawing.Brush> almacena atributos de relleno, como el color y el patrón. El <xref:System.Drawing.Brush> se pasa como uno de los argumentos del método de relleno. El ejemplo de código siguiente muestra cómo rellenar una elipse con un color rojo sólido.  
  
 [!code-csharp[LinesCurvesAndShapes#121](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  En el ejemplo anterior, el pincel es de tipo <xref:System.Drawing.SolidBrush>, que hereda de <xref:System.Drawing.Brush>.  
  
## <a name="hatch-brushes"></a>Pinceles de trama  
 Al rellenar una forma con un pincel de trama, especifique un color de primer plano, un color de fondo y un estilo de trama. El color de primer plano es el color de la sombreado.  
  
 [!code-csharp[LinesCurvesAndShapes#122](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona más de 50 estilos de sombreado; los tres estilos que se muestra en la siguiente ilustración son <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, y <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.  
  
 ![Rellenar formas](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")  
  
## <a name="texture-brushes"></a>Pinceles de textura  
 Con un pincel de textura, puede rellenar una forma con un modelo almacenado en un mapa de bits. Por ejemplo, suponga la siguiente imagen se almacena en un archivo de disco denominado `MyTexture.bmp`.  
  
 ![Rellena de forma](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")  
  
 El ejemplo de código siguiente muestra cómo rellenar una elipse repitiendo la imagen almacenada en `MyTexture.bmp`.  
  
 [!code-csharp[LinesCurvesAndShapes#123](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 La siguiente ilustración muestra la elipse rellena.  
  
 ![Rellena de forma](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")  
  
## <a name="gradient-brushes"></a>Pinceles de degradado  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona dos tipos de pinceles de degradado: lineal y ruta de acceso. Puede utilizar un pincel de degradado lineal para rellenar una forma con un color que cambia gradualmente al desplazarse a través de la forma horizontal, vertical o diagonalmente. El ejemplo de código siguiente muestra cómo rellenar una elipse con un pincel de degradado horizontal que cambia de azul a verde a medida que se desplaza desde el borde izquierdo de la elipse hasta el borde derecho.  
  
 [!code-csharp[LinesCurvesAndShapes#124](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 La siguiente ilustración muestra la elipse rellena.  
  
 ![Rellena de forma](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")  
  
 Un pincel de degradado de la ruta de acceso puede configurarse para cambiar el color al desplazarse desde el centro de una forma hacia el borde.  
  
 ![Rellena de forma](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")  
  
 Pinceles de degradado de trazado son bastante flexibles. El pincel de degradado que se usa para rellenar el triángulo situado en la siguiente ilustración cambia gradualmente de rojo en el centro a cada uno de tres colores distintos en los vértices.  
  
 ![Rellena de forma](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")  
  
## <a name="see-also"></a>Vea también
- <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>
- <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [Líneas, curvas y formas](lines-curves-and-shapes.md)
- [Cómo: Dibujar un rectángulo relleno en un formulario de Windows](how-to-draw-a-filled-rectangle-on-a-windows-form.md)
- [Cómo: Dibujar una elipse con relleno en un formulario de Windows](how-to-draw-a-filled-ellipse-on-a-windows-form.md)
