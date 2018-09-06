---
title: 'Cómo: Sesgar un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: f828e4d4e59fa5ed31f81f3e83570a25add19e01
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43734908"
---
# <a name="how-to-skew-an-element"></a>Cómo: Sesgar un elemento
En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.SkewTransform> para sesgar un elemento. Un sesgo, también conocido como distorsión, es una transformación que expande el espacio de coordenadas de una manera no uniforme. Un uso típico de un <xref:System.Windows.Media.SkewTransform> para simular [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] profundidad en [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] objetos.  
  
 Use la <xref:System.Windows.Media.SkewTransform.CenterX%2A> y <xref:System.Windows.Media.SkewTransform.CenterY%2A> propiedades para especificar el centro de punto de la <xref:System.Windows.Media.SkewTransform>.  
  
 Use la <xref:System.Windows.Media.SkewTransform.AngleX%2A> y <xref:System.Windows.Media.SkewTransform.AngleY%2A> propiedades para especificar el ángulo de sesgado de los ejes x y y y para sesgar el sistema de coordenadas actual a lo largo de estos ejes.  
  
 Para predecir el efecto de una transformación de sesgo, considere la posibilidad de que <xref:System.Windows.Media.SkewTransform.AngleX%2A> sesga los valores del eje x en relación con el sistema de coordenadas original. Por lo tanto, para un <xref:System.Windows.Media.SkewTransform.AngleX%2A> de 30, el eje y gira 30 grados a través del origen y sesga los valores de x-30 grados desde ese origen. Del mismo modo, un <xref:System.Windows.Media.SkewTransform.AngleY%2A> de 30 sesga los valores y de la forma 30 grados desde el origen. Tenga en cuenta que esto no tiene el mismo efecto que trasladar (mover) el sistema de coordenadas 30 grados en x o y.  
  
 El ejemplo siguiente aplica un sesgo horizontal de 45 grados a un <xref:System.Windows.Shapes.Rectangle> desde un punto central de (0,0).  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[transformsSample#41](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 El ejemplo siguiente aplica un sesgo horizontal de 45 grados a un <xref:System.Windows.Shapes.Rectangle> desde un punto central de (25,25).  
  
 [!code-xaml[transformsSample#42](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 El ejemplo siguiente aplica un sesgo vertical de 45 grados a un <xref:System.Windows.Shapes.Rectangle> desde un punto central de (25,25).  
  
 [!code-xaml[transformsSample#43](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 La ilustración siguiente muestra los diferentes sesgos que se usan en este ejemplo.  
  
 ![Ejemplos de SkewTransform](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")  
Los tres ejemplos de SkewTransform ilustrados  
  
 Para ver el ejemplo completo, consulte [Ejemplo de transformaciones 2D](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.SkewTransform>  
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
