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
ms.openlocfilehash: 381b8ba08db6ff5bb817c9c89008dacb1085ac1b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956035"
---
# <a name="how-to-trigger-menu-events-for-toolbar-buttons"></a><span data-ttu-id="923fd-102">Procedimiento para desencadenar eventos de menú para los botones de la barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="923fd-102">How to: Trigger Menu Events for Toolbar Buttons</span></span>
> [!NOTE]
> <span data-ttu-id="923fd-103">El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>; sin embargo, el control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="923fd-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="923fd-104">Si Windows Forms incluye un <xref:System.Windows.Forms.ToolBar> control con botones de barra de herramientas, querrá saber en qué botón hace clic el usuario.</span><span class="sxs-lookup"><span data-stu-id="923fd-104">If your Windows Form features a <xref:System.Windows.Forms.ToolBar> control with toolbar buttons, you will want to know which button the user clicks.</span></span>  
  
 <span data-ttu-id="923fd-105">En el <xref:System.Windows.Forms.ToolBar.ButtonClick> <xref:System.Windows.Forms.ToolBar> caso del control, puede evaluar la <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> propiedad de la <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> clase.</span><span class="sxs-lookup"><span data-stu-id="923fd-105">On the <xref:System.Windows.Forms.ToolBar.ButtonClick> event of the <xref:System.Windows.Forms.ToolBar> control, you can evaluate the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> property of the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> class.</span></span> <span data-ttu-id="923fd-106">En el ejemplo siguiente se muestra un cuadro de mensaje que indica en qué botón se hizo clic.</span><span class="sxs-lookup"><span data-stu-id="923fd-106">In the example below, a message box is shown, indicating which button was clicked.</span></span> <span data-ttu-id="923fd-107">Para obtener información detallada, vea <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="923fd-107">For details, see <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="923fd-108">En el ejemplo siguiente se <xref:System.Windows.Forms.ToolBar> supone que se ha agregado un control a un formulario de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="923fd-108">The example below assumes a <xref:System.Windows.Forms.ToolBar> control has been added to a Windows Form.</span></span>  
  
### <a name="to-handle-the-click-event-on-a-toolbar"></a><span data-ttu-id="923fd-109">Controlar el evento de clic en una barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="923fd-109">To handle the Click event on a toolbar</span></span>  
  
1. <span data-ttu-id="923fd-110">En un procedimiento, agregue botones de barra de <xref:System.Windows.Forms.ToolBar> herramientas al control.</span><span class="sxs-lookup"><span data-stu-id="923fd-110">In a procedure, add toolbar buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
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
  
2. <span data-ttu-id="923fd-111">Agregue un controlador de eventos para <xref:System.Windows.Forms.ToolBar> el evento <xref:System.Windows.Forms.ToolBar.ButtonClick> del control.</span><span class="sxs-lookup"><span data-stu-id="923fd-111">Add an event handler for the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ButtonClick> event.</span></span> <span data-ttu-id="923fd-112">Use una instrucción de cambio de mayúsculas y minúsculas y la <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> clase para determinar el botón de la barra de herramientas en el que se hizo clic.</span><span class="sxs-lookup"><span data-stu-id="923fd-112">Use a case switching statement and the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> class to determine the toolbar button that was clicked.</span></span> <span data-ttu-id="923fd-113">En función de esto, muestre un cuadro de mensaje adecuado.</span><span class="sxs-lookup"><span data-stu-id="923fd-113">Based on this, show an appropriate message box.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="923fd-114">Un cuadro de mensaje solo se usa como marcador de posición en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="923fd-114">A message box is being used solely as a placeholder in this example.</span></span> <span data-ttu-id="923fd-115">Puede agregar código que se ejecutará cuando se haga clic en los botones de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="923fd-115">Feel free to add other code to execute when the toolbar buttons are clicked.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="923fd-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="923fd-116">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="923fd-117">Cómo: Agregar botones a un control ToolBar</span><span class="sxs-lookup"><span data-stu-id="923fd-117">How to: Add Buttons to a ToolBar Control</span></span>](how-to-add-buttons-to-a-toolbar-control.md)
- [<span data-ttu-id="923fd-118">Procedimientos: Definir un icono para un botón de la barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="923fd-118">How to: Define an Icon for a ToolBar Button</span></span>](how-to-define-an-icon-for-a-toolbar-button.md)
- [<span data-ttu-id="923fd-119">ToolBar (control)</span><span class="sxs-lookup"><span data-stu-id="923fd-119">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
