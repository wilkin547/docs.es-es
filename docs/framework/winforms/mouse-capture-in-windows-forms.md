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
# <a name="mouse-capture-in-windows-forms"></a>Captura del mouse (ratón) en formularios Windows Forms
*Captura el mouse* hace referencia a cuando un control dirige la entrada del mouse. Cuando un control ha capturado el mouse, recibe la entrada del mouse si o no el puntero está dentro de sus bordes.  
  
## <a name="setting-mouse-capture"></a>Configuración de captura del Mouse  
 En formularios Windows Forms se captura el mouse por el control cuando el usuario presiona un botón del mouse en un control, y se suelta el mouse por el control cuando el usuario suelta el botón del mouse.  
  
 El <xref:System.Windows.Forms.Control.Capture%2A> propiedad de la <xref:System.Windows.Forms.Control> clase especifica si un control ha capturado el mouse. Para determinar si un control pierde la captura del mouse, controle el <xref:System.Windows.Forms.Control.MouseCaptureChanged> eventos.  
  
 Solo la ventana a primer plano puede capturar el mouse. Cuando una ventana de segundo plano intenta capturar el mouse, la ventana recibe los mensajes sólo para los eventos del mouse que se producen cuando el puntero del mouse está dentro de la parte visible de la ventana. Además, incluso si la ventana a primer plano ha capturado el mouse, el usuario puede hacer clic en otra ventana, ponerla en primer plano. Cuando se captura el mouse, teclas de método abreviado no funcionan.  
  
## <a name="see-also"></a>Vea también  
 [Entradas mediante el mouse en una aplicación de Windows Forms](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
