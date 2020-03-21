---
title: Sintaxis de marcado de trazados
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: adcedcea6c8d6d988021cbbccf87bd25a042fd16
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181860"
---
# <a name="path-markup-syntax"></a>Sintaxis de marcado de trazados
Las rutas de acceso se describen en Formas y dibujo básico en Información general de [WPFWPF](shapes-and-basic-drawing-in-wpf-overview.md) y [Información general](geometry-overview.md)sobre geometría , [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]sin embargo, en este tema se describe en detalle el potente y complejo minilenguaje que puede usar para especificar geometrías de ruta de acceso de forma más compacta mediante .  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe estar familiarizado <xref:System.Windows.Media.Geometry> con las características básicas de los objetos. Para obtener más información, consulte [Información general sobre geometría](geometry-overview.md).  
  
<a name="abouthisdocument"></a>
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a>Minilenguajes StreamGeometry y PathFigureCollection  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]proporciona dos clases que proporcionan mini-idiomas <xref:System.Windows.Media.StreamGeometry> <xref:System.Windows.Media.PathFigureCollection>para describir trazados geométricos: y .  
  
- El mini-idioma se <xref:System.Windows.Media.StreamGeometry> utiliza al <xref:System.Windows.Media.Geometry>establecer una <xref:System.Windows.UIElement.Clip%2A> propiedad de <xref:System.Windows.UIElement> tipo <xref:System.Windows.Shapes.Path.Data%2A> , <xref:System.Windows.Shapes.Path> como la propiedad de un elemento o la propiedad de un elemento. En el ejemplo siguiente se <xref:System.Windows.Media.StreamGeometry>utiliza la sintaxis de atributo para crear un archivo .  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
- Utilice el <xref:System.Windows.Media.PathFigureCollection> mini-idioma al <xref:System.Windows.Media.PathGeometry.Figures%2A> establecer <xref:System.Windows.Media.PathGeometry>la propiedad de un archivo . En el ejemplo siguiente se <xref:System.Windows.Media.PathFigureCollection> utiliza <xref:System.Windows.Media.PathGeometry>una sintaxis de atributo para crear un for a .  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 Como puede ver en los ejemplos anteriores, los dos minilenguajes son muy similares. Siempre es posible utilizar <xref:System.Windows.Media.PathGeometry> un en cualquier situación <xref:System.Windows.Media.StreamGeometry>en la que se puede utilizar un ; así que, ¿cuál deberías usar? Utilice <xref:System.Windows.Media.StreamGeometry> a cuando no necesite modificar la ruta de acceso después de crearla; <xref:System.Windows.Media.PathGeometry> si necesita modificar la ruta de acceso.  
  
 Para obtener más información <xref:System.Windows.Media.PathGeometry> sobre <xref:System.Windows.Media.StreamGeometry> las diferencias entre y los objetos, consulte [Información general](geometry-overview.md)sobre geometría .  
  
### <a name="a-note-about-white-space"></a>Nota sobre los espacios en blanco  
 Por razones de brevedad, se muestra un solo espacio en las secciones de sintaxis siguientes, pero también se aceptan varios espacios cada vez que se muestra uno solo.  
  
 Dos números en realidad no tienen que estar separados por una coma o un espacio en blanco, pero esto solo se puede hacer cuando la cadena resultante es inequívoca. Por ejemplo, `2..3` en realidad son dos números: "2." y ".3". Del `2-3` mismo modo, es "2" y "-3". Tampoco se necesitan espacios antes o después de los comandos.  
  
