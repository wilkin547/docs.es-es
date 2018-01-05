---
title: "Cómo: Elegir entre StackPanel y DockPanel"
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
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], StackPanel control compared to
- StackPanel control [WPF], DockPanel control compared to
- controls [WPF], StackPanel
ms.assetid: f9239086-451f-42e6-81f7-ef89ef349742
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0274a0f078c378a101bdf4a4ae456fd2ce9f4185
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a><span data-ttu-id="a59e2-102">Cómo: Elegir entre StackPanel y DockPanel</span><span class="sxs-lookup"><span data-stu-id="a59e2-102">How to: Choose Between StackPanel and DockPanel</span></span>
<span data-ttu-id="a59e2-103">Este ejemplo muestra cómo elegir entre usar un <xref:System.Windows.Controls.StackPanel> o un <xref:System.Windows.Controls.DockPanel> cuando apilar el contenido en un <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="a59e2-103">This example shows how to choose between using a <xref:System.Windows.Controls.StackPanel> or a <xref:System.Windows.Controls.DockPanel> when you stack content in a <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a59e2-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a59e2-104">Example</span></span>  
 <span data-ttu-id="a59e2-105">Aunque puede usar <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.Controls.StackPanel> para apilar los elementos secundarios, los dos controles no siempre generan los mismos resultados.</span><span class="sxs-lookup"><span data-stu-id="a59e2-105">Although you can use either <xref:System.Windows.Controls.DockPanel> or <xref:System.Windows.Controls.StackPanel> to stack child elements, the two controls do not always produce the same results.</span></span> <span data-ttu-id="a59e2-106">Por ejemplo, el orden en que se colocan los elementos secundarios puede afectar al tamaño de los elementos secundarios de un <xref:System.Windows.Controls.DockPanel> , pero no en un <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="a59e2-106">For example, the order that you place child elements can affect the size of child elements in a <xref:System.Windows.Controls.DockPanel> but not in a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="a59e2-107">Se produce este comportamiento diferente porque <xref:System.Windows.Controls.StackPanel> medidas en la dirección de apilado en <xref:System.Double>.<xref:System.Double.PositiveInfinity>; sin embargo, <xref:System.Windows.Controls.DockPanel> mide solo el tamaño disponible.</span><span class="sxs-lookup"><span data-stu-id="a59e2-107">This different behavior occurs because <xref:System.Windows.Controls.StackPanel> measures in the direction of stacking at <xref:System.Double>.<xref:System.Double.PositiveInfinity>; however, <xref:System.Windows.Controls.DockPanel> measures only the available size.</span></span>  
  
 <span data-ttu-id="a59e2-108">En el ejemplo siguiente se muestra esta diferencia clave entre <xref:System.Windows.Controls.DockPanel> y <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="a59e2-108">The following example demonstrates this key difference between <xref:System.Windows.Controls.DockPanel> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a59e2-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="a59e2-109">See Also</span></span>  
 <xref:System.Windows.Controls.StackPanel>  
 <xref:System.Windows.Controls.DockPanel>  
 [<span data-ttu-id="a59e2-110">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="a59e2-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
