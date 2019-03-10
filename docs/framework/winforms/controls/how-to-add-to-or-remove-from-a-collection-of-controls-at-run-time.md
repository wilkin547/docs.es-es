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
ms.openlocfilehash: 6ec4e41f5a3bee6302996f21afa81f2b5eeb9568
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720896"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a><span data-ttu-id="f9116-102">Filtrar Agregar o quitar de una colección de controles en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f9116-102">How to: Add to or Remove from a Collection of Controls at Run Time</span></span>
<span data-ttu-id="f9116-103">Tareas comunes de desarrollo de aplicaciones son agregar controles a y quitar controles de un control contenedor en los formularios (como el <xref:System.Windows.Forms.Panel> o <xref:System.Windows.Forms.GroupBox> control, o incluso el propio formulario).</span><span class="sxs-lookup"><span data-stu-id="f9116-103">Common tasks in application development are adding controls to and removing controls from any container control on your forms (such as the <xref:System.Windows.Forms.Panel> or <xref:System.Windows.Forms.GroupBox> control, or even the form itself).</span></span> <span data-ttu-id="f9116-104">En tiempo de diseño, los controles se pueden arrastrar directamente al panel o grupo de cuadro.</span><span class="sxs-lookup"><span data-stu-id="f9116-104">At design time, controls can be dragged directly onto a panel or group box.</span></span> <span data-ttu-id="f9116-105">En tiempo de ejecución, estos controles mantienen una colección `Controls`, que realiza un seguimiento de los controles que se colocan en ellos.</span><span class="sxs-lookup"><span data-stu-id="f9116-105">At run time, these controls maintain a `Controls` collection, which keeps track of what controls are placed on them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9116-106">El ejemplo de código siguiente se aplica a cualquier control que contenga una colección de controles.</span><span class="sxs-lookup"><span data-stu-id="f9116-106">The following code example applies to any control that maintains a collection of controls within it.</span></span>  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a><span data-ttu-id="f9116-107">Para agregar un control a una colección mediante programación</span><span class="sxs-lookup"><span data-stu-id="f9116-107">To add a control to a collection programmatically</span></span>  
  
1.  <span data-ttu-id="f9116-108">Cree una instancia del control que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="f9116-108">Create an instance of the control to be added.</span></span>  
  
2.  <span data-ttu-id="f9116-109">Defina las propiedades del nuevo control.</span><span class="sxs-lookup"><span data-stu-id="f9116-109">Set properties of the new control.</span></span>  
  
3.  <span data-ttu-id="f9116-110">Agregue el control a la colección `Controls` del control primario.</span><span class="sxs-lookup"><span data-stu-id="f9116-110">Add the control to the `Controls` collection of the parent control.</span></span>  
  
     <span data-ttu-id="f9116-111">En el ejemplo de código siguiente se muestra cómo crear una instancia de la <xref:System.Windows.Forms.Button> control.</span><span class="sxs-lookup"><span data-stu-id="f9116-111">The following code example shows how to create an instance of the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="f9116-112">Requiere un formulario con un <xref:System.Windows.Forms.Panel> control y que se crea el método de control de eventos para el botón, `NewPanelButton_Click`, ya existe.</span><span class="sxs-lookup"><span data-stu-id="f9116-112">It requires a form with a <xref:System.Windows.Forms.Panel> control and that the event-handling method for the button being created, `NewPanelButton_Click`, already exists.</span></span>  
  
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
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a><span data-ttu-id="f9116-113">Para quitar controles de una colección mediante programación</span><span class="sxs-lookup"><span data-stu-id="f9116-113">To remove controls from a collection programmatically</span></span>  
  
1.  <span data-ttu-id="f9116-114">Quite el controlador de eventos del evento.</span><span class="sxs-lookup"><span data-stu-id="f9116-114">Remove the event handler from the event.</span></span> <span data-ttu-id="f9116-115">En Visual Basic, utilice el [RemoveHandler (instrucción)](~/docs/visual-basic/language-reference/statements/removehandler-statement.md) palabra clave; en Visual C#, utilice el [= operador (C# referencia)](~/docs/csharp/language-reference/operators/subtraction-assignment-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f9116-115">In Visual Basic, use the [RemoveHandler Statement](~/docs/visual-basic/language-reference/statements/removehandler-statement.md) keyword; in Visual C#, use the [-= Operator (C# Reference)](~/docs/csharp/language-reference/operators/subtraction-assignment-operator.md).</span></span>  
  
2.  <span data-ttu-id="f9116-116">Utilice el método `Remove` para eliminar el control deseado de la colección `Controls` del panel.</span><span class="sxs-lookup"><span data-stu-id="f9116-116">Use the `Remove` method to delete the desired control from the panel's `Controls` collection.</span></span>  
  
3.  <span data-ttu-id="f9116-117">Llame a la <xref:System.Windows.Forms.Control.Dispose%2A> método para liberar todos los recursos utilizados por el control.</span><span class="sxs-lookup"><span data-stu-id="f9116-117">Call the <xref:System.Windows.Forms.Control.Dispose%2A> method to release all the resources used by the control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f9116-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9116-118">See also</span></span>
- <xref:System.Windows.Forms.Panel>
- [<span data-ttu-id="f9116-119">Panel (control)</span><span class="sxs-lookup"><span data-stu-id="f9116-119">Panel Control</span></span>](panel-control-windows-forms.md)
