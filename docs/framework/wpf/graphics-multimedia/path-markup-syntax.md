---
title: "Sintaxis de marcado de trazados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "PathGeometry (clase)"
  - "uso de atributos en XAML"
  - "Uso de atributos XAML"
  - "clases de PathGeometry"
  - "gráficos, PathGeometry (clase)"
  - "Uso de elementos de objeto XAML"
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Sintaxis de marcado de trazados
Las rutas de acceso se describen en [formas y dibujo básico en WPF Overview](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md) y [información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md), sin embargo, este tema describe en detalle el lenguaje mínima potente y complejo que puede utilizar para especificar las geometrías de trazado de forma más sólida con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 Este tema contiene las siguientes secciones:  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe estar familiarizado con las características básicas de <xref:System.Windows.Media.Geometry> objetos. Para obtener más información, consulte el [información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="abouthisdocument"></a>   
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a>StreamGeometry y PathFigureCollection Mini-lenguajes  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]proporciona dos clases que proporcionan minilenguajes para describir trazados geométricos: <xref:System.Windows.Media.StreamGeometry> y <xref:System.Windows.Media.PathFigureCollection>.  
  
-   Utiliza la <xref:System.Windows.Media.StreamGeometry> lenguaje mínima al establecer una propiedad de tipo <xref:System.Windows.Media.Geometry>, como el <xref:System.Windows.UIElement.Clip%2A> propiedad de un <xref:System.Windows.UIElement> o <xref:System.Windows.Shapes.Path.Data%2A> propiedad de un <xref:System.Windows.Shapes.Path> elemento. En el ejemplo siguiente se utiliza la sintaxis de atributo para crear una <xref:System.Windows.Media.StreamGeometry>.  
  
     [!code-xml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
-   Utiliza la <xref:System.Windows.Media.PathFigureCollection> mini-idioma al establecer el <xref:System.Windows.Media.PathGeometry.Figures%2A> propiedad de un <xref:System.Windows.Media.PathGeometry>. En el ejemplo siguiente se utiliza una sintaxis de atributo para crear una <xref:System.Windows.Media.PathFigureCollection> para un <xref:System.Windows.Media.PathGeometry>.  
  
     [!code-xml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 Como puede ver en los ejemplos anteriores, los dos lenguajes de mini son muy similares. ¿Siempre es posible utilizar un <xref:System.Windows.Media.PathGeometry> en cualquier situación donde podría usar un <xref:System.Windows.Media.StreamGeometry>; así cuál debe usar? Utilice un <xref:System.Windows.Media.StreamGeometry> cuando no es necesario modificar la ruta de acceso después de crearlo; utilice un <xref:System.Windows.Media.PathGeometry> si es necesario modificar la ruta de acceso.  
  
 Para obtener más información acerca de las diferencias entre <xref:System.Windows.Media.PathGeometry> y <xref:System.Windows.Media.StreamGeometry> los objetos, vea la [información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
### <a name="a-note-about-white-space"></a>Una nota sobre el espacio en blanco  
 Para mayor brevedad, se muestra un espacio en las siguientes secciones de sintaxis, pero varios espacios también son aceptables, siempre que se muestra un único espacio.  
  
 Dos números realmente no tienen que estar separados por una coma o un espacio en blanco, pero esto sólo es posible cuando la cadena resultante es inequívoca. Por ejemplo, `2..3` es en realidad dos números: "2". Y ".&3;". De forma similar, `2-3` es "2" y "-3". No se requieren espacios antes o después de los comandos, o bien.  
  
### <a name="syntax"></a>Sintaxis  
 El [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] atributo sintaxis de uso para un <xref:System.Windows.Media.StreamGeometry> se compone de una función opcional <xref:System.Windows.Media.FillRule> valor y una o más descripciones de figura.  
  
|Uso de atributos XAML StreamGeometry|  
|-----------------------------------------|  
|`<`*object* *property* `="`[                                         `fillRule`]                                          `figureDescription`[                                         `figureDescription`]*`" ... />`|  
  
 El [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] atributo sintaxis de uso para un <xref:System.Windows.Media.PathFigureCollection> se compone de una o más descripciones de figura.  
  
|Uso de atributos de PathFigureCollection en XAML|  
|-----------------------------------------------|  
|`<`*object* *property* `="` `figureDescription`[                                         `figureDescription`]*`" ... />`|  
  
|Término|Descripción|  
|----------|-----------------|  
|*fillRule*|<xref:System.Windows.Media.FillRule?displayProperty=fullName><br /><br /> Especifica si la <xref:System.Windows.Media.StreamGeometry> utiliza la <xref:System.Windows.Media.FillRule> o <xref:System.Windows.Media.FillRule><xref:System.Windows.Media.PathGeometry.FillRule%2A>.<br /><br /> -   `F0`Especifica la <xref:System.Windows.Media.FillRule> regla de relleno.<br />-   `F1`Especifica la <xref:System.Windows.Media.FillRule> regla de relleno.<br /><br /> Si omite este comando, la subruta de acceso utiliza el comportamiento predeterminado, que es <xref:System.Windows.Media.FillRule>. Si especifica este comando, debe colocarlo primero.|  
|*figureDescription*|Una figura compuesta de un comando de movimiento, comandos de dibujo y un comando de cierre opcional.<br /><br /> `moveCommand` `drawCommands`  `[` `closeCommand` `]`|  
|*moveCommand*|Un comando de movimiento que especifica el punto inicial de la figura. Consulte la [comando Move](#themovecommand) sección.|  
|*drawCommands*|Uno o más comandos de dibujo que describen el contenido de la figura. Consulte la [comandos de dibujo](#drawcommands) sección.|  
|*closeCommand*|Comando de cierre opcional que cierra la figura. Consulte la [comando Close](#closecommand) sección.|  
  
<a name="themovecommand"></a>   
## <a name="move-command"></a>Comando Mover  
 Especifica el punto inicial de una nueva figura.  
  
|Sintaxis|  
|------------|  
|`M`*startPoint*<br /><br /> o bien<br /><br /> `m`*startPoint*|  
  
|Término|Descripción|  
|----------|-----------------|  
|*punto inicial*|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> El punto de inicio de una nueva figura.|  
  
 Una letra mayúscula `M` indica que `startPoint` es un valor absoluto; minúscula `m` indica que `startPoint` es un desplazamiento hasta el punto anterior, o (0,0) si no existe ninguno. Si enumera varios puntos después del comando de movimiento, se dibuja una línea en esos puntos si se ha especificado en la línea de comandos.  
  
<a name="drawcommands"></a>   
## <a name="draw-commands"></a>Comandos de dibujo  
 Un comando de dibujo puede constar de varios comandos de forma. Están disponibles los comandos de forma siguientes: línea, línea horizontal, línea vertical, curva Bézier cúbica, curva Bézier cuadrática, curva Bézier cúbica suavizada, curva Bézier cuadrática suavizada y arco elíptico.  
  
 Escribir cada comando con una letra mayúscula o minúscula: las letras mayúsculas indican valores absolutos y letras minúsculas indican valores relativos: los puntos de control para ese segmento son relativos al punto final del ejemplo anterior. Cuando escriba secuencialmente más de un comando del mismo tipo, puede omitir la entrada del comando duplicados; Por ejemplo, `L 100,200 300,400` es equivalente a `L 100,200 L 300,400`. La tabla siguiente describe la **mover** y **dibujar** comandos.  
  
### <a name="line-command"></a>La línea de comandos  
 Crea una línea recta entre el punto actual y el extremo especificado.                           `l 20 30`y `L 20,30` son ejemplos de válido **línea** comandos.  
  
|Sintaxis|  
|------------|  
|`L`*extremo*<br /><br /> o bien<br /><br /> `l`*extremo*|  
  
|Término|Descripción|  
|----------|-----------------|  
|*Extremo*|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Punto de conexión de la línea.|  
  
### <a name="horizontal-line-command"></a>Comando de línea horizontal  
 Crea una línea horizontal entre el punto actual y la coordenada x especificada.                          `H 90`es un ejemplo de un comando de línea horizontal válido.  
  
|Sintaxis|  
|------------|  
|`H`  *x*<br /><br /> o bien<br /><br /> `h`  *x*|  
  
|Término|Descripción|  
|----------|-----------------|  
|*x*|<xref:System.Double?displayProperty=fullName><br /><br /> Coordenada x del punto final de la línea.|  
  
### <a name="vertical-line-command"></a>Comando de línea vertical  
 Crea una línea vertical entre el punto actual y la coordenada y especificada.                          `v 90`es un ejemplo de un comando de línea vertical válido.  
  
|Sintaxis|  
|------------|  
|`V`  *y*<br /><br /> o bien<br /><br /> `v`  *y*|  
  
|Término|Descripción|  
|----------|-----------------|  
|*y*|<xref:System.Double?displayProperty=fullName><br /><br /> Coordenada y del punto final de la línea.|  
  
### <a name="cubic-bezier-curve-command"></a>Comando de curva Bézier cúbica  
 Crea una curva Bézier cúbica entre el punto actual y el punto final especificado utilizando los dos puntos de control especificado ( `controlPoint`1 y `controlPoint`2).                          `C 100,200 200,400 300,200`es un ejemplo de un comando de curva válido.  
  
|Sintaxis|  
|------------|  
|`C` `controlPoint`1`controlPoint`2`endPoint`<br /><br /> o bien<br /><br /> `c` `controlPoint`1`controlPoint`2`endPoint`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`controlPoint`1|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> El primer punto de control de la curva, que determina la tangente inicial de la curva.|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> El segundo punto de control de la curva, que determina la tangente final de la curva.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Punto en el que se dibuja la curva.|  
  
### <a name="quadratic-bezier-curve-command"></a>Comando de curva Bézier cuadrática  
 Crea una curva Bézier cuadrática entre el punto actual y el punto final especificado utilizando el punto de control especificado ( `controlPoint`).                          `q 100,200 300,200`es un ejemplo de un comando de curva Bézier cuadrático válido.  
  
|Sintaxis|  
|------------|  
|`Q` `controlPoint` `endPoint`<br /><br /> o bien<br /><br /> `q` `controlPoint` `endPoint`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> El punto de control de la curva, que determina las iniciales y finales tangentes de la curva.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Punto en el que se dibuja la curva.|  
  
### <a name="smooth-cubic-bezier-curve-command"></a>Curva Bézier cúbica suavizada comando  
 Crea una curva Bézier cúbica entre el punto actual y el extremo especificado. El primer punto de control se supone que la reflexión del segundo punto de control del comando anterior en relación con el punto actual. Si no hay ningún comando anterior o si el comando anterior no es un comando de curva Bézier cúbica o cúbica suavizada, se supone que el primer punto de control es coincide con el punto actual. El segundo punto de control, el punto de control para el final de la curva, se especifica mediante `controlPoint`2. Por ejemplo, `S 100,200 200,300` es un buen cúbica Bézier curva comando válido.  
  
|Sintaxis|  
|------------|  
|`S` `controlPoint`2`endPoint`<br /><br /> o bien<br /><br /> `s` `controlPoint`2`endPoint`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> El punto de control de la curva, que determina la tangente final de la curva.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Punto en el que se dibuja la curva.|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a>Curva Bézier cuadrática suavizada comando  
 Crea una curva Bézier cuadrática entre el punto actual y el extremo especificado. Se supone que el punto de control es la reflexión del punto de control del comando anterior en relación con el punto actual. Si no hay ningún comando anterior o si el comando anterior no es un comando de curva Bézier cuadrática o cuadrática suavizada, el punto de control coincide con el punto actual.  
  
|Sintaxis|  
|------------|  
|`T` `controlPoint` `endPoint`<br /><br /> o bien<br /><br /> `t` `controlPoint` `endPoint`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> El punto de control de la curva, que determina el inicio y la tangente de la curva.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Punto en el que se dibuja la curva.|  
  
### <a name="elliptical-arc-command"></a>Comando de arco elíptico  
 Crea un arco elíptico entre el punto actual y el extremo especificado.  
  
|Sintaxis|  
|------------|  
|`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`<br /><br /> o bien<br /><br /> `a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`size`|<xref:System.Windows.Size?displayProperty=fullName><br /><br /> Los radios X e Y del arco.|  
|`rotationAngle`|<xref:System.Double?displayProperty=fullName><br /><br /> La rotación de la elipse, en grados.|  
|`isLargeArcFlag`|Establece en 1 si el ángulo del arco debe ser de 180 grados o mayor; de lo contrario, se establece en 0.|  
|`sweepDirectionFlag`|Establece en 1 si el arco se dibuja en una dirección angular positiva; de lo contrario, se establece en 0.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=fullName><br /><br /> Punto en el que está dibujado el arco.|  
  
<a name="closecommand"></a>   
## <a name="the-close-command"></a>El comando de cierre  
 Finaliza la figura actual y crea una línea que conecta el punto actual al punto inicial de la figura. Este comando crea una unión de línea (esquina) entre el último segmento y el primer segmento de la figura.  
  
|Sintaxis|  
|------------|  
|`Z`<br /><br /> o bien<br /><br /> `z`|  
  
<a name="pointsyntax"></a>   
## <a name="point-syntax"></a>Sintaxis de punto  
 Describe las coordenadas x e y de un punto.  
  
|Sintaxis|  
|------------|  
|`x` `,` `y`<br /><br /> o bien<br /><br /> `x` `y`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=fullName><br /><br /> Coordenada x del punto.|  
|`y`|<xref:System.Double?displayProperty=fullName><br /><br /> Coordenada y del punto.|  
  
<a name="specialvalues"></a>   
## <a name="special-values"></a>Valores especiales  
 En lugar de un valor numérico estándar, puede utilizar también los valores especiales siguientes. Estos valores distinguen mayúsculas de minúsculas.  
  
 Infinito  
 Representa <xref:System.Double.PositiveInfinity?displayProperty=fullName>.  
  
 -Infinity  
 Representa <xref:System.Double.NegativeInfinity?displayProperty=fullName>.  
  
 NaN  
 Representa <xref:System.Double.NaN?displayProperty=fullName>.  
  
 También puede utilizar la notación científica. Por ejemplo, `+1.e17` es un valor válido.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Shapes.Path>   
 <xref:System.Windows.Media.StreamGeometry>   
 <xref:System.Windows.Media.PathGeometry>   
 <xref:System.Windows.Media.PathFigureCollection>   
 [Formas y dibujo básico en información general WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Temas de procedimientos](../../../../docs/framework/wpf/graphics-multimedia/geometries-how-to-topics.md)