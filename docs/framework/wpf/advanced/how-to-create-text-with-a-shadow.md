---
title: 'Cómo: Crear texto con sombreado'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: 1b7740284afcda6eab41fb68be3b4a2f032cc77d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-text-with-a-shadow"></a>Cómo: Crear texto con sombreado
En los ejemplos de esta sección se muestra cómo crear un efecto de sombreado para el texto mostrado.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Media.Effects.DropShadowEffect> objeto le permite crear una variedad de colocar los efectos de sombra para [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objetos. En el ejemplo siguiente se muestra un efecto de sombra paralela aplicado al texto. En este caso, la sombra es suave, lo que significa que su color se desenfoca.  
  
 ![Sombra de texto con suavidad &#61; 0,25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")  
Ejemplo de texto con una sombra suave  
  
 Puede controlar el ancho de una sombra estableciendo la <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> propiedad. Un valor de `4.0` indica un ancho de la sombra de 4 píxeles. Puede controlar la suavidad, o desenfoque, de una sombra modificando la <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> propiedad. Un valor de `0.0` indica que no está. El ejemplo de código siguiente muestra cómo crear una sombra suave.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  Estos efectos de sombra no pasan a través de la [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] canalización de representación de texto. Como resultado, ClearType está deshabilitado cuando se usan estos efectos.  
  
 En el ejemplo siguiente se muestra un efecto de sombra paralela intensa aplicado al texto. En este caso, la sombra no está desenfocada.  
  
 ![Sombra de texto con suavidad &#61; 0](../../../../docs/framework/wpf/advanced/media/shadowtext02.jpg "ShadowText02")  
Ejemplo de texto con una sombra intensa  
  
 Puede crear una sombra nítida estableciendo la <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> propiedad `0.0`, lo que indica que se utiliza ningún desenfoque. Puede controlar la dirección de la sombra modificando la <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> propiedad. Establezca el valor direccional de esta propiedad en un grado entre `0` y `360`. La ilustración siguiente muestra los valores de dirección de la <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> configuración de la propiedad.  
  
 ![Valor de grado de sombra paralela de sombra](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")  
Diagrama de dirección de un objeto DropShadow  
  
 En el ejemplo de código siguiente se muestra cómo crear una sombra intensa.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a>Uso de un efecto de desenfoque  
 Un <xref:System.Windows.Media.Effects.BlurBitmapEffect> puede utilizarse para crear un efecto similar a la sombra que puede colocarse detrás de un objeto de texto. Un efecto de mapa de bits de desenfoque aplicado al texto desenfoca el texto de manera uniforme en todas las direcciones.  
  
 En el ejemplo siguiente se muestra un efecto de desenfoque aplicado al texto.  
  
 ![Sombra de texto usando BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")  
Ejemplo de texto con efecto de desenfoque  
  
 En el ejemplo de código siguiente se muestra cómo crear un efecto de desenfoque.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a>Uso de una transformación de traslación  
 Un <xref:System.Windows.Media.TranslateTransform> puede utilizarse para crear un efecto similar a la sombra que puede colocarse detrás de un objeto de texto.  
  
 El siguiente ejemplo de código utiliza un <xref:System.Windows.Media.TranslateTransform> para desplazar el texto. En este ejemplo, una copia ligeramente desplazada del texto bajo el texto primario crea un efecto de sombra.  
  
 ![Sombra de texto usando TranslateTransform](../../../../docs/framework/wpf/advanced/media/shadowtext07.jpg "ShadowText07")  
Ejemplo de texto que usa una transformación para un efecto de sombra  
  
 En el ejemplo de código siguiente se muestra cómo crear una transformación para un efecto de sombra.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
