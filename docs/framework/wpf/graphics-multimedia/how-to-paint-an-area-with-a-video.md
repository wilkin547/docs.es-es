---
title: 'Cómo: Pintar un área con un vídeo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting with a video [WPF]
- video [WPF], painting with
- brushes [WPF], painting with a video
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
ms.openlocfilehash: d2ca0f8b70abf6e895ea275d2a47eb4a6dd4bfe4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560782"
---
# <a name="how-to-paint-an-area-with-a-video"></a><span data-ttu-id="cdd36-102">Cómo: Pintar un área con un vídeo</span><span class="sxs-lookup"><span data-stu-id="cdd36-102">How to: Paint an Area with a Video</span></span>
<span data-ttu-id="cdd36-103">Este ejemplo muestra cómo se pinta un área con multimedia.</span><span class="sxs-lookup"><span data-stu-id="cdd36-103">This example shows how to paint an area with media.</span></span> <span data-ttu-id="cdd36-104">Una manera de pintar un área con multimedia es utilizar un <xref:System.Windows.Controls.MediaElement> junto con un <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="cdd36-104">One way to paint an area with media is to use a <xref:System.Windows.Controls.MediaElement> together with a <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="cdd36-105">Utilice la <xref:System.Windows.Controls.MediaElement> para cargar y reproducir el archivo multimedia y, a continuación, usarla para definir la <xref:System.Windows.Media.VisualBrush.Visual%2A> propiedad de la <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="cdd36-105">Use the <xref:System.Windows.Controls.MediaElement> to load and play the media, and then use it to set the <xref:System.Windows.Media.VisualBrush.Visual%2A> property of the <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="cdd36-106">A continuación, puede usar el <xref:System.Windows.Media.VisualBrush> para pintar un área con el contenido multimedia cargado.</span><span class="sxs-lookup"><span data-stu-id="cdd36-106">You can then use the <xref:System.Windows.Media.VisualBrush> to paint an area with the loaded media.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdd36-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cdd36-107">Example</span></span>  
 <span data-ttu-id="cdd36-108">En el ejemplo siguiente se usa un <xref:System.Windows.Controls.MediaElement> y un <xref:System.Windows.Media.VisualBrush> para pintar el <xref:System.Windows.Controls.TextBlock.Foreground%2A> de un <xref:System.Windows.Controls.TextBlock> control con vídeo.</span><span class="sxs-lookup"><span data-stu-id="cdd36-108">The following example uses a <xref:System.Windows.Controls.MediaElement> and a <xref:System.Windows.Media.VisualBrush> to paint the <xref:System.Windows.Controls.TextBlock.Foreground%2A> of a <xref:System.Windows.Controls.TextBlock> control with video.</span></span> <span data-ttu-id="cdd36-109">Este ejemplo se establece la <xref:System.Windows.Controls.MediaElement.IsMuted%2A> propiedad de la <xref:System.Windows.Controls.MediaElement> a `true` para que no genere ningún sonido.</span><span class="sxs-lookup"><span data-stu-id="cdd36-109">This example sets the <xref:System.Windows.Controls.MediaElement.IsMuted%2A> property of the <xref:System.Windows.Controls.MediaElement> to `true` so that it produces no sound.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a><span data-ttu-id="cdd36-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cdd36-110">Example</span></span>  
 <span data-ttu-id="cdd36-111">Dado que <xref:System.Windows.Media.VisualBrush> hereda de la <xref:System.Windows.Media.TileBrush> (clase), proporciona varios modos de mosaico.</span><span class="sxs-lookup"><span data-stu-id="cdd36-111">Because <xref:System.Windows.Media.VisualBrush> inherits from the <xref:System.Windows.Media.TileBrush> class, it provides several tiling modes.</span></span> <span data-ttu-id="cdd36-112">Estableciendo la <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedad de un <xref:System.Windows.Media.VisualBrush> a <xref:System.Windows.Media.TileMode.Tile> y estableciendo su <xref:System.Windows.Media.TileBrush.Viewport%2A> propiedad en un valor menor que el área que se está pintando, puede crear un modelo en mosaico.</span><span class="sxs-lookup"><span data-stu-id="cdd36-112">By setting the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.VisualBrush> to <xref:System.Windows.Media.TileMode.Tile> and by setting its <xref:System.Windows.Media.TileBrush.Viewport%2A> property to a value smaller than the area that you are painting, you can create a tiled pattern.</span></span>  
  
 <span data-ttu-id="cdd36-113">El ejemplo siguiente es idéntico al ejemplo anterior, salvo que la <xref:System.Windows.Media.VisualBrush> genera un modelo a partir del vídeo.</span><span class="sxs-lookup"><span data-stu-id="cdd36-113">The following example is identical to the previous example, except that the <xref:System.Windows.Media.VisualBrush> generates a pattern from the video.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 <span data-ttu-id="cdd36-114">Para obtener información sobre cómo agregar un archivo de contenido, como un archivo de medios, para la aplicación, consulte [recursos de la aplicación de WPF, contenido y archivos de datos](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).</span><span class="sxs-lookup"><span data-stu-id="cdd36-114">For information about how to add a content file, such as a media file, to your application, see [WPF Application Resource, Content, and Data Files](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).</span></span> <span data-ttu-id="cdd36-115">Cuando se agrega un archivo multimedia, debe agregarlo como un archivo de contenido, no como un archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="cdd36-115">When you add a media file, you must add it as a content file, not as a resource file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdd36-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="cdd36-116">See Also</span></span>  
 <xref:System.Windows.Media.VisualBrush>  
 [<span data-ttu-id="cdd36-117">Pintar con imágenes, dibujos y elementos visuales</span><span class="sxs-lookup"><span data-stu-id="cdd36-117">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [<span data-ttu-id="cdd36-118">Información general sobre objetos TileBrush</span><span class="sxs-lookup"><span data-stu-id="cdd36-118">TileBrush Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)  
 [<span data-ttu-id="cdd36-119">Información general sobre multimedia</span><span class="sxs-lookup"><span data-stu-id="cdd36-119">Multimedia Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md)
