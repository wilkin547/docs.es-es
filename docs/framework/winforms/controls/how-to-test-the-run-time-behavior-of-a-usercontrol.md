---
title: "Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9ccf386acd50338f1743bbf8f6be38b3267a7103
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="1b461-102">Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1b461-102">How to: Test the Run-Time Behavior of a UserControl</span></span>
<span data-ttu-id="1b461-103">Al desarrollar un <xref:System.Windows.Forms.UserControl>, debe probar su comportamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1b461-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="1b461-104">Puede crear un proyecto de aplicación basada en Windows independiente y colocar el control en un formulario de prueba, pero este procedimiento es un problema.</span><span class="sxs-lookup"><span data-stu-id="1b461-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="1b461-105">Una manera más rápida y sencilla es usar el **UserControl Test Container** proporcionada por Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1b461-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="1b461-106">Este contenedor de prueba se inicia directamente desde el proyecto de biblioteca de controles de Windows.</span><span class="sxs-lookup"><span data-stu-id="1b461-106">This test container starts directly from your Windows control library project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1b461-107">Para el contenedor de prueba cargar su <xref:System.Windows.Forms.UserControl>, el control debe tener al menos un constructor público.</span><span class="sxs-lookup"><span data-stu-id="1b461-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b461-108">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="1b461-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1b461-109">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="1b461-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1b461-110">Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="1b461-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b461-111">No se puede probar un control de Visual C++ mediante el **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="1b461-111">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="1b461-112">Para probar el comportamiento de tiempo de ejecución de un control de usuario</span><span class="sxs-lookup"><span data-stu-id="1b461-112">To test the run-time behavior of a UserControl</span></span>  
  
