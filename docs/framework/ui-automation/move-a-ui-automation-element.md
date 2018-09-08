---
title: Mover un elemento de UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- moving elements
- elements, moving
- UI Automation, moving elements
ms.assetid: 4042cb44-e27e-4a03-ac36-9be1eed65b47
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: cb239adc6dfb11c83fb983a41ea40ad8bf714038
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44133933"
---
# <a name="move-a-ui-automation-element"></a><span data-ttu-id="d4e1d-102">Mover un elemento de UI Automation</span><span class="sxs-lookup"><span data-stu-id="d4e1d-102">Move a UI Automation Element</span></span>
> [!NOTE]
>  <span data-ttu-id="d4e1d-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="d4e1d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d4e1d-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="d4e1d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="d4e1d-105">En este ejemplo se muestra cómo mover un elemento [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] a una ubicación de pantalla especificada.</span><span class="sxs-lookup"><span data-stu-id="d4e1d-105">This example demonstrates how to move a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element to a specified screen location.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4e1d-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4e1d-106">Example</span></span>  
 <span data-ttu-id="d4e1d-107">En el ejemplo siguiente se usa los patrones de control <xref:System.Windows.Automation.WindowPattern> y <xref:System.Windows.Automation.TransformPattern> para mover mediante programación una aplicación de destino [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] target application to discrete screen locations y track the <xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> <xref:System.Windows.Automation.AutomationElement.AutomationPropertyChangedEvent>.</span><span class="sxs-lookup"><span data-stu-id="d4e1d-107">The following example uses the <xref:System.Windows.Automation.WindowPattern> and <xref:System.Windows.Automation.TransformPattern> control patterns to programmatically move a [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] target application to discrete screen locations and track the <xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> <xref:System.Windows.Automation.AutomationElement.AutomationPropertyChangedEvent>.</span></span>  
  
 [!code-csharp[WindowMove#1301](../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowMove/CSharp/WindowMove.cs#1301)]
 [!code-vb[WindowMove#1301](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowMove/VisualBasic/windowmove.vb#1301)]  
[!code-csharp[WindowMove#1300](../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowMove/CSharp/WindowMove.cs#1300)]
[!code-vb[WindowMove#1300](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowMove/VisualBasic/windowmove.vb#1300)]  
  
## <a name="see-also"></a><span data-ttu-id="d4e1d-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4e1d-108">See Also</span></span>  
 [<span data-ttu-id="d4e1d-109">Ejemplo de WindowPattern</span><span class="sxs-lookup"><span data-stu-id="d4e1d-109">WindowPattern Sample</span></span>](https://msdn.microsoft.com/library/598b695c-8baf-406e-bbfb-2a1c7842a1de)
