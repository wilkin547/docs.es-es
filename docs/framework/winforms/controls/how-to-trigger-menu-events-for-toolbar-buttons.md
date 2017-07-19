---
title: "C&#243;mo: Desencadenar eventos de men&#250; para los botones de la barra de herramientas | Microsoft Docs"
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
  - "ejemplos [Windows Forms], barras de herramientas"
  - "ToolBar (control) [Windows Forms], controladores de los eventos Click"
  - "ToolBar (control) [Windows Forms], codificar los eventos Click de los botones"
  - "barras de herramientas [Windows Forms], controladores de los eventos Click"
ms.assetid: 98374f70-993d-4ca4-89fb-48fea6ce5b45
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Desencadenar eventos de men&#250; para los botones de la barra de herramientas
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>, este control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  
  
 Si Windows Form presenta controles <xref:System.Windows.Forms.ToolBar> con botones de la barra de herramientas, deseará saber en qué botón ha hecho clic el usuario.  
  
 En el evento <xref:System.Windows.Forms.ToolBar.ButtonClick> del control <xref:System.Windows.Forms.ToolBar>, puede evaluar la propiedad <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> de la clase <xref:System.Windows.Forms.ToolBarButtonClickEventArgs>.  En el ejemplo siguiente, se muestra un cuadro de mensajes, que indica en qué botón se ha hecho clic.  Para obtener información más detallada, vea [MessageBox \(Clase\)](frlrfSystemWindowsFormsMessageBoxClassTopic).  
  
 En el ejemplo siguiente se supone que se ha agregado un control <xref:System.Windows.Forms.ToolBar> a un Windows Form.  
  
### Para administrar el evento Click en la barra de herramientas  
  
1.  En un procedimiento, agregue botones de la barra de herramientas al control <xref:System.Windows.Forms.ToolBar>.  
  
    ```vb  
    Public Sub ToolBarConfig()  
    ' Instantiate the toolbar buttons, set their Text properties  
    ' and add them to the ToolBar control.  
       ToolBar1.Buttons.Add(New ToolBarButton("One"))  
       ToolBar1.Buttons.Add(New ToolBarButton("Two"))  
       ToolBar1.Buttons.Add(New ToolBarButton("Three"))  
    ' Add the event handler delegate.  
       AddHandler ToolBar1.ButtonClick, AddressOf Me.ToolBar1_ButtonClick  
    End Sub  
  
    ```  
  
    ```csharp  
    public void ToolBarConfig()   
    {  
       toolBar1.Buttons.Add(new ToolBarButton("One"));  
       toolBar1.Buttons.Add(new ToolBarButton("Two"));  
       toolBar1.Buttons.Add(new ToolBarButton("Three"));  
  
       toolBar1.ButtonClick +=   
          new ToolBarButtonClickEventHandler(this.toolBar1_ButtonClick);  
    }  
  
    ```  
  
    ```cpp  
    public:  
       void ToolBarConfig()  
       {  
          toolBar1->Buttons->Add(gcnew ToolBarButton("One"));  
          toolBar1->Buttons->Add(gcnew ToolBarButton("Two"));  
          toolBar1->Buttons->Add(gcnew ToolBarButton("Three"));  
  
          toolBar1->ButtonClick +=   
             gcnew ToolBarButtonClickEventHandler(this,  
             &Form1::toolBar1_ButtonClick);  
       }  
    ```  
  
2.  Agregue un controlador de eventos para el evento <xref:System.Windows.Forms.ToolBar.ButtonClick> del control <xref:System.Windows.Forms.ToolBar>.  Utilice una instrucción de cambio de mayúsculas y minúsculas, y la clase <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> para determinar en qué botón de la barra de herramientas se ha hecho clic.  Basándose en esto, muestre el cuadro de mensajes adecuado.  
  
    > [!NOTE]
    >  El cuadro de mensajes de este ejemplo sólo se utiliza como un marcador de posición.  Agregue el código que desee que se ejecute cuando se haga clic en los botones de la barra de herramientas.  
  
    ```vb  
    Protected Sub ToolBar1_ButtonClick(ByVal sender As Object, _  
    ByVal e As ToolBarButtonClickEventArgs)  
    ' Evaluate the Button property of the ToolBarButtonClickEventArgs  
    ' to determine which button was clicked.  
       Select Case ToolBar1.Buttons.IndexOf(e.Button)  
         Case 0  
           MessageBox.Show("First toolbar button clicked")  
         Case 1  
           MessageBox.Show("Second toolbar button clicked")  
         Case 2  
           MessageBox.Show("Third toolbar button clicked")  
       End Select  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void toolBar1_ButtonClick(object sender,  
    ToolBarButtonClickEventArgs e)  
    {  
       // Evaluate the Button property of the ToolBarButtonClickEventArgs  
       // to determine which button was clicked.  
       switch (toolBar1.Buttons.IndexOf(e.Button))  
       {  
          case 0 :  
             MessageBox.Show("First toolbar button clicked");  
             break;  
          case 1 :  
             MessageBox.Show("Second toolbar button clicked");  
             break;  
          case 2 :  
             MessageBox.Show("Third toolbar button clicked");  
             break;  
       }  
    }  
  
    ```  
  
    ```cpp  
    protected:  
       void toolBar1_ButtonClick(System::Object ^ sender,  
          ToolBarButtonClickEventArgs ^ e)  
       {  
         // Evaluate the Button property of the ToolBarButtonClickEventArgs  
         // to determine which button was clicked.  
          switch (toolBar1->Buttons->IndexOf(e->Button))  
          {  
             case 0 :  
                MessageBox::Show("First toolbar button clicked");  
                break;  
             case 1 :  
                MessageBox::Show("Second toolbar button clicked");  
                break;  
             case 2 :  
                MessageBox::Show("Third toolbar button clicked");  
                break;  
          }  
       }  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.ToolBar>   
 [Cómo: Agregar botones a un control ToolBar](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)   
 [Cómo: Definir un icono para un botón ToolBar](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)   
 [Barra de herramientas \(Control\)](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)