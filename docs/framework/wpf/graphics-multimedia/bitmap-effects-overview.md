---
title: Información general sobre efectos de imagen
ms.date: 03/30/2017
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: 1866ba7a5419ea435a56daa63f94122d3b83473e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61752755"
---
# <a name="bitmap-effects-overview"></a>Información general sobre efectos de imagen
Los efectos de imagen permiten a los diseñadores y desarrolladores para aplicar efectos visuales a contenidos representan en Windows Presentation Foundation (WPF). Por ejemplo, los efectos de imagen permiten aplicar con facilidad un <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> efecto o un efecto de desenfoque a una imagen o un botón.  
  
> [!IMPORTANT]
>  En el [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] o versiones posteriores, el <xref:System.Windows.Media.Effects.BitmapEffect> clase está obsoleta. Si intenta usar el <xref:System.Windows.Media.Effects.BitmapEffect> (clase), obtendrá una excepción obsoleta. La alternativa no obsoleta a la <xref:System.Windows.Media.Effects.BitmapEffect> clase es el <xref:System.Windows.Media.Effects.Effect> clase. En la mayoría de los casos, la <xref:System.Windows.Media.Effects.Effect> clase es significativamente más rápida.  

<a name="wpf_effects"></a>   
## <a name="wpf-bitmap-effects"></a>Efectos de imagen de WPF  
 Efectos de imagen (<xref:System.Windows.Media.Effects.BitmapEffect> objeto) son operaciones de procesamiento de píxeles simples. Un efecto de mapa de bits toma una <xref:System.Windows.Media.Imaging.BitmapSource> como entrada y genera un nuevo <xref:System.Windows.Media.Imaging.BitmapSource> después de aplicar el efecto, como un desenfoque o una sombra. Cada efecto de imagen expone propiedades que pueden controlar las propiedades de filtrado, como <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> de <xref:System.Windows.Media.Effects.BlurBitmapEffect>.  
  
 Como caso especial, en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], los efectos se pueden establecer como propiedades en vivo <xref:System.Windows.Media.Visual> objetos, como un <xref:System.Windows.Controls.Button> o <xref:System.Windows.Controls.TextBox>. El procesamiento de píxeles se aplica y se representa en tiempo de ejecución. En este caso, en el momento de la representación, un <xref:System.Windows.Media.Visual> se convierte automáticamente en su <xref:System.Windows.Media.Imaging.BitmapSource> equivalentes y se introduce como entrada para el <xref:System.Windows.Media.Effects.BitmapEffect>. La salida reemplaza el <xref:System.Windows.Media.Visual> comportamiento de representación predeterminado del objeto. Por ello <xref:System.Windows.Media.Effects.BitmapEffect> objetos forzar los objetos visuales para no representar en el software solo; es decir, aceleración de hardware en objetos visuales cuando se aplican efectos.  
  
- <xref:System.Windows.Media.Effects.BlurBitmapEffect> simula un objeto que aparece fuera de foco.  
  
- <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect> crea un halo de color alrededor del perímetro de un objeto.  
  
- <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> crea una sombra detrás de un objeto.  
  
- <xref:System.Windows.Media.Effects.BevelBitmapEffect> crea un bisel que eleva la superficie de una imagen según una curva especificada.  
  
- <xref:System.Windows.Media.Effects.EmbossBitmapEffect> crea un mapa de rugosidad de un <xref:System.Windows.Media.Visual> para dar la impresión de profundidad y textura de una fuente de luz artificial.  
  
> [!NOTE]
>  Los efectos de imagen de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se representan en modo de software. Cualquier objeto que aplique un efecto también se representará en software. El rendimiento disminuye al máximo al usar los efectos de imagen en objetos visuales grandes o al animar las propiedades de un efecto de imagen. Esto no quiere decir que no se deben usar efectos de imagen de esta manera en absoluto, pero hay que tener cuidado y probarlos exhaustivamente para asegurarse de que los usuarios obtengan la experiencia esperada.  
  
> [!NOTE]
>  Los efectos de imagen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] no admiten la ejecución de confianza parcial. Una aplicación debe tener permisos de plena confianza para usar efectos de imagen.  
  
<a name="applyeffects"></a>   
## <a name="how-to-apply-an-effect"></a>Cómo aplicar un efecto  
 <xref:System.Windows.Media.Effects.BitmapEffect> es una propiedad de <xref:System.Windows.Media.Visual>. Por lo tanto, aplicar efectos a objetos visuales, como un <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual>, o <xref:System.Windows.UIElement>, es tan fácil como establecer una propiedad. <xref:System.Windows.UIElement.BitmapEffect%2A> se puede establecer en una sola <xref:System.Windows.Media.Effects.BitmapEffect> objeto o varios efectos pueden encadenarse utilizando el <xref:System.Windows.Media.Effects.BitmapEffectGroup> objeto.  
  
 En el ejemplo siguiente se muestra cómo aplicar un <xref:System.Windows.Media.Effects.BitmapEffect> en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 En el ejemplo siguiente se muestra cómo aplicar un <xref:System.Windows.Media.Effects.BitmapEffect> en el código.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
>  Cuando un <xref:System.Windows.Media.Effects.BitmapEffect> se aplica a un contenedor de diseño, como <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.Controls.Canvas>, el efecto se aplica al árbol visual del elemento u objeto visual, incluidos todos sus elementos secundarios.  
  
<a name="customeffects"></a>   
## <a name="creating-custom-effects"></a>Crear efectos personalizados  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] también proporciona interfaces no administradas para crear efectos personalizados que pueden utilizarse en aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] administradas. Para obtener material de referencia adicional para crear efectos de imagen personalizados, consulte la documentación de [Unmanaged WPF Bitmap Effect](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh) (Efecto de imagen de WPF no administrado).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Effects.BitmapEffectGroup>
- <xref:System.Windows.Media.Effects.BitmapEffectInput>
- <xref:System.Windows.Media.Effects.BitmapEffectCollection>
- [Efecto de mapa de bits WPF no administrado](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh)
- [Información general sobre imágenes](imaging-overview.md)
- [Seguridad](../security-wpf.md)
- [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md)
- [Imágenes y gráficos 2D](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
