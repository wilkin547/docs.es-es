---
description: 'Más información acerca de cómo: hospedar varias versiones de un flujo de trabajo en paralelo'
title: Procedimiento para hospedar varias versiones de un flujo de trabajo en paralelo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09c575df-e0a3-4f3b-9e01-a7ac59d65287
ms.openlocfilehash: 7662aa6375467e6bc283e1e743488439c8bf087a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99777676"
---
# <a name="how-to-host-multiple-versions-of-a-workflow-side-by-side"></a><span data-ttu-id="38351-103">Procedimiento para hospedar varias versiones de un flujo de trabajo en paralelo</span><span class="sxs-lookup"><span data-stu-id="38351-103">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>

<span data-ttu-id="38351-104">`WorkflowIdentity` proporciona una manera para que los desarrolladores de aplicaciones de flujo de trabajo asocien un nombre y una versión con una definición de flujo de trabajo, y para que esta información se asocie a una instancia de flujo de trabajo persistente.</span><span class="sxs-lookup"><span data-stu-id="38351-104">`WorkflowIdentity` provides a way for workflow application developers to associate a name and a version with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="38351-105">Los desarrolladores de aplicaciones de flujo de trabajo pueden usar esta información de identidad para habilitar escenarios como la ejecución en paralelo de varias versiones de una definición de flujo de trabajo; además esta información proporciona la piedra angular para otras funcionalidades como la actualización dinámica.</span><span class="sxs-lookup"><span data-stu-id="38351-105">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="38351-106">Este paso del tutorial demuestra cómo usar `WorkflowIdentity` para hospedar varias versiones de un flujo de trabajo simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="38351-106">This step in the tutorial demonstrates how to use `WorkflowIdentity` to host multiple versions of a workflow at the same time.</span></span>

## <a name="in-this-topic"></a><span data-ttu-id="38351-107">En este tema</span><span class="sxs-lookup"><span data-stu-id="38351-107">In this topic</span></span>

