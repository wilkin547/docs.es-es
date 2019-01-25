---
title: Información general sobre Splitter (Control, formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
ms.openlocfilehash: 583596ec44dd5318c199d6cfc33901dbd952b115
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522614"
---
# <a name="splitter-control-overview-windows-forms"></a><span data-ttu-id="9a68a-102">Información general sobre Splitter (Control, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="9a68a-102">Splitter Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="9a68a-103">Aunque el control <xref:System.Windows.Forms.SplitContainer> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.Splitter> de las versiones anteriores, <xref:System.Windows.Forms.Splitter> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, si se desea.</span><span class="sxs-lookup"><span data-stu-id="9a68a-103">Although <xref:System.Windows.Forms.SplitContainer> replaces and adds functionality to the <xref:System.Windows.Forms.Splitter> control of previous versions, <xref:System.Windows.Forms.Splitter> is retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="9a68a-104">Windows Forms <xref:System.Windows.Forms.Splitter> controles se usan para cambiar el tamaño de los controles acoplados en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9a68a-104">Windows Forms <xref:System.Windows.Forms.Splitter> controls are used to resize docked controls at run time.</span></span> <span data-ttu-id="9a68a-105">El <xref:System.Windows.Forms.Splitter> control suele utilizarse en formularios con controles que tienen distintas longitudes de datos que se va a presentar, como el Explorador de Windows, cuyos paneles de datos contienen información de diversos anchos en momentos diferentes.</span><span class="sxs-lookup"><span data-stu-id="9a68a-105">The <xref:System.Windows.Forms.Splitter> control is often used on forms with controls that have varying lengths of data to present, like Windows Explorer, whose data panes contain information of varying widths at different times.</span></span>  
  
## <a name="working-with-the-splitter-control"></a><span data-ttu-id="9a68a-106">Trabajar con el Control divisor</span><span class="sxs-lookup"><span data-stu-id="9a68a-106">Working with the Splitter Control</span></span>  
 <span data-ttu-id="9a68a-107">Cuando el usuario sitúa el puntero del mouse sobre el borde de un control que se puede cambiar el tamaño de un control divisor desacoplado, el puntero cambia de apariencia para indicar que se puede cambiar el tamaño del control.</span><span class="sxs-lookup"><span data-stu-id="9a68a-107">When the user points the mouse pointer at the undocked edge of a control that can be resized by a splitter control, the pointer changes its appearance to indicate that the control can be resized.</span></span> <span data-ttu-id="9a68a-108">Con el control divisor, el usuario puede cambiar el tamaño del control acoplado inmediatamente anterior.</span><span class="sxs-lookup"><span data-stu-id="9a68a-108">With the splitter control, the user can resize the docked control that is immediately before it.</span></span> <span data-ttu-id="9a68a-109">Por lo tanto, para permitir al usuario cambiar el tamaño de un control acoplado en tiempo de ejecución, acople el control para cambiar de tamaño a un borde de un contenedor y, a continuación, acoplar un control divisor en el mismo lado de ese contenedor.</span><span class="sxs-lookup"><span data-stu-id="9a68a-109">Therefore, to enable the user to resize a docked control at run time, dock the control to be resized to an edge of a container, and then dock a splitter control to the same side of that container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a68a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a68a-110">See also</span></span>
- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="9a68a-111">Cómo: Acoplar controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9a68a-111">How to: Dock Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="9a68a-112">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9a68a-112">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
