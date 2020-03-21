---
title: 'Cómo: Sesgar un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 10b00044c1c518641281e2e72cdb5a68474b5170
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112029"
---
# <a name="how-to-skew-an-element"></a>Cómo: Sesgar un elemento
En este ejemplo se <xref:System.Windows.Media.SkewTransform> muestra cómo utilizar a para sesgar un elemento. Un sesgo, también conocido como distorsión, es una transformación que expande el espacio de coordenadas de una manera no uniforme. Un uso típico <xref:System.Windows.Media.SkewTransform> de a es para simular la profundidad 3D en objetos 2D.  
  
 Utilice <xref:System.Windows.Media.SkewTransform.CenterX%2A> las <xref:System.Windows.Media.SkewTransform.CenterY%2A> propiedades y para especificar <xref:System.Windows.Media.SkewTransform>el punto central del archivo .  
  
 Utilice <xref:System.Windows.Media.SkewTransform.AngleX%2A> las <xref:System.Windows.Media.SkewTransform.AngleY%2A> propiedades y para especificar el ángulo de sesgo del eje X y el eje Y, y para sesgar el sistema de coordenadas actual a lo largo de estos ejes.  
  
 Para predecir el efecto de una <xref:System.Windows.Media.SkewTransform.AngleX%2A> transformación de sesgo, tenga en cuenta que sesga los valores del eje X en relación con el sistema de coordenadas original. Por lo <xref:System.Windows.Media.SkewTransform.AngleX%2A> tanto, para un de 30, el eje Y gira 30 grados a través del origen y sesga los valores en x- por 30 grados desde ese origen. Del mismo <xref:System.Windows.Media.SkewTransform.AngleY%2A> modo, un de 30 sesga los valores y de la forma en 30 grados desde el origen. Tenga en cuenta que esto no tiene el mismo efecto que trasladar (mover) el sistema de coordenadas 30 grados en x o y.  
  
 En el ejemplo siguiente se aplica un <xref:System.Windows.Shapes.Rectangle> sesgo horizontal de 45 grados a un punto central de (0,0).  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 En el ejemplo siguiente se aplica un <xref:System.Windows.Shapes.Rectangle> sesgo horizontal de 45 grados a un punto central de (25,25).  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 En el ejemplo siguiente se aplica un <xref:System.Windows.Shapes.Rectangle> sesgo vertical de 45 grados a un punto central de (25,25).  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 La ilustración siguiente muestra los diferentes sesgos que se usan en este ejemplo.  
  
 ![Ejemplos de SkewTransform](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")  
Los tres ejemplos de SkewTransform ilustrados  
  
 Para ver el ejemplo completo, consulte Ejemplo de [transformaciones 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [Información general sobre transformaciones](transforms-overview.md)
- [Temas de información](transformations-how-to-topics.md)
