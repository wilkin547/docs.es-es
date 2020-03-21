---
title: 'Cómo: Pintar un área con un color sólido'
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: be28a0af04c4e43cdf745a5429468aee99e34c40
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849527"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a>Cómo: Pintar un área con un color sólido
Para pintar un área con un color sólido, puede utilizar <xref:System.Windows.Media.Brushes.Red%2A> <xref:System.Windows.Media.Brushes.Blue%2A>un pincel del sistema <xref:System.Windows.Media.SolidColorBrush> predefinido, <xref:System.Windows.Media.SolidColorBrush.Color%2A> como o , o puede crear un nuevo y describir su uso de valores alfa, rojo, verde y azul. En XAML, también puede pintar un área con un color sólido utilizando la notación hexadecimal.  
  
 En los ejemplos siguientes se utiliza <xref:System.Windows.Shapes.Rectangle> cada una de estas técnicas para pintar un azul.  
  
## <a name="example"></a>Ejemplo  
 **Utilizar un pincel predefinido**  
  
 En el ejemplo siguiente se <xref:System.Windows.Media.Brushes.Blue%2A> utiliza el pincel predefinido para pintar un rectángulo azul.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **Utilizar la notación hexadecimal**  
  
 En el ejemplo siguiente se utiliza la notación hexadecimal de 8 dígitos para pintar un rectángulo azul.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **Utilizar los valores ARGB**  
  
 En el ejemplo <xref:System.Windows.Media.SolidColorBrush> siguiente se <xref:System.Windows.Media.SolidColorBrush.Color%2A> crea a y se describe su uso de los valores ARGB para el color azul.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 Para otras formas de describir <xref:System.Windows.Media.Color> el color, consulte la estructura.  
  
 **Temas relacionados**  
  
 Para obtener <xref:System.Windows.Media.SolidColorBrush> más información y ejemplos adicionales, consulte La [información general sobre la pintura con colores sólidos y degradados.](painting-with-solid-colors-and-gradients-overview.md)  
  
 Este ejemplo de código forma parte <xref:System.Windows.Media.SolidColorBrush> de un ejemplo más amplio proporcionado para la clase. Para ver el ejemplo completo, consulte la [muestra Pinceles](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Brushes>
