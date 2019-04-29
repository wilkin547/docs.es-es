---
title: Procedimiento Buscar un reloj de forma sincrónica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
ms.openlocfilehash: 9b6b1f5523effc56ccd9ddaa4f478e1d3a20ada8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651264"
---
# <a name="how-to-seek-a-clock-synchronously"></a><span data-ttu-id="a8b97-102">Procedimiento Buscar un reloj de forma sincrónica</span><span class="sxs-lookup"><span data-stu-id="a8b97-102">How to: Seek a Clock Synchronously</span></span>
<span data-ttu-id="a8b97-103">Use el <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> método para buscar un reloj de hasta un momento determinado de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="a8b97-103">Use the <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> method to seek a clock to a specific point synchronously.</span></span> <span data-ttu-id="a8b97-104">En el ejemplo siguiente se muestra tanto el <xref:System.Windows.Media.Animation.ClockController.Seek%2A> y <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> métodos de un <xref:System.Windows.Media.Animation.ClockController>.</span><span class="sxs-lookup"><span data-stu-id="a8b97-104">The following example demonstrates both the <xref:System.Windows.Media.Animation.ClockController.Seek%2A> and <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> methods of a <xref:System.Windows.Media.Animation.ClockController>.</span></span>  
  
 <span data-ttu-id="a8b97-105">En este ejemplo se muestra cómo buscar un <xref:System.Windows.Media.Animation.Clock>; para obtener un ejemplo que muestra cómo buscar un guión gráfico, vea [buscar un guión gráfico de forma sincrónica](how-to-seek-a-storyboard-synchronously.md) .</span><span class="sxs-lookup"><span data-stu-id="a8b97-105">This example shows how to seek a <xref:System.Windows.Media.Animation.Clock>; for an example showing how to seek a storyboard, see [Seek a Storyboard Synchronously](how-to-seek-a-storyboard-synchronously.md) .</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8b97-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8b97-106">Example</span></span>  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
