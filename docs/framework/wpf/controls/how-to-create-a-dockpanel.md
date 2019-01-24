---
title: Procedimiento Crear un DockPanel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], creating
ms.assetid: 9194f663-e279-4f1a-86d7-125a57d05c6f
ms.openlocfilehash: 1686ce0d9cd6f02fc524789c1e3ad7daedcbbaf2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674354"
---
# <a name="how-to-create-a-dockpanel"></a><span data-ttu-id="c3208-102">Procedimiento Crear un DockPanel</span><span class="sxs-lookup"><span data-stu-id="c3208-102">How to: Create a DockPanel</span></span>
## <a name="example"></a><span data-ttu-id="c3208-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3208-103">Example</span></span>  
 <span data-ttu-id="c3208-104">El ejemplo siguiente se crea y utiliza una instancia de <xref:System.Windows.Controls.DockPanel> mediante código.</span><span class="sxs-lookup"><span data-stu-id="c3208-104">The following example creates and uses an instance of <xref:System.Windows.Controls.DockPanel> by using code.</span></span> <span data-ttu-id="c3208-105">En el ejemplo se muestra cómo dividir el espacio mediante la creación de cinco <xref:System.Windows.Shapes.Rectangle> elementos y colocarlos (acoplarlos) dentro de un elemento primario <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="c3208-105">The example shows you how to partition space by creating five <xref:System.Windows.Shapes.Rectangle> elements and positioning (docking) them inside a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="c3208-106">Si mantiene la configuración predeterminada, el último rectángulo rellena todo el espacio sin asignar restante.</span><span class="sxs-lookup"><span data-stu-id="c3208-106">If you retain the default setting, the final rectangle fills all the remaining unallocated space.</span></span>  
  
 [!code-csharp[DockPanelCode#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelCode/CSharp/DockPanel_Code.cs#1)]
 [!code-vb[DockPanelCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelCode/VisualBasic/dockpanel_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c3208-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3208-107">See also</span></span>
- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.Dock>
- [<span data-ttu-id="c3208-108">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="c3208-108">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
