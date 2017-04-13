---
title: "C&#243;mo: Agregar o quitar controles de una colecci&#243;n en tiempo de ejecuci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "colecciones, agregar elementos"
  - "controles [Windows Forms], agregar mediante colecciones"
  - "controles [Windows Forms], quitar mediante colecciones"
  - "colecciones de controles"
  - "tiempo de ejecución, agregar controles"
  - "tiempo de ejecución, quitar controles"
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Agregar o quitar controles de una colecci&#243;n en tiempo de ejecuci&#243;n
Las tareas comunes de desarrollo de una aplicación son la inclusión y eliminación de controles de un control de contenedores en formularios \(como el control <xref:System.Windows.Forms.Panel> o <xref:System.Windows.Forms.GroupBox> o incluso el mismo formulario\).  En tiempo de diseño, los controles se pueden arrastrar directamente al panel o cuadro de grupo.  En tiempo de ejecución, estos controles mantienen una colección `Controls`, que realiza el seguimiento de los controles que se colocan en ellos.  
  
> [!NOTE]
>  Tenga en cuenta que el ejemplo siguiente se aplica a cualquier control que contenga una colección de controles.  
  
### Para agregar un control a una colección mediante programación  
  
1.  Cree una instancia del control que se va a agregar.  
  
2.  Defina las propiedades del nuevo control.  
  
3.  Agregue el control a la colección `Controls` del control primario.  
  
     El ejemplo siguiente muestra cómo crear una instancia del control <xref:System.Windows.Forms.Button>.  Requiere que haya un control <xref:System.Windows.Forms.Panel> en un formulario y que ya existe el método de control de eventos para el botón que se va a crear, `NewPanelButton_Click`.  
  
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
       // below is used as an example. Substite the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### Para quitar controles de una colección mediante programación  
  
1.  Quite el controlador de eventos del evento.  En [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], utilice la palabra clave [RemoveHandler \(Instrucción\)](../../../../ocs/visual-basic/language-reference/statements/removehandler-statement.md), en [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] utilice [\-\= \(Operador\)](../Topic/-=%20Operator%20\(C%23%20Reference\)2.md).  
  
2.  Utilice el método `Remove` para eliminar el control deseado de la colección `Controls` del panel.  
  
3.  Llame al método <xref:System.Windows.Forms.Control.Dispose%2A> para liberar todos los recursos utilizados por el control.  
  
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
  
## Vea también  
 <xref:System.Windows.Forms.Panel>   
 [Control Panel](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)