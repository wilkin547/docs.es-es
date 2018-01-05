---
title: "Cómo: Buscar un reloj de forma sincrónica"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90611e0b18e58e4c24b44e7c87cba56e4b0b01ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-seek-a-clock-synchronously"></a>Cómo: Buscar un reloj de forma sincrónica
Use la <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> método para buscar un reloj hasta un momento determinado de forma sincrónica. En el ejemplo siguiente se muestra la <xref:System.Windows.Media.Animation.ClockController.Seek%2A> y <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> métodos de un <xref:System.Windows.Media.Animation.ClockController>.  
  
 Este ejemplo muestra cómo buscar un <xref:System.Windows.Media.Animation.Clock>; para obtener un ejemplo que muestra cómo buscar un guión gráfico, vea [buscar un guión gráfico de forma sincrónica](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md) .  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
