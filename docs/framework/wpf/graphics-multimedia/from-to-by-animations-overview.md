---
title: Descripción general de las animaciones de uso por medio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
ms.openlocfilehash: 135f01823d374b30f8d4d41762d2267a254f98c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186459"
---
# <a name="fromtoby-animations-overview"></a>Información general sobre animaciones From/To/By
En este tema se describe cómo usar animaciones From/To/By para animar propiedades de dependencia. Una animación From/To/By crea una transición entre dos valores.  
  
<a name="prereq"></a>
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] estar familiarizado con las características de animaciones. Para obtener una introducción a las características de animación, consulte [Información general sobre animaciones](animation-overview.md).  
  
<a name="whatisanimation"></a>
## <a name="what-is-a-fromtoby-animation"></a>¿Qué es una animación From/To/By?  
 Una animación From/To/By <xref:System.Windows.Media.Animation.AnimationTimeline> es un tipo que crea una transición entre un valor inicial y un valor final. La cantidad de tiempo que tarda la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> transición en completarse viene determinada por la animación de esa.  
  
 Puede aplicar un From/To/By animación a <xref:System.Windows.Media.Animation.Storyboard> una propiedad mediante un <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> en el marcado y el código, o mediante el método en el código. También puede utilizar una animación From/To/By para crear una <xref:System.Windows.Media.Animation.AnimationClock> y aplicarla a una o más propiedades. Para más información sobre los distintos métodos para aplicar animaciones, consulte la [Información general sobre técnicas de animación de propiedades](property-animation-techniques-overview.md).  
  
 Las animaciones From/To/By no pueden tener más de dos valores de destino. Si necesita una animación que tenga más de dos valores de destino, use una animación de fotogramas clave. Las animaciones de fotogramas clave se describen en Información general sobre [animaciones de fotogramas](key-frame-animations-overview.md)clave .  
  
<a name="animation_types"></a>
## <a name="fromtoby-animation-types"></a>Tipos de animaciones From/To/By  
 Dado que las animaciones generan valores de propiedad, existen distintos tipos de animaciones para los diversos tipos de propiedades. Para animar una propiedad <xref:System.Double>que toma <xref:System.Windows.FrameworkElement.Width%2A> un , como la propiedad <xref:System.Double> de un elemento, utilice una animación que produzca valores. Para animar una propiedad <xref:System.Windows.Point>que toma un <xref:System.Windows.Point> , utilice una animación que produzca valores, etc.  
  
 Las clases de animación <xref:System.Windows.Media.Animation> From/To/By pertenecen al espacio de nombres y usan la siguiente convención de nomenclatura:  
  
 * \<Tipo>*`Animation`  
  
 Donde * \<Type>* es el tipo de valor que anima la clase.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona las siguientes clases de animación From/To/By.  
  
|Tipo de propiedad|Clase de animación From/To/By correspondiente|  
|-------------------|------------------------------------------------|  
|<xref:System.Byte>|<xref:System.Windows.Media.Animation.ByteAnimation>|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|  
|<xref:System.Decimal>|<xref:System.Windows.Media.Animation.DecimalAnimation>|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|  
|<xref:System.Int16>|<xref:System.Windows.Media.Animation.Int16Animation>|  
|<xref:System.Int32>|<xref:System.Windows.Media.Animation.Int32Animation>|  
|<xref:System.Int64>|<xref:System.Windows.Media.Animation.Int64Animation>|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|  
|<xref:System.Windows.Media.Media3D.Quaternion>|<xref:System.Windows.Media.Animation.QuaternionAnimation>|  
|<xref:System.Windows.Rect>|<xref:System.Windows.Media.Animation.RectAnimation>|  
|<xref:System.Windows.Media.Media3D.Rotation3D>|<xref:System.Windows.Media.Animation.Rotation3DAnimation>|  
|<xref:System.Single>|<xref:System.Windows.Media.Animation.SingleAnimation>|  
|<xref:System.Windows.Size>|<xref:System.Windows.Media.Animation.SizeAnimation>|  
|<xref:System.Windows.Thickness>|<xref:System.Windows.Media.Animation.ThicknessAnimation>|  
|<xref:System.Windows.Media.Media3D.Vector3D>|<xref:System.Windows.Media.Animation.Vector3DAnimation>|  
|<xref:System.Windows.Vector>|<xref:System.Windows.Media.Animation.VectorAnimation>|  
  
