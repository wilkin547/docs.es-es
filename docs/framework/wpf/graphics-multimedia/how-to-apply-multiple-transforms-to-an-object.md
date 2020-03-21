---
title: 'Cómo: Aplicar varias transformaciones a un objeto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- grouping Transform objects [WPF]
- Transform objects [WPF], grouping
- graphics [WPF], grouping Transform objects
- TransformGroup [WPF]
ms.assetid: 98cd1921-12bc-4bf5-8193-529228fb7402
ms.openlocfilehash: 3ef11104b2a4fc775d29d2a388c9a70a69a3f10f
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112120"
---
# <a name="how-to-apply-multiple-transforms-to-an-object"></a>Cómo: Aplicar varias transformaciones a un objeto
En este ejemplo se <xref:System.Windows.Media.TransformGroup> muestra cómo <xref:System.Windows.Media.Transform> utilizar a para <xref:System.Windows.Media.Transform>agrupar dos o más objetos en un único compuesto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo <xref:System.Windows.Media.TransformGroup> siguiente <xref:System.Windows.Media.ScaleTransform> se <xref:System.Windows.Media.RotateTransform> usa <xref:System.Windows.Controls.Button>a para aplicar a y a a un archivo .  
  
 [!code-xaml[Transforms_snip#MultipleTransformExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Media.TransformGroup>
- [Información general sobre transformaciones](transforms-overview.md)
- [Muestra de transformaciones 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
