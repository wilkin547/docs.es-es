---
title: 'Cómo: Establecer el tamaño del mosaico de un TileBrush'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: af7bab59a292549b29dad9b6a7417f22b1b84e48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186835"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>Cómo: Establecer el tamaño del mosaico de un TileBrush

En este ejemplo se muestra cómo <xref:System.Windows.Media.TileBrush>establecer el tamaño de tesela para un archivo . De forma <xref:System.Windows.Media.TileBrush> predeterminada, un produce un único mosaico que rellena completamente el área que está pintando. Puede invalidar este comportamiento <xref:System.Windows.Media.TileBrush.Viewport%2A> estableciendo las propiedades y. <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>

La <xref:System.Windows.Media.TileBrush.Viewport%2A> propiedad especifica el tamaño <xref:System.Windows.Media.TileBrush>de tesela para un archivo . De forma predeterminada, <xref:System.Windows.Media.TileBrush.Viewport%2A> el valor de la propiedad es relativo al tamaño del área que se va a pintar. Para que <xref:System.Windows.Media.TileBrush.Viewport%2A> la propiedad especifique un <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> tamaño <xref:System.Windows.Media.BrushMappingMode.Absolute>de tesela absoluto, establezca la propiedad en .

## <a name="example"></a>Ejemplo

En el ejemplo <xref:System.Windows.Media.ImageBrush>siguiente se <xref:System.Windows.Media.TileBrush>utiliza un , un tipo de , para pintar un rectángulo con mosaicos. En el ejemplo se establece cada icono en 50 por ciento por 50 por ciento del área de salida (el rectángulo). Como resultado, el rectángulo se pinta con cuatro proyecciones de la imagen.

La ilustración siguiente muestra la salida que produce el ejemplo:

![Un rectángulo con cuatro cerezas que demuestran mosaicos con un pincel de imagen.](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

En el ejemplo <xref:System.Windows.Media.ImageBrush>siguiente <xref:System.Windows.Media.TileBrush.Viewport%2A> se `0,0,25,25` crea <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> <xref:System.Windows.Media.BrushMappingMode.Absolute>un , establece su en y su en , y se utiliza para pintar otro rectángulo. Como resultado, el pincel genera iconos que tienen un ancho de 25 píxeles y un alto de 25 píxeles.

La ilustración siguiente muestra la salida que produce el ejemplo:

![Un rectángulo con cuarenta y ocho cerezas que demuestran un TileBrush en mosaico con una ventana gráfica.](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

Los ejemplos anteriores forman parte de un ejemplo mayor. Para obtener el ejemplo completo, vea [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).

Aunque en este <xref:System.Windows.Media.ImageBrush> ejemplo <xref:System.Windows.Media.TileBrush.Viewport%2A> se <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> utiliza la clase, <xref:System.Windows.Media.TileBrush> las propiedades y <xref:System.Windows.Media.DrawingBrush> se <xref:System.Windows.Media.VisualBrush>comportan de forma idéntica para los demás objetos, es decir, for y . Para obtener <xref:System.Windows.Media.ImageBrush> más información <xref:System.Windows.Media.TileBrush> sobre y los demás objetos, vea [Pintar con imágenes, dibujos y objetos visuales](painting-with-images-drawings-and-visuals.md).

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.TileBrush>
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
- [Crear patrones de mosaico diferentes con un objeto TileBrush](how-to-create-different-tile-patterns-with-a-tilebrush.md)
