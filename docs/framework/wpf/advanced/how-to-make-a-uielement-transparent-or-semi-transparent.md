---
title: "Cómo: Hacer que un elemento UIElement sea transparente o semitransparente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 25245319c02ae376410d71afb7a1e56eda259e99
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a>Cómo: Hacer que un elemento UIElement sea transparente o semitransparente
Este ejemplo muestra cómo realizar una <xref:System.Windows.UIElement> sea transparente o semitransparente. Para hacer que un elemento sea transparente o semitransparente, establezca su <xref:System.Windows.UIElement.Opacity%2A> propiedad. Un valor de `0.0` hace que el elemento sea completamente transparente, mientras que un valor de `1.0` hace que el elemento sea completamente opaco. Un valor de `0.5` hace que el elemento 50% opaco y así sucesivamente. Un elemento <xref:System.Windows.UIElement.Opacity%2A> está establecido en `1.0` de forma predeterminada.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se establece la <xref:System.Windows.UIElement.Opacity%2A> de un botón a `0.25`, hacer que él y su contenido (en este caso, el texto del botón) 25% opaco.  
  
 [!code-xaml[brushsamples_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 Si el contenido de un elemento tiene sus propios <xref:System.Windows.UIElement.Opacity%2A> configuración, esos valores se multiplica frente a los elementos que contiene <xref:System.Windows.UIElement.Opacity%2A>.  
  
 En el ejemplo siguiente se establece un botón <xref:System.Windows.UIElement.Opacity%2A> a `0.25`y el <xref:System.Windows.UIElement.Opacity%2A> de un <xref:System.Windows.Controls.Image> control contenido en el botón para `0.5`. Como resultado, la imagen aparece 12,5% opaco: 0,25 * 0,5 = 0,125.  
  
 [!code-xaml[brushsamples_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 Es otra manera de controlar la opacidad de un elemento establecer la opacidad de la <xref:System.Windows.Media.Brush> que pinta el elemento. Este enfoque permite modificar selectivamente la opacidad de las partes de un elemento y proporciona ventajas de rendimiento en comparación con el elemento <xref:System.Windows.UIElement.Opacity%2A> propiedad. El ejemplo siguiente se establece la <xref:System.Windows.Media.Brush.Opacity%2A> de un <xref:System.Windows.Media.SolidColorBrush> utilizado para pintar el botón <xref:System.Windows.Controls.Control.Background%2A> está establecido en `0.25`. Como resultado, el fondo del pincel es 25% opaco, pero su contenido (el texto del botón) permanece 100% opaco.  
  
 [!code-xaml[brushsamples_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 También puede controlar la opacidad de colores individuales dentro de un pincel. Para obtener más información acerca de los colores y los pinceles, consulte [pintar con colores sólidos y degradados información general sobre](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md). Para obtener un ejemplo que muestra cómo animar la opacidad de un elemento, vea [animar la opacidad de un elemento o pincel](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).
