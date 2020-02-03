---
title: Información general sobre Splitter (Control)
ms.date: 03/30/2017
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
ms.openlocfilehash: 3d6da8daf9bb0e8df4f69554a87725a7ddb65acb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742890"
---
# <a name="splitter-control-overview-windows-forms"></a><span data-ttu-id="48fa9-102">Información general sobre Splitter (Control, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="48fa9-102">Splitter Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="48fa9-103">Aunque el control <xref:System.Windows.Forms.SplitContainer> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.Splitter> de las versiones anteriores, <xref:System.Windows.Forms.Splitter> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, si se desea.</span><span class="sxs-lookup"><span data-stu-id="48fa9-103">Although <xref:System.Windows.Forms.SplitContainer> replaces and adds functionality to the <xref:System.Windows.Forms.Splitter> control of previous versions, <xref:System.Windows.Forms.Splitter> is retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="48fa9-104">Windows Forms controles de <xref:System.Windows.Forms.Splitter> se utilizan para cambiar el tamaño de los controles acoplados en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="48fa9-104">Windows Forms <xref:System.Windows.Forms.Splitter> controls are used to resize docked controls at run time.</span></span> <span data-ttu-id="48fa9-105">El control <xref:System.Windows.Forms.Splitter> se usa a menudo en formularios con controles que tienen diferentes longitudes de datos para presentar, como el explorador de Windows, cuyos paneles de datos contienen información de distintos anchos en momentos distintos.</span><span class="sxs-lookup"><span data-stu-id="48fa9-105">The <xref:System.Windows.Forms.Splitter> control is often used on forms with controls that have varying lengths of data to present, like Windows Explorer, whose data panes contain information of varying widths at different times.</span></span>  
  
## <a name="working-with-the-splitter-control"></a><span data-ttu-id="48fa9-106">Trabajar con el control divisor</span><span class="sxs-lookup"><span data-stu-id="48fa9-106">Working with the Splitter Control</span></span>  
 <span data-ttu-id="48fa9-107">Cuando el usuario apunta el puntero del mouse en el borde desacoplado de un control cuyo tamaño se puede cambiar por un control divisor, el puntero cambia su apariencia para indicar que se puede cambiar el tamaño del control.</span><span class="sxs-lookup"><span data-stu-id="48fa9-107">When the user points the mouse pointer at the undocked edge of a control that can be resized by a splitter control, the pointer changes its appearance to indicate that the control can be resized.</span></span> <span data-ttu-id="48fa9-108">Con el control divisor, el usuario puede cambiar el tamaño del control acoplado inmediatamente antes.</span><span class="sxs-lookup"><span data-stu-id="48fa9-108">With the splitter control, the user can resize the docked control that is immediately before it.</span></span> <span data-ttu-id="48fa9-109">Por lo tanto, para permitir al usuario cambiar el tamaño de un control acoplado en tiempo de ejecución, acople el control cuyo tamaño se va a cambiar a un borde de un contenedor y, a continuación, acople un control divisor al mismo lado de dicho contenedor.</span><span class="sxs-lookup"><span data-stu-id="48fa9-109">Therefore, to enable the user to resize a docked control at run time, dock the control to be resized to an edge of a container, and then dock a splitter control to the same side of that container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48fa9-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="48fa9-110">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="48fa9-111">Procedimiento para acoplar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="48fa9-111">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="48fa9-112">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="48fa9-112">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
