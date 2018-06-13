---
title: 'Cómo: Ajustar la escala de un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: f39bb4408e5b61912da30088de7c9f62587bc278
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562172"
---
# <a name="how-to-scale-an-element"></a>Cómo: Ajustar la escala de un elemento
Este ejemplo muestra cómo utilizar un <xref:System.Windows.Media.ScaleTransform> para escalar un elemento.  
  
 Use la <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> y <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> propiedades para cambiar el tamaño del elemento según el factor especificado. Por ejemplo, un <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> valor de 1,5 expande el elemento al 150 por ciento de su ancho original. Un <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> valor de 0,5 reduce el alto de un elemento a 50 por ciento.  
  
 Use la <xref:System.Windows.Media.ScaleTransform.CenterX%2A> y <xref:System.Windows.Media.ScaleTransform.CenterY%2A> propiedades para especificar el punto que representa el centro de la operación de escalado. De forma predeterminada, un <xref:System.Windows.Media.ScaleTransform> se centra en el punto (0,0), que corresponde a la esquina superior izquierda del rectángulo. Esto tiene el efecto de mover el elemento y también de lo que aparezca más grande, ya que al aplicar un <xref:System.Windows.Media.Transform>, cambie el espacio de coordenadas en el que reside el objeto.  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.ScaleTransform> duplicar el tamaño de un 50-50 <xref:System.Windows.Shapes.Rectangle>. El <xref:System.Windows.Media.ScaleTransform> tiene un valor de 0 (valor predeterminado) para ambos <xref:System.Windows.Media.ScaleTransform.CenterX%2A> y <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[transformsSample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 Normalmente, se establece <xref:System.Windows.Media.ScaleTransform.CenterX%2A> y <xref:System.Windows.Media.ScaleTransform.CenterY%2A> al centro del objeto que se escala: (<xref:System.Windows.FrameworkElement.Width%2A>/2,  <xref:System.Windows.FrameworkElement.Height%2A> /2).  
  
 En el ejemplo siguiente se muestra otro <xref:System.Windows.Shapes.Rectangle> que se duplica en tamaño; sin embargo, esto <xref:System.Windows.Media.ScaleTransform> tiene un valor de 25 para ambos <xref:System.Windows.Media.ScaleTransform.CenterX%2A> y <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, que se corresponde con el centro del rectángulo.  
  
 [!code-xaml[transformsSample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 En la siguiente ilustración muestra la diferencia entre los dos <xref:System.Windows.Media.ScaleTransform> operaciones. La línea de puntos muestra el tamaño y la posición del rectángulo antes de escalar.  
  
 ![escalas x 2 con diferentes centros](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")  
Dos operaciones de ScaleTransform con valores idénticos de ScaleX y ScaleY pero con centros diferentes  
  
 Para ver el ejemplo completo, consulte [Ejemplo de transformaciones 2D](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.ScaleTransform>  
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
