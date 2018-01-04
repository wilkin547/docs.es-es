---
title: "Cómo: Aplicar transformaciones a texto"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9c1e26b31907e7794492b88ea3a696d3db4d37d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-transforms-to-text"></a>Cómo: Aplicar transformaciones a texto
Las transformaciones pueden modificar la presentación del texto en la aplicación. Los ejemplos siguientes usan diferentes tipos de representación de las transformaciones que afectan a la presentación del texto de un <xref:System.Windows.Controls.TextBlock> control.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el texto girado sobre un punto especificado en el plano x-y bidimensional.  
  
 ![Texto girado usando RotateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext01.jpg "TransformedText01")  
Ejemplo de texto girado 90 grados  
  
 El siguiente ejemplo de código utiliza un <xref:System.Windows.Media.RotateTransform> para girar el texto. Un <xref:System.Windows.Media.RotateTransform.Angle%2A> valor de 90 gira el elemento 90 grados a la derecha.  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 En el ejemplo siguiente se muestra la segunda línea de texto escalada al 150 % a lo largo del eje X y la tercera línea de texto escalada al 150 % a lo largo del eje Y.  
  
 ![Texto con escala ajustada usando ScaleTransform](../../../../docs/framework/wpf/advanced/media/transformedtext02.jpg "TransformedText02")  
Ejemplo de texto escalado  
  
 El siguiente ejemplo de código utiliza un <xref:System.Windows.Media.ScaleTransform> al texto de la escala de su tamaño original.  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  Escalar texto no es lo mismo que aumentar el tamaño de la fuente de texto. Los tamaños de fuente se calculan de forma independiente para proporcionar la mejor resolución en diferentes tamaños. El texto escalado, por otro lado, conserva las proporciones del texto de tamaño original.  
  
 En el ejemplo siguiente se muestra el texto sesgado a lo largo del eje X.  
  
 ![Texto sesgado usando SkewTransform](../../../../docs/framework/wpf/advanced/media/transformedtext03.jpg "TransformedText03")  
Ejemplo de texto sesgado  
  
 El siguiente ejemplo de código utiliza un <xref:System.Windows.Media.SkewTransform> para sesgar el texto. Un sesgo, también conocido como distorsión, es una transformación que expande el espacio de coordenadas de una manera no uniforme. En este ejemplo, las dos cadenas de texto están sesgadas -30° y 30° a lo largo de la coordenada x.  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 En el ejemplo siguiente se muestra texto trasladado, o movido, a lo largo del eje x y el eje y.  
  
 ![Texto desplazado usando TranslateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext04.jpg "TransformedText04")  
Ejemplo de texto trasladado  
  
 El siguiente ejemplo de código utiliza un <xref:System.Windows.Media.TranslateTransform> para desplazar el texto. En este ejemplo, una copia ligeramente desplazada del texto bajo el texto primario crea un efecto de sombra.  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  El <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> proporciona un amplio conjunto de características para ofrecer efectos de sombra. Para obtener más información, consulte [crear texto con una sombra](../../../../docs/framework/wpf/advanced/how-to-create-text-with-a-shadow.md).  
  
## <a name="see-also"></a>Vea también  
 [Aplicar animaciones a texto](../../../../docs/framework/wpf/advanced/how-to-apply-animations-to-text.md)
