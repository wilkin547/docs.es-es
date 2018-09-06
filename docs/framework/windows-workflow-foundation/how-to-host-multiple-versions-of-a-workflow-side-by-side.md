---
title: Cómo hospedar varias versiones de un flujo de trabajo en paralelo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09c575df-e0a3-4f3b-9e01-a7ac59d65287
ms.openlocfilehash: 525aeab7ff08da95735e9c9df7f6f040e8b9e215
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856366"
---
# <a name="how-to-host-multiple-versions-of-a-workflow-side-by-side"></a><span data-ttu-id="4f662-102">Cómo hospedar varias versiones de un flujo de trabajo en paralelo</span><span class="sxs-lookup"><span data-stu-id="4f662-102">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>
<span data-ttu-id="4f662-103">`WorkflowIdentity` proporciona una manera para que los desarrolladores de aplicaciones de flujo de trabajo asocien un nombre y una versión con una definición de flujo de trabajo, y para que esta información se asocie a una instancia de flujo de trabajo persistente.</span><span class="sxs-lookup"><span data-stu-id="4f662-103">`WorkflowIdentity` provides a way for workflow application developers to associate a name and a version with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="4f662-104">Los desarrolladores de aplicaciones de flujo de trabajo pueden usar esta información de identidad para habilitar escenarios como la ejecución en paralelo de varias versiones de una definición de flujo de trabajo; además esta información proporciona la piedra angular para otras funcionalidades como la actualización dinámica.</span><span class="sxs-lookup"><span data-stu-id="4f662-104">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="4f662-105">Este paso del tutorial demuestra cómo usar `WorkflowIdentity` para hospedar varias versiones de un flujo de trabajo simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="4f662-105">This step in the tutorial demonstrates how to use `WorkflowIdentity` to host multiple versions of a workflow at the same time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f662-106">Para descargar una versión completada o ver un tutorial en vídeo del tutorial, vea [Windows Workflow Foundation (WF45): Tutorial de introducción](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="4f662-106">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-topic"></a><span data-ttu-id="4f662-107">En este tema</span><span class="sxs-lookup"><span data-stu-id="4f662-107">In this topic</span></span>  
 <span data-ttu-id="4f662-108">En este paso del tutorial, las actividades de `WriteLine` en el flujo de trabajo se modifican para proporcionar información adicional y se agrega una nueva actividad `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="4f662-108">In this step of the tutorial, the `WriteLine` activities in the workflow are modified to provide additional information, and a new `WriteLine` activity is added.</span></span> <span data-ttu-id="4f662-109">Una copia del ensamblado original de flujo de trabajo queda almacenada y la aplicación de host se actualiza de tal modo que puede ejecutar tanto el flujo de trabajo original como el actualizado al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="4f662-109">A copy of the original workflow assembly is stored, and the host application is updated so that it can run both the original and the updated workflows at the same time.</span></span>  
  
-   [<span data-ttu-id="4f662-110">Para realizar una copia del proyecto NumberGuessWorkflowActivities</span><span class="sxs-lookup"><span data-stu-id="4f662-110">To make a copy of the NumberGuessWorkflowActivities project</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BackupCopy)  
  
-   [<span data-ttu-id="4f662-111">Para actualizar los flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="4f662-111">To update the workflows</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflows)  
  
    -   [<span data-ttu-id="4f662-112">Para actualizar el flujo de trabajo StateMachine</span><span class="sxs-lookup"><span data-stu-id="4f662-112">To update the StateMachine workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateStateMachine)  
  
    -   [<span data-ttu-id="4f662-113">Para actualizar el flujo de trabajo de diagrama de flujo</span><span class="sxs-lookup"><span data-stu-id="4f662-113">To update the Flowchart workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateFlowchart)  
  
    -   [<span data-ttu-id="4f662-114">Para actualizar el flujo de trabajo secuencial</span><span class="sxs-lookup"><span data-stu-id="4f662-114">To update the Sequential workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateSequential)  
  
-   [<span data-ttu-id="4f662-115">Para actualizar WorkflowVersionMap para incluir las versiones anteriores del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="4f662-115">To update WorkflowVersionMap to include the previous workflow versions</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflowVersionMap)  
  
-   [<span data-ttu-id="4f662-116">Para compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="4f662-116">To build and run the application</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BuildAndRun)  
  
> [!NOTE]
>  <span data-ttu-id="4f662-117">Antes de seguir los pasos de este tema, ejecute la aplicación, inicie varios flujos de trabajo de cada tipo y realice uno o dos intentos con cada uno.</span><span class="sxs-lookup"><span data-stu-id="4f662-117">Before following the steps in this topic, run the application, start several workflows of each type, and making one or two guesses for each one.</span></span> <span data-ttu-id="4f662-118">Estos flujos de trabajo persistentes se usan en este paso y el paso siguiente, [Cómo: actualizar la definición de una instancia de flujo de trabajo ejecuta](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span><span class="sxs-lookup"><span data-stu-id="4f662-118">These persisted workflows are used in this step and the following step, [How to: Update the Definition of a Running Workflow Instance](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f662-119">Cada paso del tutorial de introducción depende de los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="4f662-119">Each step in the Getting Started tutorial depends on the previous steps.</span></span> <span data-ttu-id="4f662-120">Si no completó los pasos anteriores, puede descargar una versión completada del tutorial de [Windows Workflow Foundation (WF45): Tutorial de introducción](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="4f662-120">If you did not complete the previous steps you can download a completed version of the tutorial from [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
###  <a name="BKMK_BackupCopy"></a> <span data-ttu-id="4f662-121">Para realizar una copia del proyecto NumberGuessWorkflowActivities</span><span class="sxs-lookup"><span data-stu-id="4f662-121">To make a copy of the NumberGuessWorkflowActivities project</span></span>  
  
1.  <span data-ttu-id="4f662-122">Abra el **WF45GettingStartedTutorial** solución en [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] si no está abierto.</span><span class="sxs-lookup"><span data-stu-id="4f662-122">Open the **WF45GettingStartedTutorial** solution in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] if it is not open.</span></span>  
  
2.  <span data-ttu-id="4f662-123">Presione Ctrl+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="4f662-123">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="4f662-124">Cerrar la **WF45GettingStartedTutorial** solución.</span><span class="sxs-lookup"><span data-stu-id="4f662-124">Close the **WF45GettingStartedTutorial** solution.</span></span>  
  
4.  <span data-ttu-id="4f662-125">Abra el Explorador de Windows y navegue hasta la carpeta donde se encuentran el archivo de solución del tutorial y las carpetas de proyecto.</span><span class="sxs-lookup"><span data-stu-id="4f662-125">Open Windows Explorer and navigate to the folder where the tutorial solution file and the project folders are located.</span></span>  
  
5.  <span data-ttu-id="4f662-126">Cree una carpeta nueva denominada **PreviousVersions** en la misma carpeta que **NumberGuessWorkflowHost** y **NumberGuessWorkflowActivities**.</span><span class="sxs-lookup"><span data-stu-id="4f662-126">Create a new folder named **PreviousVersions** in the same folder as **NumberGuessWorkflowHost** and **NumberGuessWorkflowActivities**.</span></span> <span data-ttu-id="4f662-127">Esta carpeta se usa para guardar los ensamblados que contienen las distintas versiones de los flujos de trabajo usados en los pasos de tutorial posteriores.</span><span class="sxs-lookup"><span data-stu-id="4f662-127">This folder is used to contain the assemblies that contain the different versions of the workflows used in the subsequent tutorial steps.</span></span>  
  
6.  <span data-ttu-id="4f662-128">Navegue hasta la **NumberGuessWorkflowActivities\bin\debug** carpeta (o **bin\release** según la configuración del proyecto).</span><span class="sxs-lookup"><span data-stu-id="4f662-128">Navigate to the **NumberGuessWorkflowActivities\bin\debug** folder (or **bin\release** depending on your project settings).</span></span> <span data-ttu-id="4f662-129">Copia **NumberGuessWorkflowActivities.dll** y péguelo en el **PreviousVersions** carpeta.</span><span class="sxs-lookup"><span data-stu-id="4f662-129">Copy **NumberGuessWorkflowActivities.dll** and paste it into the **PreviousVersions** folder.</span></span>  
  
7.  <span data-ttu-id="4f662-130">Cambiar el nombre de **NumberGuessWorkflowActivities.dll** en el **PreviousVersions** carpeta **NumberGuessWorkflowActivities_v1.dll**.</span><span class="sxs-lookup"><span data-stu-id="4f662-130">Rename **NumberGuessWorkflowActivities.dll** in the **PreviousVersions** folder to **NumberGuessWorkflowActivities_v1.dll**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4f662-131">En los pasos de este tema se muestra una manera de administrar los ensamblados usados para contener varias versiones de los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4f662-131">The steps in this topic demonstrate one way to manage the assemblies used to contain multiple versions of the workflows.</span></span> <span data-ttu-id="4f662-132">También se pueden usar otros métodos, como el nombre seguro de los ensamblados y su registro en la memoria caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="4f662-132">Other methods such as strong naming the assemblies and registering them in the global assembly cache could also be used.</span></span>  
  
8.  <span data-ttu-id="4f662-133">Cree una carpeta nueva denominada **NumberGuessWorkflowActivities_du** en la misma carpeta que **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**y la recién agregar **PreviousVersions** carpeta y copie todos los archivos y subcarpetas de la **NumberGuessWorkflowActivities** carpeta en el nuevo  **NumberGuessWorkflowActivities_du** carpeta.</span><span class="sxs-lookup"><span data-stu-id="4f662-133">Create a new folder named **NumberGuessWorkflowActivities_du** in the same folder as **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**, and the newly added **PreviousVersions** folder, and copy all of the files and subfolders from the **NumberGuessWorkflowActivities** folder into the new **NumberGuessWorkflowActivities_du** folder.</span></span> <span data-ttu-id="4f662-134">Esta copia de seguridad del proyecto para la versión inicial de las actividades se usa en [Cómo: actualizar la definición de una instancia de flujo de trabajo ejecuta](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span><span class="sxs-lookup"><span data-stu-id="4f662-134">This backup copy of the project for the initial version of the activities is used in [How to: Update the Definition of a Running Workflow Instance](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>  
  
9. <span data-ttu-id="4f662-135">Vuelva a abrir el **WF45GettingStartedTutorial** solución en [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f662-135">Re-open the **WF45GettingStartedTutorial** solution in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span>  
  
###  <a name="BKMK_UpdateWorkflows"></a> <span data-ttu-id="4f662-136">Para actualizar los flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="4f662-136">To update the workflows</span></span>  
 <span data-ttu-id="4f662-137">En esta sección, se actualizan las definiciones de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4f662-137">In this section, the workflow definitions are updated.</span></span> <span data-ttu-id="4f662-138">Se actualizan las dos actividades de `WriteLine` que proporcionan informes sobre los intentos del usuario, y se agrega una nueva actividad `WriteLine` que proporciona información adicional sobre el juego una vez se ha adivinado el número.</span><span class="sxs-lookup"><span data-stu-id="4f662-138">The two `WriteLine` activities that give feedback on the user's guess are updated, and a new `WriteLine` activity is added that provides additional information about the game once the number is guessed.</span></span>  
  
####  <a name="BKMK_UpdateStateMachine"></a> <span data-ttu-id="4f662-139">Para actualizar el flujo de trabajo StateMachine</span><span class="sxs-lookup"><span data-stu-id="4f662-139">To update the StateMachine workflow</span></span>  
  
1.  <span data-ttu-id="4f662-140">En **el Explorador de soluciones**, en el **NumberGuessWorkflowActivities** del proyecto, haga doble clic en **StateMachineNumberGuessWorkflow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="4f662-140">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **StateMachineNumberGuessWorkflow.xaml**.</span></span>  
  
2.  <span data-ttu-id="4f662-141">Haga doble clic en el **Guess Incorrect** transición en la máquina de Estados.</span><span class="sxs-lookup"><span data-stu-id="4f662-141">Double-click the **Guess Incorrect** transition on the state machine.</span></span>  
  
3.  <span data-ttu-id="4f662-142">Actualice `Text` de `WriteLine` del extremo izquierdo en la actividad `If`.</span><span class="sxs-lookup"><span data-stu-id="4f662-142">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
4.  <span data-ttu-id="4f662-143">Actualice `Text` de `WriteLine` del extremo derecho en la actividad `If`.</span><span class="sxs-lookup"><span data-stu-id="4f662-143">Update the `Text` of the right-most `WriteLine` in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
5.  <span data-ttu-id="4f662-144">Volver a general el estado de vista de la máquina en el Diseñador de flujo de trabajo haciendo clic en **StateMachine** en la ruta de navegación que se muestran en la parte superior del Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4f662-144">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
6.  <span data-ttu-id="4f662-145">Haga doble clic en el **Guess Correct** transición en la máquina de Estados.</span><span class="sxs-lookup"><span data-stu-id="4f662-145">Double-click the **Guess Correct** transition on the state machine.</span></span>  
  
7.  <span data-ttu-id="4f662-146">Arrastre un **WriteLine** actividad desde la **primitivas** sección de la **cuadro de herramientas** y colóquela en la **coloque la actividad Action aquí** etiqueta de la transición.</span><span class="sxs-lookup"><span data-stu-id="4f662-146">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the **Drop Action activity here** label of the transition.</span></span>  
  
8.  <span data-ttu-id="4f662-147">Escriba la siguiente expresión en el cuadro de propiedad `Text`.</span><span class="sxs-lookup"><span data-stu-id="4f662-147">Type the following expression into the `Text` property box.</span></span>  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
####  <a name="BKMK_UpdateFlowchart"></a> <span data-ttu-id="4f662-148">Para actualizar el flujo de trabajo de diagrama de flujo</span><span class="sxs-lookup"><span data-stu-id="4f662-148">To update the Flowchart workflow</span></span>  
  
1.  <span data-ttu-id="4f662-149">En **el Explorador de soluciones**, en el **NumberGuessWorkflowActivities** del proyecto, haga doble clic en **FlowchartNumberGuessWorkflow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="4f662-149">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **FlowchartNumberGuessWorkflow.xaml**.</span></span>  
  
2.  <span data-ttu-id="4f662-150">Actualice `Text` de la actividad `WriteLine` del extremo izquierdo.</span><span class="sxs-lookup"><span data-stu-id="4f662-150">Update the `Text` of the left-most `WriteLine` activity.</span></span>  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
3.  <span data-ttu-id="4f662-151">Actualice `Text` de la actividad `WriteLine` del extremo derecho.</span><span class="sxs-lookup"><span data-stu-id="4f662-151">Update the `Text` of the right-most `WriteLine` activity.</span></span>  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
4.  <span data-ttu-id="4f662-152">Arrastrar un **WriteLine** actividad desde el **primitivas** sección de la **cuadro de herramientas** y colóquela en el punto de colocación de la `True` acción de la propiedad topmost `FlowDecision` .</span><span class="sxs-lookup"><span data-stu-id="4f662-152">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the drop point of the `True` action of the topmost `FlowDecision`.</span></span> <span data-ttu-id="4f662-153">La actividad `WriteLine` se agrega al diagrama de flujo y se vincula a la acción `True` de `FlowDecision`.</span><span class="sxs-lookup"><span data-stu-id="4f662-153">The `WriteLine` activity is added to the flowchart and linked to the `True` action of the `FlowDecision`.</span></span>  
  
5.  <span data-ttu-id="4f662-154">Escriba la siguiente expresión en el cuadro de propiedad `Text`.</span><span class="sxs-lookup"><span data-stu-id="4f662-154">Type the following expression into the `Text` property box.</span></span>  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
####  <a name="BKMK_UpdateSequential"></a> <span data-ttu-id="4f662-155">Para actualizar el flujo de trabajo secuencial</span><span class="sxs-lookup"><span data-stu-id="4f662-155">To update the Sequential workflow</span></span>  
  
1.  <span data-ttu-id="4f662-156">En **el Explorador de soluciones**, en el **NumberGuessWorkflowActivities** del proyecto, haga doble clic en **SequentialNumberGuessWorkflow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="4f662-156">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **SequentialNumberGuessWorkflow.xaml**.</span></span>  
  
2.  <span data-ttu-id="4f662-157">Actualice `Text` de `WriteLine` del extremo izquierdo en la actividad `If`.</span><span class="sxs-lookup"><span data-stu-id="4f662-157">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
3.  <span data-ttu-id="4f662-158">Actualice `Text` de la actividad `WriteLine` del extremo derecho en la actividad `If`.</span><span class="sxs-lookup"><span data-stu-id="4f662-158">Update the `Text` of the right-most `WriteLine` activity in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
4.  <span data-ttu-id="4f662-159">Arrastre un **WriteLine** actividad desde la **primitivas** sección de la **cuadro de herramientas** y colóquela después de la **DoWhile** actividad para que el  **WriteLine** es la actividad final en la raíz `Sequence` actividad.</span><span class="sxs-lookup"><span data-stu-id="4f662-159">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it after the **DoWhile** activity so that the **WriteLine** is the final activity in the root `Sequence` activity.</span></span>  
  
5.  <span data-ttu-id="4f662-160">Escriba la siguiente expresión en el cuadro de propiedad `Text`.</span><span class="sxs-lookup"><span data-stu-id="4f662-160">Type the following expression into the `Text` property box.</span></span>  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
###  <a name="BKMK_UpdateWorkflowVersionMap"></a> <span data-ttu-id="4f662-161">Para actualizar WorkflowVersionMap para incluir las versiones anteriores del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="4f662-161">To update WorkflowVersionMap to include the previous workflow versions</span></span>  
  
1.  <span data-ttu-id="4f662-162">Haga doble clic en **WorkflowVersionMap.cs** (o **WorkflowVersionMap.vb**) en el **NumberGuessWorkflowHost** proyecto para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="4f662-162">Double-click **WorkflowVersionMap.cs** (or **WorkflowVersionMap.vb**) under the **NumberGuessWorkflowHost** project to open it.</span></span>  
  
2.  <span data-ttu-id="4f662-163">Agregue las siguientes instrucciones `using` (o `Imports`) al principio del archivo con las demás instrucciones `using` (o `Imports`).</span><span class="sxs-lookup"><span data-stu-id="4f662-163">Add the following `using` (or `Imports`) statements to the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Reflection  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Reflection;  
    using System.IO;  
    ```  
  
3.  <span data-ttu-id="4f662-164">Agregue tres nuevas identidades de flujo de trabajo justo debajo de las tres declaraciones de identidad de flujo de trabajo existentes.</span><span class="sxs-lookup"><span data-stu-id="4f662-164">Add three new workflow identities just below the three existing workflow identity declarations.</span></span> <span data-ttu-id="4f662-165">Estas nuevas identidades de flujo de trabajo de `v1` se usarán para proporcionar la definición de flujo de trabajo correcta a los flujos de trabajo iniciados antes de que se realizaran las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="4f662-165">These new `v1` workflow identities will be used provide the correct workflow definition to workflows started before the updates were made.</span></span>  
  
    ```vb  
    'Current version identities.  
    Public StateMachineNumberGuessIdentity As WorkflowIdentity  
    Public FlowchartNumberGuessIdentity As WorkflowIdentity  
    Public SequentialNumberGuessIdentity As WorkflowIdentity  
  
    'v1 Identities.  
    Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity  
    Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity  
    Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity  
    ```  
  
    ```csharp  
    // Current version identities.  
    static public WorkflowIdentity StateMachineNumberGuessIdentity;  
    static public WorkflowIdentity FlowchartNumberGuessIdentity;  
    static public WorkflowIdentity SequentialNumberGuessIdentity;  
  
    // v1 identities.  
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;  
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;  
    static public WorkflowIdentity SequentialNumberGuessIdentity_v1;  
    ```  
  
4.  <span data-ttu-id="4f662-166">En el constructor `WorkflowVersionMap`, actualice la propiedad `Version` de las tres identidades de flujo de trabajo actuales a `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="4f662-166">In the `WorkflowVersionMap` constructor, update the `Version` property of the three current workflow identities to `2.0.0.0`.</span></span>  
  
    ```vb  
    'Add the current workflow version identities.  
    StateMachineNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "StateMachineNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    FlowchartNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "FlowchartNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    SequentialNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "SequentialNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())  
    map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())  
    map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())  
    ```  
  
    ```csharp  
    // Add the current workflow version identities.  
    StateMachineNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "StateMachineNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    FlowchartNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "FlowchartNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    SequentialNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "SequentialNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());  
    map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());  
    map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());  
    ```  
  
     <span data-ttu-id="4f662-167">El código que agrega las versiones actuales de los flujos de trabajo al diccionario usa las versiones actuales a las que se hace referencia en el proyecto, por lo que no es necesario actualizar el código que inicializa las definiciones de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4f662-167">The code in that adds the current versions of the workflows to the dictionary uses the current versions that are referenced in the project, so the code that initializes the workflow definitions does not need to be updated.</span></span>  
  
5.  <span data-ttu-id="4f662-168">Agregue el código siguiente en el constructor justo después del código que agrega las versiones actuales al diccionario.</span><span class="sxs-lookup"><span data-stu-id="4f662-168">Add the following code in the constructor just after the code that adds the current versions to the dictionary.</span></span>  
  
    ```vb  
    'Initialize the previous workflow version identities.  
    StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "StateMachineNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
  
    FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "FlowchartNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
  
    SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "SequentialNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
    ```  
  
    ```csharp  
    // Initialize the previous workflow version identities.  
    StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "StateMachineNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
  
    FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "FlowchartNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
  
    SequentialNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "SequentialNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
    ```  
  
     <span data-ttu-id="4f662-169">Estas identidades de flujo de trabajo están asociadas a las versiones iniciales de las definiciones de flujo de trabajo correspondientes.</span><span class="sxs-lookup"><span data-stu-id="4f662-169">These workflow identities are associated with the initial versions of the corresponding workflow definitions.</span></span>  
  
6.  <span data-ttu-id="4f662-170">A continuación, cargue el ensamblado que contiene la versión inicial de las definiciones de flujo de trabajo, y cree y agregue las definiciones de flujo de trabajo al diccionario.</span><span class="sxs-lookup"><span data-stu-id="4f662-170">Next, load the assembly that contains the initial version of the workflow definitions, and create and add the corresponding workflow definitions to the dictionary.</span></span>  
  
    ```vb  
    'Add the previous version workflow identities to the dictionary along with  
    'the corresponding workflow definitions loaded from the v1 assembly.  
    'Assembly.LoadFile requires an absolute path so convert this relative path  
    'to an absolute path.  
    Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"  
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)  
    Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)  
  
    map.Add(StateMachineNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))  
  
    map.Add(SequentialNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))  
  
    map.Add(FlowchartNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))  
    ```  
  
    ```csharp  
    // Add the previous version workflow identities to the dictionary along with  
    // the corresponding workflow definitions loaded from the v1 assembly.  
    // Assembly.LoadFile requires an absolute path so convert this relative path  
    // to an absolute path.  
    string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";  
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);  
    Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);  
  
    map.Add(StateMachineNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);  
  
    map.Add(SequentialNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);  
  
    map.Add(FlowchartNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);  
    ```  
  
     <span data-ttu-id="4f662-171">En el ejemplo siguiente se muestra la lista completa para la clase `WorkflowVersionMap` actualizada.</span><span class="sxs-lookup"><span data-stu-id="4f662-171">The following example is the complete listing for the updated `WorkflowVersionMap` class.</span></span>  
  
    ```vb  
    Public Module WorkflowVersionMap  
        Dim map As Dictionary(Of WorkflowIdentity, Activity)  
  
        'Current version identities.  
        Public StateMachineNumberGuessIdentity As WorkflowIdentity  
        Public FlowchartNumberGuessIdentity As WorkflowIdentity  
        Public SequentialNumberGuessIdentity As WorkflowIdentity  
  
        'v1 Identities.  
        Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity  
        Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity  
        Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity  
  
        Sub New()  
            map = New Dictionary(Of WorkflowIdentity, Activity)  
  
            'Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "StateMachineNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            FlowchartNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "FlowchartNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            SequentialNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "SequentialNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())  
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())  
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())  
  
            'Initialize the previous workflow version identities.  
            StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "StateMachineNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "FlowchartNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "SequentialNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            'Add the previous version workflow identities to the dictionary along with  
            'the corresponding workflow definitions loaded from the v1 assembly.  
            'Assembly.LoadFile requires an absolute path so convert this relative path  
            'to an absolute path.  
            Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"  
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)  
            Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)  
  
            map.Add(StateMachineNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))  
  
            map.Add(SequentialNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))  
  
            map.Add(FlowchartNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))  
        End Sub  
  
        Public Function GetWorkflowDefinition(identity As WorkflowIdentity) As Activity  
            Return map(identity)  
        End Function  
  
        Public Function GetIdentityDescription(identity As WorkflowIdentity) As String  
            Return identity.ToString()  
        End Function  
    End Module  
    ```  
  
    ```csharp  
    public static class WorkflowVersionMap  
    {  
        static Dictionary<WorkflowIdentity, Activity> map;  
  
        // Current version identities.  
        static public WorkflowIdentity StateMachineNumberGuessIdentity;  
        static public WorkflowIdentity FlowchartNumberGuessIdentity;  
        static public WorkflowIdentity SequentialNumberGuessIdentity;  
  
        // v1 identities.  
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;  
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;  
        static public WorkflowIdentity SequentialNumberGuessIdentity_v1;  
  
        static WorkflowVersionMap()  
        {  
            map = new Dictionary<WorkflowIdentity, Activity>();  
  
            // Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "StateMachineNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            FlowchartNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "FlowchartNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            SequentialNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "SequentialNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());  
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());  
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());  
  
            // Initialize the previous workflow version identities.  
            StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "StateMachineNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "FlowchartNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            SequentialNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "SequentialNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            // Add the previous version workflow identities to the dictionary along with  
            // the corresponding workflow definitions loaded from the v1 assembly.  
            // Assembly.LoadFile requires an absolute path so convert this relative path  
            // to an absolute path.  
            string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";  
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);  
            Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);  
  
            map.Add(StateMachineNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);  
  
            map.Add(SequentialNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);  
  
            map.Add(FlowchartNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);  
        }  
  
        public static Activity GetWorkflowDefinition(WorkflowIdentity identity)  
        {  
            return map[identity];  
        }  
  
        public static string GetIdentityDescription(WorkflowIdentity identity)  
        {  
            return identity.ToString();  
        }  
    }  
    ```  
  
###  <a name="BKMK_BuildAndRun"></a> <span data-ttu-id="4f662-172">Para compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="4f662-172">To build and run the application</span></span>  
  
1.  <span data-ttu-id="4f662-173">Presione CTRL+MAYÚS+B para compilar la aplicación y, a continuación, CTRL+F5 para iniciarla.</span><span class="sxs-lookup"><span data-stu-id="4f662-173">Press CTRL+SHIFT+B to build the application, and then CTRL+F5 to start.</span></span>  
  
2.  <span data-ttu-id="4f662-174">Haga clic en iniciar un nuevo flujo de trabajo **nuevo juego**.</span><span class="sxs-lookup"><span data-stu-id="4f662-174">Start a new workflow by clicking **New Game**.</span></span> <span data-ttu-id="4f662-175">La versión del flujo de trabajo se muestra debajo de la ventana de estado y refleja la versión actualizada del `WorkflowIdentity` asociado.</span><span class="sxs-lookup"><span data-stu-id="4f662-175">The version of the workflow is displayed under the status window and reflects the updated version from the associated `WorkflowIdentity`.</span></span> <span data-ttu-id="4f662-176">Anote el valor de `InstanceId` para poder ver el archivo de seguimiento del flujo de trabajo cuando se complete y, a continuación, escriba números hasta que se termine el juego.</span><span class="sxs-lookup"><span data-stu-id="4f662-176">Make a note of the `InstanceId` so you can view the tracking file for the workflow when it completes, and then enter guesses until the game is complete.</span></span> <span data-ttu-id="4f662-177">Observe cómo el intento del usuario aparece en la información que se muestra en la ventana de estado en función de las actualizaciones de las actividades `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="4f662-177">Note how the user's guess is displayed in the information displayed in the status window based on the updates to the `WriteLine` activities.</span></span>  
  
 <span data-ttu-id="4f662-178">**Escriba un número entre 1 y 10**</span><span class="sxs-lookup"><span data-stu-id="4f662-178">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="4f662-179">**5 es demasiado alto.** </span><span class="sxs-lookup"><span data-stu-id="4f662-179">**5 is too high.** </span></span>  
<span data-ttu-id="4f662-180">**Escriba un número entre 1 y 10** </span><span class="sxs-lookup"><span data-stu-id="4f662-180">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="4f662-181">**3 es demasiado alto.** </span><span class="sxs-lookup"><span data-stu-id="4f662-181">**3 is too high.** </span></span>  
<span data-ttu-id="4f662-182">**Escriba un número entre 1 y 10** </span><span class="sxs-lookup"><span data-stu-id="4f662-182">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="4f662-183">**1 es demasiado bajo.** </span><span class="sxs-lookup"><span data-stu-id="4f662-183">**1 is too low.** </span></span>  
<span data-ttu-id="4f662-184">**Escriba un número entre 1 y 10** </span><span class="sxs-lookup"><span data-stu-id="4f662-184">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="4f662-185">**Enhorabuena, acertó el número en 4 intentos.**</span><span class="sxs-lookup"><span data-stu-id="4f662-185">**Congratulations, you guessed the number in 4 turns.**</span></span>    
    > [!NOTE]
    >  <span data-ttu-id="4f662-186">Se muestra el texto actualizado de las actividades `WriteLine`, pero no se muestra el resultado de la actividad final `WriteLine` que se agregó en este tema.</span><span class="sxs-lookup"><span data-stu-id="4f662-186">The updated text from the `WriteLine` activities is displayed, but the output of the final `WriteLine` activity that was added in this topic is not.</span></span> <span data-ttu-id="4f662-187">Esto se debe a que el controlador `PersistableIdle` actualiza la ventana de estado.</span><span class="sxs-lookup"><span data-stu-id="4f662-187">That is because the status window is updated by the `PersistableIdle` handler.</span></span> <span data-ttu-id="4f662-188">Debido a que el flujo de trabajo se completa y no queda inactivo después de la actividad final, no se llama al controlador `PersistableIdle`.</span><span class="sxs-lookup"><span data-stu-id="4f662-188">Because the workflow completes and does not go idle after the final activity, the `PersistableIdle` handler is not called.</span></span> <span data-ttu-id="4f662-189">Sin embargo, el controlador `Completed` muestra un mensaje similar en la ventana de estado.</span><span class="sxs-lookup"><span data-stu-id="4f662-189">However, a similar message is displayed in the status window by the `Completed` handler.</span></span> <span data-ttu-id="4f662-190">Si se desea, se puede agregar un código al controlador `Completed` para extraer el texto de `StringWriter` y mostrarlo en la ventana de estado.</span><span class="sxs-lookup"><span data-stu-id="4f662-190">If desired, code could be added to the `Completed` handler to extract the text from the `StringWriter` and display it to the status window.</span></span>  
  
3.  <span data-ttu-id="4f662-191">Abra el Explorador de Windows y navegue hasta la **NumberGuessWorkflowHost\bin\debug** carpeta (o **bin\release** según la configuración del proyecto) y abra el archivo de seguimiento con el Bloc de notas que corresponde en el flujo de trabajo completado.</span><span class="sxs-lookup"><span data-stu-id="4f662-191">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings) and open the tracking file using Notepad that corresponds to the completed workflow.</span></span> <span data-ttu-id="4f662-192">Si no ha realizado una nota de la `InstanceId`, puede identificar el archivo correcto de seguimiento utilizando el **fecha de modificación** información en el Explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="4f662-192">If you did not make a note of the `InstanceId`, you can identify the correct tracking file by using the **Date modified** information in Windows Explorer.</span></span>  
  
 <span data-ttu-id="4f662-193">**Escriba un número entre 1 y 10**</span><span class="sxs-lookup"><span data-stu-id="4f662-193">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="4f662-194">**5 es demasiado alto.** </span><span class="sxs-lookup"><span data-stu-id="4f662-194">**5 is too high.** </span></span>  
<span data-ttu-id="4f662-195">**Escriba un número entre 1 y 10** </span><span class="sxs-lookup"><span data-stu-id="4f662-195">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="4f662-196">**3 es demasiado alto.** </span><span class="sxs-lookup"><span data-stu-id="4f662-196">**3 is too high.** </span></span>  
<span data-ttu-id="4f662-197">**Escriba un número entre 1 y 10** </span><span class="sxs-lookup"><span data-stu-id="4f662-197">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="4f662-198">**1 es demasiado bajo.** </span><span class="sxs-lookup"><span data-stu-id="4f662-198">**1 is too low.** </span></span>  
<span data-ttu-id="4f662-199">**Escriba un número entre 1 y 10** </span><span class="sxs-lookup"><span data-stu-id="4f662-199">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="4f662-200">**2 es correcto. Lo acertó en 4 intentos.**</span><span class="sxs-lookup"><span data-stu-id="4f662-200">**2 is correct. You guessed it in 4 turns.**</span></span>      <span data-ttu-id="4f662-201">La salida de `WriteLine` actualizada se encuentra en el archivo de seguimiento, incluida la salida de `WriteLine` que se agregó en este tema.</span><span class="sxs-lookup"><span data-stu-id="4f662-201">The updated `WriteLine` output is contained within the tracking file, including the output of the `WriteLine` that was added in this topic.</span></span>  
  
4.  <span data-ttu-id="4f662-202">Vuelva a la aplicación para adivinar números y seleccione uno de los flujos de trabajo iniciado antes de que se realizaran las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="4f662-202">Switch back to the number guessing application and select one of the workflows that was started before the updates were made.</span></span> <span data-ttu-id="4f662-203">Puede identificar la versión del flujo de trabajo seleccionado actualmente si examina la información de versión que aparece debajo de la ventana de estado.</span><span class="sxs-lookup"><span data-stu-id="4f662-203">You can identify the version of the currently selected workflow by looking at the version information that is displayed below the status window.</span></span> <span data-ttu-id="4f662-204">Escriba los números y observe que las actualizaciones de estado coinciden con el resultado de la actividad `WriteLine` de la versión anterior y no incluyen el intento del usuario.</span><span class="sxs-lookup"><span data-stu-id="4f662-204">Enter some guesses and note that the status updates match the `WriteLine` activity output from the previous version, and do not include the user's guess.</span></span> <span data-ttu-id="4f662-205">Esto se debe a que estos flujos de trabajo usan la definición de flujo de trabajo anterior que no tiene las actualizaciones `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="4f662-205">That is because these workflows are using the previous workflow definition that does not have the `WriteLine` updates.</span></span>  
  
     <span data-ttu-id="4f662-206">En el paso siguiente, [Cómo: actualizar la definición de una instancia de flujo de trabajo ejecuta](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md), la ejecución `v1` las instancias de flujo de trabajo se actualizan para que contengan la nueva funcionalidad como la `v2` instancias.</span><span class="sxs-lookup"><span data-stu-id="4f662-206">In the next step, [How to: Update the Definition of a Running Workflow Instance](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md), the running `v1` workflow instances are updated so they contain the new functionality as the `v2` instances.</span></span>
