---
title: 'Cómo: Buscar un reloj de forma sincrónica'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
ms.openlocfilehash: d8e7b0f4bfa3a59814d87bfb6d7e8b40bd80f6e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-seek-a-clock-synchronously"></a>Cómo: Buscar un reloj de forma sincrónica
Use la <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> método para buscar un reloj hasta un momento determinado de forma sincrónica. En el ejemplo siguiente se muestra la <xref:System.Windows.Media.Animation.ClockController.Seek%2A> y <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> métodos de un <xref:System.Windows.Media.Animation.ClockController>.  
  
 Este ejemplo muestra cómo buscar un <xref:System.Windows.Media.Animation.Clock>; para obtener un ejemplo que muestra cómo buscar un guión gráfico, vea [buscar un guión gráfico de forma sincrónica](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md) .  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
