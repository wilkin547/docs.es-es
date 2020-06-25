---
title: Procedimiento para agregar o quitar controles de una colección en tiempo de ejecución
description: Obtenga información sobre cómo agregar y quitar controles de cualquier control contenedor de los formularios, como el control panel o GroupBox, o incluso el propio formulario.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- run time [Windows Forms], removing controls
- controls [Windows Forms], adding using collections
- controls collections
- collections [Windows Forms], adding items
- run time [Windows Forms], adding controls
- controls [Windows Forms], removing using collections
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
ms.openlocfilehash: 6c3f2d1f42b130de4d808871265b50510cfb8f47
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325876"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a>Procedimiento para agregar o quitar controles de una colección en tiempo de ejecución
Las tareas comunes en el desarrollo de aplicaciones son la adición de controles y la eliminación de controles de cualquier control contenedor de los formularios (como el <xref:System.Windows.Forms.Panel> <xref:System.Windows.Forms.GroupBox> control o, o incluso el propio formulario). En tiempo de diseño, los controles se pueden arrastrar directamente al panel o grupo de cuadro. En tiempo de ejecución, estos controles mantienen una colección `Controls`, que realiza un seguimiento de los controles que se colocan en ellos.  
  
> [!NOTE]
> El ejemplo de código siguiente se aplica a cualquier control que contenga una colección de controles.  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a>Para agregar un control a una colección mediante programación  
  
1. Cree una instancia del control que se va a agregar.  
  
2. Defina las propiedades del nuevo control.  
  
3. Agregue el control a la colección `Controls` del control primario.  
  
     En el ejemplo de código siguiente se muestra cómo crear una instancia del <xref:System.Windows.Forms.Button> control. Requiere un formulario con un <xref:System.Windows.Forms.Panel> control y que ya existe el método de control de eventos para el botón que se va a crear `NewPanelButton_Click` .  
  
    ```vb  
    Public NewPanelButton As New Button()  
  
    Public Sub AddNewControl()  
       ' The Add method will accept as a parameter any object that derives  
       ' from the Control class. In this case, it is a Button control.  
       Panel1.Controls.Add(NewPanelButton)  
       ' The event handler indicated for the Click event in the code
       ' below is used as an example. Substite the appropriate event  
       ' handler for your application.  
       AddHandler NewPanelButton.Click, AddressOf NewPanelButton_Click  
    End Sub  
    ```  
  
    ```csharp  
    public Button newPanelButton = new Button();  
  
    public void addNewControl()  
    {
       // The Add method will accept as a parameter any object that derives  
       // from the Control class. In this case, it is a Button control.  
       panel1.Controls.Add(newPanelButton);  
       // The event handler indicated for the Click event in the code
       // below is used as an example. Substitute the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a>Para quitar controles de una colección mediante programación  
  
1. Quite el controlador de eventos del evento. En Visual Basic, use la palabra clave de la [instrucción RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md) ; en C#, use el [operador-=](../../../csharp/language-reference/operators/subtraction-operator.md).  
  
2. Utilice el método `Remove` para eliminar el control deseado de la colección `Controls` del panel.  
  
3. Llame al <xref:System.Windows.Forms.Control.Dispose%2A> método para liberar todos los recursos utilizados por el control.  
  
    ```vb  
    Public Sub RemoveControl()  
    ' NOTE: The code below uses the instance of
    ' the button (NewPanelButton) from the previous example.  
       If Panel1.Controls.Contains(NewPanelButton) Then  
          RemoveHandler NewPanelButton.Click, AddressOf _
             NewPanelButton_Click  
          Panel1.Controls.Remove(NewPanelButton)  
          NewPanelButton.Dispose()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void removeControl(object sender, System.EventArgs e)  
    {  
    // NOTE: The code below uses the instance of
    // the button (newPanelButton) from the previous example.  
       if(panel1.Controls.Contains(newPanelButton))  
       {  
          this.newPanelButton.Click -= new System.EventHandler(this.
             NewPanelButton_Click);  
          panel1.Controls.Remove(newPanelButton);  
          newPanelButton.Dispose();  
       }  
    }  
    ```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Panel>
- [Control Panel](panel-control-windows-forms.md)
