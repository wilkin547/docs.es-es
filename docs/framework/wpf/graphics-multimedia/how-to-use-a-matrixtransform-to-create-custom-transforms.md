---
title: Procedimiento Usar un objeto MatrixTransform para crear transformaciones personalizadas
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: aeccb961db539d4cc6dea75fb487fba06e59d6de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769270"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a>Procedimiento Usar un objeto MatrixTransform para crear transformaciones personalizadas
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
