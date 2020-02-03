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
ms.openlocfilehash: 10ba458197973ede35849a86fec35003f139b8d2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743464"
---
# <a name="event-handlers-overview-windows-forms"></a>Información general sobre controladores de eventos (Windows Forms)
Un controlador de eventos es un método que está enlazado a un evento. Cuando se genera el evento, se ejecuta el código del controlador de eventos. Cada controlador de eventos proporciona dos parámetros que permiten controlar el evento correctamente. En el ejemplo siguiente se muestra un controlador de eventos para un evento de <xref:System.Windows.Forms.Control.Click> del control <xref:System.Windows.Forms.Button>.  
  
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
  
 El primer parámetro,`sender`, proporciona una referencia al objeto que generó el evento. El segundo parámetro, `e`, en el ejemplo anterior, pasa un objeto específico del evento que se está controlando. Al hacer referencia a las propiedades del objeto (y, a veces, a sus métodos), puede obtener información como la ubicación del mouse para los eventos del mouse o los datos que se transfieren en los eventos de arrastrar y colocar.  
  
 Normalmente, cada evento genera un controlador de eventos con un tipo de objeto de evento diferente para el segundo parámetro. Algunos controladores de eventos, como los de los eventos <xref:System.Windows.Forms.Control.MouseDown> y <xref:System.Windows.Forms.Control.MouseUp>, tienen el mismo tipo de objeto para el segundo parámetro. Para estos tipos de eventos, puede usar el mismo controlador de eventos para controlar ambos eventos.  
  
 También puede usar el mismo controlador de eventos para controlar el mismo evento para los diferentes controles. Por ejemplo, si tiene un grupo de <xref:System.Windows.Forms.RadioButton> controles en un formulario, puede crear un único controlador de eventos para el evento <xref:System.Windows.Forms.Control.Click> y hacer que el evento <xref:System.Windows.Forms.Control.Click> de cada control esté enlazado al controlador de eventos único. Para obtener más información, consulte [Cómo: conectar varios eventos a un solo controlador de eventos en Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).  
  
## <a name="see-also"></a>Consulte también

- [Crear controladores de eventos en Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Información general sobre eventos](events-overview-windows-forms.md)
