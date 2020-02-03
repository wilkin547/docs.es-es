---
title: Eventos en controles
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: c60713917b9c84aa7fad50fb1c81fc9252149ad6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745754"
---
# <a name="events-in-windows-forms-controls"></a><span data-ttu-id="7f877-102">Eventos de los controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f877-102">Events in Windows Forms Controls</span></span>
<span data-ttu-id="7f877-103">Un control Windows Forms hereda más de 60 eventos de <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7f877-103">A Windows Forms control inherits more than sixty events from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7f877-104">Incluyen el evento <xref:System.Windows.Forms.Control.Paint>, que hace que se dibuje un control, eventos relacionados con la presentación de una ventana, como los eventos <xref:System.Windows.Forms.Control.Resize> y <xref:System.Windows.Forms.Control.Layout> y eventos de teclado y mouse de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="7f877-104">These include the <xref:System.Windows.Forms.Control.Paint> event, which causes a control to be drawn, events related to displaying a window, such as the <xref:System.Windows.Forms.Control.Resize> and <xref:System.Windows.Forms.Control.Layout> events, and low-level mouse and keyboard events.</span></span> <span data-ttu-id="7f877-105">Algunos eventos de bajo nivel se sintetizan mediante <xref:System.Windows.Forms.Control> en eventos semánticos como <xref:System.Windows.Forms.Control.Click> y <xref:System.Windows.Forms.Control.DoubleClick>.</span><span class="sxs-lookup"><span data-stu-id="7f877-105">Some low-level events are synthesized by <xref:System.Windows.Forms.Control> into semantic events such as <xref:System.Windows.Forms.Control.Click> and <xref:System.Windows.Forms.Control.DoubleClick>.</span></span> <span data-ttu-id="7f877-106">Para obtener más información sobre los eventos heredados, vea <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="7f877-106">For details about inherited events, see <xref:System.Windows.Forms.Control>.</span></span>  
  
 <span data-ttu-id="7f877-107">Si el control personalizado tiene que reemplazar funcionalidad del evento heredado, reemplace el método `On`*EventName* heredado en lugar de asociar un delegado.</span><span class="sxs-lookup"><span data-stu-id="7f877-107">If your custom control needs to override inherited event functionality, override the inherited `On`*EventName* method instead of attaching a delegate.</span></span> <span data-ttu-id="7f877-108">Si no está familiarizado con el modelo de eventos de .NET Framework, vea [Provocar eventos de un componente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="7f877-108">If you are not familiar with the event model in the .NET Framework, see [Raising Events from a Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f877-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7f877-109">See also</span></span>

- [<span data-ttu-id="7f877-110">Reemplazar el método OnPaint</span><span class="sxs-lookup"><span data-stu-id="7f877-110">Overriding the OnPaint Method</span></span>](overriding-the-onpaint-method.md)
- [<span data-ttu-id="7f877-111">Controlar la introducción de datos por el usuario</span><span class="sxs-lookup"><span data-stu-id="7f877-111">Handling User Input</span></span>](handling-user-input.md)
- [<span data-ttu-id="7f877-112">Definir un evento en los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f877-112">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
- [<span data-ttu-id="7f877-113">Eventos</span><span class="sxs-lookup"><span data-stu-id="7f877-113">Events</span></span>](../../../standard/events/index.md)
