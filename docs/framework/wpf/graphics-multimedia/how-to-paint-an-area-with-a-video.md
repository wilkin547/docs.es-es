---
title: Procedimiento Pintar un área con un vídeo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting with a video [WPF]
- video [WPF], painting with
- brushes [WPF], painting with a video
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
ms.openlocfilehash: be09d1310847cd7214ea795a704c25d994f07b7a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921737"
---
# <a name="how-to-paint-an-area-with-a-video"></a>Procedimiento Pintar un área con un vídeo
En este ejemplo se muestra cómo pintar un área con medios. Una manera de pintar un área con medios es usar un <xref:System.Windows.Controls.MediaElement> junto con un <xref:System.Windows.Media.VisualBrush>. Utilice la <xref:System.Windows.Controls.MediaElement> para cargar y reproducir el archivo multimedia y, a continuación, usarla para establecer el <xref:System.Windows.Media.VisualBrush.Visual%2A> propiedad de la <xref:System.Windows.Media.VisualBrush>. A continuación, puede usar el <xref:System.Windows.Media.VisualBrush> para pintar un área con el elemento multimedia cargado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Controls.MediaElement> y un <xref:System.Windows.Media.VisualBrush> para pintar el <xref:System.Windows.Controls.TextBlock.Foreground%2A> de un <xref:System.Windows.Controls.TextBlock> control con vídeo. Este ejemplo se establece la <xref:System.Windows.Controls.MediaElement.IsMuted%2A> propiedad de la <xref:System.Windows.Controls.MediaElement> a `true` para que no genere ningún sonido.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a>Ejemplo  
 Dado que <xref:System.Windows.Media.VisualBrush> hereda el <xref:System.Windows.Media.TileBrush> (clase), proporciona varios modos de mosaico. Estableciendo el <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedad de un <xref:System.Windows.Media.VisualBrush> a <xref:System.Windows.Media.TileMode.Tile> y estableciendo su <xref:System.Windows.Media.TileBrush.Viewport%2A> propiedad en un valor menor que el área que se está pintando, puede crear un patrón de mosaicos.  
  
 El ejemplo siguiente es idéntico al ejemplo anterior, salvo que el <xref:System.Windows.Media.VisualBrush> genera un modelo a partir del vídeo.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 Para obtener información acerca de cómo agregar un archivo de contenido, como un archivo multimedia, a la aplicación, consulte [WPF Application Resource, contenido y los archivos de datos](../app-development/wpf-application-resource-content-and-data-files.md). Cuando se agrega un archivo multimedia, debe agregarlo como un archivo de contenido, no como un archivo de recursos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.VisualBrush>
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
- [Información general sobre objetos TileBrush](tilebrush-overview.md)
- [Información general sobre multimedia](multimedia-overview.md)
