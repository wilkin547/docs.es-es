---
title: Filtrar Buscar un reloj de forma sincrónica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
ms.openlocfilehash: 9b6b1f5523effc56ccd9ddaa4f478e1d3a20ada8
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356003"
---
# <a name="how-to-seek-a-clock-synchronously"></a>Filtrar Buscar un reloj de forma sincrónica
Use el <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> método para buscar un reloj de hasta un momento determinado de forma sincrónica. En el ejemplo siguiente se muestra tanto el <xref:System.Windows.Media.Animation.ClockController.Seek%2A> y <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> métodos de un <xref:System.Windows.Media.Animation.ClockController>.  
  
 En este ejemplo se muestra cómo buscar un <xref:System.Windows.Media.Animation.Clock>; para obtener un ejemplo que muestra cómo buscar un guión gráfico, vea [buscar un guión gráfico de forma sincrónica](how-to-seek-a-storyboard-synchronously.md) .  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
