---
title: "Cómo: Hacer que un elemento gire en su posición"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae76d33a30853107cbecf0749230aefce77a866d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-an-element-spin-in-place"></a>Cómo: Hacer que un elemento gire en su posición
Este ejemplo muestra cómo hacer que un elemento de número utilizando un <xref:System.Windows.Media.RotateTransform> y <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 El ejemplo siguiente aplica el <xref:System.Windows.Media.RotateTransform> a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad del elemento. El ejemplo se usa un <xref:System.Windows.Media.Animation.DoubleAnimation> para animar la <xref:System.Windows.Media.RotateTransform.Angle%2A> de la <xref:System.Windows.Media.RotateTransform>. Para hacer que el elemento gire en su lugar, el ejemplo establece la <xref:System.Windows.UIElement.RenderTransformOrigin%2A> propiedad del elemento en el punto (0,5, 0,5).  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[transformanimations_snip#11](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 Para obtener el ejemplo completo, que incluye varios ejemplos de transformación, vea [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
