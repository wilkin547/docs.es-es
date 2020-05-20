---
title: Procedimiento para crear una actividad
description: 'En este artículo se muestra cómo crear dos actividades en Workflow Foundation: una que usa código para implementar su lógica y otra definida mediante otras actividades.'
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: dae099d102b0c85d09a1ef8bcce56e8a9096bd20
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419595"
---
# <a name="how-to-create-an-activity"></a><span data-ttu-id="997f4-103">Procedimiento para crear una actividad</span><span class="sxs-lookup"><span data-stu-id="997f4-103">How to: Create an Activity</span></span>

<span data-ttu-id="997f4-104">Las actividades son la unidad básica de comportamiento en [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="997f4-104">Activities are the core unit of behavior in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="997f4-105">La lógica de ejecución de una actividad se puede implementar en un código administrado o mediante otras actividades.</span><span class="sxs-lookup"><span data-stu-id="997f4-105">The execution logic of an activity can be implemented in managed code or it can be implemented by using other activities.</span></span> <span data-ttu-id="997f4-106">Este tema muestra cómo crear dos actividades.</span><span class="sxs-lookup"><span data-stu-id="997f4-106">This topic demonstrates how to create two activities.</span></span> <span data-ttu-id="997f4-107">La primera actividad es una actividad simple que usa código para implementar la lógica de ejecución.</span><span class="sxs-lookup"><span data-stu-id="997f4-107">The first activity is a simple activity that uses code to implement its execution logic.</span></span> <span data-ttu-id="997f4-108">La implementación de la segunda actividad se define mediante otras actividades.</span><span class="sxs-lookup"><span data-stu-id="997f4-108">The implementation of the second activity is defined by using other activities.</span></span> <span data-ttu-id="997f4-109">Estas actividades se usan en los siguientes pasos del tutorial.</span><span class="sxs-lookup"><span data-stu-id="997f4-109">These activities are used in following steps in the tutorial.</span></span>

> [!NOTE]
> <span data-ttu-id="997f4-110">Para descargar una versión completa del tutorial, consulte [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45): tutorial introductorio)](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="997f4-110">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="create-the-activity-library-project"></a><span data-ttu-id="997f4-111">Crear el proyecto de biblioteca de actividades</span><span class="sxs-lookup"><span data-stu-id="997f4-111">Create the activity library project</span></span>

1. <span data-ttu-id="997f4-112">Abra Visual Studio y elija **nuevo**  >  **proyecto** en el menú **archivo** .</span><span class="sxs-lookup"><span data-stu-id="997f4-112">Open Visual Studio and choose **New** > **Project** from the **File** menu.</span></span>

2. <span data-ttu-id="997f4-113">En el cuadro de diálogo **nuevo proyecto** , en la categoría **instalado** , seleccione flujo de trabajo de **Visual C#**  >  **Workflow** (o **Visual Basic**  >  **flujo de trabajo**).</span><span class="sxs-lookup"><span data-stu-id="997f4-113">In the **New Project** dialog, under the **Installed** category, select **Visual C#** > **Workflow** (or **Visual Basic** > **Workflow**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="997f4-114">Si no ve la categoría de la plantilla de **flujo de trabajo** , es posible que deba instalar el componente de **Windows Workflow Foundation** de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="997f4-114">If you don't see the **Workflow** template category, you may need to install the **Windows Workflow Foundation** component of Visual Studio.</span></span> <span data-ttu-id="997f4-115">Elija el vínculo **abrir instalador de Visual Studio** en el lado izquierdo del cuadro de diálogo **nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="997f4-115">Choose the **Open Visual Studio Installer** link on the left-hand side of the **New Project** dialog.</span></span> <span data-ttu-id="997f4-116">En Instalador de Visual Studio, seleccione la pestaña **componentes individuales** . A continuación, en la categoría **actividades de desarrollo** , seleccione el componente **Windows Workflow Foundation** .</span><span class="sxs-lookup"><span data-stu-id="997f4-116">In Visual Studio Installer, select the **Individual components** tab. Then, under the **Development activities** category, select the **Windows Workflow Foundation** component.</span></span> <span data-ttu-id="997f4-117">Elija **modificar** para instalar el componente.</span><span class="sxs-lookup"><span data-stu-id="997f4-117">Choose **Modify** to install the component.</span></span>

3. <span data-ttu-id="997f4-118">Seleccione la plantilla de proyecto **biblioteca de actividades** .</span><span class="sxs-lookup"><span data-stu-id="997f4-118">Select the **Activity Library** project template.</span></span> <span data-ttu-id="997f4-119">Escriba `NumberGuessWorkflowActivities` en el cuadro **Nombre** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="997f4-119">Type `NumberGuessWorkflowActivities` in the **Name** box and then click **OK**.</span></span>

4. <span data-ttu-id="997f4-120">Haga clic con el botón secundario en **Activity1.xaml** en el **Explorador de soluciones** y elija **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="997f4-120">Right-click **Activity1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="997f4-121">Haga clic en **Aceptar** para confirmar la operación.</span><span class="sxs-lookup"><span data-stu-id="997f4-121">Click **OK** to confirm.</span></span>

## <a name="create-the-readint-activity"></a><span data-ttu-id="997f4-122">Crear la actividad ReadInt</span><span class="sxs-lookup"><span data-stu-id="997f4-122">Create the ReadInt activity</span></span>

1. <span data-ttu-id="997f4-123">Elija **Agregar nuevo elemento** en el menú **proyecto** .</span><span class="sxs-lookup"><span data-stu-id="997f4-123">Choose **Add New Item** from the **Project** menu.</span></span>

2. <span data-ttu-id="997f4-124">En el **Installed**  >  nodo**elementos comunes** instalados, seleccione **flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="997f4-124">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="997f4-125">Seleccione **actividad de código** en la lista **flujo de trabajo** .</span><span class="sxs-lookup"><span data-stu-id="997f4-125">Select **Code Activity** from the **Workflow** list.</span></span>

3. <span data-ttu-id="997f4-126">Escriba `ReadInt` en el cuadro **Nombre** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="997f4-126">Type `ReadInt` into the **Name** box and then click **Add**.</span></span>

4. <span data-ttu-id="997f4-127">Reemplace la definición de `ReadInt` existente con la siguiente.</span><span class="sxs-lookup"><span data-stu-id="997f4-127">Replace the existing `ReadInt` definition with the following definition.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]

    > [!NOTE]
    > <span data-ttu-id="997f4-128">La actividad `ReadInt` se deriva de <xref:System.Activities.NativeActivity%601> en lugar de <xref:System.Activities.CodeActivity>, que es el valor predeterminado para la plantilla de actividades de código.</span><span class="sxs-lookup"><span data-stu-id="997f4-128">The `ReadInt` activity derives from <xref:System.Activities.NativeActivity%601> instead of <xref:System.Activities.CodeActivity>, which is the default for the code activity template.</span></span> <span data-ttu-id="997f4-129"><xref:System.Activities.CodeActivity%601> puede usarse si la actividad proporciona un único resultado, que se expone a través del argumento <xref:System.Activities.Activity%601.Result%2A>, pero <xref:System.Activities.CodeActivity%601> no admite el uso de marcadores, por lo que se usa <xref:System.Activities.NativeActivity%601>.</span><span class="sxs-lookup"><span data-stu-id="997f4-129"><xref:System.Activities.CodeActivity%601> can be used if the activity provides a single result, which is exposed through the <xref:System.Activities.Activity%601.Result%2A> argument, but <xref:System.Activities.CodeActivity%601> does not support the use of bookmarks, so <xref:System.Activities.NativeActivity%601> is used.</span></span>

