---
title: Información general sobre objetos TileBrush
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF]
- brushes [WPF], TileBrush
ms.assetid: aa4a7b7e-d09d-44c2-8d61-310c50e08d68
ms.openlocfilehash: c129f902937363972e6be1a6518ae5a97e467f44
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625695"
---
# <a name="tilebrush-overview"></a>Información general sobre objetos TileBrush
<xref:System.Windows.Media.TileBrush> los objetos que proporcionan un gran control sobre cómo se pinta un área con una imagen, <xref:System.Windows.Media.Drawing>, o <xref:System.Windows.Media.Visual>. Este tema describe cómo usar <xref:System.Windows.Media.TileBrush> características para obtener más control sobre cómo un <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, o <xref:System.Windows.Media.VisualBrush> pinta un área.  

<a name="prerequisite"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, es útil entender cómo usar las características básicas de la <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, o <xref:System.Windows.Media.VisualBrush> clase. Para obtener una introducción a estos tipos, vea la [pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md).  
  
<a name="tilebrush"></a>   
## <a name="painting-an-area-with-tiles"></a>Dibujo de un área con mosaicos  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, son <xref:System.Windows.Media.VisualBrush> son tipos de <xref:System.Windows.Media.TileBrush> objetos. Los pinceles de mosaico proporcionan un gran control sobre cómo se dibuja un área con una imagen, un dibujo o un objeto visual. Por ejemplo, en lugar de limitarse a dibujar un área con una sola imagen ajustada, puede dibujar un área con una serie de mosaicos de imagen que crean un patrón.  
  
 Para dibujar un área con un pincel de mosaico se necesitan tres componentes: contenido, mosaico base y área de resultados.  
  
 ![Componentes de TileBrush](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Componentes de TileBrush con un solo mosaico  
  
 ![Componentes de TileBrush en mosaico](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
Componentes de TileBrush con un valor de TileMode de Tile  
  
 El área de salida es el área que se va a pintar, como el <xref:System.Windows.Shapes.Shape.Fill%2A> de un <xref:System.Windows.Shapes.Ellipse> o <xref:System.Windows.Controls.Control.Background%2A> de un <xref:System.Windows.Controls.Button>. Las secciones siguientes describen los dos componentes de un <xref:System.Windows.Media.TileBrush>.  
  
<a name="brushcontent"></a>   
## <a name="brush-content"></a>Contenido del objeto Brush  
 Hay tres tipos diferentes de <xref:System.Windows.Media.TileBrush> y cada uno de ellos pinta con un tipo diferente del contenido.  
  
- Si el pincel es un <xref:System.Windows.Media.ImageBrush>, este contenido es una imagen del <xref:System.Windows.Media.ImageBrush.ImageSource%2A> propiedad especifica el contenido de la <xref:System.Windows.Media.ImageBrush>.  
  
- Si el pincel es un <xref:System.Windows.Media.DrawingBrush>, este contenido es un dibujo. El <xref:System.Windows.Media.DrawingBrush.Drawing%2A> propiedad especifica el contenido de la <xref:System.Windows.Media.DrawingBrush>.  
  
- Si el pincel es un <xref:System.Windows.Media.VisualBrush>, este contenido es un objeto visual. El <xref:System.Windows.Media.VisualBrush.Visual%2A> propiedad especifica el contenido de la <xref:System.Windows.Media.VisualBrush>.  
  
 Puede especificar la posición y las dimensiones de <xref:System.Windows.Media.TileBrush> contenido mediante el uso de la <xref:System.Windows.Media.TileBrush.Viewbox%2A> propiedad, aunque es frecuente dejar el <xref:System.Windows.Media.TileBrush.Viewbox%2A> establecido en su valor predeterminado. De forma predeterminada, el <xref:System.Windows.Media.TileBrush.Viewbox%2A> se configura para contener completamente el contenido del pincel. Para obtener más información acerca de cómo configurar el <xref:System.Windows.Controls.Viewbox>, consulte la <xref:System.Windows.Controls.Viewbox> página de propiedades.  
  
<a name="thebasetile"></a>   
## <a name="the-base-tile"></a>Mosaico base  
 Un <xref:System.Windows.Media.TileBrush> proyecta su contenido en un mosaico base. El <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad controla cómo <xref:System.Windows.Media.TileBrush> contenido se ajusta para rellenar el mosaico base. El <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad acepta los valores siguientes, definidos por el <xref:System.Windows.Media.Stretch> enumeración:  
  
- <xref:System.Windows.Media.Stretch.None>: El contenido del pincel no se ajusta para rellenar el mosaico.  
  
- <xref:System.Windows.Media.Stretch.Fill>: El contenido del pincel se ajusta para rellenar el mosaico. Como el alto y el ancho del contenido se ajustan de forma independiente, podría no conservarse la relación de aspecto original del contenido. En otras palabras, el contenido del pincel podría distorsionarse para rellenar por completo el mosaico de salida.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: El contenido del pincel se escala para que quepa completamente dentro del mosaico. Se conserva la relación de aspecto del contenido.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: El contenido del pincel se escala para que rellene completamente el área de salida conservando la relación de aspecto original del contenido.  
  
 La siguiente imagen ilustra los diferentes <xref:System.Windows.Media.TileBrush.Stretch%2A> configuración.  
  
 ![Diferentes valores de Stretch para TileBrush](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
  
 En el ejemplo siguiente, el contenido de un <xref:System.Windows.Media.ImageBrush> está establecida para que no se ajusta para rellenar el área de salida.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMNoStretchExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/StretchExample.xaml#graphicsmmnostretchexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/StretchExample.cs#graphicsmmnostretchexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/stretchexample.vb#graphicsmmnostretchexample)]  
  
 De forma predeterminada, un <xref:System.Windows.Media.TileBrush> genera un único mosaico (el mosaico base) y ajusta ese mosaico hasta rellenar completamente el área de salida. Puede cambiar el tamaño y la posición del mosaico base estableciendo la <xref:System.Windows.Media.TileBrush.Viewport%2A> y <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> propiedades.  
  
<a name="basetilesize"></a>   
### <a name="base-tile-size"></a>Tamaño del mosaico base  
 El <xref:System.Windows.Media.TileBrush.Viewport%2A> propiedad determina el tamaño y la posición del mosaico base y el <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> propiedad determina si el <xref:System.Windows.Media.TileBrush.Viewport%2A> se especifica mediante coordenadas absolutas o relativas. Si las coordenadas son relativas, lo son con respecto al tamaño del área de salida. El punto (0,0) representa la parte superior izquierda esquina del área de salida y (1,1) representa la parte inferior derecha del área de salida. Para especificar que el <xref:System.Windows.Media.TileBrush.Viewport%2A> propiedad usa coordenadas absolutas, establezca el <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> propiedad <xref:System.Windows.Media.BrushMappingMode.Absolute>.  
  
 La siguiente ilustración muestra la diferencia entre un <xref:System.Windows.Media.TileBrush> con el valor relativo frente a absoluto <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>. Observe que las ilustraciones muestran un patrón de mosaicos; en la siguiente sección se describe cómo especificar el patrón de mosaicos.  
  
 ![Unidades de viewPort absolutas y relativas](./media/absolute-and-relative-viewports.png "absolute_and_relative_viewports")  
  
 En el ejemplo siguiente, se utiliza una imagen para crear un mosaico con un ancho y alto del 50%. El mosaico base se encuentra en la posición (0,0) del área de salida.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmrelativeviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmrelativeviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmrelativeviewportunitsexample1)]  
  
 El ejemplo siguiente establece los iconos de un <xref:System.Windows.Media.ImageBrush> a 25 por 25 píxeles independientes del dispositivo. Dado que el <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> son absolutos, el <xref:System.Windows.Media.ImageBrush> los iconos son siempre de 25 por 25 píxeles, independientemente del tamaño del área que se está pintando.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmabsoluteviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmabsoluteviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmabsoluteviewportunitsexample1)]  
  
<a name="tilingbehavior"></a>   
### <a name="tiling-behavior"></a>Comportamiento de la colocación en mosaico  
 Un <xref:System.Windows.Media.TileBrush> genera un patrón de mosaicos cuando su mosaico base no rellena completamente el área de salida y un modo de disposición en mosaico distinto <xref:System.Windows.Media.TileMode.None> se especifica. Cuando mosaico un icono de pincel de no rellena completamente el área de salida, su <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedad especifica si el mosaico base se debe duplicar para rellenar el área de salida y, si es así, ¿cómo la base se debe duplicar. El <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedad acepta los valores siguientes, definidos por el <xref:System.Windows.Media.TileMode> enumeración:  
  
- <xref:System.Windows.Media.TileMode.None>: Se dibuja el mosaico base.  
  
- <xref:System.Windows.Media.TileMode.Tile>: Se dibuja el mosaico base y el área restante se rellena repitiendo el mosaico base, que es adyacente al borde izquierdo del siguiente y el borde derecho de un mosaico de forma similar para los bordes superior e inferior.  
  
- <xref:System.Windows.Media.TileMode.FlipX>: Igual que <xref:System.Windows.Media.TileMode.Tile>, pero las columnas alternativas de los mosaicos se voltean horizontalmente.  
  
- <xref:System.Windows.Media.TileMode.FlipY>: Igual que <xref:System.Windows.Media.TileMode.Tile>, pero las filas alternas de los mosaicos se voltean verticalmente.  
  
- <xref:System.Windows.Media.TileMode.FlipXY>: Combinación de <xref:System.Windows.Media.TileMode.FlipX> y <xref:System.Windows.Media.TileMode.FlipY>.  
  
 La siguiente imagen ilustra los diferentes modos de colocación en mosaico.  
  
 ![Diferentes valores de TileMode para TileBrush](./media/img-mmgraphics-tilemodes.gif "img_mmgraphics_tilemodes")  
  
 En el ejemplo siguiente, se utiliza una imagen para dibujar un rectángulo de 100 píxeles de ancho por 100 píxeles de alto. Al establecer el pincel <xref:System.Windows.Media.TileBrush.Viewport%2A> se ha establecido en 0,0,0.25,0.25, mosaico base el pincel de se realiza para ser de 1/4 del área de salida. El pincel <xref:System.Windows.Media.TileBrush.TileMode%2A> está establecido en <xref:System.Windows.Media.TileMode.FlipXY>. para que rellene el rectángulo con filas de mosaicos.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMFlipXYExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TilingExample.xaml#graphicsmmflipxyexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TilingExample.cs#graphicsmmflipxyexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilingexample.vb#graphicsmmflipxyexample)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
- [Temas "Cómo..."](brushes-how-to-topics.md)
- [Información general sobre objetos Freezable](../advanced/freezable-objects-overview.md)
- [Ejemplo de ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005)
- [Ejemplo de VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049)
