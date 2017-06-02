---
title: "Drag-and-Drop Operations and Clipboard Support | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "drag and drop"
  - "drag and drop, Windows Forms"
  - "Clipboard, Windows Forms"
ms.assetid: 7cce79b6-5835-46fd-b690-73f12ad368b2
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Drag-and-Drop Operations and Clipboard Support
Puede habilitar las operaciones de arrastrar y colocar del usuario en una aplicación basada en Windows controlando una serie de eventos, sobre todo los eventos <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave> y <xref:System.Windows.Forms.Control.DragDrop>.  
  
 También puede implementar la compatibilidad de cortar, copiar y pegar del usuario, y la transferencia de datos del usuario en el Portapapeles en las aplicaciones basadas en Windows mediante llamadas a métodos simples.  
  
## En esta sección  
 [Walkthrough: Performing a Drag\-and\-Drop Operation in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)  
 Explica cómo iniciar una operación de arrastrar y colocar.  
  
 [How to: Perform Drag\-and\-Drop Operations Between Applications](../../../../docs/framework/winforms/advanced/how-to-perform-drag-and-drop-operations-between-applications.md)  
 Ilustra cómo realizar operaciones de arrastrar y colocar entre aplicaciones.  
  
 [How to: Add Data to the Clipboard](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)  
 Describe una manera de insertar información en el Portapapeles mediante programación.  
  
 [How to: Retrieve Data from the Clipboard](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)  
 Describe cómo acceder a los datos almacenados en el Portapapeles.  
  
## Secciones relacionadas  
 [Drag\-and\-Drop Functionality in Windows Forms](../../../../docs/framework/winforms/drag-and-drop-functionality-in-windows-forms.md)  
 Describe los métodos, eventos y clases utilizadas para implementar el comportamiento de arrastrar y colocar.  
  
 <xref:System.Windows.Forms.Control.QueryContinueDrag>  
 Describe los detalles del evento que solicita permiso para continuar la operación de arrastre.  
  
 <xref:System.Windows.Forms.Control.DoDragDrop%2A>  
 Describe los detalles del método que resulta esencial para iniciar una operación de arrastre.  
  
 <xref:System.Windows.Forms.Clipboard>  
 Consulte también [Cómo: Enviar datos al formulario secundario MDI activo](http://msdn.microsoft.com/library/y0hkh2c8\(v=vs.110\)).