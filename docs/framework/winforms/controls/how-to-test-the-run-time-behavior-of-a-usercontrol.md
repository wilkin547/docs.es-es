---
title: Procedimiento para comprobar el comportamiento de UserControl en tiempo de ejecución
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
ms.openlocfilehash: 15b37c71e6643b588c0378510965a9a3e7cb56e9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61672580"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="b1a53-102">Procedimiento para comprobar el comportamiento de UserControl en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b1a53-102">How to: Test the Run-Time Behavior of a UserControl</span></span>
<span data-ttu-id="b1a53-103">Al desarrollar un <xref:System.Windows.Forms.UserControl>, debe probar su comportamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b1a53-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="b1a53-104">Puede crear un proyecto de aplicación basada en Windows independiente y colocar el control en un formulario de prueba, pero este procedimiento es un problema.</span><span class="sxs-lookup"><span data-stu-id="b1a53-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="b1a53-105">Una forma más rápida y sencilla es usar el **UserControl Test Container** proporcionadas por Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b1a53-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="b1a53-106">Este contenedor de prueba se inicia directamente desde un proyecto de biblioteca de control de Windows.</span><span class="sxs-lookup"><span data-stu-id="b1a53-106">This test container starts directly from your Windows control library project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b1a53-107">Para el contenedor de prueba cargar su <xref:System.Windows.Forms.UserControl>, el control debe tener al menos un constructor público.</span><span class="sxs-lookup"><span data-stu-id="b1a53-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1a53-108">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="b1a53-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b1a53-109">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="b1a53-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b1a53-110">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="b1a53-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1a53-111">No se puede probar un control Visual C++ utilizando el **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="b1a53-111">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="b1a53-112">Para probar el comportamiento de tiempo de ejecución de una clase UserControl</span><span class="sxs-lookup"><span data-stu-id="b1a53-112">To test the run-time behavior of a UserControl</span></span>  
  
