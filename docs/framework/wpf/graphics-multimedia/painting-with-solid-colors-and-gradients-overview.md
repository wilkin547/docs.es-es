---
title: Información general sobre el dibujo con colores sólidos y degradados
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- painting with gradients [WPF]
- gradients [WPF], painting with
- brushes [WPF], painting with solid colors
- brushes [WPF], painting with gradients
- painting with solid colors [WPF]
ms.assetid: f5b182f3-c5c7-4cbe-9f2f-65e690d08255
ms.openlocfilehash: 7945660f40e44596fe36a6b9d53223a0e264a064
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148309"
---
# <a name="painting-with-solid-colors-and-gradients-overview"></a>Información general sobre el dibujo con colores sólidos y degradados
Este tema describe cómo usar <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.LinearGradientBrush>, y <xref:System.Windows.Media.RadialGradientBrush> objetos para pintar con colores sólidos, degradados lineales y degradados radiales.  

<a name="solidcolor"></a>   
## <a name="painting-an-area-with-a-solid-color"></a>Pintar un área con un color sólido  
 Una de las operaciones más comunes en cualquier plataforma es pintar un área con un sólido <xref:System.Windows.Media.Color>. Para realizar esta tarea, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona el <xref:System.Windows.Media.SolidColorBrush> clase. Las secciones siguientes describen las distintas formas de pintar con un <xref:System.Windows.Media.SolidColorBrush>.  
  
<a name="solidcolorinxaml"></a>   
### <a name="using-a-solidcolorbrush-in-xaml"></a>Usar SolidColorBrush en "XAML"  
 Para pintar un área con un color sólido en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use una de las opciones siguientes.  
  
