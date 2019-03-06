---
title: Filtrar Hacer que un elemento UIElement sea transparente o semitransparente
ms.date: 03/30/2017
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
ms.openlocfilehash: 1de9a7e11fee241ecb71242e9808e77b7e5e63b0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370532"
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a>Filtrar Hacer que un elemento UIElement sea transparente o semitransparente
En este ejemplo se muestra cómo realizar una <xref:System.Windows.UIElement> transparente o semitransparente. Para hacer un elemento transparente o semitransparente, establezca su <xref:System.Windows.UIElement.Opacity%2A> propiedad. Un valor de `0.0` hace que el elemento sea completamente transparente, mientras que un valor de `1.0` hace que el elemento sea completamente opaco. Un valor de `0.5` hace que el elemento 50% opaco y así sucesivamente. Un elemento <xref:System.Windows.UIElement.Opacity%2A> está establecido en `1.0` de forma predeterminada.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se establece la <xref:System.Windows.UIElement.Opacity%2A> de un botón para `0.25`, lo que y su contenido (en este caso, el texto del botón) 25% opaco.  
  
 [!code-xaml[brushsamples_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 Si el contenido de un elemento tiene su propio <xref:System.Windows.UIElement.Opacity%2A> configuración, esos valores se multiplica frente a los elementos que contienen <xref:System.Windows.UIElement.Opacity%2A>.  
  
 En el ejemplo siguiente se establece un botón <xref:System.Windows.UIElement.Opacity%2A> a `0.25`y el <xref:System.Windows.UIElement.Opacity%2A> de un <xref:System.Windows.Controls.Image> control contenido en el botón para `0.5`. Como resultado, la imagen aparece 12,5% opaco: 0.25 * 0.5 = 0.125.  
  
 [!code-xaml[brushsamples_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 Otra manera de controlar la opacidad de un elemento es establecer la opacidad de la <xref:System.Windows.Media.Brush> que pinta el elemento. Este enfoque permite modificar selectivamente la opacidad de partes de un elemento y ofrece ventajas de rendimiento respecto al uso del elemento <xref:System.Windows.UIElement.Opacity%2A> propiedad. El ejemplo siguiente se establece la <xref:System.Windows.Media.Brush.Opacity%2A> de un <xref:System.Windows.Media.SolidColorBrush> se usa para pintar el botón <xref:System.Windows.Controls.Control.Background%2A> está establecido en `0.25`. Como resultado, el fondo del pincel es opaca al 25%, pero su contenido (el texto del botón) siguen siendo 100% opaco.  
  
 [!code-xaml[brushsamples_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 También puede controlar la opacidad de colores individuales dentro de un pincel. Para obtener más información acerca de los colores y pinceles, vea [el dibujo con colores sólidos y degradados](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md). Para obtener un ejemplo que muestra cómo animar la opacidad de un elemento, vea [animar la opacidad de un elemento o pincel](../graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).
