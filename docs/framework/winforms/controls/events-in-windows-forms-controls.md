---
title: Eventos de los controles de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: dfbac71335615af52de3b5862c4058981f965654
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720809"
---
# <a name="events-in-windows-forms-controls"></a><span data-ttu-id="e656e-102">Eventos de los controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e656e-102">Events in Windows Forms Controls</span></span>
<span data-ttu-id="e656e-103">Un control de Windows Forms hereda más de sesenta eventos de <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e656e-103">A Windows Forms control inherits more than sixty events from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e656e-104">Estos incluyen el <xref:System.Windows.Forms.Control.Paint> evento, lo que hace que se dibuje un control, eventos relacionados con la presentación de una ventana, como el <xref:System.Windows.Forms.Control.Resize> y <xref:System.Windows.Forms.Control.Layout> eventos y eventos de teclado y mouse de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="e656e-104">These include the <xref:System.Windows.Forms.Control.Paint> event, which causes a control to be drawn, events related to displaying a window, such as the <xref:System.Windows.Forms.Control.Resize> and <xref:System.Windows.Forms.Control.Layout> events, and low-level mouse and keyboard events.</span></span> <span data-ttu-id="e656e-105">Algunos eventos de bajo nivel se sintetizan mediante <xref:System.Windows.Forms.Control> en eventos semánticos como <xref:System.Windows.Forms.Control.Click> y <xref:System.Windows.Forms.Control.DoubleClick>.</span><span class="sxs-lookup"><span data-stu-id="e656e-105">Some low-level events are synthesized by <xref:System.Windows.Forms.Control> into semantic events such as <xref:System.Windows.Forms.Control.Click> and <xref:System.Windows.Forms.Control.DoubleClick>.</span></span> <span data-ttu-id="e656e-106">Para obtener más información sobre los eventos heredados, vea <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="e656e-106">For details about inherited events, see <xref:System.Windows.Forms.Control>.</span></span>  
  
 <span data-ttu-id="e656e-107">Si el control personalizado tiene que reemplazar funcionalidad del evento heredado, reemplace el método `On`*EventName* heredado en lugar de asociar un delegado.</span><span class="sxs-lookup"><span data-stu-id="e656e-107">If your custom control needs to override inherited event functionality, override the inherited `On`*EventName* method instead of attaching a delegate.</span></span> <span data-ttu-id="e656e-108">Si no está familiarizado con el modelo de eventos de .NET Framework, vea [Provocar eventos de un componente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="e656e-108">If you are not familiar with the event model in the .NET Framework, see [Raising Events from a Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e656e-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="e656e-109">See also</span></span>
- [<span data-ttu-id="e656e-110">Reemplazar el método OnPaint</span><span class="sxs-lookup"><span data-stu-id="e656e-110">Overriding the OnPaint Method</span></span>](overriding-the-onpaint-method.md)
- [<span data-ttu-id="e656e-111">Controlar la introducción de datos por el usuario</span><span class="sxs-lookup"><span data-stu-id="e656e-111">Handling User Input</span></span>](handling-user-input.md)
- [<span data-ttu-id="e656e-112">Definir un evento en los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e656e-112">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
- [<span data-ttu-id="e656e-113">Eventos</span><span class="sxs-lookup"><span data-stu-id="e656e-113">Events</span></span>](../../../standard/events/index.md)
