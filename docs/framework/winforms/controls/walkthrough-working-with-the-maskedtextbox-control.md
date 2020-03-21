---
title: 'Tutorial: Trabajar con el control MaskedTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: db32b3ec88a07747ea3e286af9f04edce3f1ba3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182050"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a><span data-ttu-id="b7490-102">Tutorial: Trabajar con el control MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="b7490-102">Walkthrough: Working with the MaskedTextBox Control</span></span>
<span data-ttu-id="b7490-103">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="b7490-103">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="b7490-104">Inicialización <xref:System.Windows.Forms.MaskedTextBox> del control</span><span class="sxs-lookup"><span data-stu-id="b7490-104">Initializing the <xref:System.Windows.Forms.MaskedTextBox> control</span></span>  
  
- <span data-ttu-id="b7490-105">Uso <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> del controlador de eventos para alertar al usuario cuando un carácter no se ajusta a la máscara</span><span class="sxs-lookup"><span data-stu-id="b7490-105">Using the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event handler to alert the user when a character does not conform to the mask</span></span>  
  
- <span data-ttu-id="b7490-106">Asignar un tipo <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> a la <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> propiedad y usar el controlador de eventos para alertar al usuario cuando el valor que intentan confirmar no es válido para el tipo</span><span class="sxs-lookup"><span data-stu-id="b7490-106">Assigning a type to the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property and using the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event handler to alert the user when the value they're attempting to commit is not valid for the type</span></span>  
  
## <a name="creating-the-project-and-adding-a-control"></a><span data-ttu-id="b7490-107">Creación del proyecto y adición de un control</span><span class="sxs-lookup"><span data-stu-id="b7490-107">Creating the Project and Adding a Control</span></span>  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a><span data-ttu-id="b7490-108">Para agregar un control MaskedTextBox al formulario</span><span class="sxs-lookup"><span data-stu-id="b7490-108">To add a MaskedTextBox control to your form</span></span>  
  
1. <span data-ttu-id="b7490-109">Abra el formulario en el <xref:System.Windows.Forms.MaskedTextBox> que desea colocar el control.</span><span class="sxs-lookup"><span data-stu-id="b7490-109">Open the form on which you want to place the <xref:System.Windows.Forms.MaskedTextBox> control.</span></span>  
  
2. <span data-ttu-id="b7490-110">Arrastre <xref:System.Windows.Forms.MaskedTextBox> un control desde el **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="b7490-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control from the **Toolbox** to your form.</span></span>  
  
3. <span data-ttu-id="b7490-111">Haga clic con el botón derecho en el control y elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b7490-111">Right-click the control and choose **Properties**.</span></span> <span data-ttu-id="b7490-112">En la ventana **Propiedades,** seleccione la propiedad **Máscara** y haga clic en el botón **...** (ellipsis) situado junto al nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7490-112">In the **Properties** window, select the **Mask** property and click the **...** (ellipsis) button next to the property name.</span></span>  
  
4. <span data-ttu-id="b7490-113">En el cuadro de diálogo Máscara de **entrada,** seleccione la máscara **Fecha corta** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b7490-113">In the **Input Mask** dialog box, select the **Short Date** mask and click **OK**.</span></span>  
  
5. <span data-ttu-id="b7490-114">En la ventana <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> **Propiedades,** establezca la propiedad en . `true`</span><span class="sxs-lookup"><span data-stu-id="b7490-114">In the **Properties** window set the <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> property to `true`.</span></span> <span data-ttu-id="b7490-115">Esta propiedad hace que un pitido corto suene cada vez que el usuario intenta introducir un carácter que infringe la definición de máscara.</span><span class="sxs-lookup"><span data-stu-id="b7490-115">This property causes a short beep to sound every time the user attempts to input a character that violates the mask definition.</span></span>  
  
 <span data-ttu-id="b7490-116">Para obtener un resumen de los caracteres que admite <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> la propiedad Mask, vea la sección Comentarios de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7490-116">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
## <a name="alert-the-user-to-input-errors"></a><span data-ttu-id="b7490-117">Alertar al usuario de los errores de entrada</span><span class="sxs-lookup"><span data-stu-id="b7490-117">Alert the User to Input Errors</span></span>  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a><span data-ttu-id="b7490-118">Agregue una punta de globo para la entrada de máscara rechazada</span><span class="sxs-lookup"><span data-stu-id="b7490-118">Add a balloon tip for rejected mask input</span></span>  
  
1. <span data-ttu-id="b7490-119">Vuelva al cuadro de <xref:System.Windows.Forms.ToolTip> **herramientas** y agregue un al formulario.</span><span class="sxs-lookup"><span data-stu-id="b7490-119">Return to the **Toolbox** and add a <xref:System.Windows.Forms.ToolTip> to your form.</span></span>  
  
2. <span data-ttu-id="b7490-120">Cree un controlador <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> de eventos para <xref:System.Windows.Forms.ToolTip> el evento que provoca el momento en que se produce un error de entrada.</span><span class="sxs-lookup"><span data-stu-id="b7490-120">Create an event handler for the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event that raises the <xref:System.Windows.Forms.ToolTip> when an input error occurs.</span></span> <span data-ttu-id="b7490-121">La punta del globo permanece visible durante cinco segundos o hasta que el usuario hace clic en ella.</span><span class="sxs-lookup"><span data-stu-id="b7490-121">The balloon tip remains visible for five seconds, or until the user clicks it.</span></span>  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a><span data-ttu-id="b7490-122">Alertar al usuario de un tipo que no es válido</span><span class="sxs-lookup"><span data-stu-id="b7490-122">Alert the User to a Type that Is Not Valid</span></span>  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a><span data-ttu-id="b7490-123">Agregue una sugerencia de globo para tipos de datos no válidos</span><span class="sxs-lookup"><span data-stu-id="b7490-123">Add a balloon tip for invalid data types</span></span>  
  
1. <span data-ttu-id="b7490-124">En el controlador <xref:System.Windows.Forms.Form.Load> de eventos <xref:System.Type> del formulario, asigne un objeto que represente el <xref:System.DateTime> tipo a la <xref:System.Windows.Forms.MaskedTextBox> propiedad del <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> control:</span><span class="sxs-lookup"><span data-stu-id="b7490-124">In your form's <xref:System.Windows.Forms.Form.Load> event handler, assign a <xref:System.Type> object representing the <xref:System.DateTime> type to the <xref:System.Windows.Forms.MaskedTextBox> control's <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property:</span></span>  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2. <span data-ttu-id="b7490-125">Agregue un controlador de eventos para el evento <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>:</span><span class="sxs-lookup"><span data-stu-id="b7490-125">Add an event handler for the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event:</span></span>  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b7490-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7490-126">See also</span></span>

- <xref:System.Windows.Forms.MaskedTextBox>
- [<span data-ttu-id="b7490-127">Control MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="b7490-127">MaskedTextBox Control</span></span>](maskedtextbox-control-windows-forms.md)
