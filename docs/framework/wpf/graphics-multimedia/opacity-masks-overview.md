---
title: Información general sobre las máscaras de opacidad
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [WPF], opacity masks
- masks [WPF], opacity
- opacity [WPF], masks
ms.assetid: 22367fab-5f59-4583-abfd-db2bf86eaef7
ms.openlocfilehash: 76ec595b1d2cc732e1c8bc2dc2ca6def904bf94c
ms.sourcegitcommit: 43761fcee10aeefcf851ea81cea3f3c691420856
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "69545345"
---
# <a name="opacity-masks-overview"></a>Información general sobre las máscaras de opacidad
Las máscaras de opacidad permiten hacer que partes de un elemento o un objeto visual sea total o parcialmente transparentes. Para crear una máscara de opacidad, aplique <xref:System.Windows.Media.Brush> a la <xref:System.Windows.UIElement.OpacityMask%2A> propiedad de un elemento o <xref:System.Windows.Media.Visual>.  El pincel se asigna al elemento o al objeto visual, y el valor de opacidad de cada píxel del pincel se usa para determinar la opacidad resultante de cada píxel correspondiente del elemento o objeto visual.  
  
<a name="prereqs"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En esta información general se supone que está <xref:System.Windows.Media.Brush> familiarizado con los objetos. Para una introducción sobre el uso de los pinceles, consulte [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md). Para obtener información <xref:System.Windows.Media.ImageBrush> sobre <xref:System.Windows.Media.DrawingBrush>y, vea [pintar con imágenes, dibujos y objetos visuales](painting-with-images-drawings-and-visuals.md).  
  
<a name="opacitymasks"></a>   
## <a name="creating-visual-effects-with-opacity-masks"></a>Creación de efectos visuales con máscaras de opacidad  
 Una máscara de opacidad funciona asignado su contenido al elemento o al objeto visual. Luego, el canal alfa de cada uno de los píxeles del pincel se usa para determinar la opacidad resultante de los píxeles correspondientes del elemento o el objeto visual y se omite el color real del pincel. Si una parte determinada del pincel es transparente, la parte correspondiente del elemento o del objeto visual se vuelve transparente. Si una parte determinada del pincel es opaca, no se modifica la parte correspondiente del elemento o del objeto visual. La opacidad que la máscara de opacidad especifica se combina con cualquier ajuste de opacidad existente en el elemento o el objeto visual. Por ejemplo, si un elemento es opaco en un 25 por ciento y se le aplica una máscara de opacidad que realiza la transición desde totalmente opaco a totalmente transparente, el resultado es un elemento que hace una transición desde el 25 por ciento de opacidad a totalmente transparente.  
  
> [!NOTE]
>  Aunque en los ejemplos de esta información general se muestra el uso de las máscaras de opacidad en los elementos de imagen, una máscara de <xref:System.Windows.Media.Visual>opacidad se puede aplicar a cualquier elemento o, incluidos los paneles y controles.  
  
 Las máscaras de opacidad se usan para crear efectos visuales interesantes, como crear imágenes o botones que se desvanecen mediante un fundido, agregar texturas a los elementos o combinar degradados para generar superficies cristalinas. En la ilustración siguiente se muestra el uso de una máscara de opacidad. Se usa un fondo de cuadros para mostrar los elementos transparentes de la máscara.  
  
 ![Objeto con una máscara de opacidad LinearGradientBrush](./media/wcpsdk-graphicsmm-opacitymask-imageexample.png "wcpsdk_graphicsmm_opacitymask_imageexample")  
Ejemplo de máscara de opacidad  
  
<a name="creatingopacitymasks"></a>   
## <a name="creating-an-opacity-mask"></a>Creación de una máscara de opacidad  
 Para crear una máscara de opacidad, cree un <xref:System.Windows.Media.Brush> y aplíquelo a la <xref:System.Windows.UIElement.OpacityMask%2A> propiedad de un elemento u objetos visuales. Puede usar cualquier tipo de <xref:System.Windows.Media.Brush> como máscara de opacidad.  
  
- <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>: Se usa para hacer que un elemento o visual se atenúe de la vista.  
  
     En la imagen siguiente se <xref:System.Windows.Media.LinearGradientBrush> muestra una usada como máscara de opacidad.  
  
     ![Objeto con una máscara de opacidad LinearGradientBrush](./media/wcpsdk-graphicsmm-brushes-lineagradientopacitymasksingle.jpg "wcpsdk_graphicsmm_brushes_lineagradientopacitymasksingle")  
