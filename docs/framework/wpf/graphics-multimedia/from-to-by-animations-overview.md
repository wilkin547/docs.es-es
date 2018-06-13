---
title: Información general sobre animaciones From-To-By
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
ms.openlocfilehash: 3095ec2c6307faaaa8049f23fffb5909cb3042d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557802"
---
# <a name="fromtoby-animations-overview"></a>Información general sobre animaciones From/To/By
En este tema se describe cómo usar animaciones From/To/By para animar propiedades de dependencia. Una animación From/To/By crea una transición entre dos valores.  
  
<a name="prereq"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe estar familiarizado con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] características de las animaciones. Para obtener una introducción a las características de animación, consulte el [información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="whatisanimation"></a>   
## <a name="what-is-a-fromtoby-animation"></a>¿Qué es una animación From/To/By?  
 Un From/To/By animación es un tipo de <xref:System.Windows.Media.Animation.AnimationTimeline> que crea una transición entre un valor inicial y un valor final. La cantidad de tiempo que se tarda en completar la transición viene determinada por la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de esa animación.  
  
 Puede aplicar un From/To/By animación a una propiedad mediante el uso de un <xref:System.Windows.Media.Animation.Storyboard> en código y marcado, o mediante el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método en el código. También puede usar una animación de From/To/By para crear un <xref:System.Windows.Media.Animation.AnimationClock> y aplicarla a una o varias propiedades. Para más información sobre los distintos métodos para aplicar animaciones, consulte la [Información general sobre técnicas de animación de propiedades](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
 Las animaciones From/To/By no pueden tener más de dos valores de destino. Si necesita una animación que tenga más de dos valores de destino, use una animación de fotogramas clave. Animación de fotogramas clave se describen en la [información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
<a name="animation_types"></a>   
## <a name="fromtoby-animation-types"></a>Tipos de animaciones From/To/By  
 Dado que las animaciones generan valores de propiedad, existen distintos tipos de animaciones para los diversos tipos de propiedades. Para animar una propiedad que toma un <xref:System.Double>, como el <xref:System.Windows.FrameworkElement.Width%2A> propiedad de un elemento, se usa una animación que genera <xref:System.Double> valores. Para animar una propiedad que toma un <xref:System.Windows.Point>, se usa una animación que genera <xref:System.Windows.Point> valores y así sucesivamente.  
  
 Clases de animación From/To/By pertenecen a la <xref:System.Windows.Media.Animation> espacio de nombres y utilizan la convención de nomenclatura siguiente:  
  
 *\<Tipo>* `Animation`  
  
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
 Una animación From/To/By crea una transición entre dos valores de destino. Es común para especificar un valor inicial (establecer mediante el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad) y un valor final (establecer mediante el <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad). Pero también se puede especificar solo un valor inicial, un valor de destino o un valor de desplazamiento. En estos casos, la animación obtiene el valor de destino que falta de la propiedad que se anima. La lista siguiente describe las diferentes maneras de especificar los valores de destino de una animación.  
  
-   **Valor inicial**  
  
     Use la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad si desea especificar explícitamente el valor inicial de una animación. Puede usar el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad por sí solo o con el <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> o <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad. Si especifica solo el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad, las transiciones de animación de ese valor al valor base de la propiedad animada.  
  
-   **Valor final**  
  
     Para especificar un valor final de una animación, use su <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad. Si usas el <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad por sí sola, la animación obtiene su valor inicial de la propiedad que se anima o desde la salida de otra animación que se aplica a la misma propiedad. Puede usar el <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad junto con la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad para especificar explícitamente inicial y final de los valores de la animación.  
  
-   **Valor de desplazamiento**  
  
     El <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad le permite especificar un desplazamiento en lugar de un inicio explícita o el valor final para la animación. El <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad de una animación especifica cuánto la animación cambia un valor a través de su duración. Puede usar el <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad por sí solo o con el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad. Si especifica solo el <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad, la animación agrega el valor de desplazamiento al valor base de la propiedad o a la salida de otra animación.  
  
<a name="examples"></a>   
## <a name="using-fromtoby-values"></a>Usar valores From/To/By  
 Las secciones siguientes describen cómo utilizar el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedades conjuntamente o por separado.  
  
 Los ejemplos de esta sección cada vez que un <xref:System.Windows.Media.Animation.DoubleAnimation>, que es un tipo de animación From/To/By, para animar la <xref:System.Windows.FrameworkElement.Width%2A> propiedad de un <xref:System.Windows.Shapes.Rectangle> que es 10 píxeles independientes del dispositivo alta y 100 píxeles independientes del dispositivo amplias.  
  
 Aunque cada ejemplo se usa un <xref:System.Windows.Media.Animation.DoubleAnimation>, From, To y By propiedades de todos los From/To/By animaciones se comportan exactamente igual. Aunque cada uno de estos ejemplos se usa un <xref:System.Windows.Media.Animation.Storyboard>, puede usar animaciones From/To/By de otras maneras. Para obtener más información, consulte [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
### <a name="fromto"></a>De/Para  
 Al establecer el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> valores juntos, la animación progresa desde el valor especificado por el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> , valor para la propiedad especificada por el <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad.  
  
 El ejemplo siguiente se establece la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad de la <xref:System.Windows.Media.Animation.DoubleAnimation> en 50 y su <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad a 300. Como resultado, el <xref:System.Windows.FrameworkElement.Width%2A> de la <xref:System.Windows.Shapes.Rectangle> se anima desde 50 hasta 300.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>En  
 Al establecer simplemente la <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad, la animación progresa desde el valor base de la propiedad animada, o desde la salida de una animación compuesta que se aplicó anteriormente a la misma propiedad en el valor especificado por el <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad.  
  
 ("Componer animación" hace referencia a un <xref:System.Windows.Media.Animation.ClockState.Active> o <xref:System.Windows.Media.Animation.ClockState.Filling> animación que se había aplicado anteriormente a la misma propiedad que está aún en vigor cuando se aplica la animación actual mediante el uso de la <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> comportamiento de entrega.)  
  
 En el ejemplo siguiente se establece solo la <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> propiedad de la <xref:System.Windows.Media.Animation.DoubleAnimation> a 300. Porque no se especificó ningún valor inicial, el <xref:System.Windows.Media.Animation.DoubleAnimation> utiliza el valor base (100) de la <xref:System.Windows.FrameworkElement.Width%2A> propiedad como su valor inicial. El <xref:System.Windows.FrameworkElement.Width%2A> de la <xref:System.Windows.Shapes.Rectangle> se anima desde 100 hasta el valor de destino de la animación de 300.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>By  
 Al establecer simplemente la <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad de una animación, la animación progresa desde el valor base de la propiedad que se anima o desde la salida de una animación compuesta para la suma de ese valor y el valor especificado por el <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad.  
  
 En el ejemplo siguiente se establece solo la <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad de la <xref:System.Windows.Media.Animation.DoubleAnimation> a 300. Dado que el ejemplo no especifica un valor inicial, el <xref:System.Windows.Media.Animation.DoubleAnimation> utiliza el valor base de la <xref:System.Windows.FrameworkElement.Width%2A> propiedad, 100, como su valor inicial. El valor final se determina mediante la adición de la <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> valor de la animación, 300, y su valor inicial, 100:400. Como resultado, el <xref:System.Windows.FrameworkElement.Width%2A> de la <xref:System.Windows.Shapes.Rectangle> se anima entre 100 y 400.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 Al establecer el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedades de una animación, la animación progresa desde el valor especificado por el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad para el valor especificado por la suma de la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedades.  
  
 El ejemplo siguiente se establece la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad de la <xref:System.Windows.Media.Animation.DoubleAnimation> en 50 y su <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad a 300. El valor final se determina mediante la adición de la <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> valor de la animación, 300, y su valor inicial, 50:350. Como resultado, el <xref:System.Windows.FrameworkElement.Width%2A> de la <xref:System.Windows.Shapes.Rectangle> se anima desde 50 a 350.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>De  
 Cuando se especifica solo el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> valor de una animación, la animación progresa desde el valor especificado por el <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad, el valor base de la propiedad que se anima o a la salida de una animación compuesta.  
  
 En el ejemplo siguiente se establece solo la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> propiedad de la <xref:System.Windows.Media.Animation.DoubleAnimation> en 50. Porque no se especificó ningún valor final, el <xref:System.Windows.Media.Animation.DoubleAnimation> utiliza el valor base de la <xref:System.Windows.FrameworkElement.Width%2A> propiedad, 100, como su valor final. El <xref:System.Windows.FrameworkElement.Width%2A> de la <xref:System.Windows.Shapes.Rectangle> se anima desde 50 hasta el valor base de la <xref:System.Windows.FrameworkElement.Width%2A> propiedad, 100.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 Si establece tanto la <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedades de una animación, la <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> propiedad se omite.  
  
<a name="otheranimationtypes"></a>   
## <a name="other-animation-types"></a>Otros tipos de animación  
 Animaciones From/To/By no son el único tipo de animaciones que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona: también proporciona animaciones de fotogramas clave y las animaciones de ruta de acceso.  
  
-   Una animación de fotogramas clave se anima a lo largo de cualquier cantidad de valores de destino, que se describen mediante fotogramas clave. Para obtener más información, consulte el [información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
-   Una animación de trazado genera valores de salida de un <xref:System.Windows.Media.PathGeometry>. Para obtener más información, consulte el [información general sobre animaciones de ruta de acceso](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también le permite crear sus propios tipos de animaciones personalizadas. Para obtener más información, consulte el [información general sobre animaciones de personalizados](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Animation.Timeline>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Información general sobre objetos Storyboard ](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Información general sobre animaciones en trazados ](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)  
 [Información general sobre animaciones personalizadas ](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)  
 [Ejemplo de valores de destino de animación From, To y By](http://go.microsoft.com/fwlink/?LinkID=159988)
