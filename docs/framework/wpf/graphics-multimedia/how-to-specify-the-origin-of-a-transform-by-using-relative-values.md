---
title: Procedimiento Especificar el origen de una transformación utilizando valores relativos
ms.date: 03/30/2017
helpviewer_keywords:
- origins of Transforms [WPF]
- Transforms [WPF], origins of
- graphics [WPF], origins of Transforms
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
ms.openlocfilehash: 55007575435ada809b8fba43d08abdd2ce9ddd73
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570621"
---
# <a name="how-to-specify-the-origin-of-a-transform-by-using-relative-values"></a>Procedimiento Especificar el origen de una transformación utilizando valores relativos
En este ejemplo se muestra cómo utilizar valores relativos para especificar el origen de un <xref:System.Windows.UIElement.RenderTransform%2A> que se aplica a un <xref:System.Windows.FrameworkElement>.  
  
 Al girar, escalar o sesgar un <xref:System.Windows.FrameworkElement> utilizando el <xref:System.Windows.UIElement.RenderTransform%2A> propiedad, el valor predeterminado aplica la transformación a la esquina superior izquierda del elemento. Si desea girar, escalar o sesgar desde el centro del elemento, puede realizar la compensación estableciendo el centro de la transformación en el centro del elemento. Sin embargo, esa solución requiere que conozca el tamaño del elemento. Una manera más fácil de aplicar una transformación al centro de un elemento es establecer su <xref:System.Windows.UIElement.RenderTransformOrigin%2A> propiedad en (0,5, 0,5), en lugar de establecer un valor central en la propia transformación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.RotateTransform> para girar un <xref:System.Windows.Controls.Button> 45 grados a la derecha. Puesto que el ejemplo no especifica un centro, el botón gira sobre el punto (0, 0), que está en la esquina superior izquierda. El <xref:System.Windows.Media.RotateTransform> se aplica a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad.  
  
 La siguiente ilustración muestra el resultado de la transformación del ejemplo siguiente.  
  
 ![Botón transformado mediante RenderTransform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
Giro hacia la derecha de 45 grados utilizando la propiedad RenderTransform  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 El ejemplo siguiente se usa también un <xref:System.Windows.Media.RotateTransform> para girar un <xref:System.Windows.Controls.Button> 45 grados a la derecha; sin embargo, este ejemplo se establece la <xref:System.Windows.UIElement.RenderTransformOrigin%2A> del botón en (0,5, 0,5). Como resultado, la rotación se aplica al centro del botón en lugar de a la esquina superior izquierda.  
  
 La siguiente ilustración muestra el resultado de la transformación del ejemplo siguiente.  
  
 ![Botón transformado alrededor de su centro](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
Una rotación de 45 grados utilizando la propiedad RenderTransform con un valor de RenderTransformOrigin de (0,5, 0,5)  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 Para obtener más información acerca de la transformación <xref:System.Windows.FrameworkElement> objetos, vea el [información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Media.Transform>
- [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
- [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