-   Seleccione un pincel de color sólido predefinido por su nombre.  Por ejemplo, puede establecer un botón <xref:System.Windows.Controls.Control.Background%2A> "Rojo" o "MediumBlue".  Para obtener una lista de otros predefinidos pinceles de color sólido, vea las propiedades estáticas de la <xref:System.Windows.Media.Brushes> clase. A continuación se muestra un ejemplo.  
  
     [!code-xaml[BrushOverviewExamples_snip#SolidColorBrushNamedColor1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushnamedcolor1xaml)]  
  
-   Elija un color en la paleta de colores de 32 bits; para ello, especifique las cantidades de rojo, verde y azul que se combinarán en un color sólido.  El formato para especificar un color de la paleta de 32 bits es "*#rrggbb*", donde *rr* es un número hexadecimal de dos dígitos que especifica la cantidad relativa de rojo, *gg* especifica la cantidad de verde y *bb* especifica la cantidad de azul.  Además, el color se puede especificar como "#*aarrggbb*", donde *aa* especifica el valor *alfa*, o la transparencia, del color. Este enfoque le permite crear colores que sean parcialmente transparentes.  En el ejemplo siguiente, la <xref:System.Windows.Controls.Control.Background%2A> de un <xref:System.Windows.Controls.Button> está establecido en rojo completamente opaco mediante la notación hexadecimal.  
  
     [!code-xaml[BrushOverviewExamples_snip#SolidColorBrushHex1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushhex1xaml)]  
  
-   Use la sintaxis de etiqueta de propiedad para describir un <xref:System.Windows.Media.SolidColorBrush>. Esta sintaxis es más detallada y le permite especificar una configuración adicional, como la opacidad del pincel. En el ejemplo siguiente, la <xref:System.Windows.Controls.Control.Background%2A> propiedades de dos <xref:System.Windows.Controls.Button> elementos se establecen en rojo completamente opaco. El color del primer pincel se describe con un nombre de color predefinido. El color del segundo pincel se describe con una notación hexadecimal.  
  
     [!code-xaml[BrushOverviewExamples_snip#SolidColorBrushPropertyTag1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushpropertytag1xaml)]  
  
<a name="solidcolorsincode"></a>   
### <a name="painting-with-a-solidcolorbrush-in-code"></a>Pintar con SolidColorBrush en el código  
 Para pintar un área con un color sólido en el código, use una de las opciones siguientes.  
  
-   Utilice uno de los pinceles predefinidos proporcionados por el <xref:System.Windows.Media.Brushes> clase. En el ejemplo siguiente, la <xref:System.Windows.Controls.Control.Background%2A> de un <xref:System.Windows.Controls.Button> está establecido en <xref:System.Windows.Media.Brushes.Red%2A>.  
  
     [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushPredefinedBrush1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushpredefinedbrush1csharp)]  
  
-   Crear un <xref:System.Windows.Media.SolidColorBrush> y establezca su <xref:System.Windows.Media.SolidColorBrush.Color%2A> propiedad utilizando un <xref:System.Windows.Media.Color> estructura. Puede usar un color predefinido en el <xref:System.Windows.Media.Colors> clase o bien puede crear un <xref:System.Windows.Media.Color> mediante estático <xref:System.Windows.Media.Color.FromArgb%2A> método.  
  
     El ejemplo siguiente muestra cómo establecer el <xref:System.Windows.Media.SolidColorBrush.Color%2A> propiedad de un <xref:System.Windows.Media.SolidColorBrush> mediante un color predefinido.  
  
     [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushPredefinedColor1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushpredefinedcolor1csharp)]  
  
 Estático <xref:System.Windows.Media.Color.FromArgb%2A> le permite especificar valores de rojo, verde y azul, alfa del color. El intervalo habitual de cada uno de estos valores es 0 a 255. Por ejemplo, un valor alfa de 0 indica que un color es completamente transparente, mientras que un valor de 255 indica que es completamente opaco. Del mismo modo, un valor rojo de 0 indica que un color no tiene rojo, mientras que un valor de 255 indica que un color tiene la cantidad máxima posible de rojo.  En el ejemplo siguiente, el color de un pincel se describe al especificar los valores alfa, rojo, verde y azul.  
  
 [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushfromArgbExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushfromargbexample1csharp)]  
  
 Para que conocer otras maneras de especificar el color, vea el <xref:System.Windows.Media.Color> tema de referencia.  
  
<a name="gradient"></a>   
## <a name="painting-an-area-with-a-gradient"></a>Pintar un área con un degradado  
 Un pincel de degradado pinta un área con varios colores que se mezclan entre sí a lo largo de un eje. Puede usarlos para crear impresiones de luz y sombra, lo da a los controles una sensación tridimensional. También puede usarlos para simular vidrio, cromo, agua y otras superficies lisas.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona dos tipos de pinceles de degradado: <xref:System.Windows.Media.LinearGradientBrush> y <xref:System.Windows.Media.RadialGradientBrush>.  
  
<a name="lineargradientbrush"></a>   
## <a name="linear-gradients"></a>Degradados lineales  
 Un <xref:System.Windows.Media.LinearGradientBrush> pinta un área con un degradado definido a lo largo de una línea, el *eje de degradado*.  Especificar los colores del degradado y su ubicación a lo largo del eje de degradado mediante <xref:System.Windows.Media.GradientStop> objetos.  También puede modificar el eje de degradado, lo que le permite crear degradados horizontales y verticales e invertir la dirección de degradado. El eje de degradado se describe en la sección siguiente. De manera predeterminada, se crea un degradado diagonal.  
  
 En el ejemplo siguiente se muestra el código que crea un degradado lineal con cuatro colores.  
  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 Este código genera el degradado siguiente:  
  
 ![Degradado lineal diagonal](./media/wcpsdk-graphicsmm-diaglgradient-nolabel.jpg "wcpsdk_graphicsmm_diaglgradient_nolabel")  
  
 **Nota:** Los ejemplos de degradado en este tema usan el sistema de coordenadas predeterminado para establecer puntos de inicio y finales. El sistema de coordenadas predeterminado está relacionado con un rectángulo: 0 indica 0 por ciento del cuadro de límite y 1 indica el 100 por cien del rectángulo. Puede cambiar este sistema de coordenadas estableciendo el <xref:System.Windows.Media.GradientBrush.MappingMode%2A> valor para la propiedad <xref:System.Windows.Media.BrushMappingMode.Absolute>. Un sistema de coordenadas absoluto no está relacionado con un rectángulo de selección. Los valores se interpretan directamente en el espacio local.  
  
 El <xref:System.Windows.Media.GradientStop> es el bloque de creación básico de un pincel de degradado.  Un delimitador de degradado especifica un <xref:System.Windows.Media.GradientStop.Color%2A> en un <xref:System.Windows.Media.GradientStop.Offset%2A> a lo largo del eje de degradado.  
  
-   El delimitador de degradado <xref:System.Windows.Media.GradientStop.Color%2A> propiedad especifica el color del delimitador de degradado. Puede establecer el color mediante el uso de un color predefinido (proporcionado por el <xref:System.Windows.Media.Colors> clase) o especificando valores ScRGB o ARGB. En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], también puede usar la notación hexadecimal para describir un color. Para obtener más información, consulte el <xref:System.Windows.Media.Color> estructura.  
  
-   El delimitador de degradado <xref:System.Windows.Media.GradientStop.Offset%2A> propiedad especifica la posición del color del delimitador de degradado en el eje de degradado. El desplazamiento es un <xref:System.Double> que comprendido entre 0 y 1. Cuanto más se acerque a 0 el valor de desplazamiento de un delimitador de degradado, más cerca del inicio del degradado está el color. Cuanto más se acerque a 1 el valor de desplazamiento del degradado, más cerca del final del degradado está el color.  
  
 El color de cada punto entre los delimitadores de degradado está interpolado linealmente como una combinación del color que especifican los dos delimitadores de degradado. En la ilustración siguiente se resaltan los delimitadores de degradado del ejemplo anterior. Los círculos marcan la posición de los delimitadores de degradado y una línea discontinua muestra el eje de degradado.  
  
 ![Delimitadores de degradado en un degradado lineal](./media/wcpsdk-graphicsmm-4gradientstops.png "wcpsdk_graphicsmm_4gradientstops")  
  
 El primer delimitador de degradado especifica el color amarillo con un desplazamiento de `0.0`.  El segundo delimitador de degradado especifica el color rojo con un desplazamiento de `0.25`.  Los puntos entre estos dos delimitadores cambian gradualmente de amarillo a rojo a medida que se mueve de izquierda a derecha a lo largo del eje de degradado.  El tercer delimitador de degradado especifica el color azul con un desplazamiento de `0.75`.  Los puntos entre el segundo y el tercer delimitador de degradado cambian gradualmente de rojo a azul. El cuarto delimitador de degradado especifica el color verde lima con un desplazamiento de `1.0`. Los puntos entre el tercer y el cuarto delimitador de degradado cambian gradualmente de azul a verde lima.  
  
<a name="gradientaxis"></a>   
### <a name="the-gradient-axis"></a>El eje de degradado  
 Tal como se mencionó anteriormente, los delimitadores de degradado de un pincel de degradado lineal están ubicados a lo largo de una línea, el eje de degradado. Puede cambiar la orientación y el tamaño de la línea con el pincel <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> propiedades. Mediante la manipulación del pincel <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>, puede crear horizontal y verticales degradados, invertir la dirección del degradado, condensar la propagación del degradado y mucho más.  
  
 De forma del predeterminada, el pincel de degradado lineal <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> son relativas al área pintada. El punto (0,0) representa la esquina superior izquierda del área que se pinta, mientras que (1,1) representa la esquina inferior derecha de la misma. El valor predeterminado <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> de un <xref:System.Windows.Media.LinearGradientBrush> es (0,0) y su valor predeterminado <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> es (1,1), que crea un degradado diagonal empezando en la esquina superior izquierda y se extiende hasta la esquina inferior derecha del área que se está pintando. La siguiente ilustración muestra el eje de degradado del pincel de degradado lineal con predeterminada <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>.  
  
 ![Eje de degradado para un degradado lineal diagonal](./media/wcpsdk-graphicsmm-diagonalgradientaxis.png "wcpsdk_graphicsmm_diagonalgradientaxis")  
  
 El ejemplo siguiente muestra cómo crear una horizontal degradado especificando el pincel <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>. Tenga en cuenta que los delimitadores de degradado son los mismos que en los ejemplos anteriores; cambiando simplemente el <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>, el degradado se cambió de diagonal a horizontal.  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 En la ilustración siguiente se muestra el degradado que se creó. El eje de degradado está marcado con una línea discontinua, mientras que los delimitadores de degradado están marcados con círculos.  
  
 ![Eje de degradado para un degradado lineal horizontal](./media/wcpsdk-graphicsmm-horizontalgradient.jpg "wcpsdk_graphicsmm_horizontalgradient")  
  
 En el ejemplo siguiente se muestra cómo crear un degradado vertical.  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 En la ilustración siguiente se muestra el degradado que se creó. El eje de degradado está marcado con una línea discontinua, mientras que los delimitadores de degradado están marcados con círculos.  
  
 ![Eje de degradado para un degradado vertical](./media/wcpsdk-graphicsmm-verticalgradient.jpg "wcpsdk_graphicsmm_verticalgradient")  
  
<a name="radialgradients"></a>   
## <a name="radial-gradients"></a>Degradados radiales  
 Al igual que un <xref:System.Windows.Media.LinearGradientBrush>, un <xref:System.Windows.Media.RadialGradientBrush> pinta un área con colores que se mezclan entre sí a lo largo de un eje. En los ejemplos anteriores se mostró que el eje de un pincel de degradado lineal es una línea recta. El eje de un pincel de degradado radial está definido con un círculo; sus colores "se irradian" hacia afuera desde su origen.  
  
 En el ejemplo siguiente, se usa un pincel de degradado radial para pintar el interior de un rectángulo.  
  
 [!code-xaml[GradientBrushExamples_snip#RadialGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/RadialGradientBrushExample.xaml#radialgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#RadialGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/RadialGradientBrushExample.cs#radialgradient1csharp)]  
  
 En la ilustración siguiente se muestra el degradado que se creó en el ejemplo anterior. Se resaltan los delimitadores de degradado del pincel. Tenga en cuenta que, a pesar de que los resultados son distintos, los delimitadores de degradado de este ejemplo son idénticos a los de los ejemplos de pincel de degradado lineal anteriores.  
  
 ![Delimitadores de degradado en un degradado radial](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")  
  
 El <xref:System.Windows.Media.RadialGradientBrush.GradientOrigin%2A> especifica el punto inicial del eje de degradado de un pincel de degradado radial. El eje de degradado irradia desde el origen del degradado al círculo del degradado. Círculo del degradado de un pincel se define por su <xref:System.Windows.Media.RadialGradientBrush.Center%2A>, <xref:System.Windows.Media.RadialGradientBrush.RadiusX%2A>, y <xref:System.Windows.Media.RadialGradientBrush.RadiusY%2A> propiedades.  
  
 La ilustración siguiente muestra varios degradados radiales con distintos <xref:System.Windows.Media.RadialGradientBrush.GradientOrigin%2A>, <xref:System.Windows.Media.RadialGradientBrush.Center%2A>, <xref:System.Windows.Media.RadialGradientBrush.RadiusX%2A>, y <xref:System.Windows.Media.RadialGradientBrush.RadiusY%2A> configuración.  
  
 ![Ajustes de RadialGradientBrush](./media/wcpsdk-graphicsmm-originscirclesandradii.gif "wcpsdk_graphicsmm_originscirclesandradii")  
RadialGradientBrushes con distintos ajustes GradientOrigin, Center, RadiusX y RadiusY.  
  
<a name="specifyinggradientcolors"></a>   
## <a name="specifying-transparent-or-partially-transparent-gradient-stops"></a>Especificación de delimitadores de degradado transparentes o parcialmente transparentes  
 Porque los delimitadores de degradado no proporcionan una propiedad de opacidad, debe especificar el canal alfa de los colores usando [!INCLUDE[TLA#tla_argb](../../../../includes/tlasharptla-argb-md.md)] notación hexadecimal en el marcado o use el <xref:System.Windows.Media.Color.FromScRgb%2A?displayProperty=nameWithType> método para crear delimitadores de degradado que sean transparentes o parcialmente transparentes. En las secciones siguientes se explica cómo crear delimitadores de degradado parcialmente transparentes en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y en el código.  
  
<a name="argbsyntax"></a>   
### <a name="specifying-color-opacity-in-xaml"></a>Especificación de la opacidad del color en "XAML"  
 En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], usa la notación hexadecimal [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] para especificar la opacidad de colores individuales. [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] notación hexadecimal utiliza la sintaxis siguiente:  
  
 `#` **aa** *rrggbb*  
  
 El valor *aa* de la línea anterior representa un valor hexadecimal de dos dígitos que se usa para especificar la opacidad del color. Cada uno de los valores *rr*, *gg* y *bb* representa un valor hexadecimal de dos dígitos que se usa para especificar la cantidad de rojo, verde y azul en el color. Cada dígito hexadecimal debe tener un valor entre 0 t 9 y entre A y F. 0 es el valor menor y F, el mayor. Un valor alfa de 00 especifica un color completamente transparente, mientras que un valor alfa de FF crea un color completamente opaco.  En el ejemplo siguiente, la notación hexadecimal [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] se usa para especificar dos colores. El primero es parcialmente transparente (tiene un valor alfa de x20), mientras que el segundo es completamente opaco.  
  
 [!code-xaml[GradientBrushExamples_snip#TransparentGradientStopExample1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/GradientStopsExample.xaml#transparentgradientstopexample1xaml)]  
  
<a name="fromscrgbsyntax"></a>   
### <a name="specifying-color-opacity-in-code"></a>Especificación de la opacidad del color en el código  
 Cuando se utiliza código, estático <xref:System.Windows.Media.Color.FromArgb%2A> método le permite especificar un valor alfa cuando se crea un color. El método toma cuatro parámetros de tipo <xref:System.Byte>. El primer parámetro especifica el canal alfa del color, mientras que los otros tres especifican los valores rojo, verde y azul del color. Cada valor debe estar comprendido entre 0 y 255, ambos inclusive. Un valor alfa de 0 especifica que el color es completamente transparente, mientras que un valor alfa de 255 especifica que el color es completamente opaco. En el ejemplo siguiente, la <xref:System.Windows.Media.Color.FromArgb%2A> método se usa para generar dos colores. El primer color es parcialmente transparente (tiene un valor alfa de 32), mientras que el segundo es completamente opaco.  
  
 [!code-csharp[GradientBrushExamples_snip#TransparentGradientStopExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/GradientStopsExample.cs#transparentgradientstopexample1csharp)]  
  
 Como alternativa, puede usar el <xref:System.Windows.Media.Color.FromScRgb%2A> método, que le permite usar valores ScRGB para crear un color.  
  
<a name="otherbrushes"></a>   
## <a name="painting-with-images-drawings-visuals-and-patterns"></a>Pintar con imágenes, dibujos, elementos visuales y patrones  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, y <xref:System.Windows.Media.VisualBrush> clases le permiten pintar un área con imágenes, dibujos u objetos visuales. Para información sobre cómo pintar con imágenes, dibujos y patrones, consulte el artículo [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Brush>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
- [Información general sobre la transformación de pinceles](brush-transformation-overview.md)
- [Niveles de representación de gráficos](../advanced/graphics-rendering-tiers.md)
