---
title: "Pinceles y formas rellenas en GDI+ | Microsoft Docs"
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
  - "pinceles, GDI+"
  - "pinceles, degradados"
  - "formas rellenas, GDI+"
  - "GDI+, pinceles"
  - "GDI+, formas rellenas"
  - "pinceles degradados"
  - "formas, GDI+"
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Pinceles y formas rellenas en GDI+
Una figura cerrada, como un rectángulo o una elipse, está compuesta de un contorno y un interior.  El contorno se dibuja con un lápiz y el interior se rellena con un pincel.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona varias clases de pincel para rellenar el interior de formas cerradas: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>y <xref:System.Drawing.Drawing2D.PathGradientBrush>.  Todas estas clases se heredan de la clase <xref:System.Drawing.Brush>.  En la siguiente ilustración se muestra un rectángulo relleno con un pincel sólido y una elipse rellena con un pincel tramado.  
  
 ![Formas rellenas](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.png "Aboutgdip02\_art17")  
  
## Pinceles sólidos  
 Para rellenar una forma cerrada, necesita una instancia de la clase <xref:System.Drawing.Graphics> y <xref:System.Drawing.Brush>.  La instancia de la clase <xref:System.Drawing.Graphics> proporciona métodos, como <xref:System.Drawing.Graphics.FillRectangle%2A> y <xref:System.Drawing.Graphics.FillEllipse%2A>, y <xref:System.Drawing.Brush> almacena los atributos del relleno, como color y modelo.  <xref:System.Drawing.Brush> se pasa como uno de los argumentos del método de relleno.  En el siguiente ejemplo de código se muestra cómo rellenar una elipse con un color rojo sólido.  
  
 [!code-csharp[LinesCurvesAndShapes#121](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  En el ejemplo anterior, el pincel es de tipo <xref:System.Drawing.SolidBrush>, que hereda de <xref:System.Drawing.Brush>.  
  
## Pincel tramado  
 Cuando se rellena una forma con un pincel tramado, hay que especificar un color de primer plano, un color de fondo y un estilo tramado.  El color de primer plano es el color del tramado.  
  
 [!code-csharp[LinesCurvesAndShapes#122](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona más de 50 estilos tramados; los tres estilos que se muestran en la siguiente ilustración son <xref:System.Drawing.Drawing2D.HatchStyle>, <xref:System.Drawing.Drawing2D.HatchStyle> y <xref:System.Drawing.Drawing2D.HatchStyle>.  
  
 ![Formas rellenas](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.png "Aboutgdip02\_art18")  
  
## Pinceles de textura  
 Un pincel de textura permite rellenar una forma con un modelo almacenado en un mapa de bits.  Por ejemplo, supongamos que la siguiente imagen está almacenada en un archivo de disco denominado `MyTexture.bmp`.  
  
 ![Forma rellena](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.png "Aboutgdip02\_Art19")  
  
 En el ejemplo de código siguiente se muestra cómo rellenar una elipse repitiendo la imagen almacenada en `MyTexture.bmp`.  
  
 [!code-csharp[LinesCurvesAndShapes#123](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 En la siguiente ilustración se muestra la elipse rellena.  
  
 ![Forma rellena](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.png "AboutGdip02\_Art20")  
  
## Pinceles degradados  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona dos tipos de pinceles degradados: lineal y de trazado.  Se puede utilizar un pincel degradado para rellenar una forma con un color que cambie gradualmente conforme se avanza por la forma horizontal, vertical o diagonalmente.  En el siguiente ejemplo de código se muestra cómo rellenar una elipse con un pincel degradado horizontal que cambia de azul a verde conforme se avanza del borde izquierdo de la elipse al borde derecho.  
  
 [!code-csharp[LinesCurvesAndShapes#124](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 En la siguiente ilustración se muestra la elipse rellena.  
  
 ![Forma rellena](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.png "AboutGdip02\_Art21")  
  
 Un pincel degradado de trazado se puede configurar para que cambie de color conforme se avanza desde el centro de una forma hacia el borde de la misma.  
  
 ![Forma rellena](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.png "AboutGdip02\_Art22")  
  
 Los pinceles degradados de trazado son bastante flexibles.  El pincel degradado utilizado para rellenar el triángulo de la siguiente ilustración cambia gradualmente de rojo, en el centro, a cada uno de tres colores distintos de los vértices.  
  
 ![Forma rellena](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.png "AboutGdip02\_Art23")  
  
## Vea también  
 <xref:System.Drawing.SolidBrush?displayProperty=fullName>   
 <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=fullName>   
 <xref:System.Drawing.TextureBrush?displayProperty=fullName>   
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=fullName>   
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Cómo: Dibujar un rectángulo relleno en Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-rectangle-on-a-windows-form.md)   
 [Cómo: Dibujar una elipse rellena en Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-ellipse-on-a-windows-form.md)