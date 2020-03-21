---
title: Información general sobre animaciones en trazados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], paths
- path animations [WPF]
ms.assetid: 979c732c-df74-47a6-be96-8e07b3707d53
ms.openlocfilehash: 07628d26c8222c7c01f58826a36a15e13dc31ff4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181863"
---
# <a name="path-animations-overview"></a>Información general sobre animaciones en trazados
<a name="introduction"></a> En este tema se presentan las animaciones de trazado, que permiten usar un trazado geométrico para generar valores de salida. Las animaciones de trazado son útiles para mover y girar objetos a lo largo de trazados complejos.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] estar familiarizado con las características de animaciones. Para obtener una introducción a las características de animación, consulte [Información general sobre animaciones](animation-overview.md).  
  
 Dado que <xref:System.Windows.Media.PathGeometry> se utiliza un objeto para definir una <xref:System.Windows.Media.PathGeometry> animación de <xref:System.Windows.Media.PathSegment> ruta de acceso, también debe estar familiarizado con y los diferentes tipos de objetos. Para obtener más información, consulte [Información general sobre geometría](geometry-overview.md).  
  
<a name="what_is_a_path_animation"></a>
## <a name="what-is-a-path-animation"></a>¿Qué es una animación de trazado?  
 Una animación de <xref:System.Windows.Media.Animation.AnimationTimeline> ruta de <xref:System.Windows.Media.PathGeometry> acceso es un tipo que utiliza a como entrada. En lugar de establecer una propiedad From, To o By (como se hace para una animación From/To/By) o utilizar fotogramas clave `PathGeometry` (como se utiliza para una animación de fotograma clave), se define un trazado geométrico y se utiliza para establecer la propiedad de la animación de ruta de acceso. A medida que la animación de trazado avanza, lee la información de x, de y y del ángulo del trazado y usa esa información para generar la salida.  
  
 Las animaciones de trazado son muy útiles para animar un objeto a lo largo de un trazado complejo. Una forma de mover un objeto a <xref:System.Windows.Media.MatrixTransform> lo <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> largo de un trazado es usar a y a para transformar un objeto a lo largo de una ruta compleja. En el ejemplo siguiente se <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> muestra esta <xref:System.Windows.Media.MatrixTransform.Matrix%2A> técnica mediante <xref:System.Windows.Media.MatrixTransform>el objeto para animar la propiedad de un archivo . Se <xref:System.Windows.Media.MatrixTransform> aplica a un botón y hace que se mueva a lo largo de un trazado curvo. Dado <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> que la `true`propiedad está establecida en , el rectángulo gira a lo largo de la tangente de la ruta de acceso.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Para obtener más información acerca de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] la sintaxis de ruta de acceso que se utiliza en el ejemplo, vea la información general sobre [sintaxis](path-markup-syntax.md) de marcado de ruta de acceso. Para ver el ejemplo completo, consulte Ejemplo de [animación](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)de ruta de acceso .  
  
 Puede aplicar una animación de ruta <xref:System.Windows.Media.Animation.Storyboard> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de acceso a una <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> propiedad mediante un in y código, o mediante el método en el código. También puede usar una animación <xref:System.Windows.Media.Animation.AnimationClock> de ruta de acceso para crear una y aplicarla a una o varias propiedades. Para obtener más información acerca de los diferentes métodos para aplicar animaciones, vea Información general sobre técnicas de [animación de](property-animation-techniques-overview.md)propiedades .  
  
<a name="animation_types"></a>
## <a name="path-animation-types"></a>Tipos de animación de trazado  
 Dado que las animaciones generan valores de propiedad, existen distintos tipos de animaciones para los diversos tipos de propiedades. Para animar una propiedad <xref:System.Double> que toma <xref:System.Windows.Media.TranslateTransform.X%2A> un <xref:System.Windows.Media.TranslateTransform>(como la propiedad de <xref:System.Double> un ), utilice una animación que produce valores. Para animar una propiedad <xref:System.Windows.Point>que toma un , <xref:System.Windows.Point> utilice una animación que produce valores, etc.  
  
 Las clases de <xref:System.Windows.Media.Animation> animación de ruta de acceso pertenecen al espacio de nombres y usan la siguiente convención de nomenclatura:  
  
 * \<Tipo>*`AnimationUsingPath`  
  
 Donde * \<Type>* es el tipo de valor que anima la clase.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona las siguientes clases de animación de trazado.  
  
