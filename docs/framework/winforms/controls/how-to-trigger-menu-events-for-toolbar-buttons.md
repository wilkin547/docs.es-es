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
# <a name="how-to-trigger-menu-events-for-toolbar-buttons"></a><span data-ttu-id="fc902-102">Cómo: Desencadenar eventos de menú para los botones de la barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="fc902-102">How to: Trigger Menu Events for Toolbar Buttons</span></span>
> [!NOTE]
> <span data-ttu-id="fc902-103">El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>; sin embargo, el control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="fc902-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="fc902-104">Si el formulario <xref:System.Windows.Forms.ToolBar> Windows Forms cuenta con un control con botones de barra de herramientas, querrá saber en qué botón hace clic el usuario.</span><span class="sxs-lookup"><span data-stu-id="fc902-104">If your Windows Form features a <xref:System.Windows.Forms.ToolBar> control with toolbar buttons, you will want to know which button the user clicks.</span></span>  
  
 <span data-ttu-id="fc902-105">En <xref:System.Windows.Forms.ToolBar.ButtonClick> el evento <xref:System.Windows.Forms.ToolBar> del control, <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> puede evaluar <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> la propiedad de la clase.</span><span class="sxs-lookup"><span data-stu-id="fc902-105">On the <xref:System.Windows.Forms.ToolBar.ButtonClick> event of the <xref:System.Windows.Forms.ToolBar> control, you can evaluate the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> property of the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> class.</span></span> <span data-ttu-id="fc902-106">En el ejemplo siguiente se muestra un cuadro de mensaje que indica en qué botón se hizo clic.</span><span class="sxs-lookup"><span data-stu-id="fc902-106">In the example below, a message box is shown, indicating which button was clicked.</span></span> <span data-ttu-id="fc902-107">Para obtener información detallada, consulte <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="fc902-107">For details, see <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="fc902-108">En el ejemplo <xref:System.Windows.Forms.ToolBar> siguiente se supone que se ha agregado un control a un formulario Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fc902-108">The example below assumes a <xref:System.Windows.Forms.ToolBar> control has been added to a Windows Form.</span></span>  
  
### <a name="to-handle-the-click-event-on-a-toolbar"></a><span data-ttu-id="fc902-109">Controlar el evento de clic en una barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="fc902-109">To handle the Click event on a toolbar</span></span>  
  
1. <span data-ttu-id="fc902-110">En un procedimiento, agregue <xref:System.Windows.Forms.ToolBar> botones de barra de herramientas al control.</span><span class="sxs-lookup"><span data-stu-id="fc902-110">In a procedure, add toolbar buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
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
  
2. <span data-ttu-id="fc902-111">Agregue un controlador <xref:System.Windows.Forms.ToolBar> de eventos <xref:System.Windows.Forms.ToolBar.ButtonClick> para el evento del control.</span><span class="sxs-lookup"><span data-stu-id="fc902-111">Add an event handler for the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ButtonClick> event.</span></span> <span data-ttu-id="fc902-112">Utilice una instrucción de <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> cambio de mayúsculas y minúsculas y la clase para determinar el botón de barra de herramientas en el que se hizo clic.</span><span class="sxs-lookup"><span data-stu-id="fc902-112">Use a case switching statement and the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> class to determine the toolbar button that was clicked.</span></span> <span data-ttu-id="fc902-113">En función de esto, muestre un cuadro de mensaje adecuado.</span><span class="sxs-lookup"><span data-stu-id="fc902-113">Based on this, show an appropriate message box.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="fc902-114">Un cuadro de mensaje solo se usa como marcador de posición en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fc902-114">A message box is being used solely as a placeholder in this example.</span></span> <span data-ttu-id="fc902-115">Puede agregar código que se ejecutará cuando se haga clic en los botones de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="fc902-115">Feel free to add other code to execute when the toolbar buttons are clicked.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fc902-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fc902-116">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="fc902-117">Agregar botones a un control ToolBar</span><span class="sxs-lookup"><span data-stu-id="fc902-117">How to: Add Buttons to a ToolBar Control</span></span>](how-to-add-buttons-to-a-toolbar-control.md)
- [<span data-ttu-id="fc902-118">Definir un icono para un botón ToolBar</span><span class="sxs-lookup"><span data-stu-id="fc902-118">How to: Define an Icon for a ToolBar Button</span></span>](how-to-define-an-icon-for-a-toolbar-button.md)
- [<span data-ttu-id="fc902-119">Barra de herramientas (Control)</span><span class="sxs-lookup"><span data-stu-id="fc902-119">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
