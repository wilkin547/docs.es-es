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
ms.openlocfilehash: 99bcc8695206030a381d71df2dda495867d3e9c7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187104"
---
# <a name="tilebrush-overview"></a>Información general sobre objetos TileBrush
<xref:System.Windows.Media.TileBrush>objetos le proporcionan un gran control sobre cómo se pinta <xref:System.Windows.Media.Drawing>un <xref:System.Windows.Media.Visual>área con una imagen, , o . En este tema se <xref:System.Windows.Media.TileBrush> describe cómo utilizar entidades <xref:System.Windows.Media.DrawingBrush>para <xref:System.Windows.Media.VisualBrush> obtener más control sobre cómo un <xref:System.Windows.Media.ImageBrush>, , o pinta un área.  

<a name="prerequisite"></a>
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, es útil entender cómo usar <xref:System.Windows.Media.ImageBrush>las <xref:System.Windows.Media.DrawingBrush>características <xref:System.Windows.Media.VisualBrush> básicas de la clase , , o . Para obtener una introducción a estos tipos, vea [La pintura con imágenes, dibujos y objetos visuales](painting-with-images-drawings-and-visuals.md).  
  
<a name="tilebrush"></a>
## <a name="painting-an-area-with-tiles"></a>Dibujo de un área con mosaicos  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.VisualBrush> son <xref:System.Windows.Media.TileBrush> tipos de objetos. Los pinceles de mosaico proporcionan un gran control sobre cómo se dibuja un área con una imagen, un dibujo o un objeto visual. Por ejemplo, en lugar de limitarse a pintar un área con una sola imagen estirada, puede pintar un área con una serie de mosaicos de imagen que crean un patrón.  
  
 Para dibujar un área con un pincel de mosaico se necesitan tres componentes: contenido, mosaico base y área de resultados.  
  
 ![Componentes de TileBrush](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Componentes de TileBrush con un solo mosaico  
  
 ![Componentes de un objeto TileBrush en mosaico](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
Componentes de TileBrush con un valor de TileMode de Tile  
  
 El área de salida es el <xref:System.Windows.Shapes.Shape.Fill%2A> área <xref:System.Windows.Shapes.Ellipse> que <xref:System.Windows.Controls.Control.Background%2A> se <xref:System.Windows.Controls.Button>está pintando, como la de un o el de un archivo . En las secciones siguientes se <xref:System.Windows.Media.TileBrush>describen los otros dos componentes de un archivo .  
  
<a name="brushcontent"></a>
## <a name="brush-content"></a>Contenido del objeto Brush  
 Hay tres tipos <xref:System.Windows.Media.TileBrush> diferentes de y cada pintura con un tipo diferente de contenido.  
  
- Si el pincel <xref:System.Windows.Media.ImageBrush>es un , <xref:System.Windows.Media.ImageBrush.ImageSource%2A> este contenido es una <xref:System.Windows.Media.ImageBrush>imagen La propiedad especifica el contenido del archivo .  
  
- Si el pincel <xref:System.Windows.Media.DrawingBrush>es un , este contenido es un dibujo. La <xref:System.Windows.Media.DrawingBrush.Drawing%2A> propiedad especifica el <xref:System.Windows.Media.DrawingBrush>contenido del archivo .  
  
- Si el pincel <xref:System.Windows.Media.VisualBrush>es un , este contenido es un objeto visual. La <xref:System.Windows.Media.VisualBrush.Visual%2A> propiedad especifica el <xref:System.Windows.Media.VisualBrush>contenido del archivo .  
  
 Puede especificar la posición <xref:System.Windows.Media.TileBrush> y las <xref:System.Windows.Media.TileBrush.Viewbox%2A> dimensiones del contenido mediante <xref:System.Windows.Media.TileBrush.Viewbox%2A> la propiedad, aunque es común dejar el conjunto en su valor predeterminado. De forma <xref:System.Windows.Media.TileBrush.Viewbox%2A> predeterminada, está configurado para contener completamente el contenido del pincel. Para obtener más información <xref:System.Windows.Controls.Viewbox>acerca <xref:System.Windows.Controls.Viewbox> de cómo configurar el , consulte la página de propiedades.  
  
<a name="thebasetile"></a>
## <a name="the-base-tile"></a>Mosaico base  
 Un <xref:System.Windows.Media.TileBrush> proyecta su contenido en un mosaico base. La <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad <xref:System.Windows.Media.TileBrush> controla cómo se extiende el contenido para rellenar el icono base. La <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad acepta los siguientes valores, definidos por la <xref:System.Windows.Media.Stretch> enumeración:  
  
- <xref:System.Windows.Media.Stretch.None>: el contenido del pincel no se estira para rellenar el mosaico.  
  
- <xref:System.Windows.Media.Stretch.Fill>: el contenido del pincel se escala para ajustarse al mosaico. Como el alto y el ancho del contenido se ajustan de forma independiente, podría no conservarse la relación de aspecto original del contenido. En otras palabras, el contenido del pincel podría distorsionarse para rellenar por completo el mosaico de salida.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: El contenido del pincel se escala para que quepa completamente dentro del mosaico. Se conserva la relación de aspecto del contenido.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: El contenido del pincel se escala para que llene completamente el área de salida conservando la relación de aspecto original del contenido.  
  
 La siguiente imagen ilustra <xref:System.Windows.Media.TileBrush.Stretch%2A> los diferentes ajustes.  
  
 ![Diferentes valores de Stretch para TileBrush](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
  
 En el ejemplo siguiente, <xref:System.Windows.Media.ImageBrush> el contenido de un se establece para que no se estire para rellenar el área de salida.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMNoStretchExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/StretchExample.xaml#graphicsmmnostretchexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/StretchExample.cs#graphicsmmnostretchexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/stretchexample.vb#graphicsmmnostretchexample)]  
  
 De forma <xref:System.Windows.Media.TileBrush> predeterminada, un genera un único mosaico (el mosaico base) y estira ese mosaico para rellenar completamente el área de salida. Puede cambiar el tamaño y la posición <xref:System.Windows.Media.TileBrush.Viewport%2A> del <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> mosaico base estableciendo las propiedades y.  
  
<a name="basetilesize"></a>
### <a name="base-tile-size"></a>Tamaño del mosaico base  
 La <xref:System.Windows.Media.TileBrush.Viewport%2A> propiedad determina el tamaño y la posición <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> del mosaico <xref:System.Windows.Media.TileBrush.Viewport%2A> base y la propiedad determina si se especifica mediante coordenadas absolutas o relativas. Si las coordenadas son relativas, lo son con respecto al tamaño del área de salida. El punto (0,0) representa la parte superior izquierda esquina del área de salida y (1,1) representa la parte inferior derecha del área de salida. Para especificar <xref:System.Windows.Media.TileBrush.Viewport%2A> que la propiedad utiliza <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> coordenadas <xref:System.Windows.Media.BrushMappingMode.Absolute>absolutas, establezca la propiedad en .  
  
 En la ilustración siguiente se <xref:System.Windows.Media.TileBrush> muestra la <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>diferencia de salida entre a con relative frente a absolute . Observe que las ilustraciones muestran un patrón de mosaicos; en la siguiente sección se describe cómo especificar el patrón de mosaicos.  
  
 ![Unidades de ventanilla absoluta y relativa](./media/absolute-and-relative-viewports.png "absolute_and_relative_viewports")  
  
 En el ejemplo siguiente, se utiliza una imagen para crear un mosaico con un ancho y alto del 50%. El mosaico base se encuentra en la posición (0,0) del área de salida.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmrelativeviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmrelativeviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmrelativeviewportunitsexample1)]  
  
 En el ejemplo siguiente <xref:System.Windows.Media.ImageBrush> se establecen las teselas de un píxel independiente de 25 por 25 dispositivos. Dado <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> que son <xref:System.Windows.Media.ImageBrush> absolutos, las teselas son siempre de 25 por 25 píxeles, independientemente del tamaño del área que se va a pintar.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmabsoluteviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmabsoluteviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmabsoluteviewportunitsexample1)]  
  
