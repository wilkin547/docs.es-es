---
title: Información general sobre efectos de imagen
ms.date: 03/30/2017
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: 4a5e73f21d4ce4988f56c139d13038dca902b5b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187001"
---
# <a name="bitmap-effects-overview"></a>Información general sobre efectos de imagen
Los efectos de mapa de bits permiten a los diseñadores y desarrolladores aplicar efectos visuales al contenido representado de Windows Presentation Foundation (WPF). Por ejemplo, los efectos de <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> mapa de bits le permiten aplicar fácilmente un efecto o un efecto de desenfoque a una imagen o un botón.  
  
> [!IMPORTANT]
> En .NET Framework 4 o <xref:System.Windows.Media.Effects.BitmapEffect> posterior, la clase está obsoleta. Si intenta utilizar <xref:System.Windows.Media.Effects.BitmapEffect> la clase, obtendrá una excepción obsoleta. La alternativa no obsoleta <xref:System.Windows.Media.Effects.BitmapEffect> a <xref:System.Windows.Media.Effects.Effect> la clase es la clase. En la mayoría <xref:System.Windows.Media.Effects.Effect> de las situaciones, la clase es significativamente más rápida.  

<a name="wpf_effects"></a>
## <a name="wpf-bitmap-effects"></a>Efectos de imagen de WPF  
 Los efectos de mapa de bits (objeto)<xref:System.Windows.Media.Effects.BitmapEffect> son operaciones simples de procesamiento de píxeles. Un efecto de <xref:System.Windows.Media.Imaging.BitmapSource> mapa de bits toma <xref:System.Windows.Media.Imaging.BitmapSource> una entrada como una entrada y produce una nueva después de aplicar el efecto, como un desenfoque o una sombra paralela. Cada efecto de mapa de bits expone propiedades <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> <xref:System.Windows.Media.Effects.BlurBitmapEffect>que pueden controlar las propiedades de filtrado, como .  
  
 Como caso especial, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]en , los efectos <xref:System.Windows.Media.Visual> se pueden <xref:System.Windows.Controls.Button> establecer <xref:System.Windows.Controls.TextBox>como propiedades en objetos activos, como a o . El procesamiento de píxeles se aplica y se representa en tiempo de ejecución. En este caso, en el <xref:System.Windows.Media.Visual> momento de la <xref:System.Windows.Media.Imaging.BitmapSource> representación, a se <xref:System.Windows.Media.Effects.BitmapEffect>convierte automáticamente a su equivalente y se alimenta como entrada para el archivo . La salida reemplaza <xref:System.Windows.Media.Visual> el comportamiento de representación predeterminado del objeto. Esta es <xref:System.Windows.Media.Effects.BitmapEffect> la razón por la que los objetos fuerzan los objetos visuales a representarse en software solo, es decir, no hay aceleración de hardware en los objetos visuales cuando se aplican efectos.  
  
- <xref:System.Windows.Media.Effects.BlurBitmapEffect>simula un objeto que aparece fuera de foco.  
  
- <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect>crea un halo de color alrededor del perímetro de un objeto.  
  
- <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>crea una sombra detrás de un objeto.  
  
- <xref:System.Windows.Media.Effects.BevelBitmapEffect>crea un bisel que eleva la superficie de una imagen de acuerdo con una curva especificada.  
  
- <xref:System.Windows.Media.Effects.EmbossBitmapEffect>crea un mapeo <xref:System.Windows.Media.Visual> de protuberancias de a para dar la impresión de profundidad y textura de una fuente de luz artificial.  
  
> [!NOTE]
> WpfWPF efectos de mapa de bits se representan en modo de software. Cualquier objeto que aplique un efecto también se representará en software. El rendimiento disminuye al máximo al usar los efectos de imagen en objetos visuales grandes o al animar las propiedades de un efecto de imagen. Esto no quiere decir que no se deben usar efectos de imagen de esta manera en absoluto, pero hay que tener cuidado y probarlos exhaustivamente para asegurarse de que los usuarios obtengan la experiencia esperada.  
  
> [!NOTE]
> WpfWPF efectos de mapa de bits no admiten la ejecución parcial de confianza. Una aplicación debe tener permisos de plena confianza para usar efectos de imagen.  
  
<a name="applyeffects"></a>
## <a name="how-to-apply-an-effect"></a>Cómo aplicar un efecto  
 <xref:System.Windows.Media.Effects.BitmapEffect>es una <xref:System.Windows.Media.Visual>propiedad en . Por lo tanto, aplicar efectos <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Image>a <xref:System.Windows.Media.DrawingVisual>objetos visuales, como un , , , o <xref:System.Windows.UIElement>, es tan fácil como establecer una propiedad. <xref:System.Windows.UIElement.BitmapEffect%2A>se puede establecer <xref:System.Windows.Media.Effects.BitmapEffect> en un solo objeto o se <xref:System.Windows.Media.Effects.BitmapEffectGroup> pueden encadenar varios efectos mediante el objeto.  
  
 En el ejemplo siguiente se <xref:System.Windows.Media.Effects.BitmapEffect> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]muestra cómo aplicar un in .  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 En el ejemplo siguiente se <xref:System.Windows.Media.Effects.BitmapEffect> muestra cómo aplicar un código in.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
> Cuando <xref:System.Windows.Media.Effects.BitmapEffect> a se aplica a un <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Canvas>contenedor de diseño, como o , el efecto se aplica al árbol visual del elemento o objeto visual, incluidos todos sus elementos secundarios.  
  
<a name="customeffects"></a>
## <a name="creating-custom-effects"></a>Crear efectos personalizados  
 WPFWPF también proporciona interfaces no administradas para crear efectos personalizados que se pueden usar en aplicaciones WPF administradas. Para obtener material de referencia adicional para crear efectos de imagen personalizados, consulte la documentación de [Unmanaged WPF Bitmap Effect](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh) (Efecto de imagen de WPF no administrado).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Effects.BitmapEffectGroup>
- <xref:System.Windows.Media.Effects.BitmapEffectInput>
- <xref:System.Windows.Media.Effects.BitmapEffectCollection>
- [Efecto de imagen de WPF no administrado](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh)
- [Información general sobre imágenes](imaging-overview.md)
- [Seguridad](../security-wpf.md)
- [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md)
- [Imágenes y gráficos 2D](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
