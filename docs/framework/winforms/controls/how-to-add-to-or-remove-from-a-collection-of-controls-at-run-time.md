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
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a><span data-ttu-id="98376-103">Procedimiento para agregar o quitar controles de una colección en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="98376-103">How to: Add to or Remove from a Collection of Controls at Run Time</span></span>
<span data-ttu-id="98376-104">Las tareas comunes en el desarrollo de aplicaciones son la adición de controles y la eliminación de controles de cualquier control contenedor de los formularios (como el <xref:System.Windows.Forms.Panel> <xref:System.Windows.Forms.GroupBox> control o, o incluso el propio formulario).</span><span class="sxs-lookup"><span data-stu-id="98376-104">Common tasks in application development are adding controls to and removing controls from any container control on your forms (such as the <xref:System.Windows.Forms.Panel> or <xref:System.Windows.Forms.GroupBox> control, or even the form itself).</span></span> <span data-ttu-id="98376-105">En tiempo de diseño, los controles se pueden arrastrar directamente al panel o grupo de cuadro.</span><span class="sxs-lookup"><span data-stu-id="98376-105">At design time, controls can be dragged directly onto a panel or group box.</span></span> <span data-ttu-id="98376-106">En tiempo de ejecución, estos controles mantienen una colección `Controls`, que realiza un seguimiento de los controles que se colocan en ellos.</span><span class="sxs-lookup"><span data-stu-id="98376-106">At run time, these controls maintain a `Controls` collection, which keeps track of what controls are placed on them.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98376-107">El ejemplo de código siguiente se aplica a cualquier control que contenga una colección de controles.</span><span class="sxs-lookup"><span data-stu-id="98376-107">The following code example applies to any control that maintains a collection of controls within it.</span></span>  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a><span data-ttu-id="98376-108">Para agregar un control a una colección mediante programación</span><span class="sxs-lookup"><span data-stu-id="98376-108">To add a control to a collection programmatically</span></span>  
  
1. <span data-ttu-id="98376-109">Cree una instancia del control que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="98376-109">Create an instance of the control to be added.</span></span>  
  
2. <span data-ttu-id="98376-110">Defina las propiedades del nuevo control.</span><span class="sxs-lookup"><span data-stu-id="98376-110">Set properties of the new control.</span></span>  
  
3. <span data-ttu-id="98376-111">Agregue el control a la colección `Controls` del control primario.</span><span class="sxs-lookup"><span data-stu-id="98376-111">Add the control to the `Controls` collection of the parent control.</span></span>  
  
     <span data-ttu-id="98376-112">En el ejemplo de código siguiente se muestra cómo crear una instancia del <xref:System.Windows.Forms.Button> control.</span><span class="sxs-lookup"><span data-stu-id="98376-112">The following code example shows how to create an instance of the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="98376-113">Requiere un formulario con un <xref:System.Windows.Forms.Panel> control y que ya existe el método de control de eventos para el botón que se va a crear `NewPanelButton_Click` .</span><span class="sxs-lookup"><span data-stu-id="98376-113">It requires a form with a <xref:System.Windows.Forms.Panel> control and that the event-handling method for the button being created, `NewPanelButton_Click`, already exists.</span></span>  
  
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
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a><span data-ttu-id="98376-114">Para quitar controles de una colección mediante programación</span><span class="sxs-lookup"><span data-stu-id="98376-114">To remove controls from a collection programmatically</span></span>  
  
1. <span data-ttu-id="98376-115">Quite el controlador de eventos del evento.</span><span class="sxs-lookup"><span data-stu-id="98376-115">Remove the event handler from the event.</span></span> <span data-ttu-id="98376-116">En Visual Basic, use la palabra clave de la [instrucción RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md) ; en C#, use el [operador-=](../../../csharp/language-reference/operators/subtraction-operator.md).</span><span class="sxs-lookup"><span data-stu-id="98376-116">In Visual Basic, use the [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) keyword; in C#, use the [-= operator](../../../csharp/language-reference/operators/subtraction-operator.md).</span></span>  
  
2. <span data-ttu-id="98376-117">Utilice el método `Remove` para eliminar el control deseado de la colección `Controls` del panel.</span><span class="sxs-lookup"><span data-stu-id="98376-117">Use the `Remove` method to delete the desired control from the panel's `Controls` collection.</span></span>  
  
3. <span data-ttu-id="98376-118">Llame al <xref:System.Windows.Forms.Control.Dispose%2A> método para liberar todos los recursos utilizados por el control.</span><span class="sxs-lookup"><span data-stu-id="98376-118">Call the <xref:System.Windows.Forms.Control.Dispose%2A> method to release all the resources used by the control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="98376-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="98376-119">See also</span></span>

- <xref:System.Windows.Forms.Panel>
- [<span data-ttu-id="98376-120">Control Panel</span><span class="sxs-lookup"><span data-stu-id="98376-120">Panel Control</span></span>](panel-control-windows-forms.md)
