---
title: Sintaxis de marcado de trazados
description: Obtenga información sobre el Minilaboratorio eficaz y complejo que puede usar para especificar geometrías de ruta de acceso compacta en Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: 6d2778522b622f0b0dcb59673e793a6d772a4b4f
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853652"
---
# <a name="path-markup-syntax"></a>Sintaxis de marcado de trazados
Las rutas de acceso se tratan en el tema [información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md) y la [información general sobre geometría](geometry-overview.md); sin embargo, en este tema se describe con detalle el uso de un minilenguaje eficaz y complejo que puede usar para especificar geometrías de trazados de forma más compacta con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe estar familiarizado con las características básicas de los <xref:System.Windows.Media.Geometry> objetos. Para obtener más información, vea [información general sobre geometría](geometry-overview.md).  
  
<a name="abouthisdocument"></a>
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a>Minilenguajes StreamGeometry y PathFigureCollection  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]proporciona dos clases que proporcionan los pequeños idiomas para describir las rutas de acceso geométricas: <xref:System.Windows.Media.StreamGeometry> y <xref:System.Windows.Media.PathFigureCollection> .  
  
- El minilenguaje se usa <xref:System.Windows.Media.StreamGeometry> al establecer una propiedad de tipo, como <xref:System.Windows.Media.Geometry> la <xref:System.Windows.UIElement.Clip%2A> propiedad de <xref:System.Windows.UIElement> o la <xref:System.Windows.Shapes.Path.Data%2A> propiedad de un <xref:System.Windows.Shapes.Path> elemento. En el ejemplo siguiente se usa la sintaxis de atributo para crear un <xref:System.Windows.Media.StreamGeometry> .  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
- El minilenguaje se utiliza <xref:System.Windows.Media.PathFigureCollection> al establecer la <xref:System.Windows.Media.PathGeometry.Figures%2A> propiedad de <xref:System.Windows.Media.PathGeometry> . En el ejemplo siguiente se usa una sintaxis de atributo para crear un <xref:System.Windows.Media.PathFigureCollection> para un <xref:System.Windows.Media.PathGeometry> .  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 Como puede ver en los ejemplos anteriores, los dos minilenguajes son muy similares. Siempre es posible usar en cualquier situación en la que se <xref:System.Windows.Media.PathGeometry> pueda usar un <xref:System.Windows.Media.StreamGeometry> ; por lo que debe usarse? Use <xref:System.Windows.Media.StreamGeometry> cuando no necesite modificar la ruta de acceso después de crearla; use <xref:System.Windows.Media.PathGeometry> si necesita modificar la ruta de acceso.  
  
 Para obtener más información sobre las diferencias entre los <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.StreamGeometry> objetos y, vea la [información general sobre geometría](geometry-overview.md).  
  
### <a name="a-note-about-white-space"></a>Nota sobre los espacios en blanco  
 Por razones de brevedad, se muestra un solo espacio en las secciones de sintaxis siguientes, pero también se aceptan varios espacios cada vez que se muestra uno solo.  
  
 En realidad, dos números no tienen que estar separados por una coma o un espacio en blanco, pero esto solo se puede hacer si la cadena resultante es inequívoca. Por ejemplo, `2..3` es en realidad dos números: "2". y ".3". Del mismo modo, `2-3` es "2" y "-3". Tampoco se necesitan espacios antes o después de los comandos.  
  
