---
title: Procedimiento Agregar o quitar de una colección de controles en tiempo de ejecución
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
ms.openlocfilehash: 88a743cc6d0a1e90d2912c9ec610fae326ff5770
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744913"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a>Procedimiento Agregar o quitar de una colección de controles en tiempo de ejecución
Tareas comunes de desarrollo de aplicaciones son agregar controles a y quitar controles de un control contenedor en los formularios (como el <xref:System.Windows.Forms.Panel> o <xref:System.Windows.Forms.GroupBox> control, o incluso el propio formulario). En tiempo de diseño, los controles se pueden arrastrar directamente al panel o grupo de cuadro. En tiempo de ejecución, estos controles mantienen una colección `Controls`, que realiza un seguimiento de los controles que se colocan en ellos.  
  
> [!NOTE]
>  El ejemplo de código siguiente se aplica a cualquier control que contenga una colección de controles.  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a>Para agregar un control a una colección mediante programación  
  
1.  Cree una instancia del control que se va a agregar.  
  
2.  Defina las propiedades del nuevo control.  
  
3.  Agregue el control a la colección `Controls` del control primario.  
  
     En el ejemplo de código siguiente se muestra cómo crear una instancia de la <xref:System.Windows.Forms.Button> control. Requiere un formulario con un <xref:System.Windows.Forms.Panel> control y que se crea el método de control de eventos para el botón, `NewPanelButton_Click`, ya existe.  
  
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
  
1.  Quite el controlador de eventos del evento. En Visual Basic, utilice el [RemoveHandler (instrucción)](~/docs/visual-basic/language-reference/statements/removehandler-statement.md) palabra clave; en Visual C#, utilice el [= operador (C# referencia)](~/docs/csharp/language-reference/operators/subtraction-assignment-operator.md).  
  
2.  Utilice el método `Remove` para eliminar el control deseado de la colección `Controls` del panel.  
  
3.  Llame a la <xref:System.Windows.Forms.Control.Dispose%2A> método para liberar todos los recursos utilizados por el control.  
  
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
- [Panel (control)](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)
