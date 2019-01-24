---
title: Captura del mouse (ratón) en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: ca16d2fa2339f8d9110bb748a687f90e093598fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690337"
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="59a12-102">Captura del mouse (ratón) en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="59a12-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="59a12-103">*Captura el mouse* se refiere a un control dirige la entrada del mouse.</span><span class="sxs-lookup"><span data-stu-id="59a12-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="59a12-104">Cuando un control ha capturado el mouse, recibe la entrada del mouse si el puntero está dentro de sus bordes.</span><span class="sxs-lookup"><span data-stu-id="59a12-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="59a12-105">Configuración de captura del Mouse</span><span class="sxs-lookup"><span data-stu-id="59a12-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="59a12-106">En Windows Forms se captura el mouse por el control cuando el usuario presiona un botón del mouse en un control y se suelta el mouse por el control cuando el usuario suelta el botón del mouse.</span><span class="sxs-lookup"><span data-stu-id="59a12-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="59a12-107">El <xref:System.Windows.Forms.Control.Capture%2A> propiedad de la <xref:System.Windows.Forms.Control> clase especifica si un control ha capturado el mouse.</span><span class="sxs-lookup"><span data-stu-id="59a12-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="59a12-108">Para determinar cuándo un control pierde la captura del mouse, controle el <xref:System.Windows.Forms.Control.MouseCaptureChanged> eventos.</span><span class="sxs-lookup"><span data-stu-id="59a12-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="59a12-109">Ventana de primer plano puede capturar el mouse.</span><span class="sxs-lookup"><span data-stu-id="59a12-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="59a12-110">Cuando una ventana en segundo plano intenta capturar el mouse, la ventana recibe los mensajes solo para los eventos del mouse que se producen cuando el puntero del mouse está dentro de la parte visible de la ventana.</span><span class="sxs-lookup"><span data-stu-id="59a12-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="59a12-111">Además, incluso si la ventana de primer plano ha capturado el mouse, el usuario puede hacer clic en otra ventana, llevándola a primer plano.</span><span class="sxs-lookup"><span data-stu-id="59a12-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="59a12-112">Cuando se captura el mouse, teclas de método abreviado no funcionan.</span><span class="sxs-lookup"><span data-stu-id="59a12-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59a12-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="59a12-113">See also</span></span>
- [<span data-ttu-id="59a12-114">Entradas mediante el mouse en una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="59a12-114">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