<span data-ttu-id="38351-108">En este paso del tutorial, las actividades de `WriteLine` en el flujo de trabajo se modifican para proporcionar información adicional y se agrega una nueva actividad `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="38351-108">In this step of the tutorial, the `WriteLine` activities in the workflow are modified to provide additional information, and a new `WriteLine` activity is added.</span></span> <span data-ttu-id="38351-109">Una copia del ensamblado original de flujo de trabajo queda almacenada y la aplicación de host se actualiza de tal modo que puede ejecutar tanto el flujo de trabajo original como el actualizado al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="38351-109">A copy of the original workflow assembly is stored, and the host application is updated so that it can run both the original and the updated workflows at the same time.</span></span>

- [<span data-ttu-id="38351-110">Para realizar una copia del proyecto NumberGuessWorkflowActivities</span><span class="sxs-lookup"><span data-stu-id="38351-110">To make a copy of the NumberGuessWorkflowActivities project</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BackupCopy)

- [<span data-ttu-id="38351-111">Para actualizar el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="38351-111">To update the workflows</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflows)

  - [<span data-ttu-id="38351-112">Para actualizar el flujo de trabajo StateMachine</span><span class="sxs-lookup"><span data-stu-id="38351-112">To update the StateMachine workflow</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateStateMachine)

  - [<span data-ttu-id="38351-113">Para actualizar el flujo de trabajo Diagrama de flujo</span><span class="sxs-lookup"><span data-stu-id="38351-113">To update the Flowchart workflow</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateFlowchart)

  - [<span data-ttu-id="38351-114">Para actualizar el flujo de trabajo Secuencial</span><span class="sxs-lookup"><span data-stu-id="38351-114">To update the Sequential workflow</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateSequential)

- [<span data-ttu-id="38351-115">Para actualizar WorkflowVersionMap a fin de incluir las versiones de flujo de trabajo anteriores</span><span class="sxs-lookup"><span data-stu-id="38351-115">To update WorkflowVersionMap to include the previous workflow versions</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflowVersionMap)

- [<span data-ttu-id="38351-116">Para generar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="38351-116">To build and run the application</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BuildAndRun)

> [!NOTE]
> <span data-ttu-id="38351-117">Antes de seguir los pasos de este tema, ejecute la aplicación, inicie varios flujos de trabajo de cada tipo y realice uno o dos intentos con cada uno.</span><span class="sxs-lookup"><span data-stu-id="38351-117">Before following the steps in this topic, run the application, start several workflows of each type, and making one or two guesses for each one.</span></span> <span data-ttu-id="38351-118">Estos flujos de trabajo persistentes se usan en este paso y en el paso siguiente, [Cómo: actualizar la definición de una instancia de flujo de trabajo en ejecución](how-to-update-the-definition-of-a-running-workflow-instance.md).</span><span class="sxs-lookup"><span data-stu-id="38351-118">These persisted workflows are used in this step and the following step, [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>

### <a name="to-make-a-copy-of-the-numberguessworkflowactivities-project"></a><a name="BKMK_BackupCopy"></a> <span data-ttu-id="38351-119">Para hacer una copia del proyecto NumberGuessWorkflowActivities</span><span class="sxs-lookup"><span data-stu-id="38351-119">To make a copy of the NumberGuessWorkflowActivities project</span></span>

1. <span data-ttu-id="38351-120">Abra la solución **WF45GettingStartedTutorial** en Visual Studio 2012 si no está abierta.</span><span class="sxs-lookup"><span data-stu-id="38351-120">Open the **WF45GettingStartedTutorial** solution in Visual Studio 2012 if it is not open.</span></span>

2. <span data-ttu-id="38351-121">Presione CTRL+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="38351-121">Press CTRL+SHIFT+B to build the solution.</span></span>

3. <span data-ttu-id="38351-122">Cierre la solución **WF45GettingStartedTutorial** .</span><span class="sxs-lookup"><span data-stu-id="38351-122">Close the **WF45GettingStartedTutorial** solution.</span></span>

4. <span data-ttu-id="38351-123">Abra el Explorador de Windows y navegue hasta la carpeta donde se encuentran el archivo de solución del tutorial y las carpetas de proyecto.</span><span class="sxs-lookup"><span data-stu-id="38351-123">Open Windows Explorer and navigate to the folder where the tutorial solution file and the project folders are located.</span></span>

5. <span data-ttu-id="38351-124">Cree una nueva carpeta denominada **PreviousVersions** en la misma carpeta que **NumberGuessWorkflowHost** y **NumberGuessWorkflowActivities**.</span><span class="sxs-lookup"><span data-stu-id="38351-124">Create a new folder named **PreviousVersions** in the same folder as **NumberGuessWorkflowHost** and **NumberGuessWorkflowActivities**.</span></span> <span data-ttu-id="38351-125">Esta carpeta se usa para guardar los ensamblados que contienen las distintas versiones de los flujos de trabajo usados en los pasos de tutorial posteriores.</span><span class="sxs-lookup"><span data-stu-id="38351-125">This folder is used to contain the assemblies that contain the different versions of the workflows used in the subsequent tutorial steps.</span></span>

6. <span data-ttu-id="38351-126">Vaya a la carpeta **NumberGuessWorkflowActivities\bin\debug** (o **bin\release** según la configuración del proyecto).</span><span class="sxs-lookup"><span data-stu-id="38351-126">Navigate to the **NumberGuessWorkflowActivities\bin\debug** folder (or **bin\release** depending on your project settings).</span></span> <span data-ttu-id="38351-127">Copie **NumberGuessWorkflowActivities.dll** y péguelo en la carpeta **PreviousVersions** .</span><span class="sxs-lookup"><span data-stu-id="38351-127">Copy **NumberGuessWorkflowActivities.dll** and paste it into the **PreviousVersions** folder.</span></span>

7. <span data-ttu-id="38351-128">Cambie el nombre **NumberGuessWorkflowActivities.dll** de la carpeta **PreviousVersions** a **NumberGuessWorkflowActivities_v1.dll**.</span><span class="sxs-lookup"><span data-stu-id="38351-128">Rename **NumberGuessWorkflowActivities.dll** in the **PreviousVersions** folder to **NumberGuessWorkflowActivities_v1.dll**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="38351-129">En los pasos de este tema se muestra una manera de administrar los ensamblados usados para contener varias versiones de los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="38351-129">The steps in this topic demonstrate one way to manage the assemblies used to contain multiple versions of the workflows.</span></span> <span data-ttu-id="38351-130">También se pueden usar otros métodos, como el nombre seguro de los ensamblados y su registro en la memoria caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="38351-130">Other methods such as strong naming the assemblies and registering them in the global assembly cache could also be used.</span></span>

8. <span data-ttu-id="38351-131">Cree una nueva carpeta denominada **NumberGuessWorkflowActivities_du** en la misma carpeta que **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities** y la carpeta **PreviousVersions** recién agregada, y copie todos los archivos y subcarpetas de la carpeta **NumberGuessWorkflowActivities** en la nueva carpeta **NumberGuessWorkflowActivities_du** .</span><span class="sxs-lookup"><span data-stu-id="38351-131">Create a new folder named **NumberGuessWorkflowActivities_du** in the same folder as **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**, and the newly added **PreviousVersions** folder, and copy all of the files and subfolders from the **NumberGuessWorkflowActivities** folder into the new **NumberGuessWorkflowActivities_du** folder.</span></span> <span data-ttu-id="38351-132">Esta copia de seguridad del proyecto para la versión inicial de las actividades se usa en [Cómo: actualizar la definición de una instancia de flujo de trabajo en ejecución](how-to-update-the-definition-of-a-running-workflow-instance.md).</span><span class="sxs-lookup"><span data-stu-id="38351-132">This backup copy of the project for the initial version of the activities is used in [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>

9. <span data-ttu-id="38351-133">Vuelva a abrir la solución **WF45GettingStartedTutorial** en Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="38351-133">Re-open the **WF45GettingStartedTutorial** solution in Visual Studio 2012.</span></span>

### <a name="to-update-the-workflows"></a><a name="BKMK_UpdateWorkflows"></a> <span data-ttu-id="38351-134">Para actualizar los flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="38351-134">To update the workflows</span></span>

<span data-ttu-id="38351-135">En esta sección, se actualizan las definiciones de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="38351-135">In this section, the workflow definitions are updated.</span></span> <span data-ttu-id="38351-136">Se actualizan las dos actividades de `WriteLine` que proporcionan informes sobre los intentos del usuario, y se agrega una nueva actividad `WriteLine` que proporciona información adicional sobre el juego una vez se ha adivinado el número.</span><span class="sxs-lookup"><span data-stu-id="38351-136">The two `WriteLine` activities that give feedback on the user's guess are updated, and a new `WriteLine` activity is added that provides additional information about the game once the number is guessed.</span></span>

#### <a name="to-update-the-statemachine-workflow"></a><a name="BKMK_UpdateStateMachine"></a> <span data-ttu-id="38351-137">Para actualizar el flujo de trabajo StateMachine</span><span class="sxs-lookup"><span data-stu-id="38351-137">To update the StateMachine workflow</span></span>

1. <span data-ttu-id="38351-138">En **Explorador de soluciones**, en el proyecto **NumberGuessWorkflowActivities** , haga doble clic en **StateMachineNumberGuessWorkflow. Xaml**.</span><span class="sxs-lookup"><span data-stu-id="38351-138">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **StateMachineNumberGuessWorkflow.xaml**.</span></span>

2. <span data-ttu-id="38351-139">Haga doble clic en la transición **adivinar incorrectamente** en el equipo de estado.</span><span class="sxs-lookup"><span data-stu-id="38351-139">Double-click the **Guess Incorrect** transition on the state machine.</span></span>

3. <span data-ttu-id="38351-140">Actualice `Text` de `WriteLine` del extremo izquierdo en la actividad `If`.</span><span class="sxs-lookup"><span data-stu-id="38351-140">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

4. <span data-ttu-id="38351-141">Actualice `Text` de `WriteLine` del extremo derecho en la actividad `If`.</span><span class="sxs-lookup"><span data-stu-id="38351-141">Update the `Text` of the right-most `WriteLine` in the `If` activity.</span></span>

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

5. <span data-ttu-id="38351-142">Vuelva a la vista de equipo de estado general en el diseñador de flujo de trabajo haciendo clic en **StateMachine** en la pantalla de la ruta de navegación en la parte superior del diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="38351-142">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>

6. <span data-ttu-id="38351-143">Haga doble clic en la transición **adivinar corrección** en el equipo de estado.</span><span class="sxs-lookup"><span data-stu-id="38351-143">Double-click the **Guess Correct** transition on the state machine.</span></span>

7. <span data-ttu-id="38351-144">Arrastre una actividad **WriteLine** de la sección **primitivas** del **cuadro de herramientas** y colóquela en la etiqueta **colocar actividad de acción aquí** de la transición.</span><span class="sxs-lookup"><span data-stu-id="38351-144">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the **Drop Action activity here** label of the transition.</span></span>

8. <span data-ttu-id="38351-145">Escriba la siguiente expresión en el cuadro de propiedad `Text`.</span><span class="sxs-lookup"><span data-stu-id="38351-145">Type the following expression into the `Text` property box.</span></span>

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

#### <a name="to-update-the-flowchart-workflow"></a><a name="BKMK_UpdateFlowchart"></a> <span data-ttu-id="38351-146">Para actualizar el flujo de trabajo del diagrama de flujo</span><span class="sxs-lookup"><span data-stu-id="38351-146">To update the Flowchart workflow</span></span>

1. <span data-ttu-id="38351-147">En **Explorador de soluciones**, en el proyecto **NumberGuessWorkflowActivities** , haga doble clic en **FlowchartNumberGuessWorkflow. Xaml**.</span><span class="sxs-lookup"><span data-stu-id="38351-147">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **FlowchartNumberGuessWorkflow.xaml**.</span></span>

2. <span data-ttu-id="38351-148">Actualice `Text` de la actividad `WriteLine` del extremo izquierdo.</span><span class="sxs-lookup"><span data-stu-id="38351-148">Update the `Text` of the left-most `WriteLine` activity.</span></span>

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3. <span data-ttu-id="38351-149">Actualice `Text` de la actividad `WriteLine` del extremo derecho.</span><span class="sxs-lookup"><span data-stu-id="38351-149">Update the `Text` of the right-most `WriteLine` activity.</span></span>

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4. <span data-ttu-id="38351-150">Arrastre una actividad **WriteLine** de la sección **primitivas** del **cuadro de herramientas** y colóquela en el punto de colocación de la `True` acción del nivel superior `FlowDecision` .</span><span class="sxs-lookup"><span data-stu-id="38351-150">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the drop point of the `True` action of the topmost `FlowDecision`.</span></span> <span data-ttu-id="38351-151">La actividad `WriteLine` se agrega al diagrama de flujo y se vincula a la acción `True` de `FlowDecision`.</span><span class="sxs-lookup"><span data-stu-id="38351-151">The `WriteLine` activity is added to the flowchart and linked to the `True` action of the `FlowDecision`.</span></span>

5. <span data-ttu-id="38351-152">Escriba la siguiente expresión en el cuadro de propiedad `Text`.</span><span class="sxs-lookup"><span data-stu-id="38351-152">Type the following expression into the `Text` property box.</span></span>

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

#### <a name="to-update-the-sequential-workflow"></a><a name="BKMK_UpdateSequential"></a> <span data-ttu-id="38351-153">Para actualizar el flujo de trabajo secuencial</span><span class="sxs-lookup"><span data-stu-id="38351-153">To update the Sequential workflow</span></span>

1. <span data-ttu-id="38351-154">En **Explorador de soluciones**, en el proyecto **NumberGuessWorkflowActivities** , haga doble clic en **SequentialNumberGuessWorkflow. Xaml**.</span><span class="sxs-lookup"><span data-stu-id="38351-154">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **SequentialNumberGuessWorkflow.xaml**.</span></span>

2. <span data-ttu-id="38351-155">Actualice `Text` de `WriteLine` del extremo izquierdo en la actividad `If`.</span><span class="sxs-lookup"><span data-stu-id="38351-155">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3. <span data-ttu-id="38351-156">Actualice `Text` de la actividad `WriteLine` del extremo derecho en la actividad `If`.</span><span class="sxs-lookup"><span data-stu-id="38351-156">Update the `Text` of the right-most `WriteLine` activity in the `If` activity.</span></span>

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4. <span data-ttu-id="38351-157">Arrastre una **actividad WriteLine** de la sección **primitivas** del cuadro de **herramientas** y colóquela después de la actividad **While** para que **WriteLine** sea la actividad final de la actividad raíz `Sequence` .</span><span class="sxs-lookup"><span data-stu-id="38351-157">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it after the **DoWhile** activity so that the **WriteLine** is the final activity in the root `Sequence` activity.</span></span>

5. <span data-ttu-id="38351-158">Escriba la siguiente expresión en el cuadro de propiedad `Text`.</span><span class="sxs-lookup"><span data-stu-id="38351-158">Type the following expression into the `Text` property box.</span></span>

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

### <a name="to-update-workflowversionmap-to-include-the-previous-workflow-versions"></a><a name="BKMK_UpdateWorkflowVersionMap"></a> <span data-ttu-id="38351-159">Para actualizar WorkflowVersionMap para que incluya las versiones anteriores del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="38351-159">To update WorkflowVersionMap to include the previous workflow versions</span></span>

1. <span data-ttu-id="38351-160">Haga doble clic en **WorkflowVersionMap.CS** (o **WorkflowVersionMap. VB**) en el proyecto **NumberGuessWorkflowHost** para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="38351-160">Double-click **WorkflowVersionMap.cs** (or **WorkflowVersionMap.vb**) under the **NumberGuessWorkflowHost** project to open it.</span></span>

2. <span data-ttu-id="38351-161">Agregue las siguientes instrucciones `using` (o `Imports`) al principio del archivo con las demás instrucciones `using` (o `Imports`).</span><span class="sxs-lookup"><span data-stu-id="38351-161">Add the following `using` (or `Imports`) statements to the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Reflection
    Imports System.IO
    ```

    ```csharp
    using System.Reflection;
    using System.IO;
    ```

