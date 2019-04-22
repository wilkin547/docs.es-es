---
title: Procedimiento Establecer el tamaño del mosaico de un TileBrush
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: 80b5dfc668464df829db593668bea8a9a4ec09e4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839702"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>Procedimiento Establecer el tamaño del mosaico de un TileBrush

En este ejemplo se muestra cómo establecer el tamaño del mosaico para un <xref:System.Windows.Media.TileBrush>. De forma predeterminada, un <xref:System.Windows.Media.TileBrush> genera un mosaico único que rellena completamente el área que se está pintando. Puede invalidar este comportamiento estableciendo el <xref:System.Windows.Media.TileBrush.Viewport%2A> y <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> propiedades.

El <xref:System.Windows.Media.TileBrush.Viewport%2A> propiedad especifica el tamaño del mosaico para un <xref:System.Windows.Media.TileBrush>. De forma predeterminada, el valor de la <xref:System.Windows.Media.TileBrush.Viewport%2A> propiedad es relativo al tamaño del área que se está pintando. Para realizar la <xref:System.Windows.Media.TileBrush.Viewport%2A> propiedad especificar un tamaño de mosaico absoluto, establezca el <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> propiedad <xref:System.Windows.Media.BrushMappingMode.Absolute>.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usa un <xref:System.Windows.Media.ImageBrush>, un tipo de <xref:System.Windows.Media.TileBrush>, para pintar un rectángulo con mosaicos. El ejemplo establece cada mosaico al 50 por ciento al 50 por ciento del área de salida (rectángulo). Como resultado, el rectángulo se pinta con cuatro proyecciones de la imagen.

La siguiente ilustración muestra la salida que genera el ejemplo:

![Un rectángulo con cuatro cerezas demostrar la disposición en mosaico con un pincel de imagen.](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

El ejemplo siguiente se crea un <xref:System.Windows.Media.ImageBrush>, establece su <xref:System.Windows.Media.TileBrush.Viewport%2A> a `0,0,25,25` y su <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> a <xref:System.Windows.Media.BrushMappingMode.Absolute>y lo usa para pintar otro rectángulo. Como resultado, el pincel genera iconos que tienen un ancho de 25 píxeles y un alto de 25 píxeles.

La siguiente ilustración muestra la salida que genera el ejemplo:

![Un rectángulo con cerezas cuarenta y ocho demostrar un TileBrush en mosaico con una ventanilla.](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

Los ejemplos anteriores forman parte de un ejemplo mayor. Para obtener un ejemplo completo, vea [ejemplo de ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005).

Aunque este ejemplo usa el <xref:System.Windows.Media.ImageBrush> (clase), el <xref:System.Windows.Media.TileBrush.Viewport%2A> y <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> propiedades se comportan exactamente igual para los demás <xref:System.Windows.Media.TileBrush> objetos, es decir, para <xref:System.Windows.Media.DrawingBrush> y <xref:System.Windows.Media.VisualBrush>. Para obtener más información acerca de <xref:System.Windows.Media.ImageBrush> y el otro <xref:System.Windows.Media.TileBrush> objetos, vea [pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.TileBrush>
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
- [Crear patrones de mosaico diferentes con un objeto TileBrush](how-to-create-different-tile-patterns-with-a-tilebrush.md)
