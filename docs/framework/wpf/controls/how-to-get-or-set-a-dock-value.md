---
title: Procedimiento Obtener o establecer un valor de acoplamiento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock values [WPF], setting
- Dock values [WPF], getting
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
ms.openlocfilehash: 7825377146532a6660e1838fa25631b788afe035
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374532"
---
# <a name="how-to-get-or-set-a-dock-value"></a><span data-ttu-id="64b44-102">Filtrar Obtener o establecer un valor de acoplamiento</span><span class="sxs-lookup"><span data-stu-id="64b44-102">How to: Get or Set a Dock Value</span></span>
<span data-ttu-id="64b44-103">El ejemplo siguiente muestra cómo asignar un <xref:System.Windows.Controls.Dock> valor para un objeto.</span><span class="sxs-lookup"><span data-stu-id="64b44-103">The following example shows how to assign a <xref:System.Windows.Controls.Dock> value for an object.</span></span> <span data-ttu-id="64b44-104">El ejemplo se usa el <xref:System.Windows.Controls.DockPanel.GetDock%2A> y <xref:System.Windows.Controls.DockPanel.SetDock%2A> métodos de <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="64b44-104">The example uses the <xref:System.Windows.Controls.DockPanel.GetDock%2A> and <xref:System.Windows.Controls.DockPanel.SetDock%2A> methods of <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64b44-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="64b44-105">Example</span></span>  
 <span data-ttu-id="64b44-106">En el ejemplo se crea una instancia de la <xref:System.Windows.Controls.TextBlock> elemento, `txt1`y asigna un <xref:System.Windows.Controls.Dock> valor de `Top` mediante el uso de la <xref:System.Windows.Controls.DockPanel.SetDock%2A> método <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="64b44-106">The example creates an instance of the <xref:System.Windows.Controls.TextBlock> element, `txt1`, and assigns a <xref:System.Windows.Controls.Dock> value of `Top` by using the <xref:System.Windows.Controls.DockPanel.SetDock%2A> method of <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="64b44-107">A continuación, anexa el valor de la <xref:System.Windows.Controls.Dock> propiedad a la <xref:System.Windows.Controls.TextBlock.Text%2A> de la <xref:System.Windows.Controls.TextBlock> elemento mediante el uso de la <xref:System.Windows.Controls.DockPanel.GetDock%2A> método.</span><span class="sxs-lookup"><span data-stu-id="64b44-107">It then appends the value of the <xref:System.Windows.Controls.Dock> property to the <xref:System.Windows.Controls.TextBlock.Text%2A> of the <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.DockPanel.GetDock%2A> method.</span></span> <span data-ttu-id="64b44-108">Por último, en el ejemplo se agrega el <xref:System.Windows.Controls.TextBlock> elemento con el elemento primario <xref:System.Windows.Controls.DockPanel>, `dp1`.</span><span class="sxs-lookup"><span data-stu-id="64b44-108">Finally, the example adds the <xref:System.Windows.Controls.TextBlock> element to the parent <xref:System.Windows.Controls.DockPanel>, `dp1`.</span></span>  
  
 [!code-csharp[DockPanelSetDock#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="64b44-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="64b44-109">See also</span></span>
- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.DockPanel.GetDock%2A>
- <xref:System.Windows.Controls.DockPanel.SetDock%2A>
- [<span data-ttu-id="64b44-110">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="64b44-110">Panels Overview</span></span>](panels-overview.md)