### <a name="syntax"></a>Sintaxis  
 La [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Sintaxis de uso de atributos para un <xref:System.Windows.Media.StreamGeometry> se compone de un <xref:System.Windows.Media.FillRule> valor opcional y una o varias descripciones de la figura.  
  
|Uso del atributo XAML StreamGeometry|  
|-----------------------------------------|  
|`<`*object* *propiedad* de objeto `="` [ `fillRule` ] `figureDescription` [ `figureDescription` ] *`" ... />`|  
  
 La [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Sintaxis de uso de atributos para un <xref:System.Windows.Media.PathFigureCollection> se compone de una o varias descripciones de figura.  
  
|Uso del atributo XAML PathFigureCollection|  
|-----------------------------------------------|  
|`<`*object* *propiedad* de objeto `="` `figureDescription` [ `figureDescription` ] *`" ... />`|  
  
|Término|Descripción|  
|----------|-----------------|  
|*fillRule*|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> Especifica si <xref:System.Windows.Media.StreamGeometry> utiliza <xref:System.Windows.Media.FillRule.EvenOdd> o <xref:System.Windows.Media.FillRule.Nonzero> <xref:System.Windows.Media.PathGeometry.FillRule%2A> .<br /><br /> -   `F0`Especifica la <xref:System.Windows.Media.FillRule.EvenOdd> regla de relleno.<br />-   `F1`Especifica la <xref:System.Windows.Media.FillRule.Nonzero> regla de relleno.<br /><br /> Si omite este comando, el subtrazado usa el comportamiento predeterminado, que es <xref:System.Windows.Media.FillRule.EvenOdd> . Si especifica el comando, debe colocarlo primero.|  
|*figureDescription*|Figura compuesta de un comando de movimiento, comandos de dibujo y un comando de cierre opcional.<br /><br /> `moveCommand` `drawCommands`  `[` `closeCommand` `]`|  
|*moveCommand*|Comando de movimiento que especifica el punto inicial de la figura. Vea la sección [comando de movimiento](#themovecommand) .|  
|*drawCommands*|Uno o más comandos de dibujo que describe el contenido de la figura. Vea la sección [comandos de Draw](#drawcommands) .|  
|*closeCommand*|Comando opcional de cierre que cierra la figura. Vea la sección [comando cerrar](#closecommand) .|  
  
<a name="themovecommand"></a>
## <a name="move-command"></a>Comando de movimiento  
 Especificar el punto inicial de una figura nueva.  
  
|Sintaxis|  
|------------|  
|`M`*startPoint*<br /><br /> o bien<br /><br /> `m`*startPoint*|  
  
|Término|Descripción|  
|----------|-----------------|  
|*startPoint*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> El punto inicial de una figura nueva.|  
  
 Un carácter en mayúscula `M` indica que `startPoint` es un valor absoluto; una minúscula `m` indica que `startPoint` es un desplazamiento al punto anterior o (0,0) si no existe ninguno. Si enumera varios puntos después del comando de movimiento, se dibuja una línea a esos puntos si especificó el comando de línea.  
  
<a name="drawcommands"></a>
## <a name="draw-commands"></a>Comandos de dibujo  
 Un comando de dibujo puede constar de varios comandos de forma. Están disponibles los siguientes comandos de forma: línea, línea horizontal, línea vertical, curva Bézier cúbica, curva Bézier cuadrática, curva Bézier cúbica suavizada, curva Bézier cuadrática suavizada y arco elíptico.  
  
 Puede escribir cada comando con una letra mayúscula o una minúscula, donde las letras mayúsculas indican valores absolutos y las minúsculas, valores relativos: los puntos de control de ese segmento son relativos al punto final del ejemplo anterior. Al escribir secuencialmente más de un comando del mismo tipo, puede omitir la entrada de comando duplicada; por ejemplo, `L 100,200 300,400` es equivalente a `L 100,200 L 300,400` . En la tabla siguiente se describen los comandos de **movimiento** y **dibujo** .  
  
### <a name="line-command"></a>Comando de línea  
 Crea una línea recta entre el punto actual y el punto final especificado. `l 20 30`y `L 20,30` son ejemplos de comandos de **línea** válidos.  
  
|Sintaxis|  
|------------|  
|`L`*punto de conexión*<br /><br /> o bien<br /><br /> `l`*punto de conexión*|  
  
|Término|Descripción|  
|----------|-----------------|  
|*Finales*|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto de conexión de la línea.|  

Un carácter en mayúscula `L` indica que `endPoint` es un valor absoluto; una minúscula `l` indica que `endPoint` es un desplazamiento al punto anterior o (0,0) si no existe ninguno.

### <a name="horizontal-line-command"></a>Comando de línea horizontal  
 Crea una línea horizontal entre el punto actual y la coordenada x especificada. `H 90` es un ejemplo de un comando de línea horizontal válido.

|Sintaxis|  
|------------|  
|`H`  *x1*<br /><br /> o bien<br /><br /> `h`  *x1*|  
  
|Término|Descripción|  
|----------|-----------------|  
|*x*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Coordenada x del punto final de la línea.|  
  
Un carácter en mayúscula `H` indica que `x` es un valor absoluto; una minúscula `h` indica que `x` es un desplazamiento al punto anterior o (0,0) si no existe ninguno.
  
### <a name="vertical-line-command"></a>Comando de línea vertical  
 Crea una línea vertical entre el punto actual y la coordenada y especificada. `v 90` es un ejemplo de comando de línea vertical válido.

|Sintaxis|  
|------------|  
|`V`  *sí*<br /><br /> o bien<br /><br /> `v`  *sí*|  
  
|Término|Descripción|  
|----------|-----------------|  
|*sí*|<xref:System.Double?displayProperty=nameWithType><br /><br /> Coordenada y del punto final de la línea.|  

Un carácter en mayúscula `V` indica que `y` es un valor absoluto; una minúscula `v` indica que `y` es un desplazamiento al punto anterior o (0,0) si no existe ninguno.  

### <a name="cubic-bezier-curve-command"></a>Comando de curva Bézier cúbica  
 Crea una curva Bézier cúbica entre el punto actual y el punto final especificado usando los dos puntos de control especificados ( `controlPoint` 1 y `controlPoint` 2). `C 100,200 200,400 300,200` es un ejemplo de un comando de curva válido.  
  
|Sintaxis|  
|------------|  
|`C``controlPoint`1 `controlPoint` 2`endPoint`<br /><br /> o bien<br /><br /> `c``controlPoint`1 `controlPoint` 2`endPoint`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`controlPoint`1|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> El primer punto de control de la curva, que determina la tangente de inicio de la misma.|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> El segundo punto de control de la curva, que determina la tangente final de la misma.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto en el que se dibuja la curva.|  
  
### <a name="quadratic-bezier-curve-command"></a>Comando de curva Bézier cuadrática  
 Crea una curva Bézier cuadrática entre el punto actual y el punto final especificado mediante el punto de control especificado ( `controlPoint` ). `q 100,200 300,200` es un ejemplo de un comando de curva Bézier cuadrática válido.  
  
|Sintaxis|  
|------------|  
|`Q` `controlPoint` `endPoint`<br /><br /> o bien<br /><br /> `q` `controlPoint` `endPoint`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> El punto de control de la curva, que determina las tangentes de inicio y final de la misma.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto en el que se dibuja la curva.|  
  
### <a name="smooth-cubic-bezier-curve-command"></a>Comando de curva Bézier cúbica suavizada  
 Crea una curva Bézier cúbica entre el punto actual y el punto final especificado. El primer punto de control se supone que es el reflejo del segundo punto de control del comando anterior en relación al punto actual. Si no hay un comando anterior o si el comando anterior no fuera un comando de curva Bézier cúbica o un comando de curva Bézier cúbica suavizada, el primer punto de control se supone coincidente con el punto actual. El segundo punto de control, el punto de control del final de la curva, se especifica en `controlPoint` 2. Por ejemplo, `S 100,200 200,300` es un comando de curva Bézier cúbica suave válido.  
  
|Sintaxis|  
|------------|  
|`S``controlPoint`2`endPoint`<br /><br /> o bien<br /><br /> `s``controlPoint`2`endPoint`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`controlPoint`2|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> El punto de control de la curva, que determina la tangente final de la misma.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto en el que se dibuja la curva.|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a>Comando de curva Bézier cuadrática suavizada  
 Crea una curva Bézier cuadrática entre el punto actual y el punto final especificado. El punto de control se supone que es el reflejo del punto de control del comando anterior en relación al punto actual. Si no hay un comando anterior o si el comando anterior no fuera un comando de curva Bézier cuadrática o un comando de curva Bézier cuadrática suavizada, el punto de control coincide con el punto actual.  
  
|Sintaxis|  
|------------|  
|`T` `controlPoint` `endPoint`<br /><br /> o bien<br /><br /> `t` `controlPoint` `endPoint`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> El punto de control de la curva, que determina el inicio y la tangente de la curva.|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> Punto en el que se dibuja la curva.|  
  
### <a name="elliptical-arc-command"></a>Comando de arco elíptico  
 Crea un arco elíptico entre el punto actual y el punto final especificado.  
  
|Sintaxis|  
|------------|  
|`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`<br /><br /> o bien<br /><br /> `a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`|  
  
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
|`Z`<br /><br /> o bien<br /><br /> `z`|  

<a name="pointsyntax"></a>
## <a name="point-syntax"></a>Sintaxis de punto  
 Describe las coordenadas x e y de un punto donde (0,0) es la esquina superior izquierda.
  
|Sintaxis|  
|------------|  
|`x` `,` `y`<br /><br /> o bien<br /><br /> `x` `y`|  
  
|Término|Descripción|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=nameWithType><br /><br /> La coordenada x del punto.|  
|`y`|<xref:System.Double?displayProperty=nameWithType><br /><br /> La coordenada y del punto.|  
  
<a name="specialvalues"></a>
## <a name="special-values"></a>Valores especiales  
 En lugar de un valor numérico estándar, también puede usar los valores especiales siguientes. Estos valores distinguen mayúsculas de minúsculas.  
  
 Infinito  
 Representa <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> .  
  
 -Infinity  
 Representa <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> .  
  
 NaN  
 Representa <xref:System.Double.NaN?displayProperty=nameWithType> .  
  
 También puede usar la notación científica. Por ejemplo, `+1.e17` es un valor válido.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.PathFigureCollection>
- [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Información general sobre geometría](geometry-overview.md)
- [Temas "Cómo..."](geometries-how-to-topics.md)
