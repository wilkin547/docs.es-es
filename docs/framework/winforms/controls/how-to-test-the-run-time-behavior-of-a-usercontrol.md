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
ms.openlocfilehash: 48531ab1ef3b30b6516e3f2e7b5858a8884cbfe8
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211701"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="df7c5-102">Procedimiento Probar el comportamiento de tiempo de ejecución de una clase UserControl</span><span class="sxs-lookup"><span data-stu-id="df7c5-102">How to: Test the run-time behavior of a UserControl</span></span>

<span data-ttu-id="df7c5-103">Al desarrollar un <xref:System.Windows.Forms.UserControl>, debe probar su comportamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="df7c5-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="df7c5-104">Puede crear un proyecto de aplicación basada en Windows independiente y colocar el control en un formulario de prueba, pero este procedimiento es un problema.</span><span class="sxs-lookup"><span data-stu-id="df7c5-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="df7c5-105">Una forma más rápida y sencilla es usar el **UserControl Test Container** proporcionadas por Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="df7c5-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="df7c5-106">Este contenedor de prueba se inicia directamente desde un proyecto de biblioteca de control de Windows.</span><span class="sxs-lookup"><span data-stu-id="df7c5-106">This test container starts directly from your Windows control library project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="df7c5-107">Para el contenedor de prueba cargar su <xref:System.Windows.Forms.UserControl>, el control debe tener al menos un constructor público.</span><span class="sxs-lookup"><span data-stu-id="df7c5-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="df7c5-108">No se puede probar un control Visual C++ utilizando el **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="df7c5-108">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="df7c5-109">Probar el comportamiento de tiempo de ejecución de una clase UserControl</span><span class="sxs-lookup"><span data-stu-id="df7c5-109">Test the run-time behavior of a UserControl</span></span>

