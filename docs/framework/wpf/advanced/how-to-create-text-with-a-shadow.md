---
title: Procedimiento Crear texto con sombreado
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: 0fe64e4e9e7aadbd30a38743647251f9fa49ba95
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960441"
---
# <a name="how-to-create-text-with-a-shadow"></a>Procedimiento Crear texto con sombreado
En los ejemplos de esta sección se muestra cómo crear un efecto de sombreado para el texto mostrado.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Media.Effects.DropShadowEffect> objeto permite crear una variedad de efectos de sombra paralela para [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] los objetos. En el ejemplo siguiente se muestra un efecto de sombra paralela aplicado al texto. En este caso, la sombra es suave, lo que significa que su color se desenfoca.  
  
 ![Sombra de texto con suavidad &#61; 0,25](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg) 
  
 Puede controlar el ancho de una sombra estableciendo la <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> propiedad. Un valor de `4.0` indica un ancho de sombra de 4 píxeles. Puede controlar la suavidad, o desenfoque, de una sombra modificando la <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> propiedad. Un valor de `0.0` indica que no hay ningún desenfoque. El ejemplo de código siguiente muestra cómo crear una sombra suave.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
> Estos efectos de sombra no pasan por la [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] canalización de representación de texto. Como resultado, ClearType está deshabilitado cuando se usan estos efectos.  
  
 En el ejemplo siguiente se muestra un efecto de sombra paralela intensa aplicado al texto. En este caso, la sombra no está desenfocada.  
  
 ![Sombra de texto con suavidad &#61; 0](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg) 
  
 Puede crear una sombra difícil estableciendo la <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> propiedad en `0.0`, lo que indica que no se usa ningún desenfoque. Puede controlar la dirección de la sombra modificando la <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> propiedad. Establezca el valor direccional de esta propiedad en un grado entre `0` y `360`. En la ilustración siguiente se muestran los valores direccionales del valor de la <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> propiedad.  
  
 ![Valor de grado de sombra paralela de una sombra](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 En el ejemplo de código siguiente se muestra cómo crear una sombra intensa.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a>Uso de un efecto de desenfoque  
 Se <xref:System.Windows.Media.Effects.BlurBitmapEffect> puede usar para crear un efecto de sombra que se puede colocar detrás de un objeto de texto. Un efecto de mapa de bits de desenfoque aplicado al texto desenfoca el texto de manera uniforme en todas las direcciones.  
  
 En el ejemplo siguiente se muestra un efecto de desenfoque aplicado al texto.  
  
 ![Sombra de texto usando BlurBitmapEffect](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 En el ejemplo de código siguiente se muestra cómo crear un efecto de desenfoque.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a>Uso de una transformación de traslación  
 Se <xref:System.Windows.Media.TranslateTransform> puede usar para crear un efecto de sombra que se puede colocar detrás de un objeto de texto.  
  
 En el ejemplo de código siguiente <xref:System.Windows.Media.TranslateTransform> se utiliza para desplazar el texto. En este ejemplo, una copia ligeramente desplazada del texto bajo el texto primario crea un efecto de sombra.  
  
 ![Sombra de texto usando TranslateTransform](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)    
  
 En el ejemplo de código siguiente se muestra cómo crear una transformación para un efecto de sombra.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
