---
title: Información general sobre efectos de imagen
ms.date: 03/30/2017
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: f2fa42d5d63cad6a71efd259416dad3416bf2d72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935299"
---
# <a name="bitmap-effects-overview"></a>Información general sobre efectos de imagen
Los efectos de imagen permiten a los diseñadores y desarrolladores aplicar efectos visuales a contenido representado Windows Presentation Foundation (WPF). Por ejemplo, los efectos de imagen permiten aplicar fácilmente un <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> efecto o un efecto de desenfoque a una imagen o un botón.  
  
> [!IMPORTANT]
> En el .NET Framework 4 o posterior, la <xref:System.Windows.Media.Effects.BitmapEffect> clase está obsoleta. Si intenta utilizar la <xref:System.Windows.Media.Effects.BitmapEffect> clase, obtendrá una excepción obsoleta. La alternativa no obsoleta a la <xref:System.Windows.Media.Effects.BitmapEffect> clase es la <xref:System.Windows.Media.Effects.Effect> clase. En la mayoría de los <xref:System.Windows.Media.Effects.Effect> casos, la clase es significativamente más rápida.  

<a name="wpf_effects"></a>   
## <a name="wpf-bitmap-effects"></a>Efectos de imagen de WPF  
 Los efectos de<xref:System.Windows.Media.Effects.BitmapEffect> imagen (objeto) son operaciones de procesamiento de píxeles simples. Un efecto de mapa de <xref:System.Windows.Media.Imaging.BitmapSource> bits toma como entrada y genera un <xref:System.Windows.Media.Imaging.BitmapSource> nuevo después de aplicar el efecto, como un desenfoque o una sombra paralela. Cada efecto <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> de imagen expone propiedades que pueden controlar las propiedades de filtrado, como de <xref:System.Windows.Media.Effects.BlurBitmapEffect>.  
  
 Como caso especial [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], en, los efectos pueden establecerse como propiedades de <xref:System.Windows.Controls.Button> objetos <xref:System.Windows.Media.Visual> activos, como o <xref:System.Windows.Controls.TextBox>. El procesamiento de píxeles se aplica y se representa en tiempo de ejecución. En este caso, en el momento de la representación, <xref:System.Windows.Media.Visual> se convierte automáticamente en su <xref:System.Windows.Media.Imaging.BitmapSource> equivalente y se <xref:System.Windows.Media.Effects.BitmapEffect>introduce como entrada para. La salida reemplaza el <xref:System.Windows.Media.Visual> comportamiento de representación predeterminado del objeto. Este es el <xref:System.Windows.Media.Effects.BitmapEffect> motivo por el que los objetos se pueden representar en el software solo, es decir, no hay aceleración de hardware en los objetos visuales cuando se aplican efectos.  
  
- <xref:System.Windows.Media.Effects.BlurBitmapEffect>simula un objeto que aparece como desenfocado.  
  
- <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect>crea un halo de color alrededor del perímetro de un objeto.  
  
- <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>crea una sombra detrás de un objeto.  
  
- <xref:System.Windows.Media.Effects.BevelBitmapEffect>crea un bisel que eleva la superficie de una imagen según una curva especificada.  
  
- <xref:System.Windows.Media.Effects.EmbossBitmapEffect>crea una asignación de rugosidad de <xref:System.Windows.Media.Visual> un para dar la impresión de profundidad y textura de una fuente de luz artificial.  
  
> [!NOTE]
> Los efectos de imagen de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se representan en modo de software. Cualquier objeto que aplique un efecto también se representará en software. El rendimiento disminuye al máximo al usar los efectos de imagen en objetos visuales grandes o al animar las propiedades de un efecto de imagen. Esto no quiere decir que no se deben usar efectos de imagen de esta manera en absoluto, pero hay que tener cuidado y probarlos exhaustivamente para asegurarse de que los usuarios obtengan la experiencia esperada.  
  
> [!NOTE]
> Los efectos de imagen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] no admiten la ejecución de confianza parcial. Una aplicación debe tener permisos de plena confianza para usar efectos de imagen.  
  
<a name="applyeffects"></a>   
## <a name="how-to-apply-an-effect"></a>Cómo aplicar un efecto  
 <xref:System.Windows.Media.Effects.BitmapEffect>es una propiedad de <xref:System.Windows.Media.Visual>. Por lo tanto, aplicar efectos a objetos visuales, <xref:System.Windows.Controls.Button>como <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual>, o <xref:System.Windows.UIElement>, es tan sencillo como establecer una propiedad. <xref:System.Windows.UIElement.BitmapEffect%2A>se puede establecer en un solo <xref:System.Windows.Media.Effects.BitmapEffect> objeto o varios efectos se pueden encadenar mediante el <xref:System.Windows.Media.Effects.BitmapEffectGroup> objeto.  
  
 En el ejemplo siguiente se muestra cómo aplicar <xref:System.Windows.Media.Effects.BitmapEffect> un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]en.  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 En el ejemplo siguiente se muestra cómo aplicar <xref:System.Windows.Media.Effects.BitmapEffect> un en el código.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
> Cuando se <xref:System.Windows.Media.Effects.BitmapEffect> aplica un a un contenedor de diseño, <xref:System.Windows.Controls.DockPanel> como o <xref:System.Windows.Controls.Canvas>, el efecto se aplica al árbol visual del elemento u objetos visuales, incluidos todos sus elementos secundarios.  
  
<a name="customeffects"></a>   
## <a name="creating-custom-effects"></a>Crear efectos personalizados  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] también proporciona interfaces no administradas para crear efectos personalizados que pueden utilizarse en aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] administradas. Para obtener material de referencia adicional para crear efectos de imagen personalizados, consulte la documentación de [Unmanaged WPF Bitmap Effect](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh) (Efecto de imagen de WPF no administrado).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Effects.BitmapEffectGroup>
- <xref:System.Windows.Media.Effects.BitmapEffectInput>
- <xref:System.Windows.Media.Effects.BitmapEffectCollection>
- [Efecto de imagen de WPF no administrado](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh)
- [Información general sobre imágenes](imaging-overview.md)
- [Seguridad](../security-wpf.md)
- [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md)
- [Imágenes y gráficos 2D](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