1. <span data-ttu-id="df7c5-110">En Visual Studio, cree un proyecto de biblioteca de controles de Windows denominado **TestContainerExample**.</span><span class="sxs-lookup"><span data-stu-id="df7c5-110">In Visual Studio, create a Windows control library project called **TestContainerExample**.</span></span> <span data-ttu-id="df7c5-111">Para obtener más información, consulte [plantilla Biblioteca de controles de Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="df7c5-111">For details, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>

2. <span data-ttu-id="df7c5-112">En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.Label> controlar desde la **cuadro de herramientas** hasta la superficie de diseño del control.</span><span class="sxs-lookup"><span data-stu-id="df7c5-112">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="df7c5-113">Presione **F5** para compilar el proyecto y ejecutar el **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="df7c5-113">Press **F5** to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="df7c5-114">El contenedor de prueba aparece con su <xref:System.Windows.Forms.UserControl> en el **Preview** panel.</span><span class="sxs-lookup"><span data-stu-id="df7c5-114">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="df7c5-115">Seleccione el <xref:System.Windows.Forms.Control.BackColor%2A> las propiedades mostradas en la <xref:System.Windows.Forms.PropertyGrid> control a la derecha de la **Preview** panel.</span><span class="sxs-lookup"><span data-stu-id="df7c5-115">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="df7c5-116">Cambie su valor a `ControlDark`.</span><span class="sxs-lookup"><span data-stu-id="df7c5-116">Change its value to `ControlDark`.</span></span> <span data-ttu-id="df7c5-117">Observe que el control cambia a un color más oscuro.</span><span class="sxs-lookup"><span data-stu-id="df7c5-117">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="df7c5-118">Pruebe a cambiar otros valores de propiedad y observar el efecto en el control.</span><span class="sxs-lookup"><span data-stu-id="df7c5-118">Try changing other property values and observe the effect on your control.</span></span>

5. <span data-ttu-id="df7c5-119">Haga clic en el **Control de usuario Dock Fill** casilla de verificación siguiente el **Preview** panel.</span><span class="sxs-lookup"><span data-stu-id="df7c5-119">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="df7c5-120">Observe que el control cambia de tamaño para rellenar el panel.</span><span class="sxs-lookup"><span data-stu-id="df7c5-120">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="df7c5-121">Cambiar el tamaño del contenedor de prueba y observe que el control cambia de tamaño con el panel.</span><span class="sxs-lookup"><span data-stu-id="df7c5-121">Resize the test container and observe that the control is resized with the pane.</span></span>

6. <span data-ttu-id="df7c5-122">Cierre el contenedor de prueba.</span><span class="sxs-lookup"><span data-stu-id="df7c5-122">Close the test container.</span></span>

7. <span data-ttu-id="df7c5-123">Agregue otro control de usuario para el **TestContainerExample** proyecto.</span><span class="sxs-lookup"><span data-stu-id="df7c5-123">Add another user control to the **TestContainerExample** project.</span></span> <span data-ttu-id="df7c5-124">Para obtener más detalles, vea [Cómo: Agregar elementos existentes a un proyecto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="df7c5-124">For details, see [How to: Add Existing Items to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).</span></span>

8. <span data-ttu-id="df7c5-125">En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** hasta la superficie de diseño del control.</span><span class="sxs-lookup"><span data-stu-id="df7c5-125">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>

9. <span data-ttu-id="df7c5-126">Presione F5 para compilar el proyecto y ejecutar el contenedor de prueba.</span><span class="sxs-lookup"><span data-stu-id="df7c5-126">Press F5 to build the project and run the test container.</span></span>

10. <span data-ttu-id="df7c5-127">Haga clic en el **seleccionar Control de usuario** <xref:System.Windows.Forms.ComboBox> para cambiar entre los dos controles de usuario.</span><span class="sxs-lookup"><span data-stu-id="df7c5-127">Click the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>

## <a name="test-user-controls-from-another-project"></a><span data-ttu-id="df7c5-128">Controles de usuario de prueba de otro proyecto</span><span class="sxs-lookup"><span data-stu-id="df7c5-128">Test user controls from another project</span></span>

<span data-ttu-id="df7c5-129">Puede probar los controles de usuario desde otros proyectos en el contenedor de prueba del proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="df7c5-129">You can test user controls from other projects in your current project's test container.</span></span>

1. <span data-ttu-id="df7c5-130">Crear un proyecto de biblioteca de controles de Windows denominado **TestContainerExample2**.</span><span class="sxs-lookup"><span data-stu-id="df7c5-130">Create a Windows control library project called **TestContainerExample2**.</span></span> <span data-ttu-id="df7c5-131">Para obtener más información, consulte [plantilla Biblioteca de controles de Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="df7c5-131">For details, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>

2. <span data-ttu-id="df7c5-132">En el **Diseñador de Windows Forms**, arrastre un <xref:System.Windows.Forms.RadioButton> controlar desde la **cuadro de herramientas** hasta la superficie de diseño del control.</span><span class="sxs-lookup"><span data-stu-id="df7c5-132">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="df7c5-133">Presione F5 para compilar el proyecto y ejecutar el contenedor de prueba.</span><span class="sxs-lookup"><span data-stu-id="df7c5-133">Press F5 to build the project and run the test container.</span></span> <span data-ttu-id="df7c5-134">El contenedor de prueba aparece con su <xref:System.Windows.Forms.UserControl> en el **Preview** panel.</span><span class="sxs-lookup"><span data-stu-id="df7c5-134">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="df7c5-135">Haga clic en el **carga** botón.</span><span class="sxs-lookup"><span data-stu-id="df7c5-135">Click the **Load** button.</span></span>

5. <span data-ttu-id="df7c5-136">En el **abierto** diálogo cuadro, vaya a **TestContainerExample**.dll, que basa en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="df7c5-136">In the **Open** dialog box, navigate to **TestContainerExample**.dll, which you built in the previous procedure.</span></span> <span data-ttu-id="df7c5-137">Seleccione **TestContainerExample**.dll y haga clic en el **abierto** botón para cargar los controles de usuario</span><span class="sxs-lookup"><span data-stu-id="df7c5-137">Select **TestContainerExample**.dll and click the **Open** button to load the user controls</span></span>

6. <span data-ttu-id="df7c5-138">Use la **seleccionar Control de usuario** <xref:System.Windows.Forms.ComboBox> para cambiar entre los dos controles de usuario desde el **TestContainerExample** proyecto.</span><span class="sxs-lookup"><span data-stu-id="df7c5-138">Use the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>

## <a name="see-also"></a><span data-ttu-id="df7c5-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="df7c5-139">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="df7c5-140">Cómo: Crear controles compuestos</span><span class="sxs-lookup"><span data-stu-id="df7c5-140">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="df7c5-141">Tutorial: Crear un Control compuesto con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="df7c5-141">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="df7c5-142">Tutorial: Crear un Control compuesto con VisualC#</span><span class="sxs-lookup"><span data-stu-id="df7c5-142">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- <span data-ttu-id="df7c5-143">[Diseñador de controles de usuario](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="df7c5-143">[User Control Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span></span>