Ejemplo de máscara de opacidad LinearGradientBrush  
  
- <xref:System.Windows.Media.ImageBrush>: Se usa para crear texturas y efectos de borde automáticos o inversos.  
  
     En la imagen siguiente se <xref:System.Windows.Media.ImageBrush> muestra una usada como máscara de opacidad.  
  
     ![Objeto que tiene una máscara de opacidad ImageBrush](./media/wcpsdk-graphicsmm-brushes-imageasopacitymasksingle.jpg "wcpsdk_graphicsmm_brushes_imageasopacitymasksingle")  
Ejemplo de máscara de opacidad LinearGradientBrush  
  
- <xref:System.Windows.Media.DrawingBrush>: Se usa para crear máscaras de opacidad complejas a partir de patrones de formas, imágenes y degradados.  
  
     En la imagen siguiente se <xref:System.Windows.Media.DrawingBrush> muestra una usada como máscara de opacidad.  
  
     ![Objeto con una máscara de opacidad DrawingBrush](./media/wcpsdk-drawingbrushasopacitymask-single.jpg "wcpsdk_drawingbrushasopacitymask_single")  
Ejemplo de máscara de opacidad DrawingBrush  
  
 Los pinceles de<xref:System.Windows.Media.LinearGradientBrush> degradado (y <xref:System.Windows.Media.RadialGradientBrush>) son especialmente adecuados para su uso como máscara de opacidad. Dado que <xref:System.Windows.Media.SolidColorBrush> un rellena un área con un color uniforme, las máscaras de opacidad son deficientes; <xref:System.Windows.Media.SolidColorBrush> el uso de es equivalente al establecimiento de la <xref:System.Windows.UIElement.OpacityMask%2A> propiedad del elemento u objetos visuales.  
  