## <a name="create-the-prompt-activity"></a><span data-ttu-id="997f4-130">Crear la actividad prompt</span><span class="sxs-lookup"><span data-stu-id="997f4-130">Create the Prompt activity</span></span>

1. <span data-ttu-id="997f4-131">Presione **Ctrl** + **MAYÚS** + **B** para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="997f4-131">Press **Ctrl**+**Shift**+**B** to build the project.</span></span> <span data-ttu-id="997f4-132">La compilación del proyecto permite que la actividad `ReadInt` de este proyecto se use para compilar la actividad personalizada de este paso.</span><span class="sxs-lookup"><span data-stu-id="997f4-132">Building the project enables the `ReadInt` activity in this project to be used to build the custom activity from this step.</span></span>

2. <span data-ttu-id="997f4-133">Elija **Agregar nuevo elemento** en el menú **proyecto** .</span><span class="sxs-lookup"><span data-stu-id="997f4-133">Choose **Add New Item** from the **Project** menu.</span></span>

3. <span data-ttu-id="997f4-134">En el **Installed**  >  nodo**elementos comunes** instalados, seleccione **flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="997f4-134">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="997f4-135">Seleccione **Actividad** en la lista **Flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="997f4-135">Select **Activity** from the **Workflow** list.</span></span>

