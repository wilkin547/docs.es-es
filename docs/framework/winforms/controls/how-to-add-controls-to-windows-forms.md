---
title: Procedimiento Agregar controles a Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 29a268f645810d84d9f6fb722e4728842b04ee14
ms.sourcegitcommit: acd8ed14fe94e9d4e3a7fb685fe83d05e941073c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2019
ms.locfileid: "56443177"
---
# <a name="how-to-add-controls-to-windows-forms"></a><span data-ttu-id="be4cc-102">Filtrar Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="be4cc-102">How to: Add Controls to Windows Forms</span></span>
<span data-ttu-id="be4cc-103">Mayoría de los formularios está diseñada agregando controles a la superficie del formulario para definir una interfaz de usuario (UI).</span><span class="sxs-lookup"><span data-stu-id="be4cc-103">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="be4cc-104">Un *control* es un componente en un formulario que se usa para mostrar información o Aceptar la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="be4cc-104">A *control* is a component on a form used to display information or accept user input.</span></span> <span data-ttu-id="be4cc-105">Para obtener más información acerca de los controles, vea [controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="be4cc-105">For more information about controls, see [Windows Forms Controls](../../../../docs/framework/winforms/controls/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be4cc-106">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="be4cc-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="be4cc-107">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="be4cc-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="be4cc-108">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="be4cc-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-draw-a-control-on-a-form"></a><span data-ttu-id="be4cc-109">Para dibujar un control en un formulario</span><span class="sxs-lookup"><span data-stu-id="be4cc-109">To draw a control on a form</span></span>  
  
1.  <span data-ttu-id="be4cc-110">Abra el formulario.</span><span class="sxs-lookup"><span data-stu-id="be4cc-110">Open the form.</span></span> <span data-ttu-id="be4cc-111">Para obtener más información, vea [Cómo: Mostrar Windows Forms en el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="be4cc-111">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="be4cc-112">En el **cuadro de herramientas**, haga clic en el control que desea agregar al formulario.</span><span class="sxs-lookup"><span data-stu-id="be4cc-112">In the **Toolbox**, click the control you want to add to your form.</span></span>  
  
3.  <span data-ttu-id="be4cc-113">En el formulario, haga clic donde desee que la esquina superior izquierda del control que se ubiquen y arrastre hasta donde desee que la esquina inferior derecha del control que se encuentra.</span><span class="sxs-lookup"><span data-stu-id="be4cc-113">On the form, click where you want the upper-left corner of the control to be located, and drag to where you want the lower-right corner of the control to be located.</span></span>  
  
     <span data-ttu-id="be4cc-114">El control se agrega al formulario con el tamaño y la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="be4cc-114">The control is added to the form with the specified location and size.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="be4cc-115">Cada control tiene definido un tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="be4cc-115">Each control has a default size defined.</span></span> <span data-ttu-id="be4cc-116">Puede agregar un control al formulario en el tamaño del control de forma predeterminada si lo arrastra desde el **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="be4cc-116">You can add a control to your form in the control's default size by dragging it from the **Toolbox** to the form.</span></span>  
  
### <a name="to-drag-a-control-to-a-form"></a><span data-ttu-id="be4cc-117">Para arrastrar un control a un formulario</span><span class="sxs-lookup"><span data-stu-id="be4cc-117">To drag a control to a form</span></span>  
  
1.  <span data-ttu-id="be4cc-118">Abra el formulario.</span><span class="sxs-lookup"><span data-stu-id="be4cc-118">Open the form.</span></span> <span data-ttu-id="be4cc-119">Para obtener más información, vea [Cómo: Mostrar Windows Forms en el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="be4cc-119">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="be4cc-120">En el **cuadro de herramientas**, haga clic en el control que desee y arrástrelo al formulario.</span><span class="sxs-lookup"><span data-stu-id="be4cc-120">In the **Toolbox**, click the control you want and drag it to your form.</span></span>  
  
     <span data-ttu-id="be4cc-121">El control se agrega al formulario en la ubicación especificada en su tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="be4cc-121">The control is added to the form at the specified location in its default size.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="be4cc-122">Haga doble clic en un control en el **cuadro de herramientas** para agregarlo a la esquina superior izquierda del formulario en su tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="be4cc-122">You can double-click a control in the **Toolbox** to add it to the upper-left corner of the form in its default size.</span></span>  
  
     <span data-ttu-id="be4cc-123">También puede agregar controles dinámicamente a un formulario en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="be4cc-123">You can also add controls dynamically to a form at run time.</span></span> <span data-ttu-id="be4cc-124">En el ejemplo de código siguiente, un <xref:System.Windows.Forms.TextBox> control se agregarán al formulario cuando un <xref:System.Windows.Forms.Button> se hace clic en el control.</span><span class="sxs-lookup"><span data-stu-id="be4cc-124">In the following code example, a <xref:System.Windows.Forms.TextBox> control will be added to the form when a <xref:System.Windows.Forms.Button> control is clicked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="be4cc-125">El procedimiento siguiente requiere la existencia de un formulario con un **botón** control, `Button1`, ya colocados en él.</span><span class="sxs-lookup"><span data-stu-id="be4cc-125">The following procedure requires the existence of a form with a **Button** control, `Button1`, already placed on it.</span></span>  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a><span data-ttu-id="be4cc-126">Para agregar un control a un formulario mediante programación</span><span class="sxs-lookup"><span data-stu-id="be4cc-126">To add a control to a form programmatically</span></span>  
  
1.  <span data-ttu-id="be4cc-127">En el método que controla el botón `Click` evento dentro de la clase del formulario, insertar código similar al siguiente para agregar una referencia a la variable de control, establezca el control `Location`y agregar el control.</span><span class="sxs-lookup"><span data-stu-id="be4cc-127">In the method that handles the button's `Click` event within your form's class, insert code similar to the following to add a reference to your control variable, set the control's `Location`, and add the control.</span></span>  
  
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
    >  <span data-ttu-id="be4cc-128">También puede agregar código para inicializar otras propiedades del control.</span><span class="sxs-lookup"><span data-stu-id="be4cc-128">You can also add code to initialize other properties of the control.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="be4cc-129">Podría exponer el equipo local a un riesgo de seguridad a través de la red haciendo referencia a un malintencionado `UserControl`.</span><span class="sxs-lookup"><span data-stu-id="be4cc-129">You might expose your local computer to a security risk through the network by referencing a malicious `UserControl`.</span></span> <span data-ttu-id="be4cc-130">Esto solo sería un problema en el caso de una persona malintencionada cree un control personalizado perjudicial, seguido por el que se agregara a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="be4cc-130">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be4cc-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="be4cc-131">See also</span></span>
- [<span data-ttu-id="be4cc-132">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="be4cc-132">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)
- [<span data-ttu-id="be4cc-133">Organizar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="be4cc-133">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="be4cc-134">Cómo: Cambiar el tamaño de los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="be4cc-134">How to: Resize Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)
- [<span data-ttu-id="be4cc-135">Cómo: Establecer el texto mostrado por un Windows Forms Control</span><span class="sxs-lookup"><span data-stu-id="be4cc-135">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="be4cc-136">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="be4cc-136">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