<a name="tilingbehavior"></a>
### <a name="tiling-behavior"></a>Comportamiento de la colocación en mosaico  
 Un <xref:System.Windows.Media.TileBrush> produce un patrón de mosaico cuando su mosaico base no llena <xref:System.Windows.Media.TileMode.None> completamente el área de salida y se especifica otro modo de ordenamiento en teselas. Cuando el mosaico de un pincel de teselas no llena completamente el área de salida, su <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedad especifica si el mosaico base debe duplicarse para rellenar el área de salida y, si es así, cómo se debe duplicar el mosaico base. La <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedad acepta los siguientes valores, definidos por la <xref:System.Windows.Media.TileMode> enumeración:  
  
- <xref:System.Windows.Media.TileMode.None>: Sólo se dibuja el azulejo base.  
  
- <xref:System.Windows.Media.TileMode.Tile>: el azulejo base se dibuja y el área restante se rellena repitiendo el azulejo base de modo que el borde derecho de un azulejo esté adyacente al borde izquierdo del siguiente, y de forma similar para la parte inferior y superior.  
  
- <xref:System.Windows.Media.TileMode.FlipX>: Lo <xref:System.Windows.Media.TileMode.Tile>mismo que , pero las columnas alternativas de las teselas se voltean horizontalmente.  
  
- <xref:System.Windows.Media.TileMode.FlipY>: Lo <xref:System.Windows.Media.TileMode.Tile>mismo que , pero las filas alternativas de teselas se voltean verticalmente.  
  
- <xref:System.Windows.Media.TileMode.FlipXY>: Una <xref:System.Windows.Media.TileMode.FlipX> combinación de y <xref:System.Windows.Media.TileMode.FlipY>.  
  
 La siguiente imagen ilustra los diferentes modos de colocación en mosaico.  
  
 ![Diferentes valores de TileMode para TileBrush](./media/img-mmgraphics-tilemodes.gif "img_mmgraphics_tilemodes")  
  
 En el ejemplo siguiente, se utiliza una imagen para dibujar un rectángulo de 100 píxeles de ancho por 100 píxeles de alto. Al establecer el <xref:System.Windows.Media.TileBrush.Viewport%2A> pincel se ha establecido en 0,0,0.25,0.25, el mosaico base del pincel se hace 1/4 del área de salida. El pincel <xref:System.Windows.Media.TileBrush.TileMode%2A> está ajustado <xref:System.Windows.Media.TileMode.FlipXY>en . para que rellene el rectángulo con filas de mosaicos.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMFlipXYExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TilingExample.xaml#graphicsmmflipxyexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TilingExample.cs#graphicsmmflipxyexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilingexample.vb#graphicsmmflipxyexample)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
- [Temas de información](brushes-how-to-topics.md)
- [Freezable Objects Overview](../advanced/freezable-objects-overview.md) (Información general sobre objetos Freezable)
- [Ejemplo de ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [Ejemplo de VisualBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