3. <span data-ttu-id="38351-162">Agregue tres nuevas identidades de flujo de trabajo justo debajo de las tres declaraciones de identidad de flujo de trabajo existentes.</span><span class="sxs-lookup"><span data-stu-id="38351-162">Add three new workflow identities just below the three existing workflow identity declarations.</span></span> <span data-ttu-id="38351-163">Estas nuevas identidades de flujo de trabajo de `v1` se usarán para proporcionar la definición de flujo de trabajo correcta a los flujos de trabajo iniciados antes de que se realizaran las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="38351-163">These new `v1` workflow identities will be used provide the correct workflow definition to workflows started before the updates were made.</span></span>

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

4. <span data-ttu-id="38351-164">En el constructor `WorkflowVersionMap`, actualice la propiedad `Version` de las tres identidades de flujo de trabajo actuales a `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="38351-164">In the `WorkflowVersionMap` constructor, update the `Version` property of the three current workflow identities to `2.0.0.0`.</span></span>

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

    <span data-ttu-id="38351-165">El código que agrega las versiones actuales de los flujos de trabajo al diccionario usa las versiones actuales a las que se hace referencia en el proyecto, por lo que no es necesario actualizar el código que inicializa las definiciones de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="38351-165">The code in that adds the current versions of the workflows to the dictionary uses the current versions that are referenced in the project, so the code that initializes the workflow definitions does not need to be updated.</span></span>

5. <span data-ttu-id="38351-166">Agregue el código siguiente en el constructor justo después del código que agrega las versiones actuales al diccionario.</span><span class="sxs-lookup"><span data-stu-id="38351-166">Add the following code in the constructor just after the code that adds the current versions to the dictionary.</span></span>

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

    <span data-ttu-id="38351-167">Estas identidades de flujo de trabajo están asociadas a las versiones iniciales de las definiciones de flujo de trabajo correspondientes.</span><span class="sxs-lookup"><span data-stu-id="38351-167">These workflow identities are associated with the initial versions of the corresponding workflow definitions.</span></span>

6. <span data-ttu-id="38351-168">A continuación, cargue el ensamblado que contiene la versión inicial de las definiciones de flujo de trabajo, y cree y agregue las definiciones de flujo de trabajo al diccionario.</span><span class="sxs-lookup"><span data-stu-id="38351-168">Next, load the assembly that contains the initial version of the workflow definitions, and create and add the corresponding workflow definitions to the dictionary.</span></span>

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

    <span data-ttu-id="38351-169">En el ejemplo siguiente se muestra la lista completa para la clase `WorkflowVersionMap` actualizada.</span><span class="sxs-lookup"><span data-stu-id="38351-169">The following example is the complete listing for the updated `WorkflowVersionMap` class.</span></span>

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

### <a name="to-build-and-run-the-application"></a><a name="BKMK_BuildAndRun"></a> <span data-ttu-id="38351-170">Para compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="38351-170">To build and run the application</span></span>

1. <span data-ttu-id="38351-171">Presione CTRL+MAYÚS+B para compilar la aplicación y, a continuación, CTRL+F5 para iniciarla.</span><span class="sxs-lookup"><span data-stu-id="38351-171">Press CTRL+SHIFT+B to build the application, and then CTRL+F5 to start.</span></span>

2. <span data-ttu-id="38351-172">Para iniciar un nuevo flujo de trabajo, haga clic en **nuevo juego**.</span><span class="sxs-lookup"><span data-stu-id="38351-172">Start a new workflow by clicking **New Game**.</span></span> <span data-ttu-id="38351-173">La versión del flujo de trabajo se muestra debajo de la ventana de estado y refleja la versión actualizada del `WorkflowIdentity` asociado.</span><span class="sxs-lookup"><span data-stu-id="38351-173">The version of the workflow is displayed under the status window and reflects the updated version from the associated `WorkflowIdentity`.</span></span> <span data-ttu-id="38351-174">Anote el valor de `InstanceId` para poder ver el archivo de seguimiento del flujo de trabajo cuando se complete y, a continuación, escriba números hasta que se termine el juego.</span><span class="sxs-lookup"><span data-stu-id="38351-174">Make a note of the `InstanceId` so you can view the tracking file for the workflow when it completes, and then enter guesses until the game is complete.</span></span> <span data-ttu-id="38351-175">Observe cómo el intento del usuario aparece en la información que se muestra en la ventana de estado en función de las actualizaciones de las actividades `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="38351-175">Note how the user's guess is displayed in the information displayed in the status window based on the updates to the `WriteLine` activities.</span></span>

    ```console
    Please enter a number between 1 and 10
    5 is too high.
    Please enter a number between 1 and 10
    3 is too high.
    Please enter a number between 1 and 10
    1 is too low.
    Please enter a number between 1 and 10
    Congratulations, you guessed the number in 4 turns.
    ```

    > [!NOTE]
    > <span data-ttu-id="38351-176">Se muestra el texto actualizado de las actividades `WriteLine`, pero no se muestra el resultado de la actividad final `WriteLine` que se agregó en este tema.</span><span class="sxs-lookup"><span data-stu-id="38351-176">The updated text from the `WriteLine` activities is displayed, but the output of the final `WriteLine` activity that was added in this topic is not.</span></span> <span data-ttu-id="38351-177">Esto se debe a que el controlador `PersistableIdle` actualiza la ventana de estado.</span><span class="sxs-lookup"><span data-stu-id="38351-177">That is because the status window is updated by the `PersistableIdle` handler.</span></span> <span data-ttu-id="38351-178">Debido a que el flujo de trabajo se completa y no queda inactivo después de la actividad final, no se llama al controlador `PersistableIdle`.</span><span class="sxs-lookup"><span data-stu-id="38351-178">Because the workflow completes and does not go idle after the final activity, the `PersistableIdle` handler is not called.</span></span> <span data-ttu-id="38351-179">Sin embargo, el controlador `Completed` muestra un mensaje similar en la ventana de estado.</span><span class="sxs-lookup"><span data-stu-id="38351-179">However, a similar message is displayed in the status window by the `Completed` handler.</span></span> <span data-ttu-id="38351-180">Si se desea, se puede agregar un código al controlador `Completed` para extraer el texto de `StringWriter` y mostrarlo en la ventana de estado.</span><span class="sxs-lookup"><span data-stu-id="38351-180">If desired, code could be added to the `Completed` handler to extract the text from the `StringWriter` and display it to the status window.</span></span>

