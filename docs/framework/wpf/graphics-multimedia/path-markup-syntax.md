---
title: Sintaxis de marcado de trazados
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: d681cd15fa3daa3698edc5e0ad3d3c2669c1dfdf
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45591937"
---
# <a name="path-markup-syntax"></a>Sintaxis de marcado de trazados
Las rutas de acceso se tratan en [formas y dibujo básico en WPF Overview](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md) y [información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md), sin embargo, este tema describe en detalle el eficaz y complejo minilenguaje puede usar para especificar la ruta de acceso geometrías de manera más compacta con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe estar familiarizado con las características básicas de <xref:System.Windows.Media.Geometry> objetos. Para obtener más información, consulte el [información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="abouthisdocument"></a>   
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a>Minilenguajes StreamGeometry y PathFigureCollection  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona dos clases que proporcionan minilenguajes para describir los trazados geométricos: <xref:System.Windows.Media.StreamGeometry> y <xref:System.Windows.Media.PathFigureCollection>.  
  
-   Usa el <xref:System.Windows.Media.StreamGeometry> minilenguaje al establecer una propiedad de tipo <xref:System.Windows.Media.Geometry>, como el <xref:System.Windows.UIElement.Clip%2A> propiedad de un <xref:System.Windows.UIElement> o el <xref:System.Windows.Shapes.Path.Data%2A> propiedad de un <xref:System.Windows.Shapes.Path> elemento. En el ejemplo siguiente se usa la sintaxis de atributo para crear un <xref:System.Windows.Media.StreamGeometry>.  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
-   Usa el <xref:System.Windows.Media.PathFigureCollection> minilenguaje al establecer el <xref:System.Windows.Media.PathGeometry.Figures%2A> propiedad de un <xref:System.Windows.Media.PathGeometry>. En el ejemplo siguiente se usa una sintaxis de atributo para crear un <xref:System.Windows.Media.PathFigureCollection> para un <xref:System.Windows.Media.PathGeometry>.  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 Como puede ver en los ejemplos anteriores, los dos minilenguajes son muy similares. ¿Siempre es posible usar un <xref:System.Windows.Media.PathGeometry> en cualquier situación donde podría usar un <xref:System.Windows.Media.StreamGeometry>; por lo que debe cuál usar? Usar un <xref:System.Windows.Media.StreamGeometry> cuando no es necesario modificar la ruta de acceso después de crearla; utilice un <xref:System.Windows.Media.PathGeometry> si tiene que modificar la ruta de acceso.  
  
 Para obtener más información sobre las diferencias entre <xref:System.Windows.Media.PathGeometry> y <xref:System.Windows.Media.StreamGeometry> objetos, vea el [información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
### <a name="a-note-about-white-space"></a>Nota sobre los espacios en blanco  
 Por razones de brevedad, se muestra un solo espacio en las secciones de sintaxis siguientes, pero también se aceptan varios espacios cada vez que se muestra uno solo.  
  
 Dos números realmente no tienen que estar separados por comas o espacios en blanco, pero esto solo se puede hacer cuando la cadena resultante no es ambigua. Por ejemplo, `2..3` es realmente de dos números: "2". y ".3". De forma similar, `2-3` es "2" y "-3". Tampoco se necesitan espacios antes o después de los comandos.  
  
### <a name="syntax"></a>Sintaxis  
 El [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] atributo sintaxis de uso para un <xref:System.Windows.Media.StreamGeometry> se compone de un elemento opcional <xref:System.Windows.Media.FillRule> valor y uno o más descripciones de figura.  
  
|Uso del atributo XAML StreamGeometry|  
|-----------------------------------------|  
|`<` *objeto* *propiedad* `="`[ `fillRule`] `figureDescription`[ `figureDescription`] * `" ... />`|  
  
 El [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] atributo sintaxis de uso para un <xref:System.Windows.Media.PathFigureCollection> se compone de uno o más descripciones de figura.  
  
|Uso del atributo XAML PathFigureCollection|  
|-----------------------------------------------|  
|`<` *objeto* *propiedad* `="` `figureDescription`[ `figureDescription`] * `" ... />`|  
  
|Término|Descripción|  
|----------|-----------------|  
|*fillRule*|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> Especifica si el <xref:System.Windows.Media.StreamGeometry> usa el <xref:System.Windows.Media.FillRule.EvenOdd> o <xref:System.Windows.Media.FillRule.Nonzero> <xref:System.Windows.Media.PathGeometry.FillRule%2A>.<br /><br /> -   `F0` Especifica el <xref:System.Windows.Media.FillRule.EvenOdd> regla de relleno.<br />-   `F1` Especifica el <xref:System.Windows.Media.FillRule.Nonzero> regla de relleno.<br /><br /> Si se omite este comando, el subtrazado usa el comportamiento predeterminado, que es <xref:System.Windows.Media.FillRule.EvenOdd>. Si especifica el comando, debe colocarlo primero.|  
|*figureDescription*|Figura compuesta de un comando de movimiento, comandos de dibujo y un comando de cierre opcional.<br /><br /> `moveCommand` `drawCommands`  `[` `closeCommand` `]`|  
|*moveCommand*|Comando de movimiento que especifica el punto inicial de la figura. Consulte la [comando Move](#themovecommand) sección.|  
|*drawCommands*|Uno o más comandos de dibujo que describe el contenido de la figura. Consulte la [comandos de dibujo](#drawcommands) sección.|  
|*closeCommand*|Comando opcional de cierre que cierra la figura. Consulte la [comando Cerrar](#closecommand) sección.|  
  
<a name="themovecommand"></a>   
## <a name="move-command"></a>Comando de movimiento  
 Especificar el punto inicial de una figura nueva.  
  
|Sintaxis|  
|------------|  
|`M` *startPoint*<br /><br /> O bien<br /><br /> `m` *startPoint*|  
  
|Término|Descripción|  
|----------|-----------------|  
|*startPoint*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> El punto inicial de una figura nueva.|  
  
 En mayúscula `M` indica que `startPoint` es un valor absoluto; una minúscula `m` indica que `startPoint` es un desplazamiento hasta el punto anterior, o bien (0,0) si no existe ninguno. Si enumera varios puntos después del comando de movimiento, se dibuja una línea a esos puntos si especificó el comando de línea.  
  
<a name="drawcommands"></a>   
## <a name="draw-commands"></a>Comandos de dibujo  
 Un comando de dibujo puede constar de varios comandos de forma. Están disponibles los siguientes comandos de forma: línea, línea horizontal, línea vertical, curva Bézier cúbica, curva Bézier cuadrática, curva Bézier cúbica suavizada, curva Bézier cuadrática suavizada y arco elíptico.  
  
 Puede escribir cada comando con una letra mayúscula o una minúscula, donde las letras mayúsculas indican valores absolutos y las minúsculas, valores relativos: los puntos de control de ese segmento son relativos al punto final del ejemplo anterior. Cuando escriba secuencialmente más de un comando del mismo tipo, puede omitir la entrada de comando duplicada; Por ejemplo, `L 100,200 300,400` es equivalente a `L 100,200 L 300,400`. La tabla siguiente se describen los **mover** y **dibujar** comandos.  
  
### <a name="line-command"></a>Comando de línea  
 Crea una línea recta entre el punto actual y el punto final especificado. `l 20 30` y `L 20,30` son ejemplos de **línea** comandos.  
  
|Sintaxis|  
|------------|  
|`L` *endPoint*<br /><br /> O bien<br /><br /> `l` *endPoint*|  
  
|Término|Descripción|  
|----------|-----------------|  
|*endPoint*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto de conexión de la línea.|  

En mayúscula `L` indica que `endPoint` es un valor absoluto; una minúscula `l` indica que `endPoint` es un desplazamiento hasta el punto anterior, o bien (0,0) si no existe ninguno.

### <a name="horizontal-line-command"></a>Comando de línea horizontal  
 Crea una línea horizontal entre el punto actual y la coordenada x especificada. `H 90` es un ejemplo de un comando de línea horizontal válido.

  
|Sintaxis|  
|------------|  
|`H`  *X*<br /><br /> O bien<br /><br /> `h`  *X*|  
  
|Término|Descripción|  
|----------|-----------------|  
|*x*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Coordenada x del punto final de la línea.|  
  
En mayúscula `H` indica que `x` es un valor absoluto; una minúscula `h` indica que `x` es un desplazamiento hasta el punto anterior, o bien (0,0) si no existe ninguno.
  
### <a name="vertical-line-command"></a>Comando de línea vertical  
 Crea una línea vertical entre el punto actual y la coordenada y especificada. `v 90` es un ejemplo de comando de línea vertical válido.

  
|Sintaxis|  
|------------|  
|`V`  *y*<br /><br /> o bien<br /><br /> `v`  *y*|  
  
|Término|Descripción|  
|----------|-----------------|  
|*y*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Coordenada y del punto final de la línea.|  

En mayúscula `V` indica que `y` es un valor absoluto; una minúscula `v` indica que `y` es un desplazamiento hasta el punto anterior, o bien (0,0) si no existe ninguno.  
    
### <a name="cubic-bezier-curve-command"></a>Comando de curva Bézier cúbica  
 Crea una curva Bézier cúbica entre el punto actual y el punto final especificado mediante el uso de los dos puntos de control especificado (`controlPoint`1 y `controlPoint`2). `C 100,200 200,400 300,200` es un ejemplo de un comando de curva válido.  
  
|Sintaxis|  
|------------|  
|`C` `controlPoint`1`controlPoint`2`endPoint`<br /><br /> O bien<br /><br /> `c` `controlPoint`1`controlPoint`2`endPoint`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`controlPoint`1|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> El primer punto de control de la curva, que determina la tangente de inicio de la misma.|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> El segundo punto de control de la curva, que determina la tangente final de la misma.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto en el que se dibuja la curva.|  
  
### <a name="quadratic-bezier-curve-command"></a>Comando de curva Bézier cuadrática  
 Crea una curva Bézier cuadrática entre el punto actual y el punto final especificado utilizando el punto de control especificado (`controlPoint`). `q 100,200 300,200` es un ejemplo de un comando de curva Bézier cuadrática válido.  
  
|Sintaxis|  
|------------|  
|`Q` `controlPoint` `endPoint`<br /><br /> O bien<br /><br /> `q` `controlPoint` `endPoint`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> El punto de control de la curva, que determina las tangentes de inicio y final de la misma.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto en el que se dibuja la curva.|  
  
### <a name="smooth-cubic-bezier-curve-command"></a>Comando de curva Bézier cúbica suavizada  
 Crea una curva Bézier cúbica entre el punto actual y el punto final especificado. El primer punto de control se supone que es el reflejo del segundo punto de control del comando anterior en relación al punto actual. Si no hay un comando anterior o si el comando anterior no fuera un comando de curva Bézier cúbica o un comando de curva Bézier cúbica suavizada, el primer punto de control se supone coincidente con el punto actual. El segundo punto de control, especificado por el punto de control para el final de la curva, `controlPoint`2. Por ejemplo, `S 100,200 200,300` es un válido comando Bézier cúbica suavizada curva.  
  
|Sintaxis|  
|------------|  
|`S` `controlPoint`2`endPoint`<br /><br /> O bien<br /><br /> `s` `controlPoint`2`endPoint`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> El punto de control de la curva, que determina la tangente final de la misma.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto en el que se dibuja la curva.|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a>Comando de curva Bézier cuadrática suavizada  
 Crea una curva Bézier cuadrática entre el punto actual y el punto final especificado. El punto de control se supone que es el reflejo del punto de control del comando anterior en relación al punto actual. Si no hay un comando anterior o si el comando anterior no fuera un comando de curva Bézier cuadrática o un comando de curva Bézier cuadrática suavizada, el punto de control coincide con el punto actual.  
  
|Sintaxis|  
|------------|  
|`T` `controlPoint` `endPoint`<br /><br /> O bien<br /><br /> `t` `controlPoint` `endPoint`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> El punto de control de la curva, que determina el inicio y la tangente de la curva.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto en el que se dibuja la curva.|  
  
### <a name="elliptical-arc-command"></a>Comando de arco elíptico  
 Crea un arco elíptico entre el punto actual y el punto final especificado.  
  
|Sintaxis|  
|------------|  
|`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`<br /><br /> O bien<br /><br /> `a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`size`|<xref:System.Windows.Size?displayProperty=nameWithType><br /><br /> Los radios X e Y del arco.|  
|`rotationAngle`|<xref:System.Double?displayProperty=nameWithType><br /><br /> La rotación de la elipse, en grados.|  
|`isLargeArcFlag`|Establezca el valor en 1 si el ángulo del arco debe ser de 180 grados o más; de lo contrario, establézcalo en 0.|  
|`sweepDirectionFlag`|Establezca el valor en 1 si se dibuja en una dirección con ángulo positivo; de lo contrario, establézcalo en 0.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto en el que está dibujado el arco.|  
  
<a name="closecommand"></a>   
## <a name="the-close-command"></a>Comando de cierre  
 Finaliza la figura actual y crea una línea que conecta el punto actual con el punto inicial de la figura. Este comando crea una unión de líneas (esquina) entre el último y el primer segmento de la figura.  
  
|Sintaxis|  
|------------|  
|`Z`<br /><br /> O bien<br /><br /> `z`|  

<a name="pointsyntax"></a>   
## <a name="point-syntax"></a>Sintaxis de punto  
 Describe las coordenadas x e y de un punto donde (0,0) es la esquina superior izquierda.
  
|Sintaxis|  
|------------|  
|`x` `,` `y`<br /><br /> O bien<br /><br /> `x` `y`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=nameWithType><br /><br /> La coordenada x del punto.|  
|`y`|<xref:System.Double?displayProperty=nameWithType><br /><br /> La coordenada y del punto.|  
  
<a name="specialvalues"></a>   
## <a name="special-values"></a>Valores especiales  
 En lugar de un valor numérico estándar, también puede usar los valores especiales siguientes. Estos valores distinguen mayúsculas de minúsculas.  
  
 Infinito  
 Representa <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.  
  
 -Infinity  
 Representa <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>.  
  
 NaN  
 Representa <xref:System.Double.NaN?displayProperty=nameWithType>.  
  
 También puede usar la notación científica. Por ejemplo, `+1.e17` es un valor válido.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.StreamGeometry>  
 <xref:System.Windows.Media.PathGeometry>  
 <xref:System.Windows.Media.PathFigureCollection>  
 [Información general sobre formas y dibujo básico en WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/geometries-how-to-topics.md)
