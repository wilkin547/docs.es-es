---
title: Información general sobre controladores de eventos (Formularios Windows Forms)
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
ms.openlocfilehash: 2970cf0f83339fe86faf4af7da80bb17bd25acfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538162"
---
# <a name="event-handlers-overview-windows-forms"></a>Información general sobre controladores de eventos (Formularios Windows Forms)
Un controlador de eventos es un método que está enlazado a un evento. Cuando se genera el evento, se ejecuta el código en el controlador de eventos. Cada controlador de eventos proporciona dos parámetros que permiten controlar el evento correctamente. En el ejemplo siguiente se muestra un controlador de eventos para un <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Click> eventos.  
  
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
  
 El primer parámetro,`sender`, proporciona una referencia al objeto que provocó el evento. El segundo parámetro, `e`, en el ejemplo anterior, pasa un objeto específico para el evento que se está controlando. Si hace referencia a las propiedades del objeto (y, a veces, a sus métodos), puede obtener información como la ubicación del mouse para los eventos del mouse o datos que se transfieren en los eventos de arrastrar y colocar.  
  
 Normalmente, cada evento produce un controlador de eventos con un tipo de objeto de evento diferente para el segundo parámetro. Algunos controladores de eventos, como los relativos a la <xref:System.Windows.Forms.Control.MouseDown> y <xref:System.Windows.Forms.Control.MouseUp> eventos, tienen el mismo tipo de objeto para el segundo parámetro. Para estos tipos de eventos, puede usar el mismo controlador de eventos para controlar ambos eventos.  
  
 También puede usar el mismo controlador de eventos para controlar el mismo evento para los distintos controles. Por ejemplo, si tiene un grupo de <xref:System.Windows.Forms.RadioButton> controles en un formulario, podría crear un único controlador de eventos para el <xref:System.Windows.Forms.Control.Click> eventos y tener cada control <xref:System.Windows.Forms.Control.Click> eventos enlazados al controlador de eventos único. Para obtener más información, consulte [Cómo: conectar varios eventos a un solo controlador de eventos en formularios Windows Forms](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).  
  
## <a name="see-also"></a>Vea también  
 [Crear controladores de eventos en Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [Información general sobre eventos](../../../docs/framework/winforms/events-overview-windows-forms.md)