1. <span data-ttu-id="b1a53-113">Crear un proyecto de biblioteca de controles de Windows denominado **TestContainerExample**.</span><span class="sxs-lookup"><span data-stu-id="b1a53-113">Create a Windows control library project called **TestContainerExample**.</span></span> <span data-ttu-id="b1a53-114">Para obtener más información, consulte [plantilla Biblioteca de controles de Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b1a53-114">For details, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="b1a53-115">En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.Label> controlar desde la **cuadro de herramientas** hasta la superficie de diseño del control.</span><span class="sxs-lookup"><span data-stu-id="b1a53-115">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>  
  
3. <span data-ttu-id="b1a53-116">Presione F5 para compilar el proyecto y ejecutar el **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="b1a53-116">Press F5 to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="b1a53-117">El contenedor de prueba aparece con su <xref:System.Windows.Forms.UserControl> en el **Preview** panel.</span><span class="sxs-lookup"><span data-stu-id="b1a53-117">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>  
  
4. <span data-ttu-id="b1a53-118">Seleccione el <xref:System.Windows.Forms.Control.BackColor%2A> las propiedades mostradas en la <xref:System.Windows.Forms.PropertyGrid> control a la derecha de la **Preview** panel.</span><span class="sxs-lookup"><span data-stu-id="b1a53-118">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="b1a53-119">Cambie su valor a `ControlDark`.</span><span class="sxs-lookup"><span data-stu-id="b1a53-119">Change its value to `ControlDark`.</span></span> <span data-ttu-id="b1a53-120">Observe que el control cambia a un color más oscuro.</span><span class="sxs-lookup"><span data-stu-id="b1a53-120">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="b1a53-121">Pruebe a cambiar otros valores de propiedad y observar el efecto en el control.</span><span class="sxs-lookup"><span data-stu-id="b1a53-121">Try changing other property values and observe the effect on your control.</span></span>  
  
5. <span data-ttu-id="b1a53-122">Haga clic en el **Control de usuario Dock Fill** casilla de verificación siguiente el **Preview** panel.</span><span class="sxs-lookup"><span data-stu-id="b1a53-122">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="b1a53-123">Observe que el control cambia de tamaño para rellenar el panel.</span><span class="sxs-lookup"><span data-stu-id="b1a53-123">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="b1a53-124">Cambiar el tamaño del contenedor de prueba y observe que el control cambia de tamaño con el panel.</span><span class="sxs-lookup"><span data-stu-id="b1a53-124">Resize the test container and observe that the control is resized with the pane.</span></span>  
  
6. <span data-ttu-id="b1a53-125">Cierre el contenedor de prueba.</span><span class="sxs-lookup"><span data-stu-id="b1a53-125">Close the test container.</span></span>  
  
7. <span data-ttu-id="b1a53-126">Agregue otro control de usuario para el **TestContainerExample** proyecto.</span><span class="sxs-lookup"><span data-stu-id="b1a53-126">Add another user control to the **TestContainerExample** project.</span></span> <span data-ttu-id="b1a53-127">Para obtener más detalles, vea [Cómo: Agregar elementos existentes a un proyecto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b1a53-127">For details, see [How to: Add Existing Items to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).</span></span>  
  
8. <span data-ttu-id="b1a53-128">En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** hasta la superficie de diseño del control.</span><span class="sxs-lookup"><span data-stu-id="b1a53-128">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>  
  
9. <span data-ttu-id="b1a53-129">Presione F5 para compilar el proyecto y ejecutar el contenedor de prueba.</span><span class="sxs-lookup"><span data-stu-id="b1a53-129">Press F5 to build the project and run the test container.</span></span>  
  
10. <span data-ttu-id="b1a53-130">Haga clic en el **seleccionar Control de usuario** <xref:System.Windows.Forms.ComboBox> para cambiar entre los dos controles de usuario.</span><span class="sxs-lookup"><span data-stu-id="b1a53-130">Click the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>  
  
## <a name="testing-user-controls-from-another-project"></a><span data-ttu-id="b1a53-131">Probar los controles de usuario desde otro proyecto</span><span class="sxs-lookup"><span data-stu-id="b1a53-131">Testing User Controls from Another Project</span></span>  
 <span data-ttu-id="b1a53-132">Puede probar los controles de usuario desde otros proyectos en el contenedor de prueba del proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="b1a53-132">You can test user controls from other projects in your current project's test container.</span></span>  
  
#### <a name="to-test-user-controls-from-another-project"></a><span data-ttu-id="b1a53-133">Para probar los controles de usuario desde otro proyecto</span><span class="sxs-lookup"><span data-stu-id="b1a53-133">To test user controls from another project</span></span>  
  
1. <span data-ttu-id="b1a53-134">Crear un proyecto de biblioteca de controles de Windows denominado **TestContainerExample2**.</span><span class="sxs-lookup"><span data-stu-id="b1a53-134">Create a Windows control library project called **TestContainerExample2**.</span></span> <span data-ttu-id="b1a53-135">Para obtener más información, consulte [plantilla Biblioteca de controles de Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b1a53-135">For details, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="b1a53-136">En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.RadioButton> controlar desde la **cuadro de herramientas** hasta la superficie de diseño del control.</span><span class="sxs-lookup"><span data-stu-id="b1a53-136">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>  
  
3. <span data-ttu-id="b1a53-137">Presione F5 para compilar el proyecto y ejecutar el contenedor de prueba.</span><span class="sxs-lookup"><span data-stu-id="b1a53-137">Press F5 to build the project and run the test container.</span></span> <span data-ttu-id="b1a53-138">El contenedor de prueba aparece con su <xref:System.Windows.Forms.UserControl> en el **Preview** panel.</span><span class="sxs-lookup"><span data-stu-id="b1a53-138">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>  
  
4. <span data-ttu-id="b1a53-139">Haga clic en el **carga** botón.</span><span class="sxs-lookup"><span data-stu-id="b1a53-139">Click the **Load** button.</span></span>  
  
5. <span data-ttu-id="b1a53-140">En el **abierto** diálogo cuadro, vaya a **TestContainerExample**.dll, que basa en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="b1a53-140">In the **Open** dialog box, navigate to **TestContainerExample**.dll, which you built in the previous procedure.</span></span> <span data-ttu-id="b1a53-141">Seleccione **TestContainerExample**.dll y haga clic en el **abierto** botón para cargar los controles de usuario</span><span class="sxs-lookup"><span data-stu-id="b1a53-141">Select **TestContainerExample**.dll and click the **Open** button to load the user controls</span></span>  
  
6. <span data-ttu-id="b1a53-142">Use la **seleccionar Control de usuario** <xref:System.Windows.Forms.ComboBox> para cambiar entre los dos controles de usuario desde el **TestContainerExample** proyecto.</span><span class="sxs-lookup"><span data-stu-id="b1a53-142">Use the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1a53-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1a53-143">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="b1a53-144">Cómo: Crear controles compuestos</span><span class="sxs-lookup"><span data-stu-id="b1a53-144">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="b1a53-145">Tutorial: Crear un Control compuesto con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1a53-145">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="b1a53-146">Tutorial: Crear un Control compuesto con VisualC#</span><span class="sxs-lookup"><span data-stu-id="b1a53-146">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- <span data-ttu-id="b1a53-147">[Diseñador de controles de usuario](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b1a53-147">[User Control Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span></span>
