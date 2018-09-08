---
title: 'Cómo: Pintar un área con un color sólido'
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: 017c685139979ec3aa411be6e6b5fdf0e91657de
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44213519"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a>Cómo: Pintar un área con un color sólido
Para pintar un área con un color sólido, puede usar un pincel del sistema predefinidos, como <xref:System.Windows.Media.Brushes.Red%2A> o <xref:System.Windows.Media.Brushes.Blue%2A>, o bien puede crear un nuevo <xref:System.Windows.Media.SolidColorBrush> y describir su <xref:System.Windows.Media.SolidColorBrush.Color%2A> mediante valores alfabéticos, rojos, verde y azules. En XAML, también puede pintar un área con un color sólido utilizando la notación hexadecimal.  
  
 Los ejemplos siguientes se usa cada una de estas técnicas para pintar un <xref:System.Windows.Shapes.Rectangle> azul.  
  
## <a name="example"></a>Ejemplo  
 **Utilizar un pincel predefinido**  
  
 En el ejemplo siguiente se usa el pincel predefinido <xref:System.Windows.Media.Brushes.Blue%2A> para pintar un rectángulo azul.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **Utilizar la notación hexadecimal**  
  
 En el ejemplo siguiente se utiliza la notación hexadecimal de 8 dígitos para pintar un rectángulo azul.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **Utilizar los valores ARGB**  
  
 El ejemplo siguiente se crea un <xref:System.Windows.Media.SolidColorBrush> y describe su <xref:System.Windows.Media.SolidColorBrush.Color%2A> utilizando los valores ARGB para el color azul.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 Para conocer otras formas de describir colores, consulte el <xref:System.Windows.Media.Color> estructura.  
  
 **Temas relacionados**  
  
 Para obtener más información acerca de <xref:System.Windows.Media.SolidColorBrush> y ejemplos adicionales, vea el [el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) información general.  
  
 Este ejemplo de código forma parte de un ejemplo más extenso proporcionado para el <xref:System.Windows.Media.SolidColorBrush> clase. Para ver el ejemplo completo, consulte el [ejemplo de pinceles](https://go.microsoft.com/fwlink/?LinkID=159973).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Brushes>