4. <span data-ttu-id="997f4-136">Escriba `Prompt` en el cuadro **Nombre** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="997f4-136">Type `Prompt` into the **Name** box and then click **Add**.</span></span>

5. <span data-ttu-id="997f4-137">Haga doble clic en **prompt. Xaml** en **Explorador de soluciones** para mostrarlo en el diseñador si aún no se muestra.</span><span class="sxs-lookup"><span data-stu-id="997f4-137">Double-click **Prompt.xaml** in **Solution Explorer** to display it in the designer if it is not already displayed.</span></span>

6. <span data-ttu-id="997f4-138">Haga clic en **Argumentos** en el lado inferior izquierdo del Diseñador de actividad para mostrar el panel **Argumentos**.</span><span class="sxs-lookup"><span data-stu-id="997f4-138">Click **Arguments** in the lower-left side of the activity designer to display the **Arguments** pane.</span></span>

7. <span data-ttu-id="997f4-139">Haga clic en **Crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="997f4-139">Click **Create Argument**.</span></span>

8. <span data-ttu-id="997f4-140">Escriba `BookmarkName` en el cuadro **nombre** , seleccione **en en** la lista desplegable **Dirección** , seleccione **cadena** en la lista desplegable **tipo de argumento** y, a continuación, presione **entrar** para guardar el argumento.</span><span class="sxs-lookup"><span data-stu-id="997f4-140">Type `BookmarkName` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

9. <span data-ttu-id="997f4-141">Haga clic en **Crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="997f4-141">Click **Create Argument**.</span></span>

10. <span data-ttu-id="997f4-142">Escriba `Result` en el cuadro **nombre** que se encuentra debajo del argumento recién agregado `BookmarkName` , seleccione **salida** en la lista desplegable **Dirección** , seleccione **Int32** en la lista desplegable **tipo de argumento** y, a continuación, presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="997f4-142">Type `Result` into the **Name** box that is underneath the newly added `BookmarkName` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press **Enter**.</span></span>

11. <span data-ttu-id="997f4-143">Haga clic en **Crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="997f4-143">Click **Create Argument**.</span></span>

12. <span data-ttu-id="997f4-144">Escriba `Text` en el cuadro **nombre** , seleccione **en en** la lista desplegable **Dirección** , seleccione **cadena** en la lista desplegable **tipo de argumento** y, a continuación, presione **entrar** para guardar el argumento.</span><span class="sxs-lookup"><span data-stu-id="997f4-144">Type `Text` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

     <span data-ttu-id="997f4-145">Estos tres argumentos se enlazan a los argumentos correspondientes de las actividades <xref:System.Activities.Statements.WriteLine> y `ReadInt` que se agregan a la actividad `Prompt` en los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="997f4-145">These three arguments are bound to the corresponding arguments of the <xref:System.Activities.Statements.WriteLine> and `ReadInt` activities that are added to the `Prompt` activity in the following steps.</span></span>

13. <span data-ttu-id="997f4-146">Haga clic en **Argumentos** en el lado inferior izquierdo del Diseñador de actividad para cerrar el panel **Argumentos**.</span><span class="sxs-lookup"><span data-stu-id="997f4-146">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

14. <span data-ttu-id="997f4-147">Arrastre una actividad **Sequence** de la sección **flujo de control** del **cuadro de herramientas** y colóquela en la etiqueta **colocar actividad aquí** del diseñador de actividad **prompt** .</span><span class="sxs-lookup"><span data-stu-id="997f4-147">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Prompt** activity designer.</span></span>

    > [!TIP]
    > <span data-ttu-id="997f4-148">Si no está visible la ventana **Cuadro de herramientas**, seleccione **Cuadro de herramientas** en el menú **Ver**.</span><span class="sxs-lookup"><span data-stu-id="997f4-148">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

15. <span data-ttu-id="997f4-149">Arrastre una **actividad WriteLine** de la sección **primitivas** del **cuadro de herramientas** y colóquela en la etiqueta **colocar actividad aquí** de la actividad **Sequence** .</span><span class="sxs-lookup"><span data-stu-id="997f4-149">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Sequence** activity.</span></span>

