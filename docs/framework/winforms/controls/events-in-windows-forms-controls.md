---
title: Eventos de los controles de formularios Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e568dd7fadea8af399a63aa95347f368b4e13a54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="events-in-windows-forms-controls"></a><span data-ttu-id="0ed42-102">Eventos de los controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ed42-102">Events in Windows Forms Controls</span></span>
<span data-ttu-id="0ed42-103">Un control de formularios Windows Forms hereda más de sesenta eventos de <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0ed42-103">A Windows Forms control inherits more than sixty events from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0ed42-104">Puede tratarse de la <xref:System.Windows.Forms.Control.Paint> evento, que hace que se dibuje un control, eventos relacionados con la presentación de una ventana, como la <xref:System.Windows.Forms.Control.Resize> y <xref:System.Windows.Forms.Control.Layout> eventos y eventos de teclado y mouse de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="0ed42-104">These include the <xref:System.Windows.Forms.Control.Paint> event, which causes a control to be drawn, events related to displaying a window, such as the <xref:System.Windows.Forms.Control.Resize> and <xref:System.Windows.Forms.Control.Layout> events, and low-level mouse and keyboard events.</span></span> <span data-ttu-id="0ed42-105">Algunos eventos de bajo nivel se sintetizan por <xref:System.Windows.Forms.Control> en eventos semánticos como <xref:System.Windows.Forms.Control.Click> y <xref:System.Windows.Forms.Control.DoubleClick>.</span><span class="sxs-lookup"><span data-stu-id="0ed42-105">Some low-level events are synthesized by <xref:System.Windows.Forms.Control> into semantic events such as <xref:System.Windows.Forms.Control.Click> and <xref:System.Windows.Forms.Control.DoubleClick>.</span></span> <span data-ttu-id="0ed42-106">Para obtener más información acerca de los eventos heredados, vea <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="0ed42-106">For details about inherited events, see <xref:System.Windows.Forms.Control>.</span></span>  
  
 <span data-ttu-id="0ed42-107">Si el control personalizado tiene que reemplazar funcionalidad del evento heredado, reemplace el método `On`*EventName* heredado en lugar de asociar un delegado.</span><span class="sxs-lookup"><span data-stu-id="0ed42-107">If your custom control needs to override inherited event functionality, override the inherited `On`*EventName* method instead of attaching a delegate.</span></span> <span data-ttu-id="0ed42-108">Si no está familiarizado con el modelo de eventos de .NET Framework, vea [Provocar eventos de un componente](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).</span><span class="sxs-lookup"><span data-stu-id="0ed42-108">If you are not familiar with the event model in the .NET Framework, see [Raising Events from a Component](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ed42-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ed42-109">See Also</span></span>  
 [<span data-ttu-id="0ed42-110">Reemplazar el método OnPaint</span><span class="sxs-lookup"><span data-stu-id="0ed42-110">Overriding the OnPaint Method</span></span>](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)  
 [<span data-ttu-id="0ed42-111">Controlar la introducción de datos por el usuario</span><span class="sxs-lookup"><span data-stu-id="0ed42-111">Handling User Input</span></span>](../../../../docs/framework/winforms/controls/handling-user-input.md)  
 [<span data-ttu-id="0ed42-112">Definir un evento en los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ed42-112">Defining an Event</span></span>](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [<span data-ttu-id="0ed42-113">Eventos</span><span class="sxs-lookup"><span data-stu-id="0ed42-113">Events</span></span>](../../../../docs/standard/events/index.md)
