---
title: Información general sobre efectos de imagen
ms.date: 03/30/2017
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: 4a5c304363efe7d0e9bd9e14ff916f8d852ab3a8
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636021"
---
# <a name="bitmap-effects-overview"></a>Información general sobre efectos de imagen
Los efectos de imagen permiten a los diseñadores y desarrolladores aplicar efectos visuales a contenido representado Windows Presentation Foundation (WPF). Por ejemplo, los efectos de imagen permiten aplicar fácilmente un efecto de <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> o un efecto de desenfoque a una imagen o un botón.  
  
> [!IMPORTANT]
> En el .NET Framework 4 o posterior, la clase <xref:System.Windows.Media.Effects.BitmapEffect> está obsoleta. Si intenta utilizar la clase <xref:System.Windows.Media.Effects.BitmapEffect>, obtendrá una excepción obsoleta. La alternativa no obsoleta a la clase <xref:System.Windows.Media.Effects.BitmapEffect> es la clase <xref:System.Windows.Media.Effects.Effect>. En la mayoría de los casos, la clase <xref:System.Windows.Media.Effects.Effect> es significativamente más rápida.  

<a name="wpf_effects"></a>   
## <a name="wpf-bitmap-effects"></a>Efectos de imagen de WPF  
 Los efectos de imagen (objeto<xref:System.Windows.Media.Effects.BitmapEffect>) son operaciones de procesamiento de píxeles simples. Un efecto de mapa de bits toma un <xref:System.Windows.Media.Imaging.BitmapSource> como entrada y genera un nuevo <xref:System.Windows.Media.Imaging.BitmapSource> después de aplicar el efecto, como un desenfoque o una sombra paralela. Cada efecto de imagen expone propiedades que pueden controlar las propiedades de filtrado, como <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> de <xref:System.Windows.Media.Effects.BlurBitmapEffect>.  
  
 Como caso especial, en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], los efectos pueden establecerse como propiedades de objetos <xref:System.Windows.Media.Visual> activos, como un <xref:System.Windows.Controls.Button> o <xref:System.Windows.Controls.TextBox>. El procesamiento de píxeles se aplica y se representa en tiempo de ejecución. En este caso, en el momento de la representación, un <xref:System.Windows.Media.Visual> se convierte automáticamente a su <xref:System.Windows.Media.Imaging.BitmapSource> equivalente y se introduce como entrada para el <xref:System.Windows.Media.Effects.BitmapEffect>. La salida reemplaza el comportamiento de representación predeterminado del objeto <xref:System.Windows.Media.Visual>. Este es el motivo por el que <xref:System.Windows.Media.Effects.BitmapEffect> objetos hacen que los objetos visuales se representen solo en el software, es decir, no hay aceleración de hardware en objetos visuales cuando se aplican efectos.  
  
- <xref:System.Windows.Media.Effects.BlurBitmapEffect> simula un objeto que aparece como desenfocado.  
  
- <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect> crea un halo de color alrededor del perímetro de un objeto.  
  
- <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> crea una sombra detrás de un objeto.  
  
- <xref:System.Windows.Media.Effects.BevelBitmapEffect> crea un bisel que eleva la superficie de una imagen según una curva especificada.  
  
- <xref:System.Windows.Media.Effects.EmbossBitmapEffect> crea una asignación de rugosidad de un <xref:System.Windows.Media.Visual> para dar la impresión de profundidad y textura de una fuente de luz artificial.  
  
> [!NOTE]
> Los efectos de imagen de WPF se representan en modo de software. Cualquier objeto que aplique un efecto también se representará en software. El rendimiento disminuye al máximo al usar los efectos de imagen en objetos visuales grandes o al animar las propiedades de un efecto de imagen. Esto no quiere decir que no se deben usar efectos de imagen de esta manera en absoluto, pero hay que tener cuidado y probarlos exhaustivamente para asegurarse de que los usuarios obtengan la experiencia esperada.  
  
> [!NOTE]
> Los efectos de imagen de WPF no admiten la ejecución de confianza parcial. Una aplicación debe tener permisos de plena confianza para usar efectos de imagen.  
  
<a name="applyeffects"></a>   
## <a name="how-to-apply-an-effect"></a>Cómo aplicar un efecto  
 <xref:System.Windows.Media.Effects.BitmapEffect> es una propiedad de <xref:System.Windows.Media.Visual>. Por lo tanto, aplicar efectos a objetos visuales, como un <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual>o <xref:System.Windows.UIElement>, es tan sencillo como establecer una propiedad. <xref:System.Windows.UIElement.BitmapEffect%2A> se puede establecer en un objeto de <xref:System.Windows.Media.Effects.BitmapEffect> único o se pueden encadenar varios efectos mediante el objeto <xref:System.Windows.Media.Effects.BitmapEffectGroup>.  
  
 En el ejemplo siguiente se muestra cómo aplicar un <xref:System.Windows.Media.Effects.BitmapEffect> en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 En el ejemplo siguiente se muestra cómo aplicar un <xref:System.Windows.Media.Effects.BitmapEffect> en el código.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
> Cuando se aplica un <xref:System.Windows.Media.Effects.BitmapEffect> a un contenedor de diseño, como <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.Controls.Canvas>, el efecto se aplica al árbol visual del elemento u objetos visuales, incluidos todos sus elementos secundarios.  
  
<a name="customeffects"></a>   
## <a name="creating-custom-effects"></a>Crear efectos personalizados  
 WPF también proporciona interfaces no administradas para crear efectos personalizados que se pueden usar en aplicaciones WPF administradas. Para obtener material de referencia adicional para crear efectos de imagen personalizados, consulte la documentación de [Unmanaged WPF Bitmap Effect](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh) (Efecto de imagen de WPF no administrado).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Effects.BitmapEffectGroup>
- <xref:System.Windows.Media.Effects.BitmapEffectInput>
- <xref:System.Windows.Media.Effects.BitmapEffectCollection>
- [Efecto de imagen de WPF no administrado](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh)
- [Información general sobre imágenes](imaging-overview.md)
- [Seguridad](../security-wpf.md)
- [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md)
- [Imágenes y gráficos 2D](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
