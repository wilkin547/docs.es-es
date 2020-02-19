---
title: Información general sobre animaciones From-to-by
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
ms.openlocfilehash: 661c035f55ba1fb550726d75921cd01a72b2eecc
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449015"
---
# <a name="fromtoby-animations-overview"></a>Información general sobre animaciones From/To/By
En este tema se describe cómo usar animaciones From/To/By para animar propiedades de dependencia. Una animación From/To/By crea una transición entre dos valores.  
  
<a name="prereq"></a>   
## <a name="prerequisites"></a>Prerequisites  
 Para entender este tema, debe estar familiarizado con las características de animaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Para ver una introducción a las características de animación, consulte [información general sobre animaciones](animation-overview.md).  
  
<a name="whatisanimation"></a>   
## <a name="what-is-a-fromtoby-animation"></a>¿Qué es una animación From/To/By?  
 Una animación from/to/by es un tipo de <xref:System.Windows.Media.Animation.AnimationTimeline> que crea una transición entre un valor inicial y un valor final. La <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de esa animación determina la cantidad de tiempo que tarda en completarse la transición.  
  
 Puede aplicar una animación from/to/by a una propiedad mediante un <xref:System.Windows.Media.Animation.Storyboard> en el marcado y el código, o mediante el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> en el código. También puede usar una animación from/to/by para crear una <xref:System.Windows.Media.Animation.AnimationClock> y aplicarla a una o más propiedades. Para más información sobre los distintos métodos para aplicar animaciones, consulte la [Información general sobre técnicas de animación de propiedades](property-animation-techniques-overview.md).  
  
 Las animaciones From/To/By no pueden tener más de dos valores de destino. Si necesita una animación que tenga más de dos valores de destino, use una animación de fotogramas clave. Las animaciones de fotogramas clave se describen en [información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md).  
  
<a name="animation_types"></a>   
## <a name="fromtoby-animation-types"></a>Tipos de animaciones From/To/By  
 Dado que las animaciones generan valores de propiedad, existen distintos tipos de animaciones para los diversos tipos de propiedades. Para animar una propiedad que toma un <xref:System.Double>, como la propiedad <xref:System.Windows.FrameworkElement.Width%2A> de un elemento, utilice una animación que genere valores <xref:System.Double>. Para animar una propiedad que toma un <xref:System.Windows.Point>, utilice una animación que genere valores de <xref:System.Windows.Point>, etc.  
  
 Las clases de animación from/to/by pertenecen al espacio de nombres <xref:System.Windows.Media.Animation> y usan la siguiente Convención de nomenclatura:  
  
 *\<tipo >* `Animation`  
  
 Donde *\<Tipo>* es el tipo de valor que la clase anima.  
  
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
 Una animación From/To/By crea una transición entre dos valores de destino. Es habitual especificar un valor inicial (establézcalo mediante la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>) y un valor final (establézcalo mediante la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>). Pero también se puede especificar solo un valor inicial, un valor de destino o un valor de desplazamiento. En estos casos, la animación obtiene el valor de destino que falta de la propiedad que se anima. La lista siguiente describe las diferentes maneras de especificar los valores de destino de una animación.  
  
- **Valor inicial**  
  
     Utilice la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> cuando desee especificar explícitamente el valor inicial de una animación. Puede usar la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> por sí sola o con la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> o <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>. Si solo especifica la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, la animación realiza la transición desde ese valor al valor base de la propiedad animada.  
  
- **Valor final**  
  
     Para especificar un valor final de una animación, use su propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>. Si usa la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> por sí misma, la animación obtiene su valor inicial de la propiedad que se anima o desde la salida de otra animación que se aplica a la misma propiedad. Puede usar la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> junto con la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> para especificar explícitamente los valores inicial y final de la animación.  
  
- **Valor de desplazamiento**  
  
     La propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> permite especificar un desplazamiento en lugar de un valor de inicio o finalización explícito para la animación. La propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> de una animación especifica en qué parte la animación cambia un valor a lo largo de su duración. Puede usar la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> por sí sola o con la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>. Si solo especifica la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, la animación agrega el valor de desplazamiento al valor base de la propiedad o a la salida de otra animación.  
  
<a name="examples"></a>   
## <a name="using-fromtoby-values"></a>Usar valores From/To/By  
 En las secciones siguientes se describe cómo usar las propiedades <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> juntas o por separado.  
  
 En los ejemplos de esta sección se usa un <xref:System.Windows.Media.Animation.DoubleAnimation>, que es un tipo de animación from/to/by, para animar la propiedad <xref:System.Windows.FrameworkElement.Width%2A> de una <xref:System.Windows.Shapes.Rectangle> que es 10 píxeles independientes del dispositivo de alto y 100 píxeles independientes del dispositivo de ancho.  
  
 Aunque en cada ejemplo se usa un <xref:System.Windows.Media.Animation.DoubleAnimation>, las propiedades from, to y by de todas las animaciones From/to/by se comportan exactamente igual. Aunque cada uno de estos ejemplos usa una <xref:System.Windows.Media.Animation.Storyboard>, puede usar animaciones From/to/by de otras maneras. Para obtener más información, vea [información general sobre técnicas de animación de propiedades](property-animation-techniques-overview.md).  
  
