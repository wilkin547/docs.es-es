---
title: "Cómo: Pintar un área con un color sólido"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cde7f7df5089806ffb3235393eacc855d137ee51
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a>Cómo: Pintar un área con un color sólido
Para pintar un área con un color sólido, puede usar un pincel del sistema predefinidas, como <xref:System.Windows.Media.Brushes.Red%2A> o <xref:System.Windows.Media.Brushes.Blue%2A>, o puede crear un nuevo <xref:System.Windows.Media.SolidColorBrush> y describir su <xref:System.Windows.Media.SolidColorBrush.Color%2A> con los valores alfabéticos, rojos, verde y azules. En XAML, también puede pintar un área con un color sólido utilizando la notación hexadecimal.  
  
 Los ejemplos siguientes se usa cada una de estas técnicas para pintar un <xref:System.Windows.Shapes.Rectangle> azul.  
  
## <a name="example"></a>Ejemplo  
 **Utilizar un pincel predefinido**  
  
 En el ejemplo siguiente se utiliza el pincel predefinido <xref:System.Windows.Media.Brushes.Blue%2A> para dibujar un rectángulo azul.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **Utilizar la notación hexadecimal**  
  
 En el ejemplo siguiente se utiliza la notación hexadecimal de 8 dígitos para pintar un rectángulo azul.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **Utilizar los valores ARGB**  
  
 En el ejemplo siguiente se crea un <xref:System.Windows.Media.SolidColorBrush> y se describe su <xref:System.Windows.Media.SolidColorBrush.Color%2A> utilizando el ARGB valores de color azul.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 Para conocer otras maneras de describir colores, vea la <xref:System.Windows.Media.Color> estructura.  
  
 **Temas relacionados**  
  
 Para obtener más información acerca de <xref:System.Windows.Media.SolidColorBrush> y ejemplos adicionales, consulte la [pintar con colores sólidos y degradados Introducción](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) información general.  
  
 Este ejemplo de código forma parte de un ejemplo mayor proporcionado para el <xref:System.Windows.Media.SolidColorBrush> clase. Para ver el ejemplo completo, consulte el [ejemplo de pinceles](http://go.microsoft.com/fwlink/?LinkID=159973).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Brushes>
