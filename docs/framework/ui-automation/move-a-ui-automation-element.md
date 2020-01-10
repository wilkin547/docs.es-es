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
ms.openlocfilehash: 72454e355fb9b673a4adafb39ad60c8414573d0e
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741316"
---
# <a name="move-a-ui-automation-element"></a><span data-ttu-id="3ddd5-102">Mover un elemento de UI Automation</span><span class="sxs-lookup"><span data-stu-id="3ddd5-102">Move a UI Automation Element</span></span>
> [!NOTE]
> <span data-ttu-id="3ddd5-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="3ddd5-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="3ddd5-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="3ddd5-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="3ddd5-105">En este ejemplo se muestra cómo mover un elemento [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] a una ubicación de pantalla especificada.</span><span class="sxs-lookup"><span data-stu-id="3ddd5-105">This example demonstrates how to move a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element to a specified screen location.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ddd5-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3ddd5-106">Example</span></span>  
 <span data-ttu-id="3ddd5-107">En el ejemplo siguiente se usan los patrones de control <xref:System.Windows.Automation.WindowPattern> y <xref:System.Windows.Automation.TransformPattern> para trasladar mediante programación una aplicación de destino Win32 a ubicaciones de pantalla discretas y hacer un seguimiento del <xref:System.Windows.Automation.AutomationElement.AutomationPropertyChangedEvent><xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>.</span><span class="sxs-lookup"><span data-stu-id="3ddd5-107">The following example uses the <xref:System.Windows.Automation.WindowPattern> and <xref:System.Windows.Automation.TransformPattern> control patterns to programmatically move a Win32 target application to discrete screen locations and track the <xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> <xref:System.Windows.Automation.AutomationElement.AutomationPropertyChangedEvent>.</span></span>  
  
 [!code-csharp[WindowMove#1301](../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowMove/CSharp/WindowMove.cs#1301)]
 [!code-vb[WindowMove#1301](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowMove/VisualBasic/windowmove.vb#1301)]  
[!code-csharp[WindowMove#1300](../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowMove/CSharp/WindowMove.cs#1300)]
[!code-vb[WindowMove#1300](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowMove/VisualBasic/windowmove.vb#1300)]  
  
## <a name="see-also"></a><span data-ttu-id="3ddd5-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ddd5-108">See also</span></span>

- [<span data-ttu-id="3ddd5-109">Ejemplo de WindowPattern</span><span class="sxs-lookup"><span data-stu-id="3ddd5-109">WindowPattern Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/WindowMove)
