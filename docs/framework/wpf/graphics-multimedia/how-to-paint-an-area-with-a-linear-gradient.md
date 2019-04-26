---
title: Procedimiento Pintar un área con un degradado lineal
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: c48ff13811d784ecc7042b73b964a9e6f2d42a34
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921915"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a>Procedimiento Pintar un área con un degradado lineal
En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.LinearGradientBrush> clase para pintar un área con un degradado lineal. En el ejemplo siguiente, la <xref:System.Windows.Shapes.Shape.Fill%2A> de un <xref:System.Windows.Shapes.Rectangle> se pinta con un degradado lineal diagonal que realiza la transición de amarillo a rojo a azul para verde lima.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 La siguiente ilustración muestra el degradado que se creó en el ejemplo anterior.  
  
 ![Degradado lineal diagonal](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")  
  
 Para crear un degradado lineal horizontal, cambie el <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> de la <xref:System.Windows.Media.LinearGradientBrush> a (0,0.5) y (1,0.5). En el ejemplo siguiente, un <xref:System.Windows.Shapes.Rectangle> se pinta con un degradado lineal horizontal.  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 La siguiente ilustración muestra el degradado que se creó en el ejemplo anterior.  
  
 ![Un degradado lineal horizontal](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")  
  
 Para crear un degradado lineal vertical, cambie el <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> de la <xref:System.Windows.Media.LinearGradientBrush> a (0.5,0) y (0.5,1). En el ejemplo siguiente, un <xref:System.Windows.Shapes.Rectangle> se pinta con un degradado lineal vertical.  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 La siguiente ilustración muestra el degradado que se creó en el ejemplo anterior.  
  
 ![Degradado lineal vertical](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")  
  
> [!NOTE]
>  Los ejemplos de este tema usan el sistema de coordenadas predeterminado para establecer puntos de inicio y finales. El sistema de coordenadas predeterminado está relacionado con un rectángulo: 0 indica 0 por ciento del rectángulo, y 1 indica un 100 por cien del rectángulo. Puede cambiar este sistema de coordenadas estableciendo el <xref:System.Windows.Media.GradientBrush.MappingMode%2A> valor para la propiedad <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>. Un sistema de coordenadas absoluto no está relacionado con un rectángulo de selección. Los valores se interpretan directamente en el espacio local.  
  
 Para obtener ejemplos adicionales, consulte [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973). Para obtener más información acerca de los degradados y otros tipos de pinceles, vea [el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md).
