---
title: 'Cómo: Ajustar la escala de un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 34d954f68747be9eedc0ef71634e0c18b411d260
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112055"
---
# <a name="how-to-scale-an-element"></a>Cómo: Ajustar la escala de un elemento
En este ejemplo se <xref:System.Windows.Media.ScaleTransform> muestra cómo utilizar a para escalar un elemento.  
  
 Utilice <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> las <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> propiedades y para cambiar el tamaño del elemento según el factor que especifique. Por ejemplo, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> un valor de 1,5 estira el elemento al 150 por ciento de su ancho original. Un <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> valor de 0,5 reduce la altura de un elemento en un 50 por ciento.  
  
 Utilice <xref:System.Windows.Media.ScaleTransform.CenterX%2A> las <xref:System.Windows.Media.ScaleTransform.CenterY%2A> propiedades y para especificar el punto que es el centro de la operación de escala. De forma <xref:System.Windows.Media.ScaleTransform> predeterminada, a se centra en el punto (0,0), que corresponde a la esquina superior izquierda del rectángulo. Esto tiene el efecto de mover el elemento y también de <xref:System.Windows.Media.Transform>hacerlo parecer más grande, porque cuando se aplica un , se cambia el espacio de coordenadas en el que reside el objeto.  
  
 En el ejemplo <xref:System.Windows.Media.ScaleTransform> siguiente se utiliza a para duplicar <xref:System.Windows.Shapes.Rectangle>el tamaño de un 50 por 50 . El <xref:System.Windows.Media.ScaleTransform> tiene un valor de 0 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> (valor predeterminado) para ambos y <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 Normalmente, se <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A> establece y se establece en el<xref:System.Windows.FrameworkElement.Width%2A>centro del <xref:System.Windows.FrameworkElement.Height%2A>objeto que se escala: ( /2, /2).  
  
 En el ejemplo <xref:System.Windows.Shapes.Rectangle> siguiente se muestra otro que se duplica en tamaño; sin <xref:System.Windows.Media.ScaleTransform> embargo, esto tiene un <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A>valor de 25 para ambos y , que corresponde al centro del rectángulo.  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 En la ilustración siguiente <xref:System.Windows.Media.ScaleTransform> se muestra la diferencia entre las dos operaciones. La línea de puntos muestra el tamaño y la posición del rectángulo antes de escalar.  
  
 ![Escalas dobles con diferentes centros](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")  
Dos operaciones de ScaleTransform con valores idénticos de ScaleX y ScaleY pero con centros diferentes  
  
 Para ver el ejemplo completo, consulte Ejemplo de [transformaciones 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [Información general sobre transformaciones](transforms-overview.md)
- [Temas de información](transformations-how-to-topics.md)
