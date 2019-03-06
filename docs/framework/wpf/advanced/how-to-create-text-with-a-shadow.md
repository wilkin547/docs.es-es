---
title: Filtrar Crear texto con sombreado
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: 4d200aa980e8f2e6d22291669dfb07db54a5f0c0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370688"
---
# <a name="how-to-create-text-with-a-shadow"></a>Filtrar Crear texto con sombreado
En los ejemplos de esta sección se muestra cómo crear un efecto de sombreado para el texto mostrado.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Media.Effects.DropShadowEffect> objeto le permite crear una variedad de colocar los efectos de sombra para [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objetos. En el ejemplo siguiente se muestra un efecto de sombra paralela aplicado al texto. En este caso, la sombra es suave, lo que significa que su color se desenfoca.  
  
 ![Sombra de texto con suavidad &#61; 0,25](./media/shadowtext01.jpg "ShadowText01")  
Ejemplo de texto con una sombra suave  
  
 Puede controlar el ancho de una sombra estableciendo el <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> propiedad. Un valor de `4.0` indica un ancho de la sombra de 4 píxeles. Puede controlar la suavidad o el desenfoque de una sombra modificando el <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> propiedad. Un valor de `0.0` no indica que existe desenfoque. El ejemplo de código siguiente muestra cómo crear una sombra suave.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  Estos efectos de sombra no pasan por la [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] canalización de representación de texto. Como resultado, ClearType está deshabilitado cuando se usan estos efectos.  
  
 En el ejemplo siguiente se muestra un efecto de sombra paralela intensa aplicado al texto. En este caso, la sombra no está desenfocada.  
  
 ![Sombra de texto con suavidad &#61; 0](./media/shadowtext02.jpg "ShadowText02")  
Ejemplo de texto con una sombra intensa  
  
 Puede crear una sombra intensa estableciendo el <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> propiedad `0.0`, lo que indica que no se usa desenfoque. Puede controlar la dirección de la sombra modificando el <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> propiedad. Establezca el valor direccional de esta propiedad en un grado entre `0` y `360`. La ilustración siguiente muestra los valores de dirección la <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> configuración de la propiedad.  
  
 ![Configuración de un objeto DropShadow grado de sombra](./media/shadowtext08.png "ShadowText08")  
Diagrama de dirección de un objeto DropShadow  
  
 En el ejemplo de código siguiente se muestra cómo crear una sombra intensa.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a>Uso de un efecto de desenfoque  
 Un <xref:System.Windows.Media.Effects.BlurBitmapEffect> puede usarse para crear un efecto de sombra que se pueda ubicar detrás de un objeto de texto. Un efecto de mapa de bits de desenfoque aplicado al texto desenfoca el texto de manera uniforme en todas las direcciones.  
  
 En el ejemplo siguiente se muestra un efecto de desenfoque aplicado al texto.  
  
 ![Sombra de texto usando BlurBitmapEffect](./media/shadowtext06.jpg "ShadowText06")  
Ejemplo de texto con efecto de desenfoque  
  
 En el ejemplo de código siguiente se muestra cómo crear un efecto de desenfoque.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a>Uso de una transformación de traslación  
 Un <xref:System.Windows.Media.TranslateTransform> puede usarse para crear un efecto de sombra que se pueda ubicar detrás de un objeto de texto.  
  
 El siguiente ejemplo de código utiliza un <xref:System.Windows.Media.TranslateTransform> para desplazar el texto. En este ejemplo, una copia ligeramente desplazada del texto bajo el texto primario crea un efecto de sombra.  
  
 ![Sombra de texto usando TranslateTransform](./media/shadowtext07.jpg "ShadowText07")  
Ejemplo de texto que usa una transformación para un efecto de sombra  
  
 En el ejemplo de código siguiente se muestra cómo crear una transformación para un efecto de sombra.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
