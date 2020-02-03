---
title: Captura del mouse
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: 10583f074831b16dce3c713b4ac9a76c7005c9f5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741020"
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="4da02-102">Captura del mouse (ratón) en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4da02-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="4da02-103">La *captura del mouse* se refiere a cuando un control toma el comando de toda la entrada del mouse.</span><span class="sxs-lookup"><span data-stu-id="4da02-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="4da02-104">Cuando un control ha capturado el mouse, recibe la entrada del mouse independientemente de si el puntero está dentro de los bordes.</span><span class="sxs-lookup"><span data-stu-id="4da02-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="4da02-105">Configuración de la captura del mouse</span><span class="sxs-lookup"><span data-stu-id="4da02-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="4da02-106">En Windows Forms se captura el mouse por el control cuando el usuario presiona un botón del mouse en un control, y el control suelta el mouse cuando el usuario suelta el botón del mouse.</span><span class="sxs-lookup"><span data-stu-id="4da02-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="4da02-107">La propiedad <xref:System.Windows.Forms.Control.Capture%2A> de la clase <xref:System.Windows.Forms.Control> especifica si un control ha capturado el mouse.</span><span class="sxs-lookup"><span data-stu-id="4da02-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="4da02-108">Para determinar si un control pierde la captura del mouse, controle el evento <xref:System.Windows.Forms.Control.MouseCaptureChanged>.</span><span class="sxs-lookup"><span data-stu-id="4da02-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="4da02-109">Solo la ventana de primer plano puede capturar el mouse.</span><span class="sxs-lookup"><span data-stu-id="4da02-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="4da02-110">Cuando una ventana en segundo plano intenta capturar el mouse, la ventana recibe mensajes solo de los eventos del mouse que se producen cuando el puntero del mouse está dentro de la parte visible de la ventana.</span><span class="sxs-lookup"><span data-stu-id="4da02-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="4da02-111">Además, incluso si la ventana de primer plano ha capturado el mouse, el usuario todavía puede hacer clic en otra ventana y colocarla en primer plano.</span><span class="sxs-lookup"><span data-stu-id="4da02-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="4da02-112">Cuando se captura el mouse, las teclas de método abreviado no funcionan.</span><span class="sxs-lookup"><span data-stu-id="4da02-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4da02-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4da02-113">See also</span></span>

- [<span data-ttu-id="4da02-114">Entradas mediante el mouse en una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4da02-114">Mouse Input in a Windows Forms Application</span></span>](mouse-input-in-a-windows-forms-application.md)