3. <span data-ttu-id="38351-181">Abra el explorador de Windows y navegue hasta la carpeta **NumberGuessWorkflowHost\bin\debug** (o **bin\release** según la configuración del proyecto) y abra el archivo de seguimiento con el Bloc de notas correspondiente al flujo de trabajo completado.</span><span class="sxs-lookup"><span data-stu-id="38351-181">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings) and open the tracking file using Notepad that corresponds to the completed workflow.</span></span> <span data-ttu-id="38351-182">Si no tome nota de `InstanceId` , puede identificar el archivo de seguimiento correcto mediante la información de **fecha de modificación** en el explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="38351-182">If you did not make a note of the `InstanceId`, you can identify the correct tracking file by using the **Date modified** information in Windows Explorer.</span></span>

    ```console
    Please enter a number between 1 and 10
    5 is too high.
    Please enter a number between 1 and 10
    3 is too high.
    Please enter a number between 1 and 10
    1 is too low.
    Please enter a number between 1 and 10
    2 is correct. You guessed it in 4 turns.
    ```

    <span data-ttu-id="38351-183">La salida de `WriteLine` actualizada se encuentra en el archivo de seguimiento, incluida la salida de `WriteLine` que se agregó en este tema.</span><span class="sxs-lookup"><span data-stu-id="38351-183">The updated `WriteLine` output is contained within the tracking file, including the output of the `WriteLine` that was added in this topic.</span></span>

