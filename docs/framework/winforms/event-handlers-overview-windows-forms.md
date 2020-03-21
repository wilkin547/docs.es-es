---
title: Información general sobre controladores de eventos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
ms.openlocfilehash: ffec8a9f8e080dec78152e62e00e2dceefbdaab0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141697"
---
# <a name="event-handlers-overview-windows-forms"></a>Información general sobre controladores de eventos (Formularios Windows Forms)
Un controlador de eventos es un método que está enlazado a un evento. Cuando se genera el evento, se ejecuta el código dentro del controlador de eventos. Cada controlador de eventos proporciona dos parámetros que le permiten controlar el evento correctamente. En el ejemplo siguiente se <xref:System.Windows.Forms.Button> muestra <xref:System.Windows.Forms.Control.Click> un controlador de eventos para el evento de un control.  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)
{  
  
}  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 El primer`sender`parámetro, , proporciona una referencia al objeto que generó el evento. El segundo `e`parámetro, , en el ejemplo anterior, pasa un objeto específico del evento que se está controlando. Al hacer referencia a las propiedades del objeto (y, a veces, a sus métodos), puede obtener información como la ubicación del mouse para eventos del mouse o datos que se transfieren en eventos de arrastrar y colocar.  
  
 Normalmente, cada evento genera un controlador de eventos con un tipo de objeto de evento diferente para el segundo parámetro. Algunos controladores de eventos, <xref:System.Windows.Forms.Control.MouseDown> como <xref:System.Windows.Forms.Control.MouseUp> los de los eventos y los, tienen el mismo tipo de objeto para su segundo parámetro. Para estos tipos de eventos, puede usar el mismo controlador de eventos para controlar ambos eventos.  
  
 También puede usar el mismo controlador de eventos para controlar el mismo evento para diferentes controles. Por ejemplo, si tiene <xref:System.Windows.Forms.RadioButton> un grupo de controles en un formulario, <xref:System.Windows.Forms.Control.Click> podría crear un <xref:System.Windows.Forms.Control.Click> único controlador de eventos para el evento y tener el evento de cada control enlazado al controlador de eventos único. Para obtener más información, vea [Cómo: conectar varios eventos a un controlador](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)de eventos único en formularios Windows Forms .  
  
## <a name="see-also"></a>Consulte también

- [Crear controladores de eventos en Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Información general sobre eventos](events-overview-windows-forms.md)
