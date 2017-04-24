---
title: "Informaci&#243;n general sobre el dibujo con colores s&#243;lidos y degradados | Microsoft Docs"
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
  - "pinceles, pintar con degradados"
  - "pinceles, pintar colores sólidos"
  - "degradados, pintar con"
  - "pintar con degradados"
  - "pintar colores sólidos"
  - "colores sólidos, pintar con"
ms.assetid: f5b182f3-c5c7-4cbe-9f2f-65e690d08255
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Informaci&#243;n general sobre el dibujo con colores s&#243;lidos y degradados
En este tema se describe cómo usar los objetos <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.LinearGradientBrush> y <xref:System.Windows.Media.RadialGradientBrush> para pintar con colores sólidos, degradados lineales y degradados radiales.  
  
   
  
<a name="solidcolor"></a>   
## Pintar un área con un color sólido  
 Una de las operaciones más comunes en cualquier plataforma es pintar un área con un <xref:System.Windows.Media.Color> sólido.  Para ello, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona la clase <xref:System.Windows.Media.SolidColorBrush>.  En las secciones siguientes, se describen las distintas formas de pintar con <xref:System.Windows.Media.SolidColorBrush>.  
  
<a name="solidcolorinxaml"></a>   
### Usar SolidColorBrush en "XAML"  
 Para pintar un área con un color sólido en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use una de las opciones siguientes.  
  