<a name="anim_values"></a>
## <a name="target-values"></a>Valores de destino  
 Una animación From/To/By crea una transición entre dos valores de destino. Es común especificar un valor inicial (establecerlo mediante la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad) y un <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> valor final (establecerlo mediante la propiedad). Pero también se puede especificar solo un valor inicial, un valor de destino o un valor de desplazamiento. En estos casos, la animación obtiene el valor de destino que falta de la propiedad que se anima. La lista siguiente describe las diferentes maneras de especificar los valores de destino de una animación.  
  
- **Valor inicial**  
  
     Utilice <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> la propiedad cuando desee especificar explícitamente el valor inicial de una animación. Puede utilizar <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> la propiedad por sí <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> misma, o con la propiedad o. Si especifica solo <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> la propiedad, la animación pasa de ese valor al valor base de la propiedad animada.  
  
- **Valor final**  
  
     Para especificar un valor final de <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> una animación, utilice su propiedad. Si utiliza <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> la propiedad por sí misma, la animación obtiene su valor inicial de la propiedad que se está animando o de la salida de otra animación que se aplica a la misma propiedad. Puede utilizar <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> junto con la propiedad para especificar explícitamente los valores inicial y final de la animación.  
  
- **Valor de desplazamiento**  
  
     La <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad permite especificar un desplazamiento en lugar de un valor inicial o final explícito para la animación. La <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad de una animación especifica cuánto cambia la animación un valor a lo largo de su duración. Puede utilizar <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> la propiedad por <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> sí misma o con la propiedad. Si especifica solo <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> la propiedad, la animación agrega el valor de desplazamiento al valor base de la propiedad o a la salida de otra animación.  
  
<a name="examples"></a>
## <a name="using-fromtoby-values"></a>Usar valores From/To/By  
 En las secciones siguientes <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>se <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> describe cómo utilizar las propiedades , , y juntas o por separado.  
  
 Los ejemplos de esta <xref:System.Windows.Media.Animation.DoubleAnimation>sección utilizan cada uno un , que es <xref:System.Windows.FrameworkElement.Width%2A> un tipo <xref:System.Windows.Shapes.Rectangle> de animación From/To/By, para animar la propiedad de un que tiene 10 píxeles independientes del dispositivo de alto y 100 píxeles independientes del dispositivo de ancho.  
  
 Aunque cada ejemplo <xref:System.Windows.Media.Animation.DoubleAnimation>utiliza un , el From, To, y By propiedades de todas las from/To/By animaciones se comportan de forma idéntica. Aunque cada uno de <xref:System.Windows.Media.Animation.Storyboard>estos ejemplos utiliza un , puede usar animaciones From/To/By de otras maneras. Para obtener más información, vea [Información general sobre técnicas](property-animation-techniques-overview.md)de animación de propiedades .  
  
### <a name="fromto"></a>De/Para  
 Cuando se <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> establecen los valores y <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> juntos, la animación <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> progresa desde el valor especificado <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> por la propiedad hasta el valor especificado por la propiedad.  
  
 En el ejemplo <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> siguiente <xref:System.Windows.Media.Animation.DoubleAnimation> se establece la <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad de la en 50 y su propiedad en 300. Como resultado, <xref:System.Windows.FrameworkElement.Width%2A> el <xref:System.Windows.Shapes.Rectangle> de la está animada de 50 a 300.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>A  
 Cuando se establece <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> solo la propiedad, la animación progresa desde el valor base de la propiedad animada, o desde la salida de <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> una animación de composición que se aplicó anteriormente a la misma propiedad, hasta el valor especificado por la propiedad.  
  
 ("Animación de composición" <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.ClockState.Filling> hace referencia a una o animación que se aplicó anteriormente <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> a la misma propiedad que todavía está en vigor cuando se aplicó la animación actual mediante el comportamiento de entrega.)  
  
 En el ejemplo <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> siguiente se <xref:System.Windows.Media.Animation.DoubleAnimation> establece solo la propiedad de la 300. Dado que no se especificó ningún valor inicial, <xref:System.Windows.Media.Animation.DoubleAnimation> utiliza <xref:System.Windows.FrameworkElement.Width%2A> el valor base (100) de la propiedad como su valor inicial. El <xref:System.Windows.FrameworkElement.Width%2A> de <xref:System.Windows.Shapes.Rectangle> la está animada de 100 al valor objetivo de la animación de 300.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>Por  
 Cuando se establece <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> solo la propiedad de una animación, la animación progresa desde el valor base de la propiedad que se está animando, o desde la salida de una animación de composición a la suma de ese valor y el valor especificado por la <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad.  
  
 En el ejemplo <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> siguiente se <xref:System.Windows.Media.Animation.DoubleAnimation> establece solo la propiedad de la 300. Dado que el ejemplo no especifica <xref:System.Windows.Media.Animation.DoubleAnimation> un valor inicial, utiliza el valor base de la <xref:System.Windows.FrameworkElement.Width%2A> propiedad, 100, como su valor inicial. El valor final se <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> determina agregando el valor de la animación, 300, a su valor inicial, 100: 400. Como resultado, <xref:System.Windows.FrameworkElement.Width%2A> el <xref:System.Windows.Shapes.Rectangle> de la está animada de 100 a 400.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 Al establecer <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> las <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedades y de una animación, la animación <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> progresa desde el valor especificado por la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad hasta el valor especificado por la suma de las propiedades.  
  
 En el ejemplo <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> siguiente <xref:System.Windows.Media.Animation.DoubleAnimation> se establece la <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad de la en 50 y su propiedad en 300. El valor final se <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> determina agregando el valor de la animación, 300, a su valor inicial, 50: 350. Como resultado, <xref:System.Windows.FrameworkElement.Width%2A> el <xref:System.Windows.Shapes.Rectangle> de la está animada de 50 a 350.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>De  
 Cuando se especifica <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> solo el valor de una animación, la animación progresa desde el valor especificado por la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad, hasta el valor base de la propiedad que se está animando o a la salida de una animación de composición.  
  
 En el ejemplo <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> siguiente se <xref:System.Windows.Media.Animation.DoubleAnimation> establece solo la propiedad de la 50. Dado que no se especificó ningún valor final, utiliza <xref:System.Windows.Media.Animation.DoubleAnimation> el valor base de la <xref:System.Windows.FrameworkElement.Width%2A> propiedad, 100, como su valor final. El <xref:System.Windows.FrameworkElement.Width%2A> de <xref:System.Windows.Shapes.Rectangle> la está animada de 50 <xref:System.Windows.FrameworkElement.Width%2A> al valor base de la propiedad, 100.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 Si establece las <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedades <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> y las de <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> una animación, se omite la propiedad.  
  
<a name="otheranimationtypes"></a>
## <a name="other-animation-types"></a>Otros tipos de animación  
 Las animaciones From/To/By no son el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] único tipo de animaciones que proporciona: también proporciona animaciones de fotogramas clave y animaciones de ruta.  
  
- Una animación de fotogramas clave se anima a lo largo de cualquier cantidad de valores de destino, que se describen mediante fotogramas clave. Para obtener más información, consulte Información general sobre [animaciones de fotogramas](key-frame-animations-overview.md)clave .  
  
- Una animación de ruta <xref:System.Windows.Media.PathGeometry>genera valores de salida a partir de un archivo . Para obtener más información, consulte Información general sobre [animaciones](path-animations-overview.md)de ruta de acceso .  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también le permite crear sus propios tipos de animaciones personalizadas. Para obtener más información, consulte [Información general sobre animaciones personalizadas](custom-animations-overview.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre objetos Storyboard ](storyboards-overview.md)
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Información general sobre animaciones en trazados ](path-animations-overview.md)
- [Información general sobre animaciones personalizadas](custom-animations-overview.md)
- [Ejemplo de valores de destino de animación From, To y By](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)
