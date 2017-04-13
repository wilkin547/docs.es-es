---
title: "Informaci&#243;n general sobre efectos de imagen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "efectos de imagen"
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# Informaci&#243;n general sobre efectos de imagen
Los efectos de imagen permiten a los diseñadores y programadores aplicar efectos visuales al contenido [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] representado.  Por ejemplo, los efectos de imagen permiten aplicar con facilidad un efecto <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> o un efecto de desenfoque a una imagen o un botón.  
  
> [!IMPORTANT]
>  En [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] o posterior, la clase <xref:System.Windows.Media.Effects.BitmapEffect> está obsoleta.  Si intenta utilizar la clase <xref:System.Windows.Media.Effects.BitmapEffect>, obtendrá una excepción obsoleta.  La alternativa no obsoleta a la clase <xref:System.Windows.Media.Effects.BitmapEffect> es la clase <xref:System.Windows.Media.Effects.Effect>.  En la mayoría de las situaciones, la clase <xref:System.Windows.Media.Effects.Effect> es significativamente más rápida.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="wpf_effects"></a>   
## Efectos de imagen en WPF  
 Los efectos de imagen \(objeto <xref:System.Windows.Media.Effects.BitmapEffect>\) son operaciones simples de procesamiento de píxeles.  Un efecto de imagen acepta un objeto <xref:System.Windows.Media.Imaging.BitmapSource> como entrada y genera un nuevo <xref:System.Windows.Media.Imaging.BitmapSource> después de aplicar el efecto, como un desenfoque o una sombra.  Cada efecto de imagen expone propiedades que pueden controlar las propiedades de filtrado, como <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> de <xref:System.Windows.Media.Effects.BlurBitmapEffect>.  
  
 Como caso especial, en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], los efectos se pueden establecer como propiedades en los objetos <xref:System.Windows.Media.Visual> activos, como <xref:System.Windows.Controls.Button> o <xref:System.Windows.Controls.TextBox>.  El procesamiento de píxeles se aplica y representa en tiempo de ejecución.  En este caso, al realizar la representación, un objeto <xref:System.Windows.Media.Visual> se convierte automáticamente en su <xref:System.Windows.Media.Imaging.BitmapSource> equivalente y se utiliza como datos de entrada en <xref:System.Windows.Media.Effects.BitmapEffect>.  El resultado reemplaza el comportamiento de representación predeterminado del objeto <xref:System.Windows.Media.Visual>.  Por este motivo, los objetos <xref:System.Windows.Media.Effects.BitmapEffect> fuerzan la presentación de los objetos visuales únicamente en software, es decir,  no se aplica ninguna aceleración de hardware a los elementos visuales cuando se aplican efectos.  
  
-   <xref:System.Windows.Media.Effects.BlurBitmapEffect> simula un objeto que parece desenfocado.  
  
-   <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect> crea un halo de color alrededor del perímetro de un objeto.  
  
-   <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> crea una sombra detrás de un objeto.  
  
-   <xref:System.Windows.Media.Effects.BevelBitmapEffect> crea un ángulo oblicuo que eleva la superficie de una imagen de acuerdo con una curva especificada.  
  
-   <xref:System.Windows.Media.Effects.EmbossBitmapEffect> crea un mapa de rugosidad de un objeto <xref:System.Windows.Media.Visual> a fin de dar la impresión de profundidad y textura a partir de una fuente de luz artificial.  
  
> [!NOTE]
>  Los efectos de imagen de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se representan en modo de software.  Cualquier objeto que aplique un efecto también se presenta por software.  Cuando más se degrada el rendimiento es al utilizar efectos de imagen en objetos visuales grandes o al animar las propiedades de un efecto de imagen.  Esto no quiere decir que no haya que utilizar nunca los efectos de imagen, pero sí debe extremar las precauciones y efectuar pruebas exhaustivas para asegurarse de que los usuarios obtengan la experiencia esperada.  
  
> [!NOTE]
>  Los efectos de imagen de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] no admiten la ejecución de confianza parcial.  Una aplicación debe tener permisos de plena confianza para usar efectos de imagen.  
  
<a name="applyeffects"></a>   
## Cómo aplicar un efecto  
 <xref:System.Windows.Media.Effects.BitmapEffect> es una propiedad de <xref:System.Windows.Media.Visual>.  Así pues, aplicar efectos a los objetos visuales, tales como <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual> o <xref:System.Windows.UIElement>, es tan sencillo como establecer la propiedad.  <xref:System.Windows.UIElement.BitmapEffect%2A> se puede establecer en un solo objeto <xref:System.Windows.Media.Effects.BitmapEffect>, pero también se pueden encadenar varios efectos mediante el objeto<xref:System.Windows.Media.Effects.BitmapEffectGroup>.  
  
 En el ejemplo de código siguiente se muestra cómo se aplica <xref:System.Windows.Media.Effects.BitmapEffect> en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xml[EffectsGallery_snip#BlurSimpleExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 En el ejemplo de código siguiente se muestra cómo se aplica <xref:System.Windows.Media.Effects.BitmapEffect> mediante código.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
>  Cuando <xref:System.Windows.Media.Effects.BitmapEffect> se aplica a un contenedor de diseño, como <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.Controls.Canvas>, el efecto se aplica al árbol visual del elemento u objeto visual, incluidos todos sus elementos secundarios.  
  
<a name="customeffects"></a>   
## Crear efectos personalizados  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] también proporciona interfaces no administradas para crear efectos personalizados que se pueden usar en aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] administradas.  Si desea obtener material de referencia adicional para crear efectos de imagen personalizados, consulte la documentación de [Unmanaged WPF Bitmap Effect](_wibe_lh).  
  
## Vea también  
 <xref:System.Windows.Media.Effects.BitmapEffectGroup>   
 <xref:System.Windows.Media.Effects.BitmapEffectInput>   
 <xref:System.Windows.Media.Effects.BitmapEffectCollection>   
 [Unmanaged WPF Bitmap Effect](_wibe_lh)   
 [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)   
 [Seguridad](../../../../docs/framework/wpf/security-wpf.md)   
 [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [Imágenes y gráficos GDI\+](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)