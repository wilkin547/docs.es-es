---
title: "Cómo: Crear una actividad"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
caps.latest.revision: "39"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a3b9698d6a060120addff52e6600916a2de19fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-activity"></a><span data-ttu-id="cca90-102">Cómo: Crear una actividad</span><span class="sxs-lookup"><span data-stu-id="cca90-102">How to: Create an Activity</span></span>
<span data-ttu-id="cca90-103">Las actividades son la unidad básica de comportamiento en [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cca90-103">Activities are the core unit of behavior in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="cca90-104">La lógica de ejecución de una actividad se puede implementar en un código administrado o mediante otras actividades.</span><span class="sxs-lookup"><span data-stu-id="cca90-104">The execution logic of an activity can be implemented in managed code or it can be implemented by using other activities.</span></span> <span data-ttu-id="cca90-105">Este tema muestra cómo crear dos actividades.</span><span class="sxs-lookup"><span data-stu-id="cca90-105">This topic demonstrates how to create two activities.</span></span> <span data-ttu-id="cca90-106">La primera actividad es una actividad simple que usa código para implementar la lógica de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cca90-106">The first activity is a simple activity that uses code to implement its execution logic.</span></span> <span data-ttu-id="cca90-107">La implementación de la segunda actividad se define mediante otras actividades.</span><span class="sxs-lookup"><span data-stu-id="cca90-107">The implementation of the second activity is defined by using other activities.</span></span> <span data-ttu-id="cca90-108">Estas actividades se usan en los siguientes pasos del tutorial.</span><span class="sxs-lookup"><span data-stu-id="cca90-108">These activities are used in following steps in the tutorial.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cca90-109">Para descargar una versión completa del tutorial, consulte [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45): tutorial introductorio)](http://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="cca90-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-activity-library-project"></a><span data-ttu-id="cca90-110">Para crear el proyecto de biblioteca de actividades</span><span class="sxs-lookup"><span data-stu-id="cca90-110">To create the activity library project</span></span>  
  
1.  <span data-ttu-id="cca90-111">Abra [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] y elija **New**, **proyecto** desde el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="cca90-111">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] and choose **New**,  **Project** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="cca90-112">Expanda el **otros tipos de proyectos** nodo en el **instalado**, **plantillas** lista y seleccione **soluciones de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="cca90-112">Expand the **Other Project Types** node in the **Installed**, **Templates** list and select **Visual Studio Solutions**.</span></span>  
  
3.  <span data-ttu-id="cca90-113">Seleccione **solución en blanco** desde el **soluciones de Visual Studio** lista.</span><span class="sxs-lookup"><span data-stu-id="cca90-113">Select **Blank Solution** from the **Visual Studio Solutions** list.</span></span> <span data-ttu-id="cca90-114">Asegúrese de que se haya seleccionado **.NET Framework 4.5** en la lista desplegable correspondiente a la versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cca90-114">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="cca90-115">Tipo de `WF45GettingStartedTutorial` en el **nombre** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cca90-115">Type `WF45GettingStartedTutorial` in the **Name** box and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="cca90-116">Haga clic en **WF45GettingStartedTutorial** en **el Explorador de soluciones** y elija **agregar**, **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="cca90-116">Right-click **WF45GettingStartedTutorial** in **Solution Explorer** and choose **Add**, **New Project**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="cca90-117">Si la ventana **Explorador de soluciones** no se muestra, seleccione **Explorador de soluciones** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="cca90-117">If the **Solution Explorer** window is not displayed, select **Solution Explorer** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="cca90-118">En el nodo **Instalado** , seleccione **Visual C#**, **Flujo de trabajo** (o **Visual Basic**, **Flujo de trabajo**).</span><span class="sxs-lookup"><span data-stu-id="cca90-118">In the **Installed** node, select **Visual C#**, **Workflow** (or **Visual Basic**, **Workflow**).</span></span> <span data-ttu-id="cca90-119">Asegúrese de que **.NET Framework 4.5** está seleccionado en el [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] lista desplegable de versión.</span><span class="sxs-lookup"><span data-stu-id="cca90-119">Ensure that **.NET Framework 4.5** is selected in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] version drop-down list.</span></span> <span data-ttu-id="cca90-120">Seleccione **biblioteca de actividades** desde el **flujo de trabajo** lista.</span><span class="sxs-lookup"><span data-stu-id="cca90-120">Select **Activity Library** from the **Workflow** list.</span></span> <span data-ttu-id="cca90-121">Tipo de `NumberGuessWorkflowActivities` en el **nombre** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cca90-121">Type `NumberGuessWorkflowActivities` in the **Name** box and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cca90-122">Función del lenguaje de programación que se configure como lenguaje principal en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], **Visual C#** o **Visual Basic** nodo puede estar bajo el **otros lenguajes**nodo en el **instalado** nodo.</span><span class="sxs-lookup"><span data-stu-id="cca90-122">Depending on which programming language is configured as the primary language in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>  
  
6.  <span data-ttu-id="cca90-123">Haga clic en **Activity1.xaml** en **el Explorador de soluciones** y elija **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="cca90-123">Right-click **Activity1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="cca90-124">Haga clic en **Aceptar** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="cca90-124">Click **OK** to confirm.</span></span>  
  
### <a name="to-create-the-readint-activity"></a><span data-ttu-id="cca90-125">Para crear la actividad ReadInt</span><span class="sxs-lookup"><span data-stu-id="cca90-125">To create the ReadInt activity</span></span>  
  
1.  <span data-ttu-id="cca90-126">Elija **Agregar nuevo elemento** desde el **proyecto** menú.</span><span class="sxs-lookup"><span data-stu-id="cca90-126">Choose **Add New Item** from the **Project** menu.</span></span>  
  
2.  <span data-ttu-id="cca90-127">En el **instalado**, **elementos comunes** nodo, seleccione **flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="cca90-127">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="cca90-128">Seleccione **actividad de código** desde el **flujo de trabajo** lista.</span><span class="sxs-lookup"><span data-stu-id="cca90-128">Select **Code Activity** from the **Workflow** list.</span></span>  
  
3.  <span data-ttu-id="cca90-129">Tipo de `ReadInt` en el **nombre** y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="cca90-129">Type `ReadInt` into the **Name** box and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="cca90-130">Reemplace la definición de `ReadInt` existente con la siguiente.</span><span class="sxs-lookup"><span data-stu-id="cca90-130">Replace the existing `ReadInt` definition with the following definition.</span></span>  
  
     [!code-csharp[CFX_WF_GettingStarted#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="cca90-131">La actividad `ReadInt` se deriva de <xref:System.Activities.NativeActivity%601> en lugar de <xref:System.Activities.CodeActivity>, que es el valor predeterminado para la plantilla de actividades de código.</span><span class="sxs-lookup"><span data-stu-id="cca90-131">The `ReadInt` activity derives from <xref:System.Activities.NativeActivity%601> instead of <xref:System.Activities.CodeActivity>, which is the default for the code activity template.</span></span> <span data-ttu-id="cca90-132"><xref:System.Activities.CodeActivity%601> puede usarse si la actividad proporciona un único resultado, que se expone a través del argumento <xref:System.Activities.Activity%601.Result%2A>, pero <xref:System.Activities.CodeActivity%601> no admite el uso de marcadores, por lo que se usa <xref:System.Activities.NativeActivity%601>.</span><span class="sxs-lookup"><span data-stu-id="cca90-132"><xref:System.Activities.CodeActivity%601> can be used if the activity provides a single result, which is exposed through the <xref:System.Activities.Activity%601.Result%2A> argument, but <xref:System.Activities.CodeActivity%601> does not support the use of bookmarks, so <xref:System.Activities.NativeActivity%601> is used.</span></span>  
  
### <a name="to-create-the-prompt-activity"></a><span data-ttu-id="cca90-133">Para crear la actividad Prompt</span><span class="sxs-lookup"><span data-stu-id="cca90-133">To create the Prompt activity</span></span>  
  
1.  <span data-ttu-id="cca90-134">Presione Ctrl+Mayús+B para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="cca90-134">Press CTRL+SHIFT+B to build the project.</span></span> <span data-ttu-id="cca90-135">La compilación del proyecto permite que la actividad `ReadInt` de este proyecto se use para compilar la actividad personalizada de este paso.</span><span class="sxs-lookup"><span data-stu-id="cca90-135">Building the project enables the `ReadInt` activity in this project to be used to build the custom activity from this step.</span></span>  
  
2.  <span data-ttu-id="cca90-136">Elija **Agregar nuevo elemento** desde el **proyecto** menú.</span><span class="sxs-lookup"><span data-stu-id="cca90-136">Choose **Add New Item** from the **Project** menu.</span></span>  
  
3.  <span data-ttu-id="cca90-137">En el **instalado**, **elementos comunes** nodo, seleccione **flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="cca90-137">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="cca90-138">Seleccione **actividad** desde el **flujo de trabajo** lista.</span><span class="sxs-lookup"><span data-stu-id="cca90-138">Select **Activity** from the **Workflow** list.</span></span>  
  
4.  <span data-ttu-id="cca90-139">Tipo de `Prompt` en el **nombre** y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="cca90-139">Type `Prompt` into the **Name** box and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="cca90-140">Haga doble clic en **Prompt.xaml** en **el Explorador de soluciones** para mostrarlo en el diseñador si no está ya visible.</span><span class="sxs-lookup"><span data-stu-id="cca90-140">Double-click **Prompt.xaml** in **Solution Explorer** to display it in the designer if it is not already displayed.</span></span>  
  
6.  <span data-ttu-id="cca90-141">Haga clic en **argumentos** en la parte inferior izquierda del Diseñador de actividad para mostrar el **argumentos** panel.</span><span class="sxs-lookup"><span data-stu-id="cca90-141">Click **Arguments** in the lower-left side of the activity designer to display the **Arguments** pane.</span></span>  
  
7.  <span data-ttu-id="cca90-142">Haga clic en **crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="cca90-142">Click **Create Argument**.</span></span>  
  
8.  <span data-ttu-id="cca90-143">Tipo de `BookmarkName` en el **nombre** cuadro, seleccione **en** desde el **dirección** lista desplegable, seleccione **cadena** desde el **Tipo de argumento** lista desplegable y, a continuación, presione ENTRAR para guardar el argumento.</span><span class="sxs-lookup"><span data-stu-id="cca90-143">Type `BookmarkName` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
9. <span data-ttu-id="cca90-144">Haga clic en **crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="cca90-144">Click **Create Argument**.</span></span>  
  
10. <span data-ttu-id="cca90-145">Tipo de `Result` en el **nombre** cuadro que se encuentra debajo de la recién agregado `BookmarkName` argumento, seleccione **Out** desde el **dirección** lista desplegable, seleccione **Int32** desde el **tipo de argumento** lista desplegable y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="cca90-145">Type `Result` into the **Name** box that is underneath the newly added `BookmarkName` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
11. <span data-ttu-id="cca90-146">Haga clic en **crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="cca90-146">Click **Create Argument**.</span></span>  
  
12. <span data-ttu-id="cca90-147">Tipo de `Text` en el **nombre** cuadro, seleccione **en** desde el **dirección** lista desplegable, seleccione **cadena** desde el **Tipo de argumento** lista desplegable y, a continuación, presione ENTRAR para guardar el argumento.</span><span class="sxs-lookup"><span data-stu-id="cca90-147">Type `Text` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
     <span data-ttu-id="cca90-148">Estos tres argumentos se enlazan a los argumentos correspondientes de las actividades <xref:System.Activities.Statements.WriteLine> y `ReadInt` que se agregan a la actividad `Prompt` en los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="cca90-148">These three arguments are bound to the corresponding arguments of the <xref:System.Activities.Statements.WriteLine> and `ReadInt` activities that are added to the `Prompt` activity in the following steps.</span></span>  
  
13. <span data-ttu-id="cca90-149">Haga clic en **argumentos** en la parte inferior izquierda del Diseñador de actividad para cerrar la **argumentos** panel.</span><span class="sxs-lookup"><span data-stu-id="cca90-149">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
14. <span data-ttu-id="cca90-150">Arrastre un **secuencia** actividad desde la **flujo de Control** sección de la **cuadro de herramientas** y colóquela en la **coloque la actividad aquí** etiqueta de la **Prompt** Diseñador de actividad.</span><span class="sxs-lookup"><span data-stu-id="cca90-150">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Prompt** activity designer.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="cca90-151">Si el **cuadro de herramientas** no se muestra la ventana, seleccione **cuadro de herramientas** desde el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="cca90-151">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
15. <span data-ttu-id="cca90-152">Arrastre un **WriteLine** actividad desde la **primitivas** sección de la **cuadro de herramientas** y colóquela en la **coloque la actividad aquí** etiqueta de la **Secuencia** actividad.</span><span class="sxs-lookup"><span data-stu-id="cca90-152">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Sequence** activity.</span></span>  
  
16. <span data-ttu-id="cca90-153">Enlazar el **texto** argumento de la **WriteLine** actividad para la **texto** argumento de la **Prompt** actividad escribiendo `Text` en el **escriba una expresión de C#** o **escriba una expresión de VB** cuadro el **propiedades** ventana y, a continuación, presione la PESTAÑA clave dos veces.</span><span class="sxs-lookup"><span data-stu-id="cca90-153">Bind the **Text** argument of the **WriteLine** activity to the **Text** argument of the **Prompt** activity by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box in the **Properties** window, and then press the TAB key two times.</span></span> <span data-ttu-id="cca90-154">Esto descarta la ventana de miembros de la lista de IntelliSense y guarda el valor de propiedad moviendo la selección fuera de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="cca90-154">This dismisses the IntelliSense list members window and saves the property value by moving the selection off the property.</span></span> <span data-ttu-id="cca90-155">Esta propiedad también puede establecerse escribiendo `Text` en el **escriba una expresión de C#** o **escriba una expresión de VB** cuadro en la propia actividad.</span><span class="sxs-lookup"><span data-stu-id="cca90-155">This property can also be set by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box on the activity itself.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="cca90-156">Si el **ventana propiedades** no se muestra, seleccione **ventana propiedades** desde el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="cca90-156">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
17. <span data-ttu-id="cca90-157">Arrastre un **ReadInt** actividad desde la **NumberGuessWorkflowActivities** sección de la **cuadro de herramientas** y colóquelo el **secuencia** actividad para que siga a la **WriteLine** actividad.</span><span class="sxs-lookup"><span data-stu-id="cca90-157">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the **WriteLine** activity.</span></span>  
  
18. <span data-ttu-id="cca90-158">Enlazar el **BookmarkName** argumento de la **ReadInt** actividad para la **BookmarkName** argumento de la **Prompt** actividad escribiendo `BookmarkName` en el **escriba una expresión de VB** cuadro a la derecha de la **BookmarkName** argumento en el **ventana propiedades**y, a continuación, presione la tecla TAB dos el tiempo de espera para cerrar la ventana de IntelliSense lista de miembros y guardar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="cca90-158">Bind the **BookmarkName** argument of the **ReadInt** activity to the **BookmarkName** argument of the **Prompt** activity by typing `BookmarkName` into the **Enter a VB expression** box to the right of the **BookmarkName** argument in the **Properties Window**, and then press the TAB key two times to close the IntelliSense list members window and save the property.</span></span>  
  
19. <span data-ttu-id="cca90-159">Enlazar el **resultado** argumento de la **ReadInt** actividad para la **resultado** argumento de la **Prompt** actividad escribiendo `Result` en el **escriba una expresión de VB** cuadro a la derecha de la **resultado** argumento en el **ventana propiedades**y, a continuación, presione la tecla TAB dos veces.</span><span class="sxs-lookup"><span data-stu-id="cca90-159">Bind the **Result** argument of the **ReadInt** activity to the **Result** argument of the **Prompt** activity by typing `Result` into the **Enter a VB expression** box to the right of the **Result** argument in the **Properties Window**, and then press the TAB key two times.</span></span>  
  
20. <span data-ttu-id="cca90-160">Presione Ctrl+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="cca90-160">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="cca90-161">Para obtener instrucciones sobre cómo crear un flujo de trabajo mediante el uso de estas actividades, vea el paso siguiente en el tutorial, [Cómo: crear un flujo de trabajo](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="cca90-161">For instructions on how to create a workflow by using these activities, see the next step in the tutorial, [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cca90-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="cca90-162">See Also</span></span>  
 <xref:System.Activities.CodeActivity>  
 <xref:System.Activities.NativeActivity%601>  
 [<span data-ttu-id="cca90-163">Diseño e implementación de actividades personalizadas</span><span class="sxs-lookup"><span data-stu-id="cca90-163">Designing and Implementing Custom Activities</span></span>](../../../docs/framework/windows-workflow-foundation/designing-and-implementing-custom-activities.md)  
 [<span data-ttu-id="cca90-164">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="cca90-164">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [<span data-ttu-id="cca90-165">Cómo crear un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="cca90-165">How to: Create a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)  
 [<span data-ttu-id="cca90-166">Uso de ExpressionTextBox en un diseñador de actividad personalizado</span><span class="sxs-lookup"><span data-stu-id="cca90-166">Using the ExpressionTextBox in a Custom Activity Designer</span></span>](../../../docs/framework/windows-workflow-foundation/samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