16. <span data-ttu-id="997f4-150">Enlace el argumento de **texto** de la actividad **WriteLine** al argumento de **texto** de la actividad **prompt** escribiendo `Text` en el cuadro **Escriba una expresión de C#** o **Escriba una expresión de VB** en la ventana **propiedades** y, a continuación, presione la tecla **Tab** dos veces.</span><span class="sxs-lookup"><span data-stu-id="997f4-150">Bind the **Text** argument of the **WriteLine** activity to the **Text** argument of the **Prompt** activity by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box in the **Properties** window, and then press the **Tab** key two times.</span></span> <span data-ttu-id="997f4-151">Esto descarta la ventana de miembros de la lista de IntelliSense y guarda el valor de propiedad moviendo la selección fuera de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="997f4-151">This dismisses the IntelliSense list members window and saves the property value by moving the selection off the property.</span></span> <span data-ttu-id="997f4-152">Esta propiedad también se puede establecer escribiendo `Text` en el cuadro **Escriba una expresión de C#** o **Escriba una expresión de VB** en la propia actividad.</span><span class="sxs-lookup"><span data-stu-id="997f4-152">This property can also be set by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box on the activity itself.</span></span>

    > [!TIP]
    > <span data-ttu-id="997f4-153">Si no se muestra la **ventana Propiedades** , seleccione **ventana Propiedades** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="997f4-153">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

17. <span data-ttu-id="997f4-154">Arrastre una actividad **ReadInt** desde la sección **NumberGuessWorkflowActivities** del **cuadro de herramientas** y colóquela en la actividad **Sequence** para que siga la actividad **WriteLine** .</span><span class="sxs-lookup"><span data-stu-id="997f4-154">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the **WriteLine** activity.</span></span>

18. <span data-ttu-id="997f4-155">Enlace el **argumento bookmarkname** de la **actividad ReadInt** al argumento **bookmarkname** de la actividad **prompt** escribiendo `BookmarkName` en el cuadro **Escriba una expresión de VB** a la derecha del argumento **bookmarkname** en la **ventana Propiedades**y, a continuación, presione la tecla **Tab** dos veces para cerrar la ventana de lista de miembros de IntelliSense y guardar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="997f4-155">Bind the **BookmarkName** argument of the **ReadInt** activity to the **BookmarkName** argument of the **Prompt** activity by typing `BookmarkName` into the **Enter a VB expression** box to the right of the **BookmarkName** argument in the **Properties Window**, and then press the **Tab** key two times to close the IntelliSense list members window and save the property.</span></span>

19. <span data-ttu-id="997f4-156">Enlace el argumento **result** de la **actividad ReadInt** al argumento **result** de la actividad **prompt** escribiendo `Result` en el cuadro **Escriba una expresión de VB** a la derecha del argumento **result** en la **ventana Propiedades**y, a continuación, presione la tecla **Tab** dos veces.</span><span class="sxs-lookup"><span data-stu-id="997f4-156">Bind the **Result** argument of the **ReadInt** activity to the **Result** argument of the **Prompt** activity by typing `Result` into the **Enter a VB expression** box to the right of the **Result** argument in the **Properties Window**, and then press the **Tab** key two times.</span></span>

20. <span data-ttu-id="997f4-157">Presione **Ctrl** + **MAYÚS** + **B** para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="997f4-157">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="next-steps"></a><span data-ttu-id="997f4-158">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="997f4-158">Next steps</span></span>

<span data-ttu-id="997f4-159">Para obtener instrucciones sobre cómo crear un flujo de trabajo mediante estas actividades, vea el siguiente paso del tutorial, [Cómo: crear un flujo de trabajo](how-to-create-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="997f4-159">For instructions on how to create a workflow by using these activities, see the next step in the tutorial, [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="997f4-160">Consulta también</span><span class="sxs-lookup"><span data-stu-id="997f4-160">See also</span></span>

- <xref:System.Activities.CodeActivity>
- <xref:System.Activities.NativeActivity%601>
- [<span data-ttu-id="997f4-161">Diseñar e implementar actividades personalizadas</span><span class="sxs-lookup"><span data-stu-id="997f4-161">Designing and Implementing Custom Activities</span></span>](designing-and-implementing-custom-activities.md)
- [<span data-ttu-id="997f4-162">Tutorial de Introducción</span><span class="sxs-lookup"><span data-stu-id="997f4-162">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="997f4-163">Procedimiento para crear un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="997f4-163">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)
- [<span data-ttu-id="997f4-164">Uso de la ExpressionTextBox en un diseñador de actividad personalizado</span><span class="sxs-lookup"><span data-stu-id="997f4-164">Using the ExpressionTextBox in a Custom Activity Designer</span></span>](./samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
