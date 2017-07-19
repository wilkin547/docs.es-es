---
title: "Informaci&#243;n general sobre animaciones From/To/By | Microsoft Docs"
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
  - "animación, From/To/By"
  - "From/To/By (animación)"
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Informaci&#243;n general sobre animaciones From/To/By
En este tema se describe cómo utilizar las animaciones From\/To\/By para animar [propiedades de dependencia](GTMT).  Una animación From\/To\/By crea una transición entre dos valores.  
  
 Este tema contiene las secciones siguientes.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prereq"></a>   
## Requisitos previos  
 Para entender este tema, debe estar familiarizado con las características de animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Para obtener una introducción a las características de animación, vea [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="whatisanimation"></a>   
## ¿Qué es una animación From\/To\/By?  
 Una animación From\/To\/By es un tipo de clase <xref:System.Windows.Media.Animation.AnimationTimeline> que crea una transición entre un valor inicial y un valor final.  La propiedad <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de una animación determina la cantidad de tiempo que tarda en completarse esa animación.  
  
 Puede aplicarse una animación From\/To\/By a una propiedad mediante una clase <xref:System.Windows.Media.Animation.Storyboard> en el marcado y el código o mediante el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> en el código.  También puede usar una animación From\/To\/By para crear una clase <xref:System.Windows.Media.Animation.AnimationClock> y aplicarla a una o más propiedades.  Para obtener más información sobre los distintos métodos para aplicar animaciones, vea [Información general sobre técnicas de animación de propiedades](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
 Las animaciones From\/To\/By pueden tener un máximo de dos valores de destino.  Si necesita una animación que tenga más de dos valores de destino, use una animación de fotogramas clave.  Las animaciones de fotogramas clave se describen en [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
<a name="animation_types"></a>   
## Tipos de animaciones From\/To\/By  
 Dado que las animaciones generan valores de propiedades, hay distintos tipos de animaciones para los diversos tipos de propiedades.  Para animar una propiedad que acepta una estructura <xref:System.Double>, como la propiedad <xref:System.Windows.FrameworkElement.Width%2A> de un elemento, se usa una animación que genera valores <xref:System.Double>.  Para animar una propiedad que acepta una estructura <xref:System.Windows.Point>, se usa una animación que genera valores <xref:System.Windows.Point>; y así sucesivamente.  
  
 Las clases de animaciones From\/To\/By pertenecen al espacio de nombres <xref:System.Windows.Media.Animation> y usan la convención de nomenclatura siguiente:  
  
 *\<Tipo\>* `Animation`  
  
 Donde *\<Tipo\>* es el tipo de valor que la clase anima.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona las siguientes clases de animaciones From\/To\/By.  
  
|Tipo de propiedad|Clase de animaciones From\/To\/By correspondiente|  
|-----------------------|-------------------------------------------------------|  
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
## Valores de destino  
 Una animación From\/To\/By crea una transición entre dos valores de destino.  Es común especificar un valor inicial \(que se establece mediante la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>\) y un valor final \(que se establece mediante la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>\).  Sin embargo, también puede especificarse sólo un valor inicial, un valor de destino o un valor de desplazamiento.  En estos casos, la animación obtiene el valor de destino que falta de la propiedad que se anima.  En la lista siguiente se describen las distintas maneras de especificar los valores de destino de una animación.  
  
-   **Valor inicial**  
  
     Use la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> cuando desee especificar explícitamente el valor inicial de una animación.  Puede usar la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> por sí sola o con la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> o <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  Si especifica únicamente la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, la animación realiza la transición desde ese valor hasta el valor base de la propiedad animada.  
  
-   **Valor final**  
  
     Para especificar el valor final de una animación, use la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.  Si usa la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> por sí sola, la animación obtiene el valor inicial de la propiedad que se anima o de la salida de otra animación que se aplique a la misma propiedad.  Puede usar la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> junto con la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> para especificar explícitamente los valores inicial y final de la animación.  
  
-   **Valor de desplazamiento**  
  
     La propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> permite especificar un desplazamiento en lugar de un valor explícito inicial o final para la animación.  La propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> de una animación especifica en qué medida cambiará el valor de una animación mientras se realiza.  Puede usar la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> por sí sola o con la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>.  Si especifica únicamente la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, la animación agrega el valor de desplazamiento al valor base de la propiedad o a la salida de otra animación.  
  
<a name="examples"></a>   
## Usar los valores From\/To\/By  
 En las secciones siguientes se describe cómo usar las propiedades <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> juntas o por separado.  
  
 En cada uno de los ejemplos de esta sección se utiliza un <xref:System.Windows.Media.Animation.DoubleAnimation>, que es un tipo de animación From\/To\/By, para animar la propiedad <xref:System.Windows.FrameworkElement.Width%2A> de un <xref:System.Windows.Shapes.Rectangle> con 10 [píxeles independientes del dispositivo](GTMT) de alto y 100 [píxeles independientes del dispositivo](GTMT) de ancho.  
  
 Aunque cada ejemplo usa una clase <xref:System.Windows.Media.Animation.DoubleAnimation>, las propiedades From, To y By de todas las animaciones From\/To\/By se comportan exactamente igual.  Aunque en cada uno de estos ejemplos se usa <xref:System.Windows.Media.Animation.Storyboard>, las animaciones From\/To\/By pueden usarse de otras maneras.  Para obtener más información, vea [Información general sobre técnicas de animación de propiedades](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
### From\/To  
 Cuando se establecen los valores de <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> conjuntamente, la animación progresa desde el valor especificado por la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> hasta el valor especificado por la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.  
  
 En el ejemplo siguiente se establece la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> del objeto <xref:System.Windows.Media.Animation.DoubleAnimation> en 50 y su propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> en 300.  Como resultado, la propiedad <xref:System.Windows.FrameworkElement.Width%2A> de <xref:System.Windows.Shapes.Rectangle> se anima desde 50 hasta 300.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### Para  
 Cuando sólo se establece la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, la animación progresa desde el valor base de la propiedad animada, o desde la salida de una animación compuesta que se aplicó previamente a la misma propiedad, hasta el valor especificado por la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.  
  
 \("Animación compuesta" hace referencia a una animación <xref:System.Windows.Media.Animation.ClockState> o <xref:System.Windows.Media.Animation.ClockState> que se aplicó previamente a la misma propiedad y que sigue en vigor al aplicar la animación actual mediante el comportamiento de entrega <xref:System.Windows.Media.Animation.HandoffBehavior>.\)  
  
 En el ejemplo siguiente se establece únicamente la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> del objeto <xref:System.Windows.Media.Animation.DoubleAnimation> en 300.  Dado que no se especifica ningún valor inicial, <xref:System.Windows.Media.Animation.DoubleAnimation> usa el valor base \(100\) de la propiedad <xref:System.Windows.FrameworkElement.Width%2A> como valor inicial.  La propiedad <xref:System.Windows.FrameworkElement.Width%2A> de <xref:System.Windows.Shapes.Rectangle> se anima desde 100 hasta el valor de destino de la animación, que es 300.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### By  
 Cuando sólo se establece la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> de una animación, esta última progresa desde el valor base de la propiedad animada, o desde la salida de una animación compuesta, hasta la suma de ese valor y del valor especificado por la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  
  
 En el ejemplo siguiente se establece únicamente la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> del objeto <xref:System.Windows.Media.Animation.DoubleAnimation> en 300.  Dado que en el ejemplo no se especifica un valor inicial, <xref:System.Windows.Media.Animation.DoubleAnimation> usa el valor base de la propiedad <xref:System.Windows.FrameworkElement.Width%2A>, 100, como valor inicial.  El valor final se determina sumando el valor de <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> de la animación, 300, y su valor inicial, 100, lo que da 400.  Como resultado, la propiedad <xref:System.Windows.FrameworkElement.Width%2A> de <xref:System.Windows.Shapes.Rectangle> se anima desde 100 hasta 400.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### From\/By  
 Cuando se establecen las propiedades <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> de una animación, esta última progresa desde valor especificado por la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> hasta el valor especificado por la suma de las propiedades <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  
  
 En el ejemplo siguiente se establece la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> del objeto <xref:System.Windows.Media.Animation.DoubleAnimation> en 50 y su propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> en 300.  El valor final se determina sumando el valor de <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> de la animación, 300, y su valor inicial, 50, lo que da 350.  Como resultado, la propiedad <xref:System.Windows.FrameworkElement.Width%2A> de <xref:System.Windows.Shapes.Rectangle> se anima desde 50 hasta 350.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### From  
 Cuando se especifica únicamente el valor de la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> de una animación, esta última progresa desde el valor especificado por la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> hasta el valor base de la propiedad animada o hasta la salida de una animación compuesta.  
  
 En el ejemplo siguiente se establece únicamente la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> del objeto <xref:System.Windows.Media.Animation.DoubleAnimation> en 50.  Dado que no se especifica ningún valor final, <xref:System.Windows.Media.Animation.DoubleAnimation> usa el valor base de la propiedad <xref:System.Windows.FrameworkElement.Width%2A>, 100, como valor final.  La propiedad <xref:System.Windows.FrameworkElement.Width%2A> de <xref:System.Windows.Shapes.Rectangle> se anima desde 50 hasta el valor base de la propiedad <xref:System.Windows.FrameworkElement.Width%2A>, 100.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### To\/By  
 Si establece las propiedades <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> de una animación, se omite la propiedad <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  
  
<a name="otheranimationtypes"></a>   
## Otros tipos de animación  
 Las animaciones From\/To\/By no son el único tipo de animación que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona: también proporciona animaciones de fotogramas clave y de trayectoria.  
  
-   Una animación de fotogramas clave se anima a lo largo de cualquier número de valores de destino, que se describen mediante fotogramas clave.  Para obtener más información, vea [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
-   Una animación de trayectoria genera los valores de salida a partir de una clase <xref:System.Windows.Media.PathGeometry>.  Para obtener más información, vea [Información general sobre animaciones en trazados](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también le permite crear sus propios tipos de animación personalizada.  Para obtener más información, vea [Información general sobre animaciones personalizadas](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md).  
  
## Vea también  
 <xref:System.Windows.Media.Animation.Timeline>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Información general sobre animaciones en trazados](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)   
 [Información general sobre animaciones personalizadas](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)   
 [Ejemplo From, To, and By Animation Target Values](http://go.microsoft.com/fwlink/?LinkID=159988)