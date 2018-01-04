---
title: "Cómo: Agregar controles a formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d9075c93181b68828a307924259a9170c046baa6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-controls-to-windows-forms"></a><span data-ttu-id="9f368-102">Cómo: Agregar controles a formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9f368-102">How to: Add Controls to Windows Forms</span></span>
<span data-ttu-id="9f368-103">Mayoría de los formularios se diseñan agregando controles a la superficie del formulario para definir una interfaz de usuario (UI).</span><span class="sxs-lookup"><span data-stu-id="9f368-103">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="9f368-104">A *control* es un componente en un formulario que se utiliza para mostrar información o Aceptar proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="9f368-104">A *control* is a component on a form used to display information or accept user input.</span></span> <span data-ttu-id="9f368-105">Para obtener más información acerca de los controles, consulte [controles de Windows Forms](../../../../docs/framework/winforms/controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="9f368-105">For more information about controls, see [Windows Forms Controls](../../../../docs/framework/winforms/controls/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f368-106">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="9f368-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="9f368-107">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="9f368-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="9f368-108">Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="9f368-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-draw-a-control-on-a-form"></a><span data-ttu-id="9f368-109">Para dibujar un control en un formulario</span><span class="sxs-lookup"><span data-stu-id="9f368-109">To draw a control on a form</span></span>  
  
1.  <span data-ttu-id="9f368-110">Abra el formulario.</span><span class="sxs-lookup"><span data-stu-id="9f368-110">Open the form.</span></span> <span data-ttu-id="9f368-111">Para obtener más información, consulte [Cómo: mostrar Windows Forms en el diseñador](http://msdn.microsoft.com/en-us/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span><span class="sxs-lookup"><span data-stu-id="9f368-111">For more information, see [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/en-us/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span></span>  
  
2.  <span data-ttu-id="9f368-112">En el **cuadro de herramientas**, haga clic en el control que desea agregar al formulario.</span><span class="sxs-lookup"><span data-stu-id="9f368-112">In the **Toolbox**, click the control you want to add to your form.</span></span>  
  
3.  <span data-ttu-id="9f368-113">En el formulario, haga clic donde desee que la esquina superior izquierda del control para que se encuentre y arrastre hasta donde desee que la esquina inferior derecha del control para que se encuentre.</span><span class="sxs-lookup"><span data-stu-id="9f368-113">On the form, click where you want the upper-left corner of the control to be located, and drag to where you want the lower-right corner of the control to be located.</span></span>  
  
     <span data-ttu-id="9f368-114">El control se agrega al formulario con el tamaño y la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="9f368-114">The control is added to the form with the specified location and size.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9f368-115">Cada control tiene definido un tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9f368-115">Each control has a default size defined.</span></span> <span data-ttu-id="9f368-116">Puede agregar un control al formulario en el tamaño del control predeterminado arrastrándolo desde el **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="9f368-116">You can add a control to your form in the control's default size by dragging it from the **Toolbox** to the form.</span></span>  
  
### <a name="to-drag-a-control-to-a-form"></a><span data-ttu-id="9f368-117">Al arrastrar un control a un formulario</span><span class="sxs-lookup"><span data-stu-id="9f368-117">To drag a control to a form</span></span>  
  
1.  <span data-ttu-id="9f368-118">Abra el formulario.</span><span class="sxs-lookup"><span data-stu-id="9f368-118">Open the form.</span></span> <span data-ttu-id="9f368-119">Para obtener más información, consulte [Cómo: mostrar Windows Forms en el diseñador](http://msdn.microsoft.com/en-us/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span><span class="sxs-lookup"><span data-stu-id="9f368-119">For more information, see [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/en-us/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span></span>  
  
2.  <span data-ttu-id="9f368-120">En el **cuadro de herramientas**, haga clic en el control que desee y arrástrelo hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="9f368-120">In the **Toolbox**, click the control you want and drag it to your form.</span></span>  
  
     <span data-ttu-id="9f368-121">El control se agrega al formulario en la ubicación especificada con su tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9f368-121">The control is added to the form at the specified location in its default size.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9f368-122">Haga doble clic en un control en el **cuadro de herramientas** para agregarlo a la esquina superior izquierda del formulario en su tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9f368-122">You can double-click a control in the **Toolbox** to add it to the upper-left corner of the form in its default size.</span></span>  
  
     <span data-ttu-id="9f368-123">También puede agregar controles de forma dinámica a un formulario en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9f368-123">You can also add controls dynamically to a form at run time.</span></span> <span data-ttu-id="9f368-124">En el ejemplo de código siguiente, un <xref:System.Windows.Forms.TextBox> control se agregará al formulario cuando un <xref:System.Windows.Forms.Button> se hace clic en el control.</span><span class="sxs-lookup"><span data-stu-id="9f368-124">In the following code example, a <xref:System.Windows.Forms.TextBox> control will be added to the form when a <xref:System.Windows.Forms.Button> control is clicked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9f368-125">El siguiente procedimiento requiere la existencia de un formulario con un **botón** control, `Button1`, ya colocados en él.</span><span class="sxs-lookup"><span data-stu-id="9f368-125">The following procedure requires the existence of a form with a **Button** control, `Button1`, already placed on it.</span></span>  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a><span data-ttu-id="9f368-126">Para agregar un control a un formulario mediante programación</span><span class="sxs-lookup"><span data-stu-id="9f368-126">To add a control to a form programmatically</span></span>  
  
1.  <span data-ttu-id="9f368-127">En el método que controla el botón `Click` evento dentro de la clase del formulario, insertar código similar al siguiente para agregar una referencia a la variable de control, establezca el control `Location`y agregar el control.</span><span class="sxs-lookup"><span data-stu-id="9f368-127">In the method that handles the button's `Click` event within your form's class, insert code similar to the following to add a reference to your control variable, set the control's `Location`, and add the control.</span></span>  
  
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
    >  <span data-ttu-id="9f368-128">También puede agregar código para inicializar otras propiedades del control.</span><span class="sxs-lookup"><span data-stu-id="9f368-128">You can also add code to initialize other properties of the control.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="9f368-129">Puede exponer el equipo local a un riesgo de seguridad a través de la red mediante una referencia a un malintencionado `UserControl`.</span><span class="sxs-lookup"><span data-stu-id="9f368-129">You might expose your local computer to a security risk through the network by referencing a malicious `UserControl`.</span></span> <span data-ttu-id="9f368-130">Esto solo sería un problema en el caso de una persona malintencionada cree un control personalizado perjudicial, seguido por el que se agregara a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="9f368-130">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f368-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f368-131">See Also</span></span>  
 [<span data-ttu-id="9f368-132">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9f368-132">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="9f368-133">Organizar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9f368-133">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="9f368-134">Procedimiento para cambiar el tamaño de los controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9f368-134">How to: Resize Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)  
 [<span data-ttu-id="9f368-135">Establecer el texto mostrado por un control de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9f368-135">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="9f368-136">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9f368-136">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