-   Seleccione un pincel de color sólido predefinido por nombre.  Por ejemplo, puede establecer la propiedad <xref:System.Windows.Controls.Control.Background%2A> de un botón en "Red" o "MediumBlue".  Para obtener una lista del resto de los pinceles predefinidos de color sólido, vea las propiedades estáticas de la clase <xref:System.Windows.Media.Brushes>.  A continuación, se muestra un ejemplo.  
  
     [!code-xml[BrushOverviewExamples_snip#SolidColorBrushNamedColor1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushnamedcolor1xaml)]  
  
-   Elija un color de la paleta de colores de 32 bits especificando las cantidades de rojo, verde y azul que se van a combinar en un solo color sólido.  El formato para especificar un color de la paleta de 32 bits es "*\#rrggbb*", donde *rr* es un número hexadecimal de dos dígitos que especifica la cantidad relativa de rojo, *gg* especifica la cantidad de verde y *bb*, la cantidad de azul.  Además, el color se puede especificar como "\#*aarrggbb*" donde *aa* especifica el valor *alfa*, o transparencia, del color.  Este enfoque permite crear colores parcialmente transparentes.  En el ejemplo siguiente, la propiedad <xref:System.Windows.Controls.Control.Background%2A> de <xref:System.Windows.Controls.Button> se establece en rojo totalmente opaco mediante la notación hexadecimal.  
  
     [!code-xml[BrushOverviewExamples_snip#SolidColorBrushHex1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushhex1xaml)]  
  
-   Use la sintaxis de las etiquetas de las propiedades para describir <xref:System.Windows.Media.SolidColorBrush>.  Esta sintaxis es más prolija pero permite especificar valores adicionales, como la opacidad del pincel.  En el ejemplo siguiente, las propiedades <xref:System.Windows.Controls.Control.Background%2A> de dos elementos <xref:System.Windows.Controls.Button> se establecen en rojo totalmente opaco.  El color del primer pincel se describe mediante un nombre de color predefinido  y el del segundo, mediante la notación hexadecimal.  
  
     [!code-xml[BrushOverviewExamples_snip#SolidColorBrushPropertyTag1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushpropertytag1xaml)]  
  
<a name="solidcolorsincode"></a>   
### Pintar con SolidColorBrush en código  
 Para pintar un área con un color sólido en código, use una de las opciones siguientes.  
  
-   Utilice uno de los pinceles predefinidos proporcionados por la clase <xref:System.Windows.Media.Brushes>.  En el ejemplo siguiente, se establece el valor de la propiedad <xref:System.Windows.Controls.Control.Background%2A> de <xref:System.Windows.Controls.Button> en <xref:System.Windows.Media.Brushes.Red%2A>.  
  
     [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushPredefinedBrush1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushpredefinedbrush1csharp)]  
  
-   Cree un <xref:System.Windows.Media.SolidColorBrush> y establezca el valor de su propiedad <xref:System.Windows.Media.SolidColorBrush.Color%2A> mediante una estructura <xref:System.Windows.Media.Color>.  Puede utilizar un color predefinido de la clase <xref:System.Windows.Media.Colors> o puede crear un objeto <xref:System.Windows.Media.Color> mediante el método <xref:System.Windows.Media.Color.FromArgb%2A> estático.  
  
     En el ejemplo siguiente, se muestra cómo establecer la propiedad <xref:System.Windows.Media.SolidColorBrush.Color%2A> de <xref:System.Windows.Media.SolidColorBrush> con un color predefinido.  
  
     [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushPredefinedColor1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushpredefinedcolor1csharp)]  
  
 El objeto <xref:System.Windows.Media.Color.FromArgb%2A> estático permite especificar los valores [alfa](GTMT), rojo, verde y azul del color.  El intervalo normal de cada uno de estos valores está comprendido entre 0 y 255.  Por ejemplo, un valor [alpha](GTMT) de 0 indica que un color es totalmente transparente, mientras que un valor de 255 indica que el color es totalmente opaco.  De igual forma, un valor rojo de 0 indica que un color no contiene rojo, mientras un valor de 255 indica que un color contiene la cantidad máxima de rojo posible.  En el ejemplo siguiente, el color de un pincel se describe especificando los valores de alfa, rojo, verde y azul.  
  
 [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushfromArgbExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushfromargbexample1csharp)]  
  
 Para obtener las formas adicionales de especificar el color, vea el tema de referencia <xref:System.Windows.Media.Color>.  
  
<a name="gradient"></a>   
## Pintar un área con un degradado  
 Un pincel de degradado pinta un área con varios colores que se mezclan entre sí a lo largo de un eje.  Puede utilizarlos para crear impresiones de luz y sombras, dando una sensación tridimensional a los controles.  También puede utilizarlos para simular cristal, cromo, agua y otras superficies suavizadas.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona dos tipos de pinceles de degradado: <xref:System.Windows.Media.LinearGradientBrush> y <xref:System.Windows.Media.RadialGradientBrush>.  
  
<a name="lineargradientbrush"></a>   
## Degradados lineales  
 <xref:System.Windows.Media.LinearGradientBrush> pinta un área con un degradado definido a lo largo de una línea, el *eje de degradado*.  Especifique los colores del degradado y su ubicación a lo largo del eje de degradado mediante objetos <xref:System.Windows.Media.GradientStop>.  También puede modificar el eje de degradado, lo que permite crear los degradados horizontal y vertical e invertir la dirección del degradado.  El eje de degradado se describe en la sección siguiente.  De forma predeterminada, se crea un degradado diagonal.  
  
 En el ejemplo siguiente, se muestra el código que crea un degradado lineal con cuatro colores.  
  
 [!code-xml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 Este código genera el siguiente degradado.  
  
 ![Degradado lineal diagonal](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-diaglgradient-nolabel.png "wcpsdk\_graphicsmm\_diaglgradient\_nolabel")  
  
 **Nota:** los ejemplos de degradado de este tema utilizan el sistema de coordenadas predeterminado para establecer los puntos inicial y final.  El sistema de coordenadas predeterminado es relativo a un rectángulo de selección: 0 indica un 0 por ciento del rectángulo de selección y 1, un 100 por cien del rectángulo de selección.  Puede cambiar este sistema de coordenadas estableciendo la propiedad <xref:System.Windows.Media.GradientBrush.MappingMode%2A> en el valor <xref:System.Windows.Media.BrushMappingMode>.  Un sistema de coordenadas absoluto no es relativo respecto a ningún rectángulo de selección.  Los valores se interpretan directamente en el espacio local.  
  
 <xref:System.Windows.Media.GradientStop> es el bloque de creación básico de un pincel de degradado.  Un punto de degradado especifica una propiedad <xref:System.Windows.Media.GradientStop.Color%2A> en una propiedad <xref:System.Windows.Media.GradientStop.Offset%2A> a lo largo del eje de degradado.  
  
-   La propiedad <xref:System.Windows.Media.GradientStop.Color%2A> del punto de degradado especifica el color del punto.  Puede establecer el color mediante un color predefinido \(proporcionado por la clase <xref:System.Windows.Media.Colors>\) o especificando los valores ScRGB o ARGB.  En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], también puede utilizar la notación hexadecimal para describir un color.  Para obtener más información, vea la estructura <xref:System.Windows.Media.Color>.  
  
-   La propiedad <xref:System.Windows.Media.GradientStop.Offset%2A> del punto de degradado especifica la posición del color del punto en el eje de degradado.  El desplazamiento es un objeto <xref:System.Double> comprendido entre 0 y 1.  Cuanto más se aproxime el valor de desplazamiento de un punto de degradado a 0, más próximo estará el color al principio del degradado.  Cuanto más se aproxime el valor de desplazamiento a 1, más próximo estará el color al final del degradado.  
  
 El color de cada punto entre los puntos de degradado se interpola linealmente como combinación del color especificado por los dos puntos limitantes de degradado.  En la ilustración siguiente se resaltan los puntos de degradado del ejemplo anterior.  Los círculos marcan la posición de los puntos de degradado y una línea de guiones muestra el eje de degradado.  
  
 ![Delimitadores de degradado en un degradado lineal](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops.png "wcpsdk\_graphicsmm\_4gradientstops")  
  
 El primer punto de degradado especifica el color amarillo en un desplazamiento de `0.0`.  El segundo punto de degradado especifica el color rojo en un desplazamiento de `0.25`.  Los puntos entre estos dos puntos cambian gradualmente del amarillo al rojo a medida que se mueva de izquierda a derecha por el eje de degradado.  El tercer punto de degradado especifica el color azul en un desplazamiento de `0.75`.  Los puntos entre los puntos segundo y tercero de degradado cambian gradualmente del rojo al azul.  El cuarto punto de degradado especifica el color verde oscuro en un desplazamiento de `1.0`.  Los puntos entre los puntos tercero y cuarto de degradado cambian gradualmente del azul al verde oscuro.  
  
<a name="gradientaxis"></a>   
### Eje de degradado  
 Como se ha mencionado anteriormente, los puntos de degradado de un pincel de degradado lineal se colocan a lo largo de una línea, el eje de degradado.  Puede cambiar la orientación y el tamaño de la línea con las propiedades <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> del pincel.  Si manipula las propiedades <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> del pincel, puede crear degradados horizontales y verticales, invertir la dirección del degradado, comprimir la extensión del degradado, etc.  
  
 De forma predeterminada, las propiedades <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> del pincel de degradado lineal son relativos al área que se pinta.  El punto \(0,0\) representa la esquina superior izquierda del área que se pinta y \(1,1\), la esquina inferior derecha.  El valor de la propiedad <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> predeterminada de <xref:System.Windows.Media.LinearGradientBrush> es \(0,0\) y el de su propiedad <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> predeterminada es \(1,1\). De esta forma, se crea un degradado diagonal que empieza en la esquina superior izquierda y se extiende hasta la esquina inferior derecha del área que se pinta.  En la ilustración siguiente, se muestra el eje de degradado de un pincel de degradado lineal con las propiedades <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> predeterminadas.  
  
 ![Eje de degradado para un degradado lineal diagonal](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-diagonalgradientaxis.png "wcpsdk\_graphicsmm\_diagonalgradientaxis")  
  
 En el ejemplo siguiente, se muestra cómo crear un degradado horizontal especificando las propiedades <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> del pincel.  Observe que los puntos de degradado son iguales a los de los ejemplos anteriores; al cambiar las propiedades <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>, el degradado se ha cambiado de diagonal a horizontal.  
  
 [!code-xml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 En la ilustración siguiente, se muestra el degradado que se crea.  El eje de degradado se marca con una línea de guiones y los puntos de degradado, con círculos.  
  
 ![Eje de degradado para un degradado lineal horizontal](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-horizontalgradient.png "wcpsdk\_graphicsmm\_horizontalgradient")  
  
 En el ejemplo siguiente, se muestra cómo crear un degradado vertical.  
  
 [!code-xml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 En la ilustración siguiente, se muestra el degradado que se crea.  El eje de degradado se marca con una línea de guiones y los puntos de degradado, con círculos.  
  
 ![Eje de degradado para un degradado vertical](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-verticalgradient.png "wcpsdk\_graphicsmm\_verticalgradient")  
  
<a name="radialgradients"></a>   
## Degradados radiales  
 Como un <xref:System.Windows.Media.LinearGradientBrush>, un <xref:System.Windows.Media.RadialGradientBrush> pinta un área con colores que se mezclan juntos a lo largo de un eje.  Los ejemplos anteriores mostraron cómo el eje de un pincel de degradado lineal es una línea recta.  Un círculo define el eje de un pincel de degradado radial; sus colores "irradian" desde su origen.  
  
 En el ejemplo siguiente, se usa un pincel de degradado radial para pintar el interior de un rectángulo.  
  
 [!code-xml[GradientBrushExamples_snip#RadialGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/RadialGradientBrushExample.xaml#radialgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#RadialGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/RadialGradientBrushExample.cs#radialgradient1csharp)]  
  
 En la ilustración siguiente, se muestra el degradado creado en el ejemplo anterior.  Se han resaltado los puntos de degradado del pincel.  Observe que, aunque los resultados sean diferentes, los puntos de degradado de este ejemplo son idénticos a los del degradado de los ejemplos anteriores del pincel de degradado lineal.  
  
 ![Delimitadores de degradado en un degradado radial](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk\_graphicsmm\_4gradientstops\_rg")  
  
 La propiedad <xref:System.Windows.Media.RadialGradientBrush.GradientOrigin%2A> especifica el punto de inicio del eje de degradado de un pincel de degradado radial.  El eje de degradado irradia desde el origen del degradado hacia el círculo del mismo.  Al círculo del degradado de un pincel lo definen sus propiedades <xref:System.Windows.Media.RadialGradientBrush.Center%2A>, <xref:System.Windows.Media.RadialGradientBrush.RadiusX%2A> y <xref:System.Windows.Media.RadialGradientBrush.RadiusY%2A>.  
  
 Las presentaciones de la ilustración siguientes muestran varios degradados radiales con valores distintos de las propiedades <xref:System.Windows.Media.RadialGradientBrush.GradientOrigin%2A>, <xref:System.Windows.Media.RadialGradientBrush.Center%2A>, <xref:System.Windows.Media.RadialGradientBrush.RadiusX%2A> y <xref:System.Windows.Media.RadialGradientBrush.RadiusY%2A>.  
  
 ![Valores de RadialGradientBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-originscirclesandradii.png "wcpsdk\_graphicsmm\_originscirclesandradii")  
RadialGradientBrushes con valores distintos de GradientOrigin, Center, RadiusX y RadiusY.  
  
<a name="specifyinggradientcolors"></a>   
## Especificar puntos de degradado parcialmente transparentes o transparentes  
 Puesto que los puntos de degradado no proporcionan ninguna propiedad de opacidad, debe especificar el canal alfa de los colores mediante la notación hexadecimal de [!INCLUDE[TLA#tla_argb](../../../../includes/tlasharptla-argb-md.md)] del marcado o use el método <xref:System.Windows.Media.Color.FromScRgb%2A?displayProperty=fullName> para crear puntos de degradado que sean transparentes o parcialmente transparentes.  En las secciones siguientes, se explica cómo crear puntos de degradado parcialmente transparentes en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y en código.  Para obtener información sobre cómo establecer la opacidad de todo el pincel, vea la sección [Especificar la opacidad de un pincel](#brushesAndOpacity).  
  
<a name="argbsyntax"></a>   
### Especificar la opacidad del color en "XAML"  
 En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], se usa la notación hexadecimal [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] para especificar la opacidad de los colores individuales.  La notación hexadecimal [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] usa la sintaxis siguiente:  
  
 `#`**aa** *rrggbb*  
  
 *aa* en la línea anterior representa un valor hexadecimal de dos dígitos utilizado para especificar la opacidad del color.  *rr*, *gg* y *bb* representan valores hexadecimales de dos dígitos utilizados para especificar, respectivamente, la cantidad de rojo, verde y azul del color.  Cada dígito hexadecimal puede tener un valor comprendido entre 0 y 9 o entre A y F.  0 es el valor mínimo y F, el máximo.  Un valor alfa de 00 especifica un color completamente transparente, mientras que un valor alfa de FF crea un color totalmente opaco.  En el ejemplo siguiente, se utiliza la notación hexadecimal [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] para especificar dos colores.  El primero es parcialmente transparente \(tiene un valor alfa de x 20\), mientras que el segundo es totalmente opaco.  
  
 [!code-xml[GradientBrushExamples_snip#TransparentGradientStopExample1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/GradientStopsExample.xaml#transparentgradientstopexample1xaml)]  
  
<a name="fromscrgbsyntax"></a>   
### Especificar la opacidad del color en código  
 Al utilizar código, el método <xref:System.Windows.Media.Color.FromArgb%2A> estático permite especificar un valor alfa al crear un color.  El método toma cuatro parámetros de tipo <xref:System.Byte>.  El primer parámetro especifica el canal alfa del color; los otros tres, los valores de rojo, verde y azul del color.  Cada valor debe estar comprendido entre 0 y 255, ambos inclusive.  Un valor alfa de 0 especifica un color completamente transparente, mientras que un valor alfa de 255, un color totalmente opaco.  En el siguiente ejemplo, se usa el método <xref:System.Windows.Media.Color.FromArgb%2A> para crear dos colores.  El primer color es parcialmente transparente \(tiene un valor alfa de 32\), mientras que el segundo es totalmente opaco.  
  
 [!code-csharp[GradientBrushExamples_snip#TransparentGradientStopExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/GradientStopsExample.cs#transparentgradientstopexample1csharp)]  
  
 O bien, puede utilizar el método <xref:System.Windows.Media.Color.FromScRgb%2A>, que permite usar los valores de ScRGB para crear un color.  
  
<a name="otherbrushes"></a>   
## Pintar con imágenes, dibujos, elementos visuales y modelos  
 Las clases <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> y <xref:System.Windows.Media.VisualBrush> permiten pintar un área con imágenes, dibujos o elementos visuales.  Para obtener información sobre cómo pintar con imágenes, dibujos y modelos, vea [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
## Vea también  
 <xref:System.Windows.Media.Brush>   
 <xref:System.Windows.Media.SolidColorBrush>   
 <xref:System.Windows.Media.LinearGradientBrush>   
 <xref:System.Windows.Media.RadialGradientBrush>   
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Información general sobre la transformación de pinceles](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)   
 [Niveles de representación de gráficos](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)