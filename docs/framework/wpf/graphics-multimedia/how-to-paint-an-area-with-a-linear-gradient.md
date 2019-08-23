---
title: Procedimiento Pintar un área con un degradado lineal
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: 92c9ccd846dbbce043d13e6ba82b9fa8e72fa8b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916162"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a>Procedimiento Pintar un área con un degradado lineal
En este ejemplo se muestra cómo utilizar <xref:System.Windows.Media.LinearGradientBrush> la clase para pintar un área con un degradado lineal. En el ejemplo siguiente, el <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Rectangle> de se pinta con un degradado lineal diagonal que realiza la transición de amarillo a rojo a azul a verde lima.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 En la ilustración siguiente se muestra el degradado creado en el ejemplo anterior.  
  
 ![Degradado lineal diagonal](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")  
  
 Para crear un degradado lineal horizontal, cambie <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> de <xref:System.Windows.Media.LinearGradientBrush> a (0, 0.5) y (1, 0.5). En el ejemplo siguiente, <xref:System.Windows.Shapes.Rectangle> se pinta con un degradado lineal horizontal.  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 En la ilustración siguiente se muestra el degradado creado en el ejemplo anterior.  
  
 ![Degradado lineal horizontal](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")  
  
 Para crear un degradado lineal vertical, cambie <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> de <xref:System.Windows.Media.LinearGradientBrush> a (0.5, 0) y (0.5, 1). En el ejemplo siguiente, <xref:System.Windows.Shapes.Rectangle> se pinta con un degradado lineal vertical.  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 En la ilustración siguiente se muestra el degradado creado en el ejemplo anterior.  
  
 ![Degradado lineal vertical](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")  
  
> [!NOTE]
> En los ejemplos de este tema se usa el sistema de coordenadas predeterminado para establecer puntos de inicio y extremos. El sistema de coordenadas predeterminado es relativo a un cuadro de límite: 0 indica un 0 por ciento del rectángulo de selección, mientras que 1 indica un 100 por cien del rectángulo de selección. Puede cambiar este sistema de coordenadas estableciendo la <xref:System.Windows.Media.GradientBrush.MappingMode%2A> propiedad en el valor. <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType> Un sistema de coordenadas absoluto no está relacionado con un rectángulo de selección. Los valores se interpretan directamente en el espacio local.  
  
 Para obtener más ejemplos, vea [ejemplo](https://go.microsoft.com/fwlink/?LinkID=159973)de pinceles. Para obtener más información sobre los degradados y otros tipos de pinceles, consulte [información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md).
