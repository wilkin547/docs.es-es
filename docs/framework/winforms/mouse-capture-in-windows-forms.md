---
title: Captura del mouse (ratón) en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: dfe983b9e407eddb9bed3bcc1a767cdeff38f2ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538413"
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="6711b-102">Captura del mouse (ratón) en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6711b-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="6711b-103">*Captura el mouse* hace referencia a cuando un control dirige la entrada del mouse.</span><span class="sxs-lookup"><span data-stu-id="6711b-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="6711b-104">Cuando un control ha capturado el mouse, recibe la entrada del mouse si o no el puntero está dentro de sus bordes.</span><span class="sxs-lookup"><span data-stu-id="6711b-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="6711b-105">Configuración de captura del Mouse</span><span class="sxs-lookup"><span data-stu-id="6711b-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="6711b-106">En formularios Windows Forms se captura el mouse por el control cuando el usuario presiona un botón del mouse en un control, y se suelta el mouse por el control cuando el usuario suelta el botón del mouse.</span><span class="sxs-lookup"><span data-stu-id="6711b-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="6711b-107">El <xref:System.Windows.Forms.Control.Capture%2A> propiedad de la <xref:System.Windows.Forms.Control> clase especifica si un control ha capturado el mouse.</span><span class="sxs-lookup"><span data-stu-id="6711b-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="6711b-108">Para determinar si un control pierde la captura del mouse, controle el <xref:System.Windows.Forms.Control.MouseCaptureChanged> eventos.</span><span class="sxs-lookup"><span data-stu-id="6711b-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="6711b-109">Solo la ventana a primer plano puede capturar el mouse.</span><span class="sxs-lookup"><span data-stu-id="6711b-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="6711b-110">Cuando una ventana de segundo plano intenta capturar el mouse, la ventana recibe los mensajes sólo para los eventos del mouse que se producen cuando el puntero del mouse está dentro de la parte visible de la ventana.</span><span class="sxs-lookup"><span data-stu-id="6711b-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="6711b-111">Además, incluso si la ventana a primer plano ha capturado el mouse, el usuario puede hacer clic en otra ventana, ponerla en primer plano.</span><span class="sxs-lookup"><span data-stu-id="6711b-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="6711b-112">Cuando se captura el mouse, teclas de método abreviado no funcionan.</span><span class="sxs-lookup"><span data-stu-id="6711b-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6711b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6711b-113">See Also</span></span>  
 [<span data-ttu-id="6711b-114">Entradas mediante el mouse en una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6711b-114">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
