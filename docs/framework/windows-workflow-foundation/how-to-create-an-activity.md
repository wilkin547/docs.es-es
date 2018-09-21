---
title: 'Cómo: Crear una actividad'
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: 8aa6900b26bbe9f77fe0802a7929febe5af61269
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2018
ms.locfileid: "46539621"
---
# <a name="how-to-create-an-activity"></a><span data-ttu-id="d2058-102">Cómo: Crear una actividad</span><span class="sxs-lookup"><span data-stu-id="d2058-102">How to: Create an Activity</span></span>

<span data-ttu-id="d2058-103">Las actividades son la unidad básica de comportamiento en [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2058-103">Activities are the core unit of behavior in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="d2058-104">La lógica de ejecución de una actividad se puede implementar en un código administrado o mediante otras actividades.</span><span class="sxs-lookup"><span data-stu-id="d2058-104">The execution logic of an activity can be implemented in managed code or it can be implemented by using other activities.</span></span> <span data-ttu-id="d2058-105">Este tema muestra cómo crear dos actividades.</span><span class="sxs-lookup"><span data-stu-id="d2058-105">This topic demonstrates how to create two activities.</span></span> <span data-ttu-id="d2058-106">La primera actividad es una actividad simple que usa código para implementar la lógica de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d2058-106">The first activity is a simple activity that uses code to implement its execution logic.</span></span> <span data-ttu-id="d2058-107">La implementación de la segunda actividad se define mediante otras actividades.</span><span class="sxs-lookup"><span data-stu-id="d2058-107">The implementation of the second activity is defined by using other activities.</span></span> <span data-ttu-id="d2058-108">Estas actividades se usan en los siguientes pasos del tutorial.</span><span class="sxs-lookup"><span data-stu-id="d2058-108">These activities are used in following steps in the tutorial.</span></span>

> [!NOTE]
> <span data-ttu-id="d2058-109">Para descargar una versión completada del tutorial, consulte [Windows Workflow Foundation (WF45): Tutorial de introducción](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="d2058-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="create-the-activity-library-project"></a><span data-ttu-id="d2058-110">Crear el proyecto de biblioteca de actividades</span><span class="sxs-lookup"><span data-stu-id="d2058-110">Create the activity library project</span></span>

1.  <span data-ttu-id="d2058-111">Abra Visual Studio y elija **New** > **proyecto** desde el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="d2058-111">Open Visual Studio and choose **New** > **Project** from the **File** menu.</span></span>

2.  <span data-ttu-id="d2058-112">En el **nuevo proyecto** cuadro de diálogo, en el **instalado** categoría, seleccione **Visual C#** > **flujo de trabajo** (o **Visual Basic** > **flujo de trabajo**).</span><span class="sxs-lookup"><span data-stu-id="d2058-112">In the **New Project** dialog, under the **Installed** category, select **Visual C#** > **Workflow** (or **Visual Basic** > **Workflow**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2058-113">Si no ve el **flujo de trabajo** categoría de plantilla, es posible que deba instalar el **Windows Workflow Foundation** componente de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d2058-113">If you don't see the **Workflow** template category, you may need to install the **Windows Workflow Foundation** component of Visual Studio.</span></span> <span data-ttu-id="d2058-114">Elija la **abrir Visual Studio Installer** vínculo en el lado izquierdo de la **nuevo proyecto** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d2058-114">Choose the **Open Visual Studio Installer** link on the left-hand side of the **New Project** dialog.</span></span> <span data-ttu-id="d2058-115">En el instalador de Visual Studio, seleccione el **componentes individuales** ficha. A continuación, en el **las actividades de desarrollo** categoría, seleccione el **Windows Workflow Foundation** componente.</span><span class="sxs-lookup"><span data-stu-id="d2058-115">In Visual Studio Installer, select the **Individual components** tab. Then, under the **Development activities** category, select the **Windows Workflow Foundation** component.</span></span> <span data-ttu-id="d2058-116">Elija **modificar** para instalar el componente.</span><span class="sxs-lookup"><span data-stu-id="d2058-116">Choose **Modify** to install the component.</span></span>

3. <span data-ttu-id="d2058-117">Seleccione el **biblioteca de actividades** plantilla de proyecto.</span><span class="sxs-lookup"><span data-stu-id="d2058-117">Select the **Activity Library** project template.</span></span> <span data-ttu-id="d2058-118">Tipo `NumberGuessWorkflowActivities` en el **nombre** cuadro y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d2058-118">Type `NumberGuessWorkflowActivities` in the **Name** box and then click **OK**.</span></span>

4.  <span data-ttu-id="d2058-119">Haga clic en **Activity1.xaml** en **el Explorador de soluciones** y elija **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d2058-119">Right-click **Activity1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="d2058-120">Haga clic en **Aceptar** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="d2058-120">Click **OK** to confirm.</span></span>

## <a name="create-the-readint-activity"></a><span data-ttu-id="d2058-121">Creación de la actividad ReadInt</span><span class="sxs-lookup"><span data-stu-id="d2058-121">Create the ReadInt activity</span></span>

1.  <span data-ttu-id="d2058-122">Elija **Agregar nuevo elemento** desde el **proyecto** menú.</span><span class="sxs-lookup"><span data-stu-id="d2058-122">Choose **Add New Item** from the **Project** menu.</span></span>

2.  <span data-ttu-id="d2058-123">En el **instalado** > **elementos comunes** nodo, seleccione **flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="d2058-123">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="d2058-124">Seleccione **actividad Code** desde el **flujo de trabajo** lista.</span><span class="sxs-lookup"><span data-stu-id="d2058-124">Select **Code Activity** from the **Workflow** list.</span></span>

3.  <span data-ttu-id="d2058-125">Tipo `ReadInt` en el **nombre** cuadro y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="d2058-125">Type `ReadInt` into the **Name** box and then click **Add**.</span></span>

4.  <span data-ttu-id="d2058-126">Reemplace la definición de `ReadInt` existente con la siguiente.</span><span class="sxs-lookup"><span data-stu-id="d2058-126">Replace the existing `ReadInt` definition with the following definition.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]

    > [!NOTE]
    > <span data-ttu-id="d2058-127">La actividad `ReadInt` se deriva de <xref:System.Activities.NativeActivity%601> en lugar de <xref:System.Activities.CodeActivity>, que es el valor predeterminado para la plantilla de actividades de código.</span><span class="sxs-lookup"><span data-stu-id="d2058-127">The `ReadInt` activity derives from <xref:System.Activities.NativeActivity%601> instead of <xref:System.Activities.CodeActivity>, which is the default for the code activity template.</span></span> <span data-ttu-id="d2058-128"><xref:System.Activities.CodeActivity%601> puede usarse si la actividad proporciona un único resultado, que se expone a través del argumento <xref:System.Activities.Activity%601.Result%2A>, pero <xref:System.Activities.CodeActivity%601> no admite el uso de marcadores, por lo que se usa <xref:System.Activities.NativeActivity%601>.</span><span class="sxs-lookup"><span data-stu-id="d2058-128"><xref:System.Activities.CodeActivity%601> can be used if the activity provides a single result, which is exposed through the <xref:System.Activities.Activity%601.Result%2A> argument, but <xref:System.Activities.CodeActivity%601> does not support the use of bookmarks, so <xref:System.Activities.NativeActivity%601> is used.</span></span>

## <a name="create-the-prompt-activity"></a><span data-ttu-id="d2058-129">Creación de la actividad Prompt</span><span class="sxs-lookup"><span data-stu-id="d2058-129">Create the Prompt activity</span></span>

1.  <span data-ttu-id="d2058-130">Presione **Ctrl**+**MAYÚS**+**B** para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d2058-130">Press **Ctrl**+**Shift**+**B** to build the project.</span></span> <span data-ttu-id="d2058-131">La compilación del proyecto permite que la actividad `ReadInt` de este proyecto se use para compilar la actividad personalizada de este paso.</span><span class="sxs-lookup"><span data-stu-id="d2058-131">Building the project enables the `ReadInt` activity in this project to be used to build the custom activity from this step.</span></span>

2.  <span data-ttu-id="d2058-132">Elija **Agregar nuevo elemento** desde el **proyecto** menú.</span><span class="sxs-lookup"><span data-stu-id="d2058-132">Choose **Add New Item** from the **Project** menu.</span></span>

3.  <span data-ttu-id="d2058-133">En el **instalado** > **elementos comunes** nodo, seleccione **flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="d2058-133">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="d2058-134">Seleccione **actividad** desde el **flujo de trabajo** lista.</span><span class="sxs-lookup"><span data-stu-id="d2058-134">Select **Activity** from the **Workflow** list.</span></span>

4.  <span data-ttu-id="d2058-135">Tipo `Prompt` en el **nombre** cuadro y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="d2058-135">Type `Prompt` into the **Name** box and then click **Add**.</span></span>

5.  <span data-ttu-id="d2058-136">Haga doble clic en **Prompt.xaml** en **el Explorador de soluciones** para mostrarlo en el diseñador, si aún no se muestra.</span><span class="sxs-lookup"><span data-stu-id="d2058-136">Double-click **Prompt.xaml** in **Solution Explorer** to display it in the designer if it is not already displayed.</span></span>

6.  <span data-ttu-id="d2058-137">Haga clic en **argumentos** en el lado inferior izquierdo del Diseñador de actividad para mostrar el **argumentos** panel.</span><span class="sxs-lookup"><span data-stu-id="d2058-137">Click **Arguments** in the lower-left side of the activity designer to display the **Arguments** pane.</span></span>

7.  <span data-ttu-id="d2058-138">Haga clic en **crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="d2058-138">Click **Create Argument**.</span></span>

8.  <span data-ttu-id="d2058-139">Tipo `BookmarkName` en el **nombre** cuadro, seleccione **en** desde el **dirección** lista desplegable, seleccione **cadena** desde el **Tipo de argumento** lista desplegable y, a continuación, presione **ENTRAR** para guardar el argumento.</span><span class="sxs-lookup"><span data-stu-id="d2058-139">Type `BookmarkName` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

9. <span data-ttu-id="d2058-140">Haga clic en **crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="d2058-140">Click **Create Argument**.</span></span>

10. <span data-ttu-id="d2058-141">Tipo `Result` en el **nombre** cuadro situado debajo de la recién agregada `BookmarkName` argumento, seleccione **Out** desde el **dirección** lista desplegable, seleccione **Int32** desde el **tipo de argumento** lista desplegable y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="d2058-141">Type `Result` into the **Name** box that is underneath the newly added `BookmarkName` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press **Enter**.</span></span>

11. <span data-ttu-id="d2058-142">Haga clic en **crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="d2058-142">Click **Create Argument**.</span></span>

12. <span data-ttu-id="d2058-143">Tipo `Text` en el **nombre** cuadro, seleccione **en** desde el **dirección** lista desplegable, seleccione **cadena** desde el **Tipo de argumento** lista desplegable y, a continuación, presione **ENTRAR** para guardar el argumento.</span><span class="sxs-lookup"><span data-stu-id="d2058-143">Type `Text` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

     <span data-ttu-id="d2058-144">Estos tres argumentos se enlazan a los argumentos correspondientes de las actividades <xref:System.Activities.Statements.WriteLine> y `ReadInt` que se agregan a la actividad `Prompt` en los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="d2058-144">These three arguments are bound to the corresponding arguments of the <xref:System.Activities.Statements.WriteLine> and `ReadInt` activities that are added to the `Prompt` activity in the following steps.</span></span>

13. <span data-ttu-id="d2058-145">Haga clic en **argumentos** en el lado inferior izquierdo del Diseñador de actividad para cerrar el **argumentos** panel.</span><span class="sxs-lookup"><span data-stu-id="d2058-145">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

14. <span data-ttu-id="d2058-146">Arrastre un **secuencia** actividad desde la **flujo de Control** sección de la **cuadro de herramientas** y colóquela en la **colocar actividad aquí** etiqueta de la **Prompt** Diseñador de actividad.</span><span class="sxs-lookup"><span data-stu-id="d2058-146">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Prompt** activity designer.</span></span>

    > [!TIP]
    > <span data-ttu-id="d2058-147">Si el **cuadro de herramientas** no se muestra la ventana, seleccione **cuadro de herramientas** desde el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="d2058-147">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

15. <span data-ttu-id="d2058-148">Arrastre un **WriteLine** actividad desde la **primitivas** sección de la **cuadro de herramientas** y colóquela en la **colocar actividad aquí** etiqueta de la **Secuencia** actividad.</span><span class="sxs-lookup"><span data-stu-id="d2058-148">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Sequence** activity.</span></span>

16. <span data-ttu-id="d2058-149">Enlazar el **texto** argumento de la **WriteLine** actividad a la **texto** argumento de la **Prompt** actividad escribiendo `Text` en el **escriba una expresión de C#** o **escriba una expresión de VB** cuadro el **propiedades** ventana y, a continuación, presione el **ficha** clave de dos veces.</span><span class="sxs-lookup"><span data-stu-id="d2058-149">Bind the **Text** argument of the **WriteLine** activity to the **Text** argument of the **Prompt** activity by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box in the **Properties** window, and then press the **Tab** key two times.</span></span> <span data-ttu-id="d2058-150">Esto descarta la ventana de miembros de la lista de IntelliSense y guarda el valor de propiedad moviendo la selección fuera de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="d2058-150">This dismisses the IntelliSense list members window and saves the property value by moving the selection off the property.</span></span> <span data-ttu-id="d2058-151">Esta propiedad también puede establecerse escribiendo `Text` en el **escriba una expresión de C#** o **escriba una expresión de VB** cuadro en la propia actividad.</span><span class="sxs-lookup"><span data-stu-id="d2058-151">This property can also be set by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box on the activity itself.</span></span>

    > [!TIP]
    > <span data-ttu-id="d2058-152">Si el **ventana propiedades** no se muestra, seleccione **ventana propiedades** desde el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="d2058-152">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

17. <span data-ttu-id="d2058-153">Arrastre un **ReadInt** actividad desde la **NumberGuessWorkflowActivities** sección de la **cuadro de herramientas** y colóquelo el **secuencia** actividad para que siga a la **WriteLine** actividad.</span><span class="sxs-lookup"><span data-stu-id="d2058-153">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the **WriteLine** activity.</span></span>

18. <span data-ttu-id="d2058-154">Enlazar el **BookmarkName** argumento de la **ReadInt** actividad a la **BookmarkName** argumento de la **Prompt** actividad escribiendo `BookmarkName` en el **escriba una expresión de VB** cuadro a la derecha de la **BookmarkName** argumento en el **ventana propiedades**y, a continuación, presione el **Ficha** dos veces para cerrar la ventana de IntelliSense lista de miembros y guardar la propiedad de clave.</span><span class="sxs-lookup"><span data-stu-id="d2058-154">Bind the **BookmarkName** argument of the **ReadInt** activity to the **BookmarkName** argument of the **Prompt** activity by typing `BookmarkName` into the **Enter a VB expression** box to the right of the **BookmarkName** argument in the **Properties Window**, and then press the **Tab** key two times to close the IntelliSense list members window and save the property.</span></span>

19. <span data-ttu-id="d2058-155">Enlazar el **resultado** argumento de la **ReadInt** actividad a la **resultado** argumento de la **Prompt** actividad escribiendo `Result` en el **escriba una expresión de VB** cuadro a la derecha de la **resultado** argumento en el **ventana propiedades**y, a continuación, presione el **ficha** clave dos veces.</span><span class="sxs-lookup"><span data-stu-id="d2058-155">Bind the **Result** argument of the **ReadInt** activity to the **Result** argument of the **Prompt** activity by typing `Result` into the **Enter a VB expression** box to the right of the **Result** argument in the **Properties Window**, and then press the **Tab** key two times.</span></span>

20. <span data-ttu-id="d2058-156">Presione **Ctrl**+**MAYÚS**+**B** para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="d2058-156">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d2058-157">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d2058-157">Next steps</span></span>

<span data-ttu-id="d2058-158">Para obtener instrucciones sobre cómo crear un flujo de trabajo mediante el uso de estas actividades, vea el paso siguiente en el tutorial, [Cómo: crear un flujo de trabajo](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="d2058-158">For instructions on how to create a workflow by using these activities, see the next step in the tutorial, [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d2058-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2058-159">See also</span></span>

- <xref:System.Activities.CodeActivity>
- <xref:System.Activities.NativeActivity%601>
- [<span data-ttu-id="d2058-160">Diseño e implementación de actividades personalizadas</span><span class="sxs-lookup"><span data-stu-id="d2058-160">Designing and Implementing Custom Activities</span></span>](../../../docs/framework/windows-workflow-foundation/designing-and-implementing-custom-activities.md)
- [<span data-ttu-id="d2058-161">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="d2058-161">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)
- [<span data-ttu-id="d2058-162">Cómo crear un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="d2058-162">How to: Create a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)
- [<span data-ttu-id="d2058-163">Uso de ExpressionTextBox en un diseñador de actividad personalizado</span><span class="sxs-lookup"><span data-stu-id="d2058-163">Using the ExpressionTextBox in a Custom Activity Designer</span></span>](../../../docs/framework/windows-workflow-foundation/samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)