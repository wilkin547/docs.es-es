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
# <a name="mouse-capture-in-windows-forms"></a>Captura del mouse (ratón) en formularios Windows Forms
La *captura del mouse* se refiere a cuando un control toma el comando de toda la entrada del mouse. Cuando un control ha capturado el mouse, recibe la entrada del mouse independientemente de si el puntero está dentro de los bordes.  
  
## <a name="setting-mouse-capture"></a>Configuración de la captura del mouse  
 En Windows Forms se captura el mouse por el control cuando el usuario presiona un botón del mouse en un control, y el control suelta el mouse cuando el usuario suelta el botón del mouse.  
  
 La propiedad <xref:System.Windows.Forms.Control.Capture%2A> de la clase <xref:System.Windows.Forms.Control> especifica si un control ha capturado el mouse. Para determinar si un control pierde la captura del mouse, controle el evento <xref:System.Windows.Forms.Control.MouseCaptureChanged>.  
  
 Solo la ventana de primer plano puede capturar el mouse. Cuando una ventana en segundo plano intenta capturar el mouse, la ventana recibe mensajes solo de los eventos del mouse que se producen cuando el puntero del mouse está dentro de la parte visible de la ventana. Además, incluso si la ventana de primer plano ha capturado el mouse, el usuario todavía puede hacer clic en otra ventana y colocarla en primer plano. Cuando se captura el mouse, las teclas de método abreviado no funcionan.  
  
## <a name="see-also"></a>Vea también

- [Entradas mediante el mouse en una aplicación de Windows Forms](mouse-input-in-a-windows-forms-application.md)