4. <span data-ttu-id="38351-184">Vuelva a la aplicación para adivinar números y seleccione uno de los flujos de trabajo iniciado antes de que se realizaran las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="38351-184">Switch back to the number guessing application and select one of the workflows that was started before the updates were made.</span></span> <span data-ttu-id="38351-185">Puede identificar la versión del flujo de trabajo seleccionado actualmente si examina la información de versión que aparece debajo de la ventana de estado.</span><span class="sxs-lookup"><span data-stu-id="38351-185">You can identify the version of the currently selected workflow by looking at the version information that is displayed below the status window.</span></span> <span data-ttu-id="38351-186">Escriba los números y observe que las actualizaciones de estado coinciden con el resultado de la actividad `WriteLine` de la versión anterior y no incluyen el intento del usuario.</span><span class="sxs-lookup"><span data-stu-id="38351-186">Enter some guesses and note that the status updates match the `WriteLine` activity output from the previous version, and do not include the user's guess.</span></span> <span data-ttu-id="38351-187">Esto se debe a que estos flujos de trabajo usan la definición de flujo de trabajo anterior que no tiene las actualizaciones `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="38351-187">That is because these workflows are using the previous workflow definition that does not have the `WriteLine` updates.</span></span>

    <span data-ttu-id="38351-188">En el paso siguiente, [Cómo: actualizar la definición de una instancia de flujo de trabajo en ejecución](how-to-update-the-definition-of-a-running-workflow-instance.md), las instancias de flujo de trabajo en ejecución `v1` se actualizan para que contengan la nueva funcionalidad como `v2` instancias.</span><span class="sxs-lookup"><span data-stu-id="38351-188">In the next step, [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md), the running `v1` workflow instances are updated so they contain the new functionality as the `v2` instances.</span></span>
