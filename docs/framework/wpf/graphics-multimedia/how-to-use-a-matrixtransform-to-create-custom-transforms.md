---
title: Procedimiento Usar un objeto MatrixTransform para crear transformaciones personalizadas
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: 1971d5fe9422c5138f140517e6fd4c9f9b2cf48b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913916"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a>Procedimiento Usar un objeto MatrixTransform para crear transformaciones personalizadas
En este ejemplo se muestra cómo utilizar <xref:System.Windows.Media.MatrixTransform> un para trasladar (mover) la posición, el ajuste y el <xref:System.Windows.Controls.Button>sesgo de un.  
  
> [!NOTE]
> Utilice la <xref:System.Windows.Media.MatrixTransform> clase para crear transformaciones personalizadas no proporcionadas por las <xref:System.Windows.Media.RotateTransform>clases, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>o <xref:System.Windows.Media.TranslateTransform> .  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [Información general sobre transformaciones](transforms-overview.md)
- [Temas "Cómo..."](transformations-how-to-topics.md)
- [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md)