### <a name="syntax"></a>Sintaxis  
 La [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sintaxis de <xref:System.Windows.Media.StreamGeometry> uso de <xref:System.Windows.Media.FillRule> atributos para a se compone de un valor opcional y una o varias descripciones de figura.  
  
|Uso del atributo XAML StreamGeometry|  
|-----------------------------------------|  
|`<`*object* *property* propiedad `="`del `fillRule` `figureDescription`objeto `figureDescription`[ ] [ ]*`" ... />`|  
  
 La [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sintaxis de <xref:System.Windows.Media.PathFigureCollection> uso de atributos para a se compone de una o varias descripciones de figuras.  
  
|Uso del atributo XAML PathFigureCollection|  
|-----------------------------------------------|  
|`<`*object* *property* propiedad `="` del `figureDescription`objeto [ ]* `figureDescription``" ... />`|  
  
|Término|Descripción|  
|----------|-----------------|  
|*fillRule*|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> Especifica si <xref:System.Windows.Media.StreamGeometry> utiliza <xref:System.Windows.Media.FillRule.EvenOdd> el <xref:System.Windows.Media.FillRule.Nonzero> <xref:System.Windows.Media.PathGeometry.FillRule%2A>archivo o .<br /><br /> -   `F0`especifica la <xref:System.Windows.Media.FillRule.EvenOdd> regla de relleno.<br />-   `F1`especifica la <xref:System.Windows.Media.FillRule.Nonzero> regla de relleno.<br /><br /> Si omite este comando, la subruta utiliza <xref:System.Windows.Media.FillRule.EvenOdd>el comportamiento predeterminado, que es . Si especifica el comando, debe colocarlo primero.|  
|*figureDescription*|Figura compuesta de un comando de movimiento, comandos de dibujo y un comando de cierre opcional.<br /><br /> `moveCommand` `drawCommands`  `[` `closeCommand` `]`|  
|*moveCommand*|Comando de movimiento que especifica el punto inicial de la figura. Consulte la sección [Mover comando.](#themovecommand)|  
|*drawCommands*|Uno o más comandos de dibujo que describe el contenido de la figura. Consulte la sección [Comandos de dibujo.](#drawcommands)|  
|*closeCommand*|Comando opcional de cierre que cierra la figura. Consulte la sección [Cerrar comando.](#closecommand)|  
  
<a name="themovecommand"></a>
## <a name="move-command"></a>Comando de movimiento  
 Especificar el punto inicial de una figura nueva.  
  
|Sintaxis|  
|------------|  
|`M`*startPoint*<br /><br /> O bien<br /><br /> `m`*startPoint*|  
  
|Término|Descripción|  
|----------|-----------------|  
|*startPoint*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> El punto inicial de una figura nueva.|  
  
 Una mayúscula `M` indica `startPoint` que es un valor absoluto; una minúscula `m` indica `startPoint` que es un desplazamiento al punto anterior, o (0,0) si no existe ninguno. Si enumera varios puntos después del comando de movimiento, se dibuja una línea a esos puntos si especificó el comando de línea.  
  
<a name="drawcommands"></a>
## <a name="draw-commands"></a>Comandos de dibujo  
 Un comando de dibujo puede constar de varios comandos de forma. Están disponibles los siguientes comandos de forma: línea, línea horizontal, línea vertical, curva Bézier cúbica, curva Bézier cuadrática, curva Bézier cúbica suavizada, curva Bézier cuadrática suavizada y arco elíptico.  
  
 Puede escribir cada comando con una letra mayúscula o una minúscula, donde las letras mayúsculas indican valores absolutos y las minúsculas, valores relativos: los puntos de control de ese segmento son relativos al punto final del ejemplo anterior. Al introducir secuencialmente más de un comando del mismo tipo, puede omitir la entrada de comando duplicada; por ejemplo, `L 100,200 300,400` es `L 100,200 L 300,400`equivalente a . En la tabla siguiente se describen los comandos **mover** y **dibujar.**  
  
### <a name="line-command"></a>Comando de línea  
 Crea una línea recta entre el punto actual y el punto final especificado. `l 20 30`y `L 20,30` son ejemplos de comandos de **línea** válidos.  
  
|Sintaxis|  
|------------|  
|`L`*endPoint*<br /><br /> O bien<br /><br /> `l`*endPoint*|  
  
|Término|Descripción|  
|----------|-----------------|  
|*Extremo*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto de conexión de la línea.|  

Una mayúscula `L` indica `endPoint` que es un valor absoluto; una minúscula `l` indica `endPoint` que es un desplazamiento al punto anterior, o (0,0) si no existe ninguno.

### <a name="horizontal-line-command"></a>Comando de línea horizontal  
 Crea una línea horizontal entre el punto actual y la coordenada x especificada. `H 90` es un ejemplo de un comando de línea horizontal válido.

|Sintaxis|  
|------------|  
|`H`  *X*<br /><br /> O bien<br /><br /> `h`  *X*|  
  
|Término|Descripción|  
|----------|-----------------|  
|*X*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Coordenada x del punto final de la línea.|  
  
Una mayúscula `H` indica `x` que es un valor absoluto; una minúscula `h` indica `x` que es un desplazamiento al punto anterior, o (0,0) si no existe ninguno.
  
### <a name="vertical-line-command"></a>Comando de línea vertical  
 Crea una línea vertical entre el punto actual y la coordenada y especificada. `v 90` es un ejemplo de comando de línea vertical válido.

|Sintaxis|  
|------------|  
|`V`  *y y*<br /><br /> O bien<br /><br /> `v`  *y y*|  
  
|Término|Descripción|  
|----------|-----------------|  
|*y y*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Coordenada y del punto final de la línea.|  

Una mayúscula `V` indica `y` que es un valor absoluto; una minúscula `v` indica `y` que es un desplazamiento al punto anterior, o (0,0) si no existe ninguno.  

### <a name="cubic-bezier-curve-command"></a>Comando de curva Bézier cúbica  
 Crea una curva Bézier cúbica entre el punto actual y el punto`controlPoint`final `controlPoint`especificado utilizando los dos puntos de control especificados ( 1 y 2). `C 100,200 200,400 300,200` es un ejemplo de un comando de curva válido.  
  
|Sintaxis|  
|------------|  
|`C``controlPoint`1`controlPoint`2`endPoint`<br /><br /> O bien<br /><br /> `c``controlPoint`1`controlPoint`2`endPoint`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`controlPoint`1|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> El primer punto de control de la curva, que determina la tangente de inicio de la misma.|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> El segundo punto de control de la curva, que determina la tangente final de la misma.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto en el que se dibuja la curva.|  
  
### <a name="quadratic-bezier-curve-command"></a>Comando de curva Bézier cuadrática  
 Crea una curva Bézier cuadrática entre el punto actual y el`controlPoint`punto final especificado utilizando el punto de control especificado ( ). `q 100,200 300,200` es un ejemplo de un comando de curva Bézier cuadrática válido.  
  
|Sintaxis|  
|------------|  
|`Q` `controlPoint` `endPoint`<br /><br /> O bien<br /><br /> `q` `controlPoint` `endPoint`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> El punto de control de la curva, que determina las tangentes de inicio y final de la misma.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto en el que se dibuja la curva.|  
  
### <a name="smooth-cubic-bezier-curve-command"></a>Comando de curva Bézier cúbica suavizada  
 Crea una curva Bézier cúbica entre el punto actual y el punto final especificado. El primer punto de control se supone que es el reflejo del segundo punto de control del comando anterior en relación al punto actual. Si no hay un comando anterior o si el comando anterior no fuera un comando de curva Bézier cúbica o un comando de curva Bézier cúbica suavizada, el primer punto de control se supone coincidente con el punto actual. El segundo punto de control, el punto de control `controlPoint`para el final de la curva, se especifica mediante 2. Por ejemplo, `S 100,200 200,300` es un comando de curva Bézier cúbica suave válido.  
  
|Sintaxis|  
|------------|  
|`S``controlPoint`2`endPoint`<br /><br /> O bien<br /><br /> `s``controlPoint`2`endPoint`|  
  
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
  
 Infinity  
 Representa <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.  
  
 -Infinity  
 Representa <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>.  
  
 NaN  
 Representa <xref:System.Double.NaN?displayProperty=nameWithType>.  
  
 También puede usar la notación científica. Por ejemplo, `+1.e17` es un valor válido.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.PathFigureCollection>
- [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Información general sobre geometría](geometry-overview.md)
- [Temas de información](geometries-how-to-topics.md)
