---
title: 'Cómo: Desencadenar eventos de menú para los botones de la barra de herramientas'
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
ms.openlocfilehash: 99db077b41a59fe9263f7283b58b8c31959c7c79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182077"
---
# <a name="how-to-trigger-menu-events-for-toolbar-buttons"></a>Cómo: Desencadenar eventos de menú para los botones de la barra de herramientas
> [!NOTE]
> El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>; sin embargo, el control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.  
  
 Si el formulario <xref:System.Windows.Forms.ToolBar> Windows Forms cuenta con un control con botones de barra de herramientas, querrá saber en qué botón hace clic el usuario.  
  
 En <xref:System.Windows.Forms.ToolBar.ButtonClick> el evento <xref:System.Windows.Forms.ToolBar> del control, <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> puede evaluar <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> la propiedad de la clase. En el ejemplo siguiente se muestra un cuadro de mensaje que indica en qué botón se hizo clic. Para obtener información detallada, consulte <xref:System.Windows.Forms.MessageBox>.  
  
 En el ejemplo <xref:System.Windows.Forms.ToolBar> siguiente se supone que se ha agregado un control a un formulario Windows Forms.  
  
### <a name="to-handle-the-click-event-on-a-toolbar"></a>Controlar el evento de clic en una barra de herramientas  
  
1. En un procedimiento, agregue <xref:System.Windows.Forms.ToolBar> botones de barra de herramientas al control.  
  
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
  
2. Agregue un controlador <xref:System.Windows.Forms.ToolBar> de eventos <xref:System.Windows.Forms.ToolBar.ButtonClick> para el evento del control. Utilice una instrucción de <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> cambio de mayúsculas y minúsculas y la clase para determinar el botón de barra de herramientas en el que se hizo clic. En función de esto, muestre un cuadro de mensaje adecuado.  
  
    > [!NOTE]
    > Un cuadro de mensaje solo se usa como marcador de posición en este ejemplo. Puede agregar código que se ejecutará cuando se haga clic en los botones de la barra de herramientas.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ToolBar>
- [Agregar botones a un control ToolBar](how-to-add-buttons-to-a-toolbar-control.md)
- [Definir un icono para un botón ToolBar](how-to-define-an-icon-for-a-toolbar-button.md)
- [Barra de herramientas (Control)](toolbar-control-windows-forms.md)
