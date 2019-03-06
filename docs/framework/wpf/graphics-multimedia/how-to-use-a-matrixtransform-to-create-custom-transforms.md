---
title: Filtrar Utilizar un objeto MatrixTransform para crear transformaciones personalizadas
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: 179c7986b6a7021f4e1245aef01eb555108ebf4f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358865"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a>Procedimiento Utilizar un objeto MatrixTransform para crear transformaciones personalizadas
En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.MatrixTransform> para trasladar (mover) la posición, stretch y el sesgo de una <xref:System.Windows.Controls.Button>.  
  
> [!NOTE]
>  Use la <xref:System.Windows.Media.MatrixTransform> clase para crear transformaciones personalizadas no proporcionadas por el <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, o <xref:System.Windows.Media.TranslateTransform> clases.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [Información general sobre transformaciones](transforms-overview.md)
- [Temas "Cómo..."](transformations-how-to-topics.md)
- [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md)
