---
title: Procedimiento para desencadenar eventos de menú para los botones de la barra de herramientas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], click event handlers
- ToolBar control [Windows Forms], coding button click events
- toolbars [Windows Forms], click event handlers
ms.assetid: 98374f70-993d-4ca4-89fb-48fea6ce5b45
ms.openlocfilehash: 0f5afde1cc0be772baff373c84c82f81df284b9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785832"
---
# <a name="how-to-trigger-menu-events-for-toolbar-buttons"></a>Procedimiento para desencadenar eventos de menú para los botones de la barra de herramientas
> [!NOTE]
>  El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>; sin embargo, el control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.  
  
 Si las características de Windows forma un <xref:System.Windows.Forms.ToolBar> control con los botones de barra de herramientas, le interesará saber en qué botón hace clic el usuario.  
  
 En el <xref:System.Windows.Forms.ToolBar.ButtonClick> eventos de la <xref:System.Windows.Forms.ToolBar> control, puede evaluar la <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> propiedad de la <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> clase. En el ejemplo siguiente se muestra un cuadro de mensaje que indica en qué botón se hizo clic. Para obtener información detallada, vea <xref:System.Windows.Forms.MessageBox>.  
  
 El ejemplo siguiente se da por supuesto un <xref:System.Windows.Forms.ToolBar> control se ha agregado a un formulario de Windows.  
  
### <a name="to-handle-the-click-event-on-a-toolbar"></a>Controlar el evento de clic en una barra de herramientas  
  
1. En un procedimiento, agregue botones de barra de herramientas para el <xref:System.Windows.Forms.ToolBar> control.  
  
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
  
2. Agregar un controlador de eventos para el <xref:System.Windows.Forms.ToolBar> del control <xref:System.Windows.Forms.ToolBar.ButtonClick> eventos. Un instrucción de conmutación de caso de uso y la <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> clase para determinar el botón de barra de herramientas que se hizo clic. En función de esto, muestre un cuadro de mensaje adecuado.  
  
    > [!NOTE]
    >  Un cuadro de mensaje solo se usa como marcador de posición en este ejemplo. Puede agregar código que se ejecutará cuando se haga clic en los botones de la barra de herramientas.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolBar>
- [Cómo: Agregar botones a un Control de barra de herramientas](how-to-add-buttons-to-a-toolbar-control.md)
- [Cómo: Definir un icono para un botón de barra de herramientas](how-to-define-an-icon-for-a-toolbar-button.md)
- [ToolBar (control)](toolbar-control-windows-forms.md)
