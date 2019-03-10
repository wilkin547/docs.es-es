---
title: Eventos de los controles de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: dfbac71335615af52de3b5862c4058981f965654
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720809"
---
# <a name="events-in-windows-forms-controls"></a>Eventos de los controles de formularios Windows Forms
Un control de Windows Forms hereda más de sesenta eventos de <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Estos incluyen el <xref:System.Windows.Forms.Control.Paint> evento, lo que hace que se dibuje un control, eventos relacionados con la presentación de una ventana, como el <xref:System.Windows.Forms.Control.Resize> y <xref:System.Windows.Forms.Control.Layout> eventos y eventos de teclado y mouse de bajo nivel. Algunos eventos de bajo nivel se sintetizan mediante <xref:System.Windows.Forms.Control> en eventos semánticos como <xref:System.Windows.Forms.Control.Click> y <xref:System.Windows.Forms.Control.DoubleClick>. Para obtener más información sobre los eventos heredados, vea <xref:System.Windows.Forms.Control>.  
  
 Si el control personalizado tiene que reemplazar funcionalidad del evento heredado, reemplace el método `On`*EventName* heredado en lugar de asociar un delegado. Si no está familiarizado con el modelo de eventos de .NET Framework, vea [Provocar eventos de un componente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).  
  
## <a name="see-also"></a>Vea también
- [Reemplazar el método OnPaint](overriding-the-onpaint-method.md)
- [Controlar la introducción de datos por el usuario](handling-user-input.md)
- [Definir un evento en los controles de Windows Forms](defining-an-event-in-windows-forms-controls.md)
- [Eventos](../../../standard/events/index.md)
