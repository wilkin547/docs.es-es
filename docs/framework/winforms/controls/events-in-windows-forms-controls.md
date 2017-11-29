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
# <a name="events-in-windows-forms-controls"></a>Eventos de los controles de formularios Windows Forms
Un control de formularios Windows Forms hereda más de sesenta eventos de <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Puede tratarse de la <xref:System.Windows.Forms.Control.Paint> evento, que hace que se dibuje un control, eventos relacionados con la presentación de una ventana, como la <xref:System.Windows.Forms.Control.Resize> y <xref:System.Windows.Forms.Control.Layout> eventos y eventos de teclado y mouse de bajo nivel. Algunos eventos de bajo nivel se sintetizan por <xref:System.Windows.Forms.Control> en eventos semánticos como <xref:System.Windows.Forms.Control.Click> y <xref:System.Windows.Forms.Control.DoubleClick>. Para obtener más información acerca de los eventos heredados, vea <xref:System.Windows.Forms.Control>.  
  
 Si el control personalizado tiene que reemplazar funcionalidad del evento heredado, reemplace el método `On`*EventName* heredado en lugar de asociar un delegado. Si no está familiarizado con el modelo de eventos de .NET Framework, vea [Provocar eventos de un componente](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).  
  
## <a name="see-also"></a>Vea también  
 [Reemplazar el método OnPaint](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)  
 [Controlar la introducción de datos por el usuario](../../../../docs/framework/winforms/controls/handling-user-input.md)  
 [Definir un evento en los controles de Windows Forms](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [Eventos](../../../../docs/standard/events/index.md)
