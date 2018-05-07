---
title: 'Cómo: Establecer el tamaño del mosaico de un TileBrush'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tilepropertys
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: 16f0a4b3a5c9b9075126ba6d8f19d65169f70921
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>Cómo: Establecer el tamaño del mosaico de un TileBrush
Este ejemplo muestra cómo establecer el tamaño del mosaico para un <xref:System.Windows.Media.TileBrush>. De forma predeterminada, un <xref:System.Windows.Media.TileBrush> genera un mosaico único que rellena completamente el área que se está pintando. Puede invalidar este comportamiento estableciendo el <xref:System.Windows.Media.TileBrush.Viewport%2A> y <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> propiedades.  
  
 El <xref:System.Windows.Media.TileBrush.Viewport%2A> propiedad especifica el tamaño del mosaico para un <xref:System.Windows.Media.TileBrush>. De forma predeterminada, el valor de la <xref:System.Windows.Media.TileBrush.Viewport%2A> propiedad es relativo al tamaño del área que se está pintando. Para realizar la <xref:System.Windows.Media.TileBrush.Viewport%2A> propiedad especifique un tamaño de icono absoluta, establecer el <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> propiedad <xref:System.Windows.Media.BrushMappingMode.Absolute>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.ImageBrush>, un tipo de <xref:System.Windows.Media.TileBrush>, para dibujar un rectángulo con mosaicos. El ejemplo establece cada mosaico en un área de salida de 50 por 50 (el rectángulo). Como resultado, el rectángulo se pinta con cuatro proyecciones de la imagen.  
  
 La siguiente ilustración muestra el resultado que genera el ejemplo.
  
 ![Ejemplo de la disposición en mosaico con un pincel de imagen](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")  
  
 [!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]  
  
 En el ejemplo siguiente se crea un <xref:System.Windows.Media.ImageBrush>, establece su <xref:System.Windows.Media.TileBrush.Viewport%2A> a `0,0,25,25` y su <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> a <xref:System.Windows.Media.BrushMappingMode.Absolute>y se utiliza para dibujar un rectángulo. Como resultado, el pincel genera iconos que tienen un ancho de 25 píxeles y un alto de 25 píxeles.  
  
 La siguiente ilustración muestra el resultado que genera el ejemplo.  
  
 ![TileBrush en mosaico con una ventanilla de 0,0,0,25,0,25](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")  
  
 [!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]  
  
 Los ejemplos anteriores forman parte de un ejemplo mayor. Para obtener un ejemplo completo, vea [ejemplo ImageBrush](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
 Aunque en este ejemplo se usa el <xref:System.Windows.Media.ImageBrush> (clase), el <xref:System.Windows.Media.TileBrush.Viewport%2A> y <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> propiedades se comportan exactamente igual para los demás <xref:System.Windows.Media.TileBrush> objetos, es decir, para <xref:System.Windows.Media.DrawingBrush> y <xref:System.Windows.Media.VisualBrush>. Para obtener más información acerca de <xref:System.Windows.Media.ImageBrush> y el otro <xref:System.Windows.Media.TileBrush> los objetos, vea [pintar con imágenes, gráficos y objetos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.TileBrush>  
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Crear patrones de mosaico diferentes con un objeto TileBrush](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-different-tile-patterns-with-a-tilebrush.md)
