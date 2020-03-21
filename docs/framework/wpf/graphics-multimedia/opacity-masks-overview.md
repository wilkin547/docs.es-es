---
title: Información general sobre las máscaras de opacidad
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [WPF], opacity masks
- masks [WPF], opacity
- opacity [WPF], masks
ms.assetid: 22367fab-5f59-4583-abfd-db2bf86eaef7
ms.openlocfilehash: 0c859659c35e2a5806b8585214c87c18fbcb62d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187683"
---
# <a name="opacity-masks-overview"></a>Información general sobre las máscaras de opacidad
Las máscaras de opacidad permiten hacer que partes de un elemento o un objeto visual sea total o parcialmente transparentes. Para crear una máscara de <xref:System.Windows.Media.Brush> opacidad, <xref:System.Windows.UIElement.OpacityMask%2A> aplique a <xref:System.Windows.Media.Visual>a la propiedad de un elemento o .  El pincel se asigna al elemento o al objeto visual, y el valor de opacidad de cada píxel del pincel se usa para determinar la opacidad resultante de cada píxel correspondiente del elemento o objeto visual.  
  
<a name="prereqs"></a>
## <a name="prerequisites"></a>Requisitos previos  
 En este resumen se supone <xref:System.Windows.Media.Brush> que está familiarizado con los objetos. Para una introducción sobre el uso de los pinceles, consulte [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md). Para obtener <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush>información sobre y , consulte [Pintura con imágenes, dibujos y objetos visuales](painting-with-images-drawings-and-visuals.md).  
  
<a name="opacitymasks"></a>
## <a name="creating-visual-effects-with-opacity-masks"></a>Creación de efectos visuales con máscaras de opacidad  
 Una máscara de opacidad funciona asignado su contenido al elemento o al objeto visual. Luego, el canal alfa de cada uno de los píxeles del pincel se usa para determinar la opacidad resultante de los píxeles correspondientes del elemento o el objeto visual y se omite el color real del pincel. Si una parte determinada del pincel es transparente, la parte correspondiente del elemento o del objeto visual se vuelve transparente. Si una parte determinada del pincel es opaca, no se modifica la parte correspondiente del elemento o del objeto visual. La opacidad que la máscara de opacidad especifica se combina con cualquier ajuste de opacidad existente en el elemento o el objeto visual. Por ejemplo, si un elemento es opaco en un 25 por ciento y se le aplica una máscara de opacidad que realiza la transición desde totalmente opaco a totalmente transparente, el resultado es un elemento que hace una transición desde el 25 por ciento de opacidad a totalmente transparente.  
  
> [!NOTE]
> Aunque los ejemplos de esta información general muestran el uso de máscaras de opacidad <xref:System.Windows.Media.Visual>en elementos de imagen, se puede aplicar una máscara de opacidad a cualquier elemento o , incluidos los paneles y controles.  
  
 Las máscaras de opacidad se usan para crear efectos visuales interesantes, como crear imágenes o botones que se desvanecen mediante un fundido, agregar texturas a los elementos o combinar degradados para generar superficies cristalinas. En la ilustración siguiente se muestra el uso de una máscara de opacidad. Se usa un fondo de cuadros para mostrar los elementos transparentes de la máscara.  
  
 ![Objeto con una máscara de opacidad LinearGradientBrush](./media/wcpsdk-graphicsmm-opacitymask-imageexample.png "wcpsdk_graphicsmm_opacitymask_imageexample")  
Ejemplo de máscara de opacidad  
  
<a name="creatingopacitymasks"></a>
## <a name="creating-an-opacity-mask"></a>Creación de una máscara de opacidad  
 Para crear una máscara de <xref:System.Windows.Media.Brush> opacidad, cree <xref:System.Windows.UIElement.OpacityMask%2A> una y aplíquela a la propiedad de un elemento o objeto visual. Puede utilizar cualquier <xref:System.Windows.Media.Brush> tipo de máscara de opacidad.  
  
- <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>: Se utiliza para hacer que un elemento o visual se desvanezca de la vista.  
  
     La siguiente imagen <xref:System.Windows.Media.LinearGradientBrush> muestra un usado como máscara de opacidad.  
  
     ![Objeto con una máscara de opacidad LinearGradientBrush](./media/wcpsdk-graphicsmm-brushes-lineagradientopacitymasksingle.jpg "wcpsdk_graphicsmm_brushes_lineagradientopacitymasksingle")  
