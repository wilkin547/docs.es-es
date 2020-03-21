---
title: 'Cómo: Aplicar transformaciones a texto'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], rotated text
- typography [WPF], scaled text
- skewed text [WPF]
- typography [WPF], translated text
- typography [WPF], shadowed text
- rotated text [WPF]
- translated text [WPF]
- shadowed text [WPF]
- transforms in text [WPF]
- typography [WPF], transforms
- scaled text [WPF]
- typography [WPF], skewed text
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
ms.openlocfilehash: 867f39e3df8493014d8601530e91310c3bbbeeb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141619"
---
# <a name="how-to-apply-transforms-to-text"></a>Cómo: Aplicar transformaciones a texto
Las transformaciones pueden modificar la presentación del texto en la aplicación. En los ejemplos siguientes se utilizan diferentes tipos de <xref:System.Windows.Controls.TextBlock> transformaciones de representación para afectar a la visualización de texto en un control.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el texto girado sobre un punto especificado en el plano x-y bidimensional.  
  
 ![Texto girado usando RotateTransform](./media/how-to-apply-transforms-to-text/text-rotated-ninety-degrees.jpg)  
  
 En el ejemplo <xref:System.Windows.Media.RotateTransform> de código siguiente se usa a para rotar texto. Un <xref:System.Windows.Media.RotateTransform.Angle%2A> valor de 90 gira el elemento 90 grados en el sentido de las agujas del reloj.  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 En el ejemplo siguiente se muestra la segunda línea de texto escalada al 150 % a lo largo del eje X y la tercera línea de texto escalada al 150 % a lo largo del eje Y.  
  
 ![Texto con escala ajustada usando ScaleTransform](./media/how-to-apply-transforms-to-text/scaled-text-scaletransform.jpg)
  
 En el ejemplo <xref:System.Windows.Media.ScaleTransform> de código siguiente se usa a para escalar texto de su tamaño original.  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
> Escalar texto no es lo mismo que aumentar el tamaño de la fuente de texto. Los tamaños de fuente se calculan de forma independiente para proporcionar la mejor resolución en diferentes tamaños. El texto escalado, por otro lado, conserva las proporciones del texto de tamaño original.  
  
 En el ejemplo siguiente se muestra el texto sesgado a lo largo del eje X.  
  
 ![Texto sesgado usando SkewTransform](./media/how-to-apply-transforms-to-text/skewed-transformed-text.jpg)

 En el ejemplo <xref:System.Windows.Media.SkewTransform> de código siguiente se usa a para sesgar texto. Un sesgo, también conocido como distorsión, es una transformación que expande el espacio de coordenadas de una manera no uniforme. En este ejemplo, las dos cadenas de texto están sesgadas -30° y 30° a lo largo de la coordenada x.  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 En el ejemplo siguiente se muestra texto trasladado, o movido, a lo largo del eje x y el eje y.  
  
 ![Texto desplazado usando TranslateTransform](./media/how-to-apply-transforms-to-text/transformed-text-x-y-axis.jpg)
  
 En el ejemplo <xref:System.Windows.Media.TranslateTransform> de código siguiente se utiliza a para desfasar texto. En este ejemplo, una copia ligeramente desplazada del texto bajo el texto primario crea un efecto de sombra.  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
> Proporciona <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> un amplio conjunto de entidades para proporcionar efectos de sombra. Para obtener más información, consulte [Crear texto con una sombra](how-to-create-text-with-a-shadow.md).  
  
## <a name="see-also"></a>Consulte también

- [Aplicar animaciones a texto](how-to-apply-animations-to-text.md)