<a name="creatingopacitymaskswithgradients"></a>   
## <a name="using-a-gradient-as-an-opacity-mask"></a>Uso de degradado como máscara de opacidad  
 Para crear un relleno de degradado, se especifican dos o más delimitadores de degradado. Cada delimitador de degradado contiene un color y una posición (consulte [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md) para más información sobre cómo crear y usar degradados). El proceso es el mismo cuando se usa un degradado como máscara de opacidad, con la excepción de que, en lugar de combinar los colores, el degradado de la máscara de opacidad combina los valores del canal alfa. Por lo tanto, no importa el color real del contenido del degradado; solo importa el canal alfa, u opacidad, de cada color. A continuación se muestra un ejemplo.  
  
 [!code-xaml[OpacityMasksSnippet#LinearGradientOpacityMaskonImage](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/GradientBrushExample.xaml#lineargradientopacitymaskonimage)]  
  
<a name="specifyinggradientcolors"></a>   
## <a name="specifying-gradient-stops-for-an-opacity-mask"></a>Especificación de delimitadores de degradado para una máscara de opacidad  
 En el ejemplo anterior, el color <xref:System.Windows.Media.Colors.Black%2A> definido por el sistema se usa como color inicial del degradado. Dado que todos los colores de la <xref:System.Windows.Media.Colors> clase, excepto <xref:System.Windows.Media.Colors.Transparent%2A>, son totalmente opacos, se pueden usar para definir simplemente un color de inicio para una máscara de opacidad de degradado.  
  
 Para tener un mayor control sobre los valores alfa al definir una máscara de opacidad, puede especificar el canal alfa de los colores mediante la notación hexadecimal ARGB <xref:System.Windows.Media.Color.FromScRgb%2A?displayProperty=nameWithType> en el marcado o mediante el método.  
  
<a name="argbsyntax"></a>   
### <a name="specifying-color-opacity-in-xaml"></a>Especificación de la opacidad del color en "XAML"  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], se usa la notación hexadecimal ARGB para especificar la opacidad de los colores individuales. La notación hexadecimal ARGB utiliza la sintaxis siguiente:  
  
 `#` **aa** *rrggbb*  
  
 El valor *aa* de la línea anterior representa un valor hexadecimal de dos dígitos que se usa para especificar la opacidad del color. Cada uno de los valores *rr*, *gg* y *bb* representa un valor hexadecimal de dos dígitos que se usa para especificar la cantidad de rojo, verde y azul en el color. Cada dígito hexadecimal debe tener un valor entre 0 t 9 y entre A y F. 0 es el valor menor y F, el mayor. Un valor alfa de 00 especifica un color completamente transparente, mientras que un valor alfa de FF crea un color completamente opaco.  En el ejemplo siguiente, la notación ARGB hexadecimal se usa para especificar dos colores. El primero es completamente opaco, mientras que el segundo, completamente transparente.  
  
 [!code-xaml[OpacityMasksSnippet#AARRGGBBValueonOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/GradientBrushExample.xaml#aarrggbbvalueonopacitymask)]  
  
<a name="usingimageasopacitymask"></a>   
## <a name="using-an-image-as-an-opacity-mask"></a>Uso de imagen como máscara de opacidad  
 También se pueden usar imágenes como máscara de opacidad. En la imagen siguiente se muestra un ejemplo. Se usa un fondo de cuadros para mostrar los elementos transparentes de la máscara.  
  
 ![Objeto con una máscara de opacidad ImageBrush](./media/wcpsdk-graphicsmm-imageasopacitymask.png "wcpsdk_graphicsmm_imageasopacitymask")  
Ejemplo de máscara de opacidad  
  
 Para usar una imagen como una máscara de opacidad, use <xref:System.Windows.Media.ImageBrush> para que contenga la imagen. Al crear una imagen para usarla como máscara de opacidad, guarde la imagen en un formato que admita varios niveles de transparencia, como Portable Network Graphics (PNG). En el ejemplo siguiente se muestra el código que se usó para crear la ilustración anterior.  
  
 [!code-xaml[OpacityMasksSnippet#UIElementOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/ImageBrushExample.xaml#uielementopacitymask)]  
  
<a name="tilingimageopacitymask"></a>   
### <a name="using-a-tiled-image-as-an-opacity-mask"></a>Uso de imagen en mosaico como máscara de opacidad  
 En el ejemplo siguiente, se usa la misma imagen con otra <xref:System.Windows.Media.ImageBrush>, pero las características de mosaico del pincel se usan para generar mosaicos de la imagen 50 píxeles cuadrados.  
  
 [!code-xaml[OpacityMasksSnippet#TiledImageasOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/ImageBrushExample.xaml#tiledimageasopacitymask)]  
  
<a name="drawingbrushasopacitymask"></a>   
## <a name="creating-an-opacity-mask-from-a-drawing"></a>Creación de una máscara de opacidad a partir de un dibujo  
 Se pueden usar dibujos como máscara de opacidad. Las formas contenidas en el dibujo se pueden rellenar con degradados, colores sólidos, imágenes e, incluso, otros dibujos. La imagen siguiente muestra un ejemplo de un dibujo que se usa como máscara de opacidad. Se usa un fondo de cuadros para mostrar los elementos transparentes de la máscara.  
  
 ![Objeto con una máscara de opacidad DrawingBrush](./media/wcpsdk-drawingbrushasopacitymask.png "wcpsdk_drawingbrushasopacitymask")  
Ejemplo de máscara de opacidad DrawingBrush  
  
 Para usar un dibujo como máscara de opacidad, use un <xref:System.Windows.Media.DrawingBrush> para que contenga el dibujo. En el ejemplo siguiente se muestra el código que se usó para crear la ilustración anterior:  
  
 [!code-xaml[OpacityMasksSnippet#OpacityMaskfromDrawing](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/DrawingBrushExample.xaml#opacitymaskfromdrawing)]  
  
<a name="tileddrawingbrush"></a>   
### <a name="using-a-tiled-drawing-as-an-opacity-mask"></a>Uso de dibujo en mosaico como máscara de opacidad  
 Al igual que <xref:System.Windows.Media.DrawingBrush> ,sepuedehacerqueel<xref:System.Windows.Media.ImageBrush>dibujo en mosaico. En el ejemplo siguiente, se usa un pincel con dibujo para crear una máscara de opacidad en mosaico.  
  
 [!code-xaml[OpacityMasksSnippet#TiledDrawingasOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/DrawingBrushExample.xaml#tileddrawingasopacitymask)]  
  
## <a name="see-also"></a>Vea también

- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
- [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md)
