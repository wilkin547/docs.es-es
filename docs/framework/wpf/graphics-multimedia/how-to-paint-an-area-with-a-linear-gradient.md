---
title: "Cómo: Pintar un área con un degradado lineal"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eec4ec2fc7ba99081eaafa6803d20c99bebc6c2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a>Cómo: Pintar un área con un degradado lineal
Este ejemplo muestra cómo utilizar la <xref:System.Windows.Media.LinearGradientBrush> clase para pintar un área con un degradado lineal. En el ejemplo siguiente, la <xref:System.Windows.Shapes.Shape.Fill%2A> de un <xref:System.Windows.Shapes.Rectangle> se pinta con un degradado lineal diagonal que realiza la transición de amarillo a rojo a azul para Lima verde.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 En la siguiente ilustración muestra el degradado creado en el ejemplo anterior.  
  
 ![Degradado lineal diagonal](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")  
  
 Para crear un degradado lineal horizontal, cambie la <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> de la <xref:System.Windows.Media.LinearGradientBrush> a (0,0.5) y (1,0.5). En el ejemplo siguiente, un <xref:System.Windows.Shapes.Rectangle> se pinta con un degradado lineal horizontal.  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 En la siguiente ilustración muestra el degradado creado en el ejemplo anterior.  
  
 ![Un degradado lineal horizontal](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")  
  
 Para crear un degradado lineal vertical, cambie la <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> de la <xref:System.Windows.Media.LinearGradientBrush> a (0.5,0) y (0.5,1). En el ejemplo siguiente, un <xref:System.Windows.Shapes.Rectangle> se pinta con un degradado lineal vertical.  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 En la siguiente ilustración muestra el degradado creado en el ejemplo anterior.  
  
 ![Degradado lineal vertical](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")  
  
> [!NOTE]
>  Los ejemplos en este tema usan el sistema de coordenadas predeterminado para establecer puntos de inicio y finales. El sistema de coordenadas predeterminado es relativo a un cuadro de límite: 0 indica un 0 por ciento del cuadro de límite y 1 indica un 100 por cien del cuadro de límite. Puede cambiar este sistema de coordenadas estableciendo la <xref:System.Windows.Media.GradientBrush.MappingMode%2A> valor para la propiedad <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>. Un sistema de coordenadas absoluto no está relacionado con un rectángulo de selección. Los valores se interpretan directamente en el espacio local.  
  
 Para obtener ejemplos adicionales, vea [ejemplo pinceles](http://go.microsoft.com/fwlink/?LinkID=159973). Para obtener más información acerca de los degradados y otros tipos de pinceles, consulte [pintar con colores sólidos y degradados información general sobre](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).