|Tipo de propiedad|Clase de animación de trazado correspondiente|Ejemplo|  
|-------------------|----------------------------------------|-------------|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|[Animación de un objeto a lo largo de un trazado (animación doble)](how-to-animate-an-object-along-a-path-double-animation.md)|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>|[Animación de un objeto a lo largo de un trazado (animación de matriz)](how-to-animate-an-object-along-a-path-matrix-animation.md)|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|[Animación de un objeto a lo largo de un trazado (animación en punto)](how-to-animate-an-object-along-a-path-point-animation.md)|  
  
 A <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> <xref:System.Windows.Media.Matrix> genera valores <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A>a partir de su archivo . Cuando se <xref:System.Windows.Media.MatrixTransform>utiliza <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> con un , a puede mover un objeto a lo largo de un trazado. Si establece <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> la propiedad <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> `true`de to , también gira el objeto a lo largo de las curvas del trazado.  
  
 A <xref:System.Windows.Media.Animation.PointAnimationUsingPath> <xref:System.Windows.Point> genera valores a partir de las <xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A>coordenadas x e y de su archivo . Mediante el <xref:System.Windows.Media.Animation.PointAnimationUsingPath> uso de a <xref:System.Windows.Point> para animar una propiedad que toma valores, puede mover un objeto a lo largo de una ruta de acceso. A <xref:System.Windows.Media.Animation.PointAnimationUsingPath> no puede girar objetos.  
  
 A <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> <xref:System.Double> genera valores <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>a partir de su archivo . Al establecer <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A> la propiedad, puede <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> especificar si utiliza la coordenada x, la coordenada y o el ángulo de la ruta como salida. Puede utilizar <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> a para girar un objeto o moverlo a lo largo del eje X o del eje Y.  
  
<a name="pathanimationinput"></a>
## <a name="path-animation-input"></a>Entrada de animación de trazado  
 Cada clase de <xref:System.Windows.Media.PathGeometry> animación de ruta de acceso proporciona una propiedad para especificar su entrada. La animación <xref:System.Windows.Media.PathGeometry> de ruta de acceso utiliza el para generar sus valores de salida. La <xref:System.Windows.Media.PathGeometry> clase permite describir varias figuras complejas que se componen de arcos, curvas y líneas.  
  
 En el corazón <xref:System.Windows.Media.PathGeometry> de a <xref:System.Windows.Media.PathFigure> hay una colección de objetos; estos objetos se denominan así porque cada <xref:System.Windows.Media.PathGeometry>figura describe una forma discreta en el archivo . Cada <xref:System.Windows.Media.PathFigure> uno consta <xref:System.Windows.Media.PathSegment> de uno o más objetos, cada uno de los cuales describe un segmento de la figura.  
  
 Hay muchos tipos de segmentos.  
  
|Tipo de segmento|Descripción|  
|------------------|-----------------|  
|<xref:System.Windows.Media.ArcSegment>|Crea un arco elíptico entre dos puntos.|  
|<xref:System.Windows.Media.BezierSegment>|Crea una curva Bézier cúbica entre dos puntos.|  
|<xref:System.Windows.Media.LineSegment>|Crea una línea entre dos puntos.|  
|<xref:System.Windows.Media.PolyBezierSegment>|Crea una serie de curvas Bézier cúbicas.|  
|<xref:System.Windows.Media.PolyLineSegment>|Crea una serie de líneas.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Crea una serie de curvas Bézier cuadráticas.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Crea una curva Bézier cuadrática.|  
  
 Los segmentos <xref:System.Windows.Media.PathFigure> de a se combinan en una sola forma geométrica, que utiliza el punto final de un segmento como punto inicial del siguiente segmento. La <xref:System.Windows.Media.PathFigure.StartPoint%2A> propiedad <xref:System.Windows.Media.PathFigure> de a especifica el punto desde el que se dibuja el primer segmento. Cada segmento posterior comienza en el punto final del segmento anterior. Por ejemplo, se `10,50` puede `10,150` definir una línea <xref:System.Windows.Media.PathFigure.StartPoint%2A> vertical `10,50` desde <xref:System.Windows.Media.LineSegment> to <xref:System.Windows.Media.LineSegment.Point%2A> estableciendo `10,150`la propiedad en y creando un valor de propiedad de .  
  
 Para obtener <xref:System.Windows.Media.PathGeometry> más información acerca de los objetos, consulte [Información general sobre geometría](geometry-overview.md).  
  
 En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], también puede utilizar una sintaxis abreviada especial para establecer la <xref:System.Windows.Media.PathGeometry.Figures%2A> propiedad de un <xref:System.Windows.Media.PathGeometry>archivo . Para obtener más información, consulte Introducción a la [sintaxis](path-markup-syntax.md) de marcado de ruta de acceso.  
  
 Para obtener más información acerca de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] la sintaxis de ruta de acceso que se utiliza en el ejemplo, vea la información general sobre [sintaxis](path-markup-syntax.md) de marcado de ruta de acceso.  
  
## <a name="see-also"></a>Consulte también

- [Ejemplo de animación de trazado](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [Sintaxis de marcado de trazados](path-markup-syntax.md)
- [Temas de procedimientos de animación de trazado](path-animation-how-to-topics.md)
- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre técnicas de animación de propiedades](property-animation-techniques-overview.md)
