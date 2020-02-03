---
title: Eventos en controles
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: c60713917b9c84aa7fad50fb1c81fc9252149ad6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745754"
---
# <a name="events-in-windows-forms-controls"></a>Eventos de los controles de formularios Windows Forms
Un control Windows Forms hereda más de 60 eventos de <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Incluyen el evento <xref:System.Windows.Forms.Control.Paint>, que hace que se dibuje un control, eventos relacionados con la presentación de una ventana, como los eventos <xref:System.Windows.Forms.Control.Resize> y <xref:System.Windows.Forms.Control.Layout> y eventos de teclado y mouse de bajo nivel. Algunos eventos de bajo nivel se sintetizan mediante <xref:System.Windows.Forms.Control> en eventos semánticos como <xref:System.Windows.Forms.Control.Click> y <xref:System.Windows.Forms.Control.DoubleClick>. Para obtener más información sobre los eventos heredados, vea <xref:System.Windows.Forms.Control>.  
  
 Si el control personalizado tiene que reemplazar funcionalidad del evento heredado, reemplace el método `On`*EventName* heredado en lugar de asociar un delegado. Si no está familiarizado con el modelo de eventos de .NET Framework, vea [Provocar eventos de un componente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).  
  
## <a name="see-also"></a>Consulte también

- [Reemplazar el método OnPaint](overriding-the-onpaint-method.md)
- [Controlar la introducción de datos por el usuario](handling-user-input.md)
- [Definir un evento en los controles de Windows Forms](defining-an-event-in-windows-forms-controls.md)
- [Eventos](../../../standard/events/index.md)
