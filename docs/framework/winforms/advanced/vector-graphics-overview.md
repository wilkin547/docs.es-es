---
title: Información general acerca de gráficos vectoriales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
ms.openlocfilehash: 31fec6d0d3769251d21783b4657d00b06431e942
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="vector-graphics-overview"></a>Información general acerca de gráficos vectoriales
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] dibuja líneas, rectángulos y otras formas en un sistema de coordenadas. Puede elegir entre una variedad de sistemas de coordenadas, pero el sistema de coordenadas predeterminado tiene el origen en la esquina superior izquierda con el eje x apuntando hacia la derecha y el eje y apuntando hacia abajo. La unidad de medida en el sistema de coordenadas predeterminado es el píxel.  
  
## <a name="the-building-blocks-of-gdi"></a>Los bloques de creación de GDI +  
 ![Gráfico vectorial](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.gif "AboutGdip02_Art01")  
  
 Un monitor de equipo crea su presentación en una matriz rectangular de puntos denominados elementos de imagen o píxeles. El número de píxeles que aparecen en la pantalla varía de un monitor a otro, y el número de píxeles que aparecen en un solo monitor normalmente puede configurarse con hasta cierto punto por el usuario.  
  
 ![Gráfico vectorial](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.gif "AboutGdip02_Art02")  
  
 Cuando se usa [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] para dibujar una línea, un rectángulo o una curva, se proporciona cierta información clave sobre el elemento que se va a dibujar. Por ejemplo, puede especificar una línea proporcionando dos puntos, y puede especificar un rectángulo proporcionando un punto, un alto y un ancho. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funciona junto con el software de controlador de vídeo para determinar qué píxeles deben estar activados para mostrar la línea, un rectángulo o una curva. La ilustración siguiente muestra los píxeles que están activados para mostrar una línea desde el punto (4, 2) al punto (12, 8).  
  
 ![Gráfico vectorial](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.gif "AboutGdip02_Art03")  
  
 Con el tiempo, determinados bloques de creación básicos han demostrado para ser las más útiles para crear imágenes bidimensionales. Estos bloques de creación, que son compatibles con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], se proporcionan en la lista siguiente:  
  
-   Líneas  
  
-   Rectángulos  
  
-   Botón de puntos suspensivos  
  
-   Arcos  
  
-   Polígonos  
  
-   Curvas spline cardinales  
  
-   curvas spline de Bézier  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a>Métodos para dibujar con un objeto gráfico  
 El <xref:System.Drawing.Graphics> clase [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona los siguientes métodos para dibujar los elementos de la lista anterior: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (para curvas spline cardinales), y <xref:System.Drawing.Graphics.DrawBezier%2A>. Cada uno de estos métodos está sobrecargado; es decir, cada método es compatible con varias listas de parámetros diferentes. Por ejemplo, una variación de la <xref:System.Drawing.Graphics.DrawLine%2A> método recibe un <xref:System.Drawing.Pen> objeto y cuatro enteros, mientras otra variación de la <xref:System.Drawing.Graphics.DrawLine%2A> método recibe un <xref:System.Drawing.Pen> objeto y dos <xref:System.Drawing.Point> objetos.  
  
 Los métodos para dibujar líneas, rectángulos y curvas spline de Bézier tienen varios métodos asociados que dibujan varios elementos en una única llamada: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, y <xref:System.Drawing.Graphics.DrawBeziers%2A>. Además, el <xref:System.Drawing.Graphics.DrawCurve%2A> método tiene un método complementario, <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, que se cierra una curva conectando el punto final de la curva a partir del punto.  
  
 Todos los métodos de dibujo de la <xref:System.Drawing.Graphics> clase trabajo junto con un <xref:System.Drawing.Pen> objeto. Para dibujar cualquier cosa, debe crear al menos dos objetos: un <xref:System.Drawing.Graphics> objeto y un <xref:System.Drawing.Pen> objeto. La <xref:System.Drawing.Pen> objeto almacena atributos, como el ancho de línea y el color, del elemento que se va a dibujar. La <xref:System.Drawing.Pen> objeto se pasa como uno de los argumentos para el método de dibujo. Por ejemplo, una variación de la <xref:System.Drawing.Graphics.DrawLine%2A> método recibe un <xref:System.Drawing.Pen> objeto y cuatro enteros, tal y como se muestra en el ejemplo siguiente, que se dibuja un rectángulo con un ancho de 100, un alto de 50 y una esquina superior izquierda de (20, 10):  
  
 [!code-csharp[LinesCurvesAndShapes#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
