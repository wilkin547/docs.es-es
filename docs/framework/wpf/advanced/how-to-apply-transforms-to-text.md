---
title: Procedimiento Aplicar transformaciones a texto
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
ms.openlocfilehash: 46a57364e0c18cc4c9fe7884642cd0b718c20f31
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776978"
---
# <a name="how-to-apply-transforms-to-text"></a>Procedimiento Aplicar transformaciones a texto
Las transformaciones pueden modificar la presentación del texto en la aplicación. Los ejemplos siguientes usan diferentes tipos de transformaciones de representación para influir en la presentación del texto en un <xref:System.Windows.Controls.TextBlock> control.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el texto girado sobre un punto especificado en el plano x-y bidimensional.  
  
 ![Texto girado usando RotateTransform](./media/how-to-apply-transforms-to-text/text-rotated-ninety-degrees.jpg)  
  
 El siguiente ejemplo de código utiliza un <xref:System.Windows.Media.RotateTransform> para girar el texto. Un <xref:System.Windows.Media.RotateTransform.Angle%2A> valor de 90 gira el elemento 90 grados a la derecha.  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 En el ejemplo siguiente se muestra la segunda línea de texto escalada al 150 % a lo largo del eje X y la tercera línea de texto escalada al 150 % a lo largo del eje Y.  
  
 ![Texto con escala ajustada usando ScaleTransform](./media/how-to-apply-transforms-to-text/scaled-text-scaletransform.jpg) 
  
 El siguiente ejemplo de código utiliza un <xref:System.Windows.Media.ScaleTransform> para escalar el texto de su tamaño original.  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  Escalar texto no es lo mismo que aumentar el tamaño de la fuente de texto. Los tamaños de fuente se calculan de forma independiente para proporcionar la mejor resolución en diferentes tamaños. El texto escalado, por otro lado, conserva las proporciones del texto de tamaño original.  
  
 En el ejemplo siguiente se muestra el texto sesgado a lo largo del eje X.  
  
 ![Texto sesgado usando SkewTransform](./media/how-to-apply-transforms-to-text/skewed-transformed-text.jpg)
   
 El siguiente ejemplo de código utiliza un <xref:System.Windows.Media.SkewTransform> para sesgar el texto. Un sesgo, también conocido como distorsión, es una transformación que expande el espacio de coordenadas de una manera no uniforme. En este ejemplo, las dos cadenas de texto están sesgadas -30° y 30° a lo largo de la coordenada x.  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 En el ejemplo siguiente se muestra texto trasladado, o movido, a lo largo del eje x y el eje y.  
  
 ![Texto desplazado usando TranslateTransform](./media/how-to-apply-transforms-to-text/transformed-text-x-y-axis.jpg)
  
 El siguiente ejemplo de código utiliza un <xref:System.Windows.Media.TranslateTransform> para desplazar el texto. En este ejemplo, una copia ligeramente desplazada del texto bajo el texto primario crea un efecto de sombra.  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  El <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> proporciona un amplio conjunto de características para ofrecer efectos de sombra. Para obtener más información, consulte [crear texto con sombreado](how-to-create-text-with-a-shadow.md).  
  
## <a name="see-also"></a>Vea también

- [Aplicar animaciones a texto](how-to-apply-animations-to-text.md)
