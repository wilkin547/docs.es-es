---
title: Eventos de los controles de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: d18938565c302be085b7ac51f878d83ae5ab533d
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2018
ms.locfileid: "47027910"
---
# <a name="events-in-windows-forms-controls"></a>Eventos de los controles de formularios Windows Forms
Un control de Windows Forms hereda más de sesenta eventos de <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Estos incluyen el <xref:System.Windows.Forms.Control.Paint> evento, lo que hace que se dibuje un control, eventos relacionados con la presentación de una ventana, como el <xref:System.Windows.Forms.Control.Resize> y <xref:System.Windows.Forms.Control.Layout> eventos y eventos de teclado y mouse de bajo nivel. Algunos eventos de bajo nivel se sintetizan mediante <xref:System.Windows.Forms.Control> en eventos semánticos como <xref:System.Windows.Forms.Control.Click> y <xref:System.Windows.Forms.Control.DoubleClick>. Para obtener más información sobre los eventos heredados, vea <xref:System.Windows.Forms.Control>.  
  
 Si el control personalizado tiene que reemplazar funcionalidad del evento heredado, reemplace el método `On`*EventName* heredado en lugar de asociar un delegado. Si no está familiarizado con el modelo de eventos de .NET Framework, vea [Provocar eventos de un componente](https://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).  
  
## <a name="see-also"></a>Vea también  
 [Reemplazar el método OnPaint](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)  
 [Controlar la introducción de datos por el usuario](../../../../docs/framework/winforms/controls/handling-user-input.md)  
 [Definir un evento en los controles de Windows Forms](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [Eventos](../../../../docs/standard/events/index.md)
