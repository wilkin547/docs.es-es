---
title: para agregar controles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 560089a23fbcccb0f0d5683a95ad06dd9c59556d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743958"
---
# <a name="how-to-add-controls-to-windows-forms"></a><span data-ttu-id="493ab-102">Adición de controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="493ab-102">How to: Add Controls to Windows Forms</span></span>

<span data-ttu-id="493ab-103">La mayoría de los formularios se diseñan agregando controles a la superficie del formulario para definir una interfaz de usuario (UI).</span><span class="sxs-lookup"><span data-stu-id="493ab-103">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="493ab-104">Un *control* es un componente de un formulario que se usa para mostrar información o para aceptar datos proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="493ab-104">A *control* is a component on a form used to display information or accept user input.</span></span> <span data-ttu-id="493ab-105">Para obtener más información sobre los controles, vea [controles de Windows Forms](index.md).</span><span class="sxs-lookup"><span data-stu-id="493ab-105">For more information about controls, see [Windows Forms Controls](index.md).</span></span>

## <a name="to-draw-a-control-on-a-form"></a><span data-ttu-id="493ab-106">Para dibujar un control en un formulario</span><span class="sxs-lookup"><span data-stu-id="493ab-106">To draw a control on a form</span></span>

1. <span data-ttu-id="493ab-107">Abra el formulario.</span><span class="sxs-lookup"><span data-stu-id="493ab-107">Open the form.</span></span> <span data-ttu-id="493ab-108">Para obtener más información, vea [Cómo: mostrar Windows Forms en el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="493ab-108">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="493ab-109">En el **cuadro de herramientas**, haga clic en el control que desee agregar al formulario.</span><span class="sxs-lookup"><span data-stu-id="493ab-109">In the **Toolbox**, click the control you want to add to your form.</span></span>

3. <span data-ttu-id="493ab-110">En el formulario, haga clic en el lugar en el que desea que se encuentre la esquina superior izquierda del control y arrastre hasta donde desee que se encuentre la esquina inferior derecha del control.</span><span class="sxs-lookup"><span data-stu-id="493ab-110">On the form, click where you want the upper-left corner of the control to be located, and drag to where you want the lower-right corner of the control to be located.</span></span>

    <span data-ttu-id="493ab-111">El control se agrega al formulario con la ubicación y el tamaño especificados.</span><span class="sxs-lookup"><span data-stu-id="493ab-111">The control is added to the form with the specified location and size.</span></span>

    > [!NOTE]
    > <span data-ttu-id="493ab-112">Cada control tiene definido un tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="493ab-112">Each control has a default size defined.</span></span> <span data-ttu-id="493ab-113">Puede Agregar un control al formulario en el tamaño predeterminado del control arrastrándolo desde el **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="493ab-113">You can add a control to your form in the control's default size by dragging it from the **Toolbox** to the form.</span></span>

## <a name="to-drag-a-control-to-a-form"></a><span data-ttu-id="493ab-114">Para arrastrar un control a un formulario</span><span class="sxs-lookup"><span data-stu-id="493ab-114">To drag a control to a form</span></span>

1. <span data-ttu-id="493ab-115">Abra el formulario.</span><span class="sxs-lookup"><span data-stu-id="493ab-115">Open the form.</span></span> <span data-ttu-id="493ab-116">Para obtener más información, vea [Cómo: mostrar Windows Forms en el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="493ab-116">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="493ab-117">En el **cuadro de herramientas**, haga clic en el control que desee y arrástrelo al formulario.</span><span class="sxs-lookup"><span data-stu-id="493ab-117">In the **Toolbox**, click the control you want and drag it to your form.</span></span>

    <span data-ttu-id="493ab-118">El control se agrega al formulario en la ubicación especificada en su tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="493ab-118">The control is added to the form at the specified location in its default size.</span></span>

    > [!NOTE]
    > <span data-ttu-id="493ab-119">Puede hacer doble clic en un control en el **cuadro de herramientas** para agregarlo a la esquina superior izquierda del formulario en su tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="493ab-119">You can double-click a control in the **Toolbox** to add it to the upper-left corner of the form in its default size.</span></span>

    <span data-ttu-id="493ab-120">También puede Agregar controles de forma dinámica a un formulario en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="493ab-120">You can also add controls dynamically to a form at run time.</span></span> <span data-ttu-id="493ab-121">En el ejemplo de código siguiente, se agregará un control <xref:System.Windows.Forms.TextBox> al formulario cuando se haga clic en un control <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="493ab-121">In the following code example, a <xref:System.Windows.Forms.TextBox> control will be added to the form when a <xref:System.Windows.Forms.Button> control is clicked.</span></span>

    > [!NOTE]
    > <span data-ttu-id="493ab-122">El procedimiento siguiente requiere la existencia de un formulario con un control **botón** , `Button1`, ya colocado en él.</span><span class="sxs-lookup"><span data-stu-id="493ab-122">The following procedure requires the existence of a form with a **Button** control, `Button1`, already placed on it.</span></span>

## <a name="to-add-a-control-to-a-form-programmatically"></a><span data-ttu-id="493ab-123">Para agregar un control a un formulario mediante programación</span><span class="sxs-lookup"><span data-stu-id="493ab-123">To add a control to a form programmatically</span></span>

1. <span data-ttu-id="493ab-124">En el método que controla el evento de `Click` del botón dentro de la clase del formulario, inserte código similar al siguiente para agregar una referencia a la variable de control, establecer el `Location`del control y agregar el control.</span><span class="sxs-lookup"><span data-stu-id="493ab-124">In the method that handles the button's `Click` event within your form's class, insert code similar to the following to add a reference to your control variable, set the control's `Location`, and add the control.</span></span>

    ```vb
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
       Dim MyText As New TextBox()
       MyText.Location = New Point(25, 25)
       Me.Controls.Add(MyText)
    End Sub
    ```

    ```csharp
    private void button1_Click(object sender, System.EventArgs e)
    {
       TextBox myText = new TextBox();
       myText.Location = new Point(25,25);
       this.Controls.Add (myText);
    }
    ```

    ```cpp
    private:
      System::Void button1_Click(System::Object ^  sender,
        System::EventArgs ^  e)
      {
        TextBox ^ myText = gcnew TextBox();
        myText->Location = Point(25,25);
        this->Controls->Add(myText);
      }
    ```

    > [!NOTE]
    > <span data-ttu-id="493ab-125">También puede agregar código para inicializar otras propiedades del control.</span><span class="sxs-lookup"><span data-stu-id="493ab-125">You can also add code to initialize other properties of the control.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="493ab-126">Puede exponer el equipo local a un riesgo de seguridad a través de la red haciendo referencia a un `UserControl`malintencionado.</span><span class="sxs-lookup"><span data-stu-id="493ab-126">You might expose your local computer to a security risk through the network by referencing a malicious `UserControl`.</span></span> <span data-ttu-id="493ab-127">Esto solo suponer un problema en el caso de que una persona malintencionada cree un control personalizado perjudicial y, después, lo agregue por error a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="493ab-127">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="493ab-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="493ab-128">See also</span></span>

- [<span data-ttu-id="493ab-129">Controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="493ab-129">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="493ab-130">Procedimiento para cambiar el tamaño de los controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="493ab-130">How to: Resize Controls on Windows Forms</span></span>](how-to-resize-controls-on-windows-forms.md)
- [<span data-ttu-id="493ab-131">Establecer el texto mostrado por un control de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="493ab-131">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="493ab-132">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="493ab-132">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
