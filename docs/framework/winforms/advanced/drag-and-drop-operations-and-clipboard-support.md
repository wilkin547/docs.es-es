---
title: Compatibilidad con las operaciones de arrastrar y colocar y con el Portapapeles
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drag and drop [Windows Forms]
- drag and drop [Windows Forms], Windows Forms
- Clipboard [Windows Forms], Windows Forms
ms.assetid: 7cce79b6-5835-46fd-b690-73f12ad368b2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 722c37645d95009ce03bbbf813bc9f9fb2418e60
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="drag-and-drop-operations-and-clipboard-support"></a>Compatibilidad con las operaciones de arrastrar y colocar y con el Portapapeles
Puede habilitar las operaciones de arrastrar y colocar del usuario en una aplicación basada en Windows controlando una serie de eventos, sobre todo los eventos <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave> y <xref:System.Windows.Forms.Control.DragDrop>.  
  
 También puede implementar la compatibilidad de cortar, copiar y pegar del usuario, y la transferencia de datos del usuario en el Portapapeles en las aplicaciones basadas en Windows mediante llamadas a métodos simples.  
  
## <a name="in-this-section"></a>En esta sección  
 [Tutorial: Llevar a cabo una operación de arrastrar y colocar en Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)  
 Explica cómo iniciar una operación de arrastrar y colocar.  
  
 [Llevar a cabo operaciones de arrastrar y colocar entre aplicaciones](../../../../docs/framework/winforms/advanced/how-to-perform-drag-and-drop-operations-between-applications.md)  
 Ilustra cómo realizar operaciones de arrastrar y colocar entre aplicaciones.  
  
 [Agregar datos al Portapapeles](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)  
 Describe una manera de insertar información en el Portapapeles mediante programación.  
  
 [Recuperar datos del Portapapeles](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)  
 Describe cómo acceder a los datos almacenados en el Portapapeles.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Funcionalidad de arrastrar y soltar en Windows Forms](../../../../docs/framework/winforms/drag-and-drop-functionality-in-windows-forms.md)  
 Describe los métodos, eventos y clases utilizadas para implementar el comportamiento de arrastrar y colocar.  
  
 <xref:System.Windows.Forms.Control.QueryContinueDrag>  
 Describe los detalles del evento que solicita permiso para continuar la operación de arrastre.  
  
 <xref:System.Windows.Forms.Control.DoDragDrop%2A>  
 Describe los detalles del método que resulta esencial para iniciar una operación de arrastre.  
  
 <xref:System.Windows.Forms.Clipboard>  
 Consulte también [Cómo: enviar datos en el formulario secundario MDI activo](http://msdn.microsoft.com/library/y0hkh2c8\(v=vs.110\)).