### <a name="fromto"></a>De/Para  
 Al establecer los valores <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> juntos, la animación progresa desde el valor especificado por la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> hasta el valor especificado por la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.  
  
 En el ejemplo siguiente se establece la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> del <xref:System.Windows.Media.Animation.DoubleAnimation> en 50 y su propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> en 300. Como resultado, el <xref:System.Windows.FrameworkElement.Width%2A> del <xref:System.Windows.Shapes.Rectangle> se anima desde 50 a 300.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>A  
 Cuando se establece solo la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, la animación progresa desde el valor base de la propiedad animada o desde la salida de una animación compuesta que se aplicó previamente a la misma propiedad, hasta el valor especificado por la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.  
  
 ("Composición de animación" hace referencia a una animación <xref:System.Windows.Media.Animation.ClockState.Active> o <xref:System.Windows.Media.Animation.ClockState.Filling> que se aplicó previamente a la misma propiedad que todavía está en vigor cuando se aplicó la animación actual mediante el comportamiento de entrega de <xref:System.Windows.Media.Animation.HandoffBehavior.Compose>).  
  
 En el ejemplo siguiente se establece solo la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> del <xref:System.Windows.Media.Animation.DoubleAnimation> en 300. Dado que no se especificó ningún valor de inicio, el <xref:System.Windows.Media.Animation.DoubleAnimation> usa el valor base (100) de la propiedad <xref:System.Windows.FrameworkElement.Width%2A> como su valor de inicio. El <xref:System.Windows.FrameworkElement.Width%2A> del <xref:System.Windows.Shapes.Rectangle> se anima desde 100 hasta el valor de destino de la animación de 300.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>Por  
 Cuando se establece solo la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> de una animación, la animación progresa desde el valor base de la propiedad que se está animando, o desde la salida de una animación compuesta hasta la suma de ese valor y el valor especificado por la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  
  
 En el ejemplo siguiente se establece solo la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> del <xref:System.Windows.Media.Animation.DoubleAnimation> en 300. Dado que el ejemplo no especifica un valor de inicio, el <xref:System.Windows.Media.Animation.DoubleAnimation> usa el valor base de la propiedad <xref:System.Windows.FrameworkElement.Width%2A>, 100, como su valor de inicio. El valor final se determina agregando el valor <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> de la animación, 300, a su valor inicial, 100:400. Como resultado, el <xref:System.Windows.FrameworkElement.Width%2A> del <xref:System.Windows.Shapes.Rectangle> se anima desde 100 a 400.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 Al establecer las propiedades <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> de una animación, la animación progresa desde el valor especificado por la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> hasta el valor especificado por la suma de las propiedades <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  
  
 En el ejemplo siguiente se establece la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> del <xref:System.Windows.Media.Animation.DoubleAnimation> en 50 y su propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> en 300. El valor final se determina agregando el valor <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> de la animación, 300, a su valor inicial, 50:350. Como resultado, el <xref:System.Windows.FrameworkElement.Width%2A> del <xref:System.Windows.Shapes.Rectangle> se anima desde 50 a 350.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>De  
 Cuando se especifica únicamente el valor de <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> de una animación, la animación progresa desde el valor especificado por la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, hasta el valor base de la propiedad que se anima o hasta la salida de una animación compuesta.  
  
 En el ejemplo siguiente se establece solo la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> del <xref:System.Windows.Media.Animation.DoubleAnimation> en 50. Dado que no se especificó ningún valor final, el <xref:System.Windows.Media.Animation.DoubleAnimation> usa el valor base de la propiedad <xref:System.Windows.FrameworkElement.Width%2A>, 100, como su valor final. El <xref:System.Windows.FrameworkElement.Width%2A> del <xref:System.Windows.Shapes.Rectangle> se anima desde 50 hasta el valor base de la propiedad <xref:System.Windows.FrameworkElement.Width%2A>, 100.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 Si establece las propiedades <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> de una animación, se omite la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  
  
<a name="otheranimationtypes"></a>   
## <a name="other-animation-types"></a>Otros tipos de animación  
 Las animaciones From/to/by no son el único tipo de animaciones que proporciona [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: también proporciona animaciones de fotogramas clave y animaciones de trazados.  
  
- Una animación de fotogramas clave se anima a lo largo de cualquier cantidad de valores de destino, que se describen mediante fotogramas clave. Para obtener más información, consulte la información [General sobre animaciones de fotogramas clave](key-frame-animations-overview.md).  
  
- Una animación de trazado genera valores de salida de un <xref:System.Windows.Media.PathGeometry>. Para obtener más información, vea [información general sobre animaciones de trazados](path-animations-overview.md).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también le permite crear sus propios tipos de animaciones personalizadas. Para obtener más información, vea [información general sobre animaciones personalizadas](custom-animations-overview.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre objetos Storyboard](storyboards-overview.md)
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Información general sobre animaciones en trazados ](path-animations-overview.md)
- [Información general sobre animaciones personalizadas ](custom-animations-overview.md)
- [Ejemplo de valores de destino de animación From, To y By](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)