1.  <span data-ttu-id="1b461-113">Crear un proyecto de biblioteca de controles de Windows denominado **TestContainerExample**.</span><span class="sxs-lookup"><span data-stu-id="1b461-113">Create a Windows control library project called **TestContainerExample**.</span></span> <span data-ttu-id="1b461-114">Para obtener más información, consulte [plantilla de biblioteca de controles de Windows](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span><span class="sxs-lookup"><span data-stu-id="1b461-114">For details, see [Windows Control Library Template](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span></span>  
  
2.  <span data-ttu-id="1b461-115">En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.Label> controlar desde la **cuadro de herramientas** en la superficie de diseño del control.</span><span class="sxs-lookup"><span data-stu-id="1b461-115">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>  
  
3.  <span data-ttu-id="1b461-116">Presione F5 para compilar el proyecto y ejecutar el **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="1b461-116">Press F5 to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="1b461-117">El contenedor de prueba aparece con su <xref:System.Windows.Forms.UserControl> en el **vista previa** panel.</span><span class="sxs-lookup"><span data-stu-id="1b461-117">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>  
  
4.  <span data-ttu-id="1b461-118">Seleccione el <xref:System.Windows.Forms.Control.BackColor%2A> las propiedades mostradas en la <xref:System.Windows.Forms.PropertyGrid> control a la derecha de la **vista previa** panel.</span><span class="sxs-lookup"><span data-stu-id="1b461-118">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="1b461-119">Cambie su valor a `ControlDark`.</span><span class="sxs-lookup"><span data-stu-id="1b461-119">Change its value to `ControlDark`.</span></span> <span data-ttu-id="1b461-120">Observe que el control cambia a un color más oscuro.</span><span class="sxs-lookup"><span data-stu-id="1b461-120">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="1b461-121">Pruebe a cambiar otros valores de propiedad y observe el efecto en el control.</span><span class="sxs-lookup"><span data-stu-id="1b461-121">Try changing other property values and observe the effect on your control.</span></span>  
  
5.  <span data-ttu-id="1b461-122">Haga clic en el **Control de usuario Dock Fill** siguiente casilla de verificación el **vista previa** panel.</span><span class="sxs-lookup"><span data-stu-id="1b461-122">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="1b461-123">Observe que el control cambia de tamaño para rellenar el panel.</span><span class="sxs-lookup"><span data-stu-id="1b461-123">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="1b461-124">Cambiar el tamaño del contenedor de prueba y observe que el control cambia de tamaño con el panel.</span><span class="sxs-lookup"><span data-stu-id="1b461-124">Resize the test container and observe that the control is resized with the pane.</span></span>  
  
6.  <span data-ttu-id="1b461-125">Cierre el contenedor de prueba.</span><span class="sxs-lookup"><span data-stu-id="1b461-125">Close the test container.</span></span>  
  
7.  <span data-ttu-id="1b461-126">Agregue otro control de usuario para la **TestContainerExample** proyecto.</span><span class="sxs-lookup"><span data-stu-id="1b461-126">Add another user control to the **TestContainerExample** project.</span></span> <span data-ttu-id="1b461-127">Para obtener más información, consulte [NIB: Cómo: agregar elementos existentes a un proyecto](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span><span class="sxs-lookup"><span data-stu-id="1b461-127">For details, see [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span></span>  
  
8.  <span data-ttu-id="1b461-128">En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** en la superficie de diseño del control.</span><span class="sxs-lookup"><span data-stu-id="1b461-128">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>  
  
9. <span data-ttu-id="1b461-129">Presione F5 para compilar el proyecto y ejecutar el contenedor de prueba.</span><span class="sxs-lookup"><span data-stu-id="1b461-129">Press F5 to build the project and run the test container.</span></span>  
  
10. <span data-ttu-id="1b461-130">Haga clic en el **seleccionar Control de usuario** <xref:System.Windows.Forms.ComboBox> para cambiar entre los dos controles de usuario.</span><span class="sxs-lookup"><span data-stu-id="1b461-130">Click the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>  
  
## <a name="testing-user-controls-from-another-project"></a><span data-ttu-id="1b461-131">Probar los controles de usuario desde otro proyecto</span><span class="sxs-lookup"><span data-stu-id="1b461-131">Testing User Controls from Another Project</span></span>  
 <span data-ttu-id="1b461-132">Puede probar los controles de usuario de otros proyectos en el contenedor de prueba del proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="1b461-132">You can test user controls from other projects in your current project's test container.</span></span>  
  
#### <a name="to-test-user-controls-from-another-project"></a><span data-ttu-id="1b461-133">Para probar los controles de usuario desde otro proyecto</span><span class="sxs-lookup"><span data-stu-id="1b461-133">To test user controls from another project</span></span>  
  
1.  <span data-ttu-id="1b461-134">Crear un proyecto de biblioteca de controles de Windows denominado **TestContainerExample2**.</span><span class="sxs-lookup"><span data-stu-id="1b461-134">Create a Windows control library project called **TestContainerExample2**.</span></span> <span data-ttu-id="1b461-135">Para obtener más información, consulte [plantilla de biblioteca de controles de Windows](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span><span class="sxs-lookup"><span data-stu-id="1b461-135">For details, see [Windows Control Library Template](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span></span>  
  
2.  <span data-ttu-id="1b461-136">En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.RadioButton> controlar desde la **cuadro de herramientas** en la superficie de diseño del control.</span><span class="sxs-lookup"><span data-stu-id="1b461-136">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>  
  
3.  <span data-ttu-id="1b461-137">Presione F5 para compilar el proyecto y ejecutar el contenedor de prueba.</span><span class="sxs-lookup"><span data-stu-id="1b461-137">Press F5 to build the project and run the test container.</span></span> <span data-ttu-id="1b461-138">El contenedor de prueba aparece con su <xref:System.Windows.Forms.UserControl> en el **vista previa** panel.</span><span class="sxs-lookup"><span data-stu-id="1b461-138">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>  
  
4.  <span data-ttu-id="1b461-139">Haga clic en el **carga** botón.</span><span class="sxs-lookup"><span data-stu-id="1b461-139">Click the **Load** button.</span></span>  
  
5.  <span data-ttu-id="1b461-140">En el **abiertos** diálogo cuadro, vaya a **TestContainerExample**.dll, que basa en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="1b461-140">In the **Open** dialog box, navigate to **TestContainerExample**.dll, which you built in the previous procedure.</span></span> <span data-ttu-id="1b461-141">Seleccione **TestContainerExample**.dll y haga clic en el **abiertos** botón para cargar los controles de usuario</span><span class="sxs-lookup"><span data-stu-id="1b461-141">Select **TestContainerExample**.dll and click the **Open** button to load the user controls</span></span>  
  
6.  <span data-ttu-id="1b461-142">Use la **seleccionar Control de usuario** <xref:System.Windows.Forms.ComboBox> para cambiar entre los dos controles de usuario desde el **TestContainerExample** proyecto.</span><span class="sxs-lookup"><span data-stu-id="1b461-142">Use the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b461-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b461-143">See Also</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 [<span data-ttu-id="1b461-144">Cómo: Crear controles compuestos</span><span class="sxs-lookup"><span data-stu-id="1b461-144">How to: Author Composite Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 [<span data-ttu-id="1b461-145">Tutorial: Crear un control compuesto con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1b461-145">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [<span data-ttu-id="1b461-146">Tutorial: Crear un control compuesto con Visual C#</span><span class="sxs-lookup"><span data-stu-id="1b461-146">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [<span data-ttu-id="1b461-147">Diseñador de controles de usuario</span><span class="sxs-lookup"><span data-stu-id="1b461-147">User Control Designer</span></span>](http://msdn.microsoft.com/en-us/2abb9eec-ba32-45cb-b73d-8b52a8bd6bf1)