Ejemplo de máscara de opacidad LinearGradientBrush  
  
- <xref:System.Windows.Media.ImageBrush>: Se utiliza para crear textura y efectos de borde suaves o desgarrados.  
  
     La siguiente imagen <xref:System.Windows.Media.ImageBrush> muestra un uso como máscara de opacidad.  
  
     ![Objeto con una máscara de opacidad ImageBrush](./media/wcpsdk-graphicsmm-brushes-imageasopacitymasksingle.jpg "wcpsdk_graphicsmm_brushes_imageasopacitymasksingle")  
Ejemplo de máscara de opacidad LinearGradientBrush  
  
- <xref:System.Windows.Media.DrawingBrush>: Se utiliza para crear máscaras de opacidad complejas a partir de patrones de formas, imágenes y degradados.  
  
     La siguiente imagen <xref:System.Windows.Media.DrawingBrush> muestra un usado como máscara de opacidad.  
  
     ![Objeto con una máscara de opacidad DrawingBrush](./media/wcpsdk-drawingbrushasopacitymask-single.jpg "wcpsdk_drawingbrushasopacitymask_single")  
Ejemplo de máscara de opacidad DrawingBrush  
  
 Los pinceles<xref:System.Windows.Media.LinearGradientBrush> de <xref:System.Windows.Media.RadialGradientBrush>degradado ( y ) son especialmente adecuados para su uso como máscara de opacidad. Debido <xref:System.Windows.Media.SolidColorBrush> a que un rellena un área con un color uniforme, hacen máscaras de opacidad deficientes; usar <xref:System.Windows.Media.SolidColorBrush> a equivale a establecer la propiedad <xref:System.Windows.UIElement.OpacityMask%2A> del elemento o del objeto visual.  
  
<a name="creatingopacitymaskswithgradients"></a>
## <a name="using-a-gradient-as-an-opacity-mask"></a>Uso de degradado como máscara de opacidad  
 Para crear un relleno de degradado, se especifican dos o más delimitadores de degradado. Cada delimitador de degradado contiene un color y una posición (consulte [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md) para más información sobre cómo crear y usar degradados). El proceso es el mismo cuando se usa un degradado como máscara de opacidad, con la excepción de que, en lugar de combinar los colores, el degradado de la máscara de opacidad combina los valores del canal alfa. Por lo tanto, no importa el color real del contenido del degradado; solo importa el canal alfa, u opacidad, de cada color. A continuación se muestra un ejemplo.  
  
 [!code-xaml[OpacityMasksSnippet#LinearGradientOpacityMaskonImage](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/GradientBrushExample.xaml#lineargradientopacitymaskonimage)]  
  
<a name="specifyinggradientcolors"></a>
## <a name="specifying-gradient-stops-for-an-opacity-mask"></a>Especificación de delimitadores de degradado para una máscara de opacidad  
 En el ejemplo anterior, el <xref:System.Windows.Media.Colors.Black%2A> color definido por el sistema se utiliza como el color inicial del degradado. Dado que todos los <xref:System.Windows.Media.Colors> colores <xref:System.Windows.Media.Colors.Transparent%2A>de la clase, excepto , son totalmente opacos, se pueden utilizar para definir simplemente un color inicial para una máscara de opacidad de degradado.  
  
 Para obtener un control adicional sobre los valores alfa al definir una máscara de opacidad, puede <xref:System.Windows.Media.Color.FromScRgb%2A?displayProperty=nameWithType> especificar el canal alfa de colores mediante la notación hexadecimal ARGB en el marcado o mediante el método.  
  
<a name="argbsyntax"></a>
### <a name="specifying-color-opacity-in-xaml"></a>Especificación de la opacidad del color en "XAML"  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], se utiliza la notación hexadecimal ARGB para especificar la opacidad de colores individuales. La notación hexadecimal ARGB utiliza la sintaxis siguiente:  
  
 `#` **aa** *rrggbb*  
  
 El valor *aa* de la línea anterior representa un valor hexadecimal de dos dígitos que se usa para especificar la opacidad del color. Cada uno de los valores *rr*, *gg* y *bb* representa un valor hexadecimal de dos dígitos que se usa para especificar la cantidad de rojo, verde y azul en el color. Cada dígito hexadecimal debe tener un valor entre 0 t 9 y entre A y F. 0 es el valor menor y F, el mayor. Un valor alfa de 00 especifica un color completamente transparente, mientras que un valor alfa de FF crea un color completamente opaco.  En el ejemplo siguiente, la notación ARGB hexadecimal se utiliza para especificar dos colores. El primero es completamente opaco, mientras que el segundo, completamente transparente.  
  
 [!code-xaml[OpacityMasksSnippet#AARRGGBBValueonOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/GradientBrushExample.xaml#aarrggbbvalueonopacitymask)]  
  
<a name="usingimageasopacitymask"></a>
## <a name="using-an-image-as-an-opacity-mask"></a>Uso de imagen como máscara de opacidad  
 También se pueden usar imágenes como máscara de opacidad. En la imagen siguiente se muestra un ejemplo: Se usa un fondo de cuadros para mostrar los elementos transparentes de la máscara.  
  
 ![Objeto con una máscara de opacidad ImageBrush](./media/wcpsdk-graphicsmm-imageasopacitymask.png "wcpsdk_graphicsmm_imageasopacitymask")  
Ejemplo de máscara de opacidad  
  
 Para utilizar una imagen como máscara <xref:System.Windows.Media.ImageBrush> de opacidad, utilice un para contener la imagen. Al crear una imagen que se utilizará como máscara de opacidad, guarde la imagen en un formato que admita varios niveles de transparencia, como gráficos de red portátiles (PNG). En el ejemplo siguiente se muestra el código que se usó para crear la ilustración anterior.  
  
 [!code-xaml[OpacityMasksSnippet#UIElementOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/ImageBrushExample.xaml#uielementopacitymask)]  
  
<a name="tilingimageopacitymask"></a>
### <a name="using-a-tiled-image-as-an-opacity-mask"></a>Uso de imagen en mosaico como máscara de opacidad  
 En el ejemplo siguiente, la misma <xref:System.Windows.Media.ImageBrush>imagen se utiliza con otra , pero las entidades de mosaico del pincel se utilizan para producir mosaicos de la imagen de 50 píxeles cuadrados.  
  
 [!code-xaml[OpacityMasksSnippet#TiledImageasOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/ImageBrushExample.xaml#tiledimageasopacitymask)]  
  
<a name="drawingbrushasopacitymask"></a>
## <a name="creating-an-opacity-mask-from-a-drawing"></a>Creación de una máscara de opacidad a partir de un dibujo  
 Se pueden usar dibujos como máscara de opacidad. Las formas contenidas en el dibujo se pueden rellenar con degradados, colores sólidos, imágenes e, incluso, otros dibujos. La imagen siguiente muestra un ejemplo de un dibujo que se usa como máscara de opacidad. Se usa un fondo de cuadros para mostrar los elementos transparentes de la máscara.  
  
 ![Objeto con una máscara de opacidad DrawingBrush](./media/wcpsdk-drawingbrushasopacitymask.png "wcpsdk_drawingbrushasopacitymask")  
Ejemplo de máscara de opacidad DrawingBrush  
  
 Para utilizar un dibujo como máscara <xref:System.Windows.Media.DrawingBrush> de opacidad, utilice a para contener el dibujo. En el ejemplo siguiente se muestra el código que se usó para crear la ilustración anterior:  
  
 [!code-xaml[OpacityMasksSnippet#OpacityMaskfromDrawing](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/DrawingBrushExample.xaml#opacitymaskfromdrawing)]  
  
<a name="tileddrawingbrush"></a>
### <a name="using-a-tiled-drawing-as-an-opacity-mask"></a>Uso de dibujo en mosaico como máscara de opacidad  
 Al <xref:System.Windows.Media.ImageBrush>igual <xref:System.Windows.Media.DrawingBrush> que el , el se puede hacer para teselar su dibujo. En el ejemplo siguiente, se usa un pincel con dibujo para crear una máscara de opacidad en mosaico.  
  
 [!code-xaml[OpacityMasksSnippet#TiledDrawingasOpacityMask](~/samples/snippets/csharp/VS_Snippets_Wpf/OpacityMasksSnippet/CS/DrawingBrushExample.xaml#tileddrawingasopacitymask)]  
  
## <a name="see-also"></a>Consulte también

- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
- [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md)
