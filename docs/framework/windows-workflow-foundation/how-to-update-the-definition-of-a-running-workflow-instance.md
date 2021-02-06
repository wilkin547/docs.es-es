---
description: 'Más información acerca de cómo: actualizar la definición de una instancia de flujo de trabajo en ejecución'
title: Procedimiento para actualizar la definición de una instancia de flujo de trabajo en ejecución
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 26dfac36-ae23-4909-9867-62495b55fb5e
ms.openlocfilehash: a3b1faa933cb79301946427823ef3e9f114823f5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631231"
---
# <a name="how-to-update-the-definition-of-a-running-workflow-instance"></a><span data-ttu-id="063e2-103">Procedimiento para actualizar la definición de una instancia de flujo de trabajo en ejecución</span><span class="sxs-lookup"><span data-stu-id="063e2-103">How to: Update the Definition of a Running Workflow Instance</span></span>

<span data-ttu-id="063e2-104">La actualización dinámica proporciona un mecanismo para que los desarrolladores de aplicaciones de flujo de trabajo actualicen la definición de flujo de trabajo de una instancia de flujo de trabajo persistente.</span><span class="sxs-lookup"><span data-stu-id="063e2-104">Dynamic update provides a mechanism for workflow application developers to update the workflow definition of a persisted workflow instance.</span></span> <span data-ttu-id="063e2-105">El cambio necesario puede ser implementar una corrección de errores, nuevos requisitos o dar cabida a cambios inesperados.</span><span class="sxs-lookup"><span data-stu-id="063e2-105">The required change can be to implement a bug fix, new requirements, or to accommodate unexpected changes.</span></span> <span data-ttu-id="063e2-106">En este paso del tutorial se muestra cómo usar la actualización dinámica para modificar las instancias persistentes del `v1` flujo de trabajo de adivinación de números para que coincida con la nueva funcionalidad introducida en [Cómo: hospedar varias versiones de un flujo de trabajo en paralelo](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span><span class="sxs-lookup"><span data-stu-id="063e2-106">This step in the tutorial demonstrates how to use dynamic update to modify  persisted instances of the `v1` number guessing workflow to match the new functionality introduced in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

## <a name="in-this-topic"></a><span data-ttu-id="063e2-107">En este tema</span><span class="sxs-lookup"><span data-stu-id="063e2-107">In this topic</span></span>

- [<span data-ttu-id="063e2-108">Para crear el proyecto de CreateUpdateMaps</span><span class="sxs-lookup"><span data-stu-id="063e2-108">To create the CreateUpdateMaps project</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_CreateProject)

- [<span data-ttu-id="063e2-109">Para actualizar StateMachineNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="063e2-109">To update StateMachineNumberGuessWorkflow</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_StateMachine)

- [<span data-ttu-id="063e2-110">Para actualizar FlowchartNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="063e2-110">To update FlowchartNumberGuessWorkflow</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_Flowchart)

- [<span data-ttu-id="063e2-111">Para actualizar SequentialNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="063e2-111">To update SequentialNumberGuessWorkflow</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_Sequential)

- [<span data-ttu-id="063e2-112">Para compilar y ejecutar la aplicación CreateUpdateMaps</span><span class="sxs-lookup"><span data-stu-id="063e2-112">To build and run the CreateUpdateMaps application</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_CreateUpdateMaps)

- [<span data-ttu-id="063e2-113">Para compilar el ensamblado de flujo de trabajo actualizado</span><span class="sxs-lookup"><span data-stu-id="063e2-113">To build the updated workflow assembly</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_BuildAssembly)

- [<span data-ttu-id="063e2-114">Para actualizar WorkflowVersionMap con las nuevas versiones</span><span class="sxs-lookup"><span data-stu-id="063e2-114">To update WorkflowVersionMap with the new versions</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_UpdateWorkflowVersionMap)

- [<span data-ttu-id="063e2-115">Para aplicar las actualizaciones dinámicas</span><span class="sxs-lookup"><span data-stu-id="063e2-115">To apply the dynamic updates</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_ApplyUpdate)

- [<span data-ttu-id="063e2-116">Para ejecutar la aplicación con los flujos de trabajo actualizados</span><span class="sxs-lookup"><span data-stu-id="063e2-116">To run the application with the updated workflows</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_BuildAndRun)

- [<span data-ttu-id="063e2-117">Para habilitar la opción de iniciar versiones anteriores del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="063e2-117">To enable starting previous versions of the workflows</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_StartPreviousVersions)

### <a name="to-create-the-createupdatemaps-project"></a><a name="BKMK_CreateProject"></a> <span data-ttu-id="063e2-118">Para crear el proyecto CreateUpdateMaps</span><span class="sxs-lookup"><span data-stu-id="063e2-118">To create the CreateUpdateMaps project</span></span>

1. <span data-ttu-id="063e2-119">Haga clic con el botón derecho en **WF45GettingStartedTutorial** en **Explorador de soluciones** y elija **Agregar**, **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="063e2-119">Right-click **WF45GettingStartedTutorial** in **Solution Explorer** and choose **Add**, **New Project**.</span></span>

2. <span data-ttu-id="063e2-120">En el nodo **instalado** , seleccione **Visual C#**, **Windows** (o **Visual Basic**, **Windows**).</span><span class="sxs-lookup"><span data-stu-id="063e2-120">In the **Installed** node, select **Visual C#**, **Windows** (or **Visual Basic**, **Windows**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="063e2-121">En función del lenguaje de programación configurado como lenguaje principal en Visual Studio, es posible que el nodo **Visual C#** o **Visual Basic** se encuentre debajo del nodo **Otros lenguajes** del nodo **Instalados**.</span><span class="sxs-lookup"><span data-stu-id="063e2-121">Depending on which programming language is configured as the primary language in Visual Studio, the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>

     <span data-ttu-id="063e2-122">Asegúrese de que **.NET Framework 4.5** está seleccionado en la lista desplegable de versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="063e2-122">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="063e2-123">Seleccione **aplicación de consola** en la lista de **ventanas** .</span><span class="sxs-lookup"><span data-stu-id="063e2-123">Select **Console Application** from the **Windows** list.</span></span> <span data-ttu-id="063e2-124">Escriba **CreateUpdateMaps** en el cuadro **nombre** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="063e2-124">Type **CreateUpdateMaps** into the **Name** box and click **OK**.</span></span>

3. <span data-ttu-id="063e2-125">Haga clic con el botón secundario en **CreateUpdateMaps** en **Explorador de soluciones** y elija **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="063e2-125">Right-click **CreateUpdateMaps** in **Solution Explorer** and choose **Add Reference**.</span></span>

4. <span data-ttu-id="063e2-126">Seleccione **Framework** en el nodo **ensamblados** de la lista **Agregar referencia** .</span><span class="sxs-lookup"><span data-stu-id="063e2-126">Select **Framework** from the **Assemblies** node in the **Add Reference** list.</span></span> <span data-ttu-id="063e2-127">Escriba **System. Activities** en el cuadro **buscar ensamblados** para filtrar los ensamblados y facilitar la selección de las referencias deseadas.</span><span class="sxs-lookup"><span data-stu-id="063e2-127">Type **System.Activities** into the **Search Assemblies** box to filter the assemblies and make the desired references easier to select.</span></span>

5. <span data-ttu-id="063e2-128">Active la casilla situada junto a **System. Activities** en la lista resultados de la **búsqueda** .</span><span class="sxs-lookup"><span data-stu-id="063e2-128">Check the checkbox beside **System.Activities** from the **Search Results** list.</span></span>

6. <span data-ttu-id="063e2-129">Escriba **serialización** en el cuadro **buscar ensamblados** y active la casilla situada junto a **System. Runtime. Serialization** en la lista de resultados de la **búsqueda** .</span><span class="sxs-lookup"><span data-stu-id="063e2-129">Type **Serialization** into the **Search Assemblies** box, and check the checkbox beside **System.Runtime.Serialization** from the **Search Results** list.</span></span>

7. <span data-ttu-id="063e2-130">Escriba **System. Xaml** en el cuadro **buscar ensamblados** y active la casilla situada junto a **System. Xaml** en la lista resultados de la **búsqueda** .</span><span class="sxs-lookup"><span data-stu-id="063e2-130">Type **System.Xaml** into the **Search Assemblies** box, and check the checkbox beside **System.Xaml** from the **Search Results** list.</span></span>

8. <span data-ttu-id="063e2-131">Haga clic en **Aceptar** para cerrar el **Administrador de referencias** y agregar las referencias.</span><span class="sxs-lookup"><span data-stu-id="063e2-131">Click **OK** to close **Reference Manager** and add the references.</span></span>

9. <span data-ttu-id="063e2-132">Agregue las siguientes instrucciones `using` (o `Imports`) al principio del archivo con las demás instrucciones `using` (o `Imports`).</span><span class="sxs-lookup"><span data-stu-id="063e2-132">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Activities
    Imports System.Activities.Statements
    Imports System.Xaml
    Imports System.Reflection
    Imports System.IO
    Imports System.Activities.XamlIntegration
    Imports System.Activities.DynamicUpdate
    Imports System.Runtime.Serialization
    Imports Microsoft.VisualBasic.Activities
    ```

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    using System.IO;
    using System.Xaml;
    using System.Reflection;
    using System.Activities.XamlIntegration;
    using System.Activities.DynamicUpdate;
    using System.Runtime.Serialization;
    using Microsoft.CSharp.Activities;
    ```

10. <span data-ttu-id="063e2-133">Agregue los dos miembros de cadena siguientes a la clase `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="063e2-133">Add the following two string members to the `Program` class (or `Module1`).</span></span>

    ```vb
    Const mapPath = "..\..\..\PreviousVersions"
    Const definitionPath = "..\..\..\NumberGuessWorkflowActivities_du"
    ```

    ```csharp
    const string mapPath = @"..\..\..\PreviousVersions";
    const string definitionPath = @"..\..\..\NumberGuessWorkflowActivities_du";
    ```

11. <span data-ttu-id="063e2-134">Agregue el siguiente método `StartUpdate` a la clase `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="063e2-134">Add the following `StartUpdate` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="063e2-135">Este método carga la definición de flujo de trabajo de xaml especificada en `ActivityBuilder` y, a continuación, llama a `DynamicUpdate.PrepareForUpdate`.</span><span class="sxs-lookup"><span data-stu-id="063e2-135">This method loads up the specified xaml workflow definition into an `ActivityBuilder`, and then calls `DynamicUpdate.PrepareForUpdate`.</span></span> <span data-ttu-id="063e2-136">`PrepareForUpdate` realiza una copia de la definición de flujo de trabajo dentro de `ActivityBuilder`.</span><span class="sxs-lookup"><span data-stu-id="063e2-136">`PrepareForUpdate` makes a copy of the workflow definition inside the `ActivityBuilder`.</span></span> <span data-ttu-id="063e2-137">Después de que se modifique la definición de flujo de trabajo, esta copia se usa junto con la definición de flujo de trabajo modificado para crear la asignación de actualización.</span><span class="sxs-lookup"><span data-stu-id="063e2-137">After the workflow definition is modified, this copy is used along with the modified workflow definition to create the update map.</span></span>

    ```vb
    Private Function StartUpdate(name As String) As ActivityBuilder
        'Create the XamlXmlReaderSettings.
        Dim readerSettings As XamlReaderSettings = New XamlXmlReaderSettings()
        'In the XAML the "local" namespace refers to artifacts that come from
        'the same project as the XAML. When loading XAML if the currently executing
        'assembly is not the same assembly that was referred to as "local" in the XAML
        'LocalAssembly must be set to the assembly containing the artifacts.
        'Assembly.LoadFile requires an absolute path so convert this relative path
        'to an absolute path.
        readerSettings.LocalAssembly = Assembly.LoadFile(
            Path.GetFullPath(Path.Combine(mapPath, "NumberGuessWorkflowActivities_v1.dll")))

        Dim fullPath As String = Path.Combine(definitionPath, name)
        Dim xamlReader As XamlXmlReader = New XamlXmlReader(fullPath, readerSettings)

        'Load the workflow definition into an ActivityBuilder.
        Dim wf As ActivityBuilder = XamlServices.Load(
            ActivityXamlServices.CreateBuilderReader(xamlReader))

        'PrepareForUpdate makes a copy of the workflow definition in the
        'ActivityBuilder that is used for comparison when the update
        'map is created.
        DynamicUpdateServices.PrepareForUpdate(wf)

        Return wf
    End Function
    ```

    ```csharp
    private static ActivityBuilder StartUpdate(string name)
    {
        // Create the XamlXmlReaderSettings.
        XamlXmlReaderSettings readerSettings = new XamlXmlReaderSettings()
        {
            // In the XAML the "local" namespace refers to artifacts that come from
            // the same project as the XAML. When loading XAML if the currently executing
            // assembly is not the same assembly that was referred to as "local" in the XAML
            // LocalAssembly must be set to the assembly containing the artifacts.
            // Assembly.LoadFile requires an absolute path so convert this relative path
            // to an absolute path.
            LocalAssembly = Assembly.LoadFile(
                Path.GetFullPath(Path.Combine(mapPath, "NumberGuessWorkflowActivities_v1.dll")))
        };

        string path = Path.Combine(definitionPath, name);
        XamlXmlReader xamlReader = new XamlXmlReader(path, readerSettings);

        // Load the workflow definition into an ActivityBuilder.
        ActivityBuilder wf = XamlServices.Load(
            ActivityXamlServices.CreateBuilderReader(xamlReader))
            as ActivityBuilder;

        // PrepareForUpdate makes a copy of the workflow definition in the
        // ActivityBuilder that is used for comparison when the update
        // map is created.
        DynamicUpdateServices.PrepareForUpdate(wf);

        return wf;
    }
    ```

12. <span data-ttu-id="063e2-138">A continuación, agregue el siguiente `CreateUpdateMethod` a la clase `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="063e2-138">Next, add the following `CreateUpdateMethod` to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="063e2-139">Esto crea una asignación de actualización dinámica al llamar a DynamicUpdateServices.CreateUpdateMap y, a continuación, guarda la asignación de actualización con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="063e2-139">This creates a dynamic update map by calling DynamicUpdateServices.CreateUpdateMap, and then saves the update map using the specified name.</span></span> <span data-ttu-id="063e2-140">Esta asignación de actualización contiene la información que necesita el runtime de flujo de trabajo para actualizar una instancia de flujo de trabajo persistente que se inició mediante la definición de flujo de trabajo inicial incluida en `ActivityBuilder`, de modo que se completa con la definición de flujo de trabajo actualizada.</span><span class="sxs-lookup"><span data-stu-id="063e2-140">This update map contains the information needed by the workflow runtime to update a persisted workflow instance that was started using the original workflow definition contained in the `ActivityBuilder` so that it completes using the updated workflow definition.</span></span>

    ```vb
    Private Sub CreateUpdateMaps(wf As ActivityBuilder, name As String)
        'Create the UpdateMap.
        Dim map As DynamicUpdateMap =
            DynamicUpdateServices.CreateUpdateMap(wf)

        'Serialize it to a file.
        Dim mapFullPath As String = Path.Combine(mapPath, name)
        Dim sz As DataContractSerializer = New DataContractSerializer(GetType(DynamicUpdateMap))
        Using fs As FileStream = File.Open(mapFullPath, FileMode.Create)
            sz.WriteObject(fs, map)
        End Using
    End Sub
    ```

    ```csharp
    private static void CreateUpdateMaps(ActivityBuilder wf, string name)
    {
        // Create the UpdateMap.
        DynamicUpdateMap map =
            DynamicUpdateServices.CreateUpdateMap(wf);

        // Serialize it to a file.
        string path = Path.Combine(mapPath, name);
        DataContractSerializer sz = new DataContractSerializer(typeof(DynamicUpdateMap));
        using (FileStream fs = System.IO.File.Open(path, FileMode.Create))
        {
            sz.WriteObject(fs, map);
        }
    }
    ```

13. <span data-ttu-id="063e2-141">Agregue el siguiente método `SaveUpdatedDefinition` a la clase `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="063e2-141">Add the following `SaveUpdatedDefinition` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="063e2-142">Este método guarda la definición de flujo de trabajo actualizado una vez creada la asignación de actualización.</span><span class="sxs-lookup"><span data-stu-id="063e2-142">This method saves the updated workflow definition once the update map is created.</span></span>

    ```vb
    Private Sub SaveUpdatedDefinition(wf As ActivityBuilder, name As String)
        Dim xamlPath As String = Path.Combine(definitionPath, name)
        Dim sw As StreamWriter = File.CreateText(xamlPath)
        Dim xw As XamlWriter = ActivityXamlServices.CreateBuilderWriter(
            New XamlXmlWriter(sw, New XamlSchemaContext()))
        XamlServices.Save(xw, wf)
        sw.Close()
    End Sub
    ```

    ```csharp
    private static void SaveUpdatedDefinition(ActivityBuilder wf, string name)
    {
        string xamlPath = Path.Combine(definitionPath, name);
        StreamWriter sw = File.CreateText(xamlPath);
        XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(
            new XamlXmlWriter(sw, new XamlSchemaContext()));
        XamlServices.Save(xw, wf);
        sw.Close();
    }
    ```

### <a name="to-update-statemachinenumberguessworkflow"></a><a name="BKMK_StateMachine"></a> <span data-ttu-id="063e2-143">Para actualizar StateMachineNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="063e2-143">To update StateMachineNumberGuessWorkflow</span></span>

1. <span data-ttu-id="063e2-144">Agregue `CreateStateMachineUpdateMap` a la clase `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="063e2-144">Add a `CreateStateMachineUpdateMap` to the `Program` class (or `Module1`).</span></span>

    ```vb
    Private Sub CreateStateMachineUpdateMap()

    End Sub
    ```

    ```csharp
    private static void CreateStateMachineUpdateMap()
    {
    }
    ```

2. <span data-ttu-id="063e2-145">Realice una llamada a `StartUpdate` y, a continuación, obtenga una referencia a la actividad `StateMachine` raíz del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="063e2-145">Make a call to `StartUpdate` and then get a reference to the root `StateMachine` activity of the workflow.</span></span>

    ```vb
    Dim wf As ActivityBuilder = StartUpdate("StateMachineNumberGuessWorkflow.xaml")

    'Get a reference to the root StateMachine activity.
    Dim sm As StateMachine = wf.Implementation
    ```

    ```csharp
    ActivityBuilder wf = StartUpdate("StateMachineNumberGuessWorkflow.xaml");

    // Get a reference to the root StateMachine activity.
    StateMachine sm = wf.Implementation as StateMachine;
    ```

3. <span data-ttu-id="063e2-146">A continuación, actualice las expresiones de las dos `WriteLine` actividades que muestran si la suposición del usuario es demasiado alta o demasiado baja, de modo que coincidan con las actualizaciones realizadas en [Cómo hospedar varias versiones de un flujo de trabajo en paralelo](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span><span class="sxs-lookup"><span data-stu-id="063e2-146">Next, update the expressions of the two `WriteLine` activities that display whether the user's guess is too high or too low so that they match the updates made in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

    ```vb
    'Update the Text of the two WriteLine activities that write the
    'results of the user's guess. They are contained in the workflow as the
    'Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
    Dim guessLow As Statements.If = sm.States(1).Transitions(1).Action

    'Update the "too low" message.
    Dim tooLow As WriteLine = guessLow.Then
    tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")

    'Update the "too high" message.
    Dim tooHigh As WriteLine = guessLow.Else
    tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")
    ```

    ```csharp
    // Update the Text of the two WriteLine activities that write the
    // results of the user's guess. They are contained in the workflow as the
    // Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
    If guessLow = sm.States[1].Transitions[1].Action as If;

    // Update the "too low" message.
    WriteLine tooLow = guessLow.Then as WriteLine;
    tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");

    // Update the "too high" message.
    WriteLine tooHigh = guessLow.Else as WriteLine;
    tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");
    ```

4. <span data-ttu-id="063e2-147">A continuación, agregue la nueva actividad `WriteLine` que muestra el mensaje de cierre.</span><span class="sxs-lookup"><span data-stu-id="063e2-147">Next, add the new `WriteLine` activity that displays the closing message.</span></span>

    ```vb
    'Create the new WriteLine that displays the closing message.
    Dim wl As New WriteLine() With
    {
        .Text = New VisualBasicValue(Of String) _
            ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
    }

    'Add it as the Action for the Guess Correct transition. The Guess Correct
    'transition is the first transition of States[1]. The transitions are listed
    'at the bottom of the State activity designer.
    sm.States(1).Transitions(0).Action = wl
    ```

    ```csharp
    // Create the new WriteLine that displays the closing message.
    WriteLine wl = new WriteLine
    {
        Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
    };

    // Add it as the Action for the Guess Correct transition. The Guess Correct
    // transition is the first transition of States[1]. The transitions are listed
    // at the bottom of the State activity designer.
    sm.States[1].Transitions[0].Action = wl;
    ```

5. <span data-ttu-id="063e2-148">Una vez actualizado el flujo de trabajo, llame a `CreateUpdateMaps` y a `SaveUpdatedDefinition`.</span><span class="sxs-lookup"><span data-stu-id="063e2-148">After the workflow is updated, call `CreateUpdateMaps` and `SaveUpdatedDefinition`.</span></span> <span data-ttu-id="063e2-149">`CreateUpdateMaps` crea y guarda `DynamicUpdateMap`, y `SaveUpdatedDefinition` guarda la definición de flujo de trabajo actualizada.</span><span class="sxs-lookup"><span data-stu-id="063e2-149">`CreateUpdateMaps` creates and saves the `DynamicUpdateMap`, and `SaveUpdatedDefinition` saves the updated workflow definition.</span></span>

    ```vb
    'Create the update map.
    CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map")

    'Save the updated workflow definition.
    SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml")
    ```

    ```csharp
    // Create the update map.
    CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map");

    // Save the updated workflow definition.
    SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml");
    ```

    <span data-ttu-id="063e2-150">El siguiente ejemplo es el método `CreateStateMachineUpdateMap` completado.</span><span class="sxs-lookup"><span data-stu-id="063e2-150">The following example is the completed `CreateStateMachineUpdateMap` method.</span></span>

    ```vb
    Private Sub CreateStateMachineUpdateMap()
        Dim wf As ActivityBuilder = StartUpdate("StateMachineNumberGuessWorkflow.xaml")

        'Get a reference to the root StateMachine activity.
        Dim sm As StateMachine = wf.Implementation

        'Update the Text of the two WriteLine activities that write the
        'results of the user's guess. They are contained in the workflow as the
        'Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
        Dim guessLow As Statements.If = sm.States(1).Transitions(1).Action

        'Update the "too low" message.
        Dim tooLow As WriteLine = guessLow.Then
        tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")

        'Update the "too high" message.
        Dim tooHigh As WriteLine = guessLow.Else
        tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")

        'Create the new WriteLine that displays the closing message.
        Dim wl As New WriteLine() With
        {
            .Text = New VisualBasicValue(Of String) _
                ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
        }

        'Add it as the Action for the Guess Correct transition. The Guess Correct
        'transition is the first transition of States[1]. The transitions are listed
        'at the bottom of the State activity designer.
        sm.States(1).Transitions(0).Action = wl

        'Create the update map.
        CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map")

        'Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml")
    End Sub
    ```

    ```csharp
    private static void CreateStateMachineUpdateMap()
    {
        ActivityBuilder wf = StartUpdate("StateMachineNumberGuessWorkflow.xaml");

        // Get a reference to the root StateMachine activity.
        StateMachine sm = wf.Implementation as StateMachine;

        // Update the Text of the two WriteLine activities that write the
        // results of the user's guess. They are contained in the workflow as the
        // Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
        If guessLow = sm.States[1].Transitions[1].Action as If;

        // Update the "too low" message.
        WriteLine tooLow = guessLow.Then as WriteLine;
        tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");

        // Update the "too high" message.
        WriteLine tooHigh = guessLow.Else as WriteLine;
        tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");

        // Create the new WriteLine that displays the closing message.
        WriteLine wl = new WriteLine
        {
            Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
        };

        // Add it as the Action for the Guess Correct transition. The Guess Correct
        // transition is the first transition of States[1]. The transitions are listed
        // at the bottom of the State activity designer.
        sm.States[1].Transitions[0].Action = wl;

        // Create the update map.
        CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map");

        // Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml");
    }
    ```

### <a name="to-update-flowchartnumberguessworkflow"></a><a name="BKMK_Flowchart"></a> <span data-ttu-id="063e2-151">Para actualizar FlowchartNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="063e2-151">To update FlowchartNumberGuessWorkflow</span></span>

1. <span data-ttu-id="063e2-152">Agregue el siguiente `CreateFlowchartUpdateMethod` a la clase `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="063e2-152">Add the following `CreateFlowchartUpdateMethod` to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="063e2-153">Este método es parecido a `CreateStateMachineUpdateMap`.</span><span class="sxs-lookup"><span data-stu-id="063e2-153">This method is similar to `CreateStateMachineUpdateMap`.</span></span> <span data-ttu-id="063e2-154">Comienza con una llamada a `StartUpdate`, actualiza la definición de flujo de trabajo del diagrama de flujo y finaliza guardando la asignación de actualización y la definición de flujo de trabajo actualizada.</span><span class="sxs-lookup"><span data-stu-id="063e2-154">It starts with a call to `StartUpdate`, updates the flowchart workflow definition, and finishes by saving the update map and the updated workflow definition.</span></span>

    ```vb
    Private Sub CreateFlowchartUpdateMap()
        Dim wf As ActivityBuilder = StartUpdate("FlowchartNumberGuessWorkflow.xaml")

        'Get a reference to the root Flowchart activity.
        Dim fc As Flowchart = wf.Implementation

        'Update the Text of the two WriteLine activities that write the
        'results of the user's guess. They are contained in the workflow as the
        'True and False action of the "Guess < Target" FlowDecision, which is
        'Nodes[4].
        Dim guessLow As FlowDecision = fc.Nodes(4)

        'Update the "too low" message.
        Dim trueStep As FlowStep = guessLow.True
        Dim tooLow As WriteLine = trueStep.Action
        tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")

        'Update the "too high" message.
        Dim falseStep As FlowStep = guessLow.False
        Dim tooHigh As WriteLine = falseStep.Action
        tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")

        'Create the new WriteLine that displays the closing message.
        Dim wl As New WriteLine() With
        {
            .Text = New VisualBasicValue(Of String) _
                ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
        }

        'Create a FlowStep to hold the WriteLine.
        Dim closingStep As New FlowStep() With
        {
            .Action = wl
        }

        'Add this new FlowStep to the True action of the
        '"Guess = Guess" FlowDecision
        Dim guessCorrect As FlowDecision = fc.Nodes(3)
        guessCorrect.True = closingStep

        'Add the new FlowStep to the Nodes collection.
        'If closingStep was replacing an existing node then
        'we would need to remove that Step from the collection.
        'In this example there was no existing True step to remove.
        fc.Nodes.Add(closingStep)

        'Create the update map.
        CreateUpdateMaps(wf, "FlowchartNumberGuessWorkflow.map")

        'Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "FlowchartNumberGuessWorkflow_du.xaml")
    End Sub
    ```

    ```csharp
    private static void CreateFlowchartUpdateMap()
    {
        ActivityBuilder wf = StartUpdate("FlowchartNumberGuessWorkflow.xaml");

        // Get a reference to the root Flowchart activity.
        Flowchart fc = wf.Implementation as Flowchart;

        // Update the Text of the two WriteLine activities that write the
        // results of the user's guess. They are contained in the workflow as the
        // True and False action of the "Guess < Target" FlowDecision, which is
        // Nodes[4].
        FlowDecision guessLow = fc.Nodes[4] as FlowDecision;

        // Update the "too low" message.
        FlowStep trueStep = guessLow.True as FlowStep;
        WriteLine tooLow = trueStep.Action as WriteLine;
        tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");

        // Update the "too high" message.
        FlowStep falseStep = guessLow.False as FlowStep;
        WriteLine tooHigh = falseStep.Action as WriteLine;
        tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");

        // Add the new WriteLine that displays the closing message.
        WriteLine wl = new WriteLine
        {
            Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
        };

        // Create a FlowStep to hold the WriteLine.
        FlowStep closingStep = new FlowStep
        {
            Action = wl
        };

        // Add this new FlowStep to the True action of the
        // "Guess == Guess" FlowDecision
        FlowDecision guessCorrect = fc.Nodes[3] as FlowDecision;
        guessCorrect.True = closingStep;

        // Add the new FlowStep to the Nodes collection.
        // If closingStep was replacing an existing node then
        // we would need to remove that Step from the collection.
        // In this example there was no existing True step to remove.
        fc.Nodes.Add(closingStep);

        // Create the update map.
        CreateUpdateMaps(wf, "FlowchartNumberGuessWorkflow.map");

        //  Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "FlowchartNumberGuessWorkflow_du.xaml");
    }
    ```

### <a name="to-update-sequentialnumberguessworkflow"></a><a name="BKMK_Sequential"></a> <span data-ttu-id="063e2-155">Para actualizar SequentialNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="063e2-155">To update SequentialNumberGuessWorkflow</span></span>

1. <span data-ttu-id="063e2-156">Agregue el siguiente `CreateSequentialUpdateMethod` a la clase `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="063e2-156">Add the following `CreateSequentialUpdateMethod` to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="063e2-157">Este método es similar a los otros dos métodos.</span><span class="sxs-lookup"><span data-stu-id="063e2-157">This method is similar to the other two methods.</span></span> <span data-ttu-id="063e2-158">Comienza con una llamada a `StartUpdate`, actualiza la definición de flujo de trabajo secuencial y finaliza guardando la asignación de actualización y la definición de flujo de trabajo actualizada.</span><span class="sxs-lookup"><span data-stu-id="063e2-158">It starts with a call to `StartUpdate`, updates the sequential workflow definition, and finishes by saving the update map and the updated workflow definition.</span></span>

    ```vb
    Private Sub CreateSequentialUpdateMap()
        Dim wf As ActivityBuilder = StartUpdate("SequentialNumberGuessWorkflow.xaml")

        'Get a reference to the root activity in the workflow.
        Dim rootSequence As Sequence = wf.Implementation

        'Update the Text of the two WriteLine activities that write the
        'results of the user's guess. They are contained in the workflow as the
        'Then and Else action of the "Guess < Target" If activity.
        'Sequence[1]->DoWhile->Body->Sequence[2]->If->Then->If
        Dim gameLoop As Statements.DoWhile = rootSequence.Activities(1)
        Dim gameBody As Sequence = gameLoop.Body
        Dim guessCorrect As Statements.If = gameBody.Activities(2)
        Dim guessLow As Statements.If = guessCorrect.Then
        Dim tooLow As WriteLine = guessLow.Then
        tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")
        Dim tooHigh As WriteLine = guessLow.Else
        tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")

        'Create the new WriteLine that displays the closing message.
        Dim wl As New WriteLine() With
        {
            .Text = New VisualBasicValue(Of String) _
                ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
        }

        'Insert it as the third activity in the root sequence
        rootSequence.Activities.Insert(2, wl)

        'Create the update map.
        CreateUpdateMaps(wf, "SequentialNumberGuessWorkflow.map")

        'Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "SequentialNumberGuessWorkflow_du.xaml")
    End Sub
    ```

    ```csharp
    private static void CreateSequentialUpdateMap()
    {
        ActivityBuilder wf = StartUpdate("SequentialNumberGuessWorkflow.xaml");

        // Get a reference to the root activity in the workflow.
        Sequence rootSequence = wf.Implementation as Sequence;

        // Update the Text of the two WriteLine activities that write the
        // results of the user's guess. They are contained in the workflow as the
        // Then and Else action of the "Guess < Target" If activity.
        // Sequence[1]->DoWhile->Body->Sequence[2]->If->Then->If
        DoWhile gameLoop = rootSequence.Activities[1] as DoWhile;
        Sequence gameBody = gameLoop.Body as Sequence;
        If guessCorrect = gameBody.Activities[2] as If;
        If guessLow = guessCorrect.Then as If;
        WriteLine tooLow = guessLow.Then as WriteLine;
        tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");
        WriteLine tooHigh = guessLow.Else as WriteLine;
        tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");

        // Add the new WriteLine that displays the closing message.
        WriteLine wl = new WriteLine
        {
            Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
        };

        // Insert it as the third activity in the root sequence
        rootSequence.Activities.Insert(2, wl);

        // Create the update map.
        CreateUpdateMaps(wf, "SequentialNumberGuessWorkflow.map");

        // Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "SequentialNumberGuessWorkflow_du.xaml");
    }
    ```

### <a name="to-build-and-run-the-createupdatemaps-application"></a><a name="BKMK_CreateUpdateMaps"></a> <span data-ttu-id="063e2-159">Para compilar y ejecutar la aplicación CreateUpdateMaps</span><span class="sxs-lookup"><span data-stu-id="063e2-159">To build and run the CreateUpdateMaps application</span></span>

1. <span data-ttu-id="063e2-160">Actualice el método `Main` y agregue las tres llamadas de método siguientes.</span><span class="sxs-lookup"><span data-stu-id="063e2-160">Update the `Main` method and add the following three method calls.</span></span> <span data-ttu-id="063e2-161">Estos métodos se agregan en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="063e2-161">These methods are added in the following sections.</span></span> <span data-ttu-id="063e2-162">Cada método actualiza el flujo de trabajo de acierto de números correspondiente y crea un elemento `DynamicUpdateMap` que describe las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="063e2-162">Each method updates the corresponding number guess workflow and creates a `DynamicUpdateMap` that describes the updates.</span></span>

    ```vb
    Sub Main()
        'Create the update maps for the changes needed to the v1 activities
        'so they match the v2 activities.
        CreateSequentialUpdateMap()
        CreateFlowchartUpdateMap()
        CreateStateMachineUpdateMap()
    End Sub
    ```

    ```csharp
    static void Main(string[] args)
    {
        // Create the update maps for the changes needed to the v1 activities
        // so they match the v2 activities.
        CreateSequentialUpdateMap();
        CreateFlowchartUpdateMap();
        CreateStateMachineUpdateMap();
    }
    ```

2. <span data-ttu-id="063e2-163">Haga clic con el botón derecho en **CreateUpdateMaps** en **Explorador de soluciones** y elija **establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="063e2-163">Right-click **CreateUpdateMaps** in **Solution Explorer** and choose **Set as StartUp Project**.</span></span>

3. <span data-ttu-id="063e2-164">Presione CTRL+MAYÚS+B para compilar la solución y, a continuación, CTRL+F5 para ejecutar la aplicación `CreateUpdateMaps`.</span><span class="sxs-lookup"><span data-stu-id="063e2-164">Press CTRL+SHIFT+B to build the solution, and then CTRL+F5 to run the `CreateUpdateMaps` application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="063e2-165">La `CreateUpdateMaps` aplicación no muestra ninguna información de estado durante la ejecución, pero si mira en la carpeta **NumberGuessWorkflowActivities_du** y en la carpeta **PreviousVersions** , verá los archivos de definición de flujo de trabajo actualizados y las asignaciones de actualización.</span><span class="sxs-lookup"><span data-stu-id="063e2-165">The `CreateUpdateMaps` application does not display any status information while running, but if you look in the **NumberGuessWorkflowActivities_du** folder and the **PreviousVersions** folder you will see the updated workflow definition files and the update maps.</span></span>

    <span data-ttu-id="063e2-166">Una vez creadas las asignaciones de actualización y actualizadas las definiciones de flujo de trabajo, el siguiente paso es compilar un ensamblado de flujo de trabajo actualizado que contenga las definiciones actualizadas.</span><span class="sxs-lookup"><span data-stu-id="063e2-166">Once the update maps are created and the workflow definitions updated, the next step is to build an updated workflow assembly containing the updated definitions.</span></span>

### <a name="to-build-the-updated-workflow-assembly"></a><a name="BKMK_BuildAssembly"></a> <span data-ttu-id="063e2-167">Para compilar el ensamblado de flujo de trabajo actualizado</span><span class="sxs-lookup"><span data-stu-id="063e2-167">To build the updated workflow assembly</span></span>

1. <span data-ttu-id="063e2-168">Abra una segunda instancia de Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="063e2-168">Open a second instance of Visual Studio 2012.</span></span>

2. <span data-ttu-id="063e2-169">Elija **abrir**, **proyecto o solución** en el menú **archivo** .</span><span class="sxs-lookup"><span data-stu-id="063e2-169">Choose **Open**, **Project/Solution** from the **File** menu.</span></span>

3. <span data-ttu-id="063e2-170">Navegue hasta la carpeta **NumberGuessWorkflowActivities_du** que creó en [Cómo hospedar varias versiones de un flujo de trabajo en paralelo](how-to-host-multiple-versions-of-a-workflow-side-by-side.md), seleccione **NumberGuessWorkflowActivities. csproj** (o **vbproj**) y haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="063e2-170">Navigate to the **NumberGuessWorkflowActivities_du** folder you created in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md), select **NumberGuessWorkflowActivities.csproj** (or **vbproj**), and click **Open**.</span></span>

4. <span data-ttu-id="063e2-171">En **Explorador de soluciones**, haga clic con el botón secundario en **SequentialNumberGuessWorkflow. Xaml** y elija **excluir del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="063e2-171">In **Solution Explorer**, right click **SequentialNumberGuessWorkflow.xaml** and choose **Exclude From Project**.</span></span> <span data-ttu-id="063e2-172">Haga lo mismo para **FlowchartNumberGuessWorkflow. Xaml** y **StateMachineNumberGuessWorkflow. Xaml**.</span><span class="sxs-lookup"><span data-stu-id="063e2-172">Do the same thing for **FlowchartNumberGuessWorkflow.xaml** and **StateMachineNumberGuessWorkflow.xaml**.</span></span> <span data-ttu-id="063e2-173">Este paso quita las versiones anteriores de las definiciones de flujo de trabajo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="063e2-173">This step removes the previous versions of the workflow definitions from the project.</span></span>

5. <span data-ttu-id="063e2-174">Elija **Agregar elemento existente** en el menú **proyecto** .</span><span class="sxs-lookup"><span data-stu-id="063e2-174">Choose **Add Existing Item** from the **Project** menu.</span></span>

6. <span data-ttu-id="063e2-175">Navegue hasta la carpeta **NumberGuessWorkflowActivities_du** que creó en [Cómo hospedar varias versiones de un flujo de trabajo en paralelo](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span><span class="sxs-lookup"><span data-stu-id="063e2-175">Navigate to the **NumberGuessWorkflowActivities_du** folder you created in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

7. <span data-ttu-id="063e2-176">Elija **archivos XAML ( \* . XAML; \* . xoml)** en la lista desplegable **archivos de tipo** .</span><span class="sxs-lookup"><span data-stu-id="063e2-176">Choose **XAML Files (\*.xaml;\*.xoml)** from the **Files of type** drop-down list.</span></span>

8. <span data-ttu-id="063e2-177">Seleccione **SequentialNumberGuessWorkflow_du. Xaml**, **FlowchartNumberGuessWorkflow_du. Xaml** y **StateMachineNumberGuessWorkflow_du. Xaml** y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="063e2-177">Select **SequentialNumberGuessWorkflow_du.xaml**, **FlowchartNumberGuessWorkflow_du.xaml**, and **StateMachineNumberGuessWorkflow_du.xaml** and click **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="063e2-178">Presione CTRL y haga clic para seleccionar varios elementos a la vez.</span><span class="sxs-lookup"><span data-stu-id="063e2-178">CTRL+Click to select multiple items at a time.</span></span>

    <span data-ttu-id="063e2-179">Este paso agrega las versiones actualizadas de las definiciones de flujo de trabajo al proyecto.</span><span class="sxs-lookup"><span data-stu-id="063e2-179">This step adds the updated versions of the workflow definitions to the project.</span></span>

9. <span data-ttu-id="063e2-180">Presione Ctrl+Mayús+B para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="063e2-180">Press CTRL+SHIFT+B to build the project.</span></span>

10. <span data-ttu-id="063e2-181">Elija **cerrar solución** en el menú **archivo** .</span><span class="sxs-lookup"><span data-stu-id="063e2-181">Choose **Close Solution** from the **File** menu.</span></span> <span data-ttu-id="063e2-182">No es necesario un archivo de solución para el proyecto, así que haga clic en **no** para cerrar Visual Studio sin guardar un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="063e2-182">A solution file for the project is not required, so click **No** to close Visual Studio without saving a solution file.</span></span> <span data-ttu-id="063e2-183">Elija **salir** en el menú **archivo** para cerrar Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="063e2-183">Choose **Exit** from the **File** menu to close Visual Studio.</span></span>

11. <span data-ttu-id="063e2-184">Abra el explorador de Windows y navegue hasta la carpeta **NumberGuessWorkflowActivities_du \bin\debug** (o **bin\Release** en función de la configuración del proyecto).</span><span class="sxs-lookup"><span data-stu-id="063e2-184">Open Windows Explorer and navigate to the **NumberGuessWorkflowActivities_du\bin\Debug** folder (or **bin\Release** depending on your project settings).</span></span>

12. <span data-ttu-id="063e2-185">Cambie el nombre **NumberGuessWorkflowActivities.dll** a **NumberGuessWorkflowActivities_v15.dll** y cópielo en la carpeta **PreviousVersions** que creó en [Cómo hospedar varias versiones de un flujo de trabajo en paralelo](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span><span class="sxs-lookup"><span data-stu-id="063e2-185">Rename **NumberGuessWorkflowActivities.dll** to **NumberGuessWorkflowActivities_v15.dll**, and copy it to the **PreviousVersions** folder you created in [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

### <a name="to-update-workflowversionmap-with-the-new-versions"></a><a name="BKMK_UpdateWorkflowVersionMap"></a> <span data-ttu-id="063e2-186">Para actualizar WorkflowVersionMap con las nuevas versiones</span><span class="sxs-lookup"><span data-stu-id="063e2-186">To update WorkflowVersionMap with the new versions</span></span>

1. <span data-ttu-id="063e2-187">Vuelva a la instancia inicial de Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="063e2-187">Switch back to the initial instance of Visual Studio 2012.</span></span>

2. <span data-ttu-id="063e2-188">Haga doble clic en **WorkflowVersionMap.CS** (o **WorkflowVersionMap. VB**) en el proyecto **NumberGuessWorkflowHost** para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="063e2-188">Double-click **WorkflowVersionMap.cs** (or **WorkflowVersionMap.vb**) under the **NumberGuessWorkflowHost** project to open it.</span></span>

3. <span data-ttu-id="063e2-189">Agregue tres nuevas identidades de flujo de trabajo justo debajo de las seis declaraciones de identidad de flujo de trabajo existentes.</span><span class="sxs-lookup"><span data-stu-id="063e2-189">Add three new workflow identities just below the six existing workflow identity declarations.</span></span> <span data-ttu-id="063e2-190">En este tutorial, `1.5.0.0` se usa como `WorkflowIdentity.Version` para las identidades de actualización dinámica.</span><span class="sxs-lookup"><span data-stu-id="063e2-190">In this tutorial, `1.5.0.0` is used as the `WorkflowIdentity.Version` for the dynamic update identities.</span></span> <span data-ttu-id="063e2-191">Estas nuevas identidades de flujo de trabajo de `v15` se usarán para proporcionar la definición de flujo de trabajo correcta para las instancias de flujo de trabajo persistentes y actualizadas dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="063e2-191">These new `v15` workflow identities will be used provide the correct workflow definition for the dynamically updated persisted workflow instances.</span></span>

    ```vb
    'Current version identities.
    Public StateMachineNumberGuessIdentity As WorkflowIdentity
    Public FlowchartNumberGuessIdentity As WorkflowIdentity
    Public SequentialNumberGuessIdentity As WorkflowIdentity

    'v1 identities.
    Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
    Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
    Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity

    'v1.5 (Dynamic Update) identities.
    Public StateMachineNumberGuessIdentity_v15 As WorkflowIdentity
    Public FlowchartNumberGuessIdentity_v15 As WorkflowIdentity
    Public SequentialNumberGuessIdentity_v15 As WorkflowIdentity
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

    // v1.5 (Dynamic Update) identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v15;
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v15;
    static public WorkflowIdentity SequentialNumberGuessIdentity_v15;
    ```

4. <span data-ttu-id="063e2-192">Al final del constructor agregue el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="063e2-192">Add the following code at the end of the constructor.</span></span> <span data-ttu-id="063e2-193">Este código inicializa las identidades de flujo de trabajo de actualización dinámica, carga las definiciones de flujo de trabajo correspondientes y las agrega al diccionario de versiones de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="063e2-193">This code initializes the dynamic update workflow identities, loads the corresponding workflow definitions, and adds them to the workflow version dictionary.</span></span>

    ```vb
    'Initialize the dynamic update workflow identities.
    StateMachineNumberGuessIdentity_v15 = New WorkflowIdentity With
    {
        .Name = "StateMachineNumberGuessWorkflow",
        .Version = New Version(1, 5, 0, 0)
    }

    FlowchartNumberGuessIdentity_v15 = New WorkflowIdentity With
    {
        .Name = "FlowchartNumberGuessWorkflow",
        .Version = New Version(1, 5, 0, 0)
    }

    SequentialNumberGuessIdentity_v15 = New WorkflowIdentity With
    {
        .Name = "SequentialNumberGuessWorkflow",
        .Version = New Version(1, 5, 0, 0)
    }

    'Add the dynamic update workflow identities to the dictionary along with
    'the corresponding workflow definitions loaded from the v15 assembly.
    'Assembly.LoadFile requires an absolute path so convert this relative path
    'to an absolute path.
    Dim v15AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll"
    v15AssemblyPath = Path.GetFullPath(v15AssemblyPath)
    Dim v15Assembly As Assembly = Assembly.LoadFile(v15AssemblyPath)

    map.Add(StateMachineNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

    map.Add(SequentialNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

    map.Add(FlowchartNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
    ```

    ```csharp
    // Initialize the dynamic update workflow identities.
    StateMachineNumberGuessIdentity_v15 = new WorkflowIdentity
    {
        Name = "StateMachineNumberGuessWorkflow",
        Version = new Version(1, 5, 0, 0)
    };

    FlowchartNumberGuessIdentity_v15 = new WorkflowIdentity
    {
        Name = "FlowchartNumberGuessWorkflow",
        Version = new Version(1, 5, 0, 0)
    };

    SequentialNumberGuessIdentity_v15 = new WorkflowIdentity
    {
        Name = "SequentialNumberGuessWorkflow",
        Version = new Version(1, 5, 0, 0)
    };

    // Add the dynamic update workflow identities to the dictionary along with
    // the corresponding workflow definitions loaded from the v15 assembly.
    // Assembly.LoadFile requires an absolute path so convert this relative path
    // to an absolute path.
    string v15AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll";
    v15AssemblyPath = Path.GetFullPath(v15AssemblyPath);
    Assembly v15Assembly = Assembly.LoadFile(v15AssemblyPath);

    map.Add(StateMachineNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

    map.Add(SequentialNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

    map.Add(FlowchartNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
    ```

     <span data-ttu-id="063e2-194">El ejemplo siguiente es la clase `WorkflowVersionMap` completada.</span><span class="sxs-lookup"><span data-stu-id="063e2-194">The following example is the completed `WorkflowVersionMap` class.</span></span>

    ```vb
    Public Module WorkflowVersionMap
        Dim map As Dictionary(Of WorkflowIdentity, Activity)

        'Current version identities.
        Public StateMachineNumberGuessIdentity As WorkflowIdentity
        Public FlowchartNumberGuessIdentity As WorkflowIdentity
        Public SequentialNumberGuessIdentity As WorkflowIdentity

        'v1 identities.
        Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
        Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
        Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity

        'v1.5 (Dynamic Update) identities.
        Public StateMachineNumberGuessIdentity_v15 As WorkflowIdentity
        Public FlowchartNumberGuessIdentity_v15 As WorkflowIdentity
        Public SequentialNumberGuessIdentity_v15 As WorkflowIdentity

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

            'Initialize the dynamic update workflow identities.
            StateMachineNumberGuessIdentity_v15 = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 5, 0, 0)
            }

            FlowchartNumberGuessIdentity_v15 = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 5, 0, 0)
            }

            SequentialNumberGuessIdentity_v15 = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 5, 0, 0)
            }

            'Add the dynamic update workflow identities to the dictionary along with
            'the corresponding workflow definitions loaded from the v15 assembly.
            'Assembly.LoadFile requires an absolute path so convert this relative path
            'to an absolute path.
            Dim v15AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll"
            v15AssemblyPath = Path.GetFullPath(v15AssemblyPath)
            Dim v15Assembly As Assembly = Assembly.LoadFile(v15AssemblyPath)

            map.Add(StateMachineNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

            map.Add(SequentialNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

            map.Add(FlowchartNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
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

        // v1.5 (Dynamic Update) identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v15;
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v15;
        static public WorkflowIdentity SequentialNumberGuessIdentity_v15;

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

            // Initialize the dynamic update workflow identities.
            StateMachineNumberGuessIdentity_v15 = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 5, 0, 0)
            };

            FlowchartNumberGuessIdentity_v15 = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 5, 0, 0)
            };

            SequentialNumberGuessIdentity_v15 = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 5, 0, 0)
            };

            // Add the dynamic update workflow identities to the dictionary along with
            // the corresponding workflow definitions loaded from the v15 assembly.
            // Assembly.LoadFile requires an absolute path so convert this relative path
            // to an absolute path.
            string v15AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll";
            v15AssemblyPath = Path.GetFullPath(v15AssemblyPath);
            Assembly v15Assembly = Assembly.LoadFile(v15AssemblyPath);

            map.Add(StateMachineNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

            map.Add(SequentialNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

            map.Add(FlowchartNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
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

5. <span data-ttu-id="063e2-195">Presione Ctrl+Mayús+B para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="063e2-195">Press CTRL+SHIFT+B to build the project.</span></span>

### <a name="to-apply-the-dynamic-updates"></a><a name="BKMK_ApplyUpdate"></a> <span data-ttu-id="063e2-196">Para aplicar las actualizaciones dinámicas</span><span class="sxs-lookup"><span data-stu-id="063e2-196">To apply the dynamic updates</span></span>

1. <span data-ttu-id="063e2-197">Haga clic con el botón derecho en **WF45GettingStartedTutorial** en **Explorador de soluciones** y elija **Agregar**, **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="063e2-197">Right-click **WF45GettingStartedTutorial** in **Solution Explorer** and choose **Add**, **New Project**.</span></span>

2. <span data-ttu-id="063e2-198">En el nodo **instalado** , seleccione **Visual C#**, **Windows** (o **Visual Basic**, **Windows**).</span><span class="sxs-lookup"><span data-stu-id="063e2-198">In the **Installed** node, select **Visual C#**, **Windows** (or **Visual Basic**, **Windows**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="063e2-199">En función del lenguaje de programación configurado como lenguaje principal en Visual Studio, es posible que el nodo **Visual C#** o **Visual Basic** se encuentre debajo del nodo **Otros lenguajes** del nodo **Instalados**.</span><span class="sxs-lookup"><span data-stu-id="063e2-199">Depending on which programming language is configured as the primary language in Visual Studio, the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>

    <span data-ttu-id="063e2-200">Asegúrese de que **.NET Framework 4.5** está seleccionado en la lista desplegable de versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="063e2-200">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="063e2-201">Seleccione **aplicación de consola** en la lista de **ventanas** .</span><span class="sxs-lookup"><span data-stu-id="063e2-201">Select **Console Application** from the **Windows** list.</span></span> <span data-ttu-id="063e2-202">Escriba **ApplyDynamicUpdate** en el cuadro **nombre** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="063e2-202">Type **ApplyDynamicUpdate** into the **Name** box and click **OK**.</span></span>

3. <span data-ttu-id="063e2-203">Haga clic con el botón secundario en **ApplyDynamicUpdate** en **Explorador de soluciones** y elija **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="063e2-203">Right-click **ApplyDynamicUpdate** in **Solution Explorer** and choose **Add Reference**.</span></span>

4. <span data-ttu-id="063e2-204">Haga clic en **solución** y active la casilla situada junto a **NumberGuessWorkflowHost**.</span><span class="sxs-lookup"><span data-stu-id="063e2-204">Click **Solution** and check the box next to **NumberGuessWorkflowHost**.</span></span> <span data-ttu-id="063e2-205">Esta referencia es necesaria para que `ApplyDynamicUpdate` pueda usar la clase `NumberGuessWorkflowHost.WorkflowVersionMap`.</span><span class="sxs-lookup"><span data-stu-id="063e2-205">This reference is needed so that `ApplyDynamicUpdate` can use the `NumberGuessWorkflowHost.WorkflowVersionMap` class.</span></span>

5. <span data-ttu-id="063e2-206">Seleccione **Framework** en el nodo **ensamblados** de la lista **Agregar referencia** .</span><span class="sxs-lookup"><span data-stu-id="063e2-206">Select **Framework** from the **Assemblies** node in the **Add Reference** list.</span></span> <span data-ttu-id="063e2-207">Escriba **System. Activities** en el cuadro **buscar ensamblados** .</span><span class="sxs-lookup"><span data-stu-id="063e2-207">Type **System.Activities** into the **Search Assemblies** box.</span></span> <span data-ttu-id="063e2-208">Esto filtrará los ensamblados y simplificará la selección de las referencias deseadas.</span><span class="sxs-lookup"><span data-stu-id="063e2-208">This will filter the assemblies and make the desired references easier to select.</span></span>

6. <span data-ttu-id="063e2-209">Active la casilla situada junto a **System. Activities** en la lista resultados de la **búsqueda** .</span><span class="sxs-lookup"><span data-stu-id="063e2-209">Check the checkbox beside **System.Activities** from the **Search Results** list.</span></span>

7. <span data-ttu-id="063e2-210">Escriba **serialización** en el cuadro **buscar ensamblados** y active la casilla situada junto a **System. Runtime. Serialization** en la lista de resultados de la **búsqueda** .</span><span class="sxs-lookup"><span data-stu-id="063e2-210">Type **Serialization** into the **Search Assemblies** box, and check the checkbox beside **System.Runtime.Serialization** from the **Search Results** list.</span></span>

8. <span data-ttu-id="063e2-211">Escriba **DurableInstancing** en el cuadro **buscar ensamblados** y active la casilla situada junto a **System. Activities. DurableInstancing** y **System. Runtime. DurableInstancing** de la lista de resultados de la **búsqueda** .</span><span class="sxs-lookup"><span data-stu-id="063e2-211">Type **DurableInstancing** into the **Search Assemblies** box, and check the checkbox beside **System.Activities.DurableInstancing** and **System.Runtime.DurableInstancing** from the **Search Results** list.</span></span>

9. <span data-ttu-id="063e2-212">Haga clic en **Aceptar** para cerrar el **Administrador de referencias** y agregar las referencias.</span><span class="sxs-lookup"><span data-stu-id="063e2-212">Click **OK** to close **Reference Manager** and add the references.</span></span>

10. <span data-ttu-id="063e2-213">Haga clic con el botón secundario en **ApplyDynamicUpdate** en explorador de soluciones y elija **Agregar**, **clase**.</span><span class="sxs-lookup"><span data-stu-id="063e2-213">Right-click **ApplyDynamicUpdate** in Solution Explorer and choose **Add**, **Class**.</span></span> <span data-ttu-id="063e2-214">Escriba `DynamicUpdateInfo` en el cuadro **nombre** y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="063e2-214">Type `DynamicUpdateInfo` into the **Name** box and click **Add**.</span></span>

11. <span data-ttu-id="063e2-215">Agregue los dos miembros siguientes a la clase `DynamicUpdateInfo`.</span><span class="sxs-lookup"><span data-stu-id="063e2-215">Add the following two members to the `DynamicUpdateInfo` class.</span></span> <span data-ttu-id="063e2-216">El ejemplo siguiente es la clase `DynamicUpdateInfo` completada.</span><span class="sxs-lookup"><span data-stu-id="063e2-216">The following example is the completed `DynamicUpdateInfo` class.</span></span> <span data-ttu-id="063e2-217">Esta clase contiene información sobre la asignación de actualización y la nueva identidad de flujo de trabajo usada cuando se actualiza una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="063e2-217">This class contains information on the update map and new workflow identity used when a workflow instance is updated.</span></span>

    ```vb
    Public Class DynamicUpdateInfo
        Public updateMap As DynamicUpdateMap
        Public newIdentity As WorkflowIdentity
    End Class
    ```

    ```csharp
    class DynamicUpdateInfo
    {
        public DynamicUpdateMap updateMap;
        public WorkflowIdentity newIdentity;
    }
    ```

12. <span data-ttu-id="063e2-218">Agregue las siguientes instrucciones `using` (o `Imports`) al principio del archivo con las demás instrucciones `using` (o `Imports`).</span><span class="sxs-lookup"><span data-stu-id="063e2-218">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Activities
    Imports System.Activities.DynamicUpdate
    ```

    ```csharp
    using System.Activities;
    using System.Activities.DynamicUpdate;
    ```

13. <span data-ttu-id="063e2-219">Haga doble clic en **Program.CS** (o **Module1. vb**) en explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="063e2-219">Double-click **Program.cs** (or **Module1.vb**) in Solution Explorer.</span></span>

14. <span data-ttu-id="063e2-220">Agregue las siguientes instrucciones `using` (o `Imports`) al principio del archivo con las demás instrucciones `using` (o `Imports`).</span><span class="sxs-lookup"><span data-stu-id="063e2-220">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports NumberGuessWorkflowHost
    Imports System.Data.SqlClient
    Imports System.Activities.DynamicUpdate
    Imports System.IO
    Imports System.Runtime.Serialization
    Imports System.Activities
    Imports System.Activities.DurableInstancing
    ```

    ```csharp
    using NumberGuessWorkflowHost;
    using System.Data;
    using System.Data.SqlClient;
    using System.Activities;
    using System.Activities.DynamicUpdate;
    using System.IO;
    using System.Runtime.Serialization;
    using System.Activities.DurableInstancing;
    ```

15. <span data-ttu-id="063e2-221">Agregue el siguiente miembro de cadena de conexión a la clase `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="063e2-221">Add the following connection string member to the `Program` class (or `Module1`).</span></span>

    ```vb
    Const connectionString = "Server=.\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI"
    ```

    ```csharp
    const string connectionString = "Server=.\\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI";
    ```

    > [!NOTE]
    > <span data-ttu-id="063e2-222">Según la edición de SQL Server, el nombre de servidor de cadena de conexión puede ser diferente.</span><span class="sxs-lookup"><span data-stu-id="063e2-222">Depending on your edition of SQL Server, the connection string server name may be different.</span></span>

16. <span data-ttu-id="063e2-223">Agregue el siguiente método `GetIDs` a la clase `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="063e2-223">Add the following `GetIDs` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="063e2-224">Este método devuelve una lista de identificadores de instancia de flujo de trabajo persistente.</span><span class="sxs-lookup"><span data-stu-id="063e2-224">This method returns a list of persisted workflow instance ids.</span></span>

    ```vb
    Function GetIds() As IList(Of Guid)
        Dim Ids As New List(Of Guid)
        Dim localCmd = _
            String.Format("Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]")
        Using localCon = New SqlConnection(connectionString)
            Dim cmd As SqlCommand = localCon.CreateCommand()
            cmd.CommandText = localCmd
            localCon.Open()
            Using reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)
                While reader.Read()
                    'Get the InstanceId of the persisted Workflow
                    Dim id As Guid = Guid.Parse(reader(0).ToString())

                    'Add it to the list.
                    Ids.Add(id)
                End While
            End Using
        End Using

        Return Ids
    End Function
    ```

    ```csharp
    static IList<Guid> GetIds()
    {
        List<Guid> Ids = new List<Guid>();
        string localCmd = string.Format("Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]");
        using (SqlConnection localCon = new SqlConnection(connectionString))
        {
            SqlCommand cmd = localCon.CreateCommand();
            cmd.CommandText = localCmd;
            localCon.Open();
            using (SqlDataReader reader = cmd.ExecuteReader(CommandBehavior.CloseConnection))
            {
                while (reader.Read())
                {
                    // Get the InstanceId of the persisted Workflow
                    Guid id = Guid.Parse(reader[0].ToString());

                    // Add it to the list.
                    Ids.Add(id);
                }
            }
        }

        return Ids;
    }
    ```

17. <span data-ttu-id="063e2-225">Agregue el siguiente método `LoadMap` a la clase `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="063e2-225">Add the following `LoadMap` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="063e2-226">Este método crea un diccionario que asigna las identidades de flujo de trabajo de `v1` a las asignaciones de actualización y a las nuevas identidades de flujo de trabajo usadas para actualizar las instancias de flujo de trabajo persistentes correspondientes.</span><span class="sxs-lookup"><span data-stu-id="063e2-226">This method creates a dictionary that maps `v1` workflow identities to the update maps and new workflow identities used to update the corresponding persisted workflow instances.</span></span>

    ```vb
    Function LoadMap(mapName As String) As DynamicUpdateMap
        Dim mapPath As String = Path.Combine("..\..\..\PreviousVersions", mapName)

        Dim map As DynamicUpdateMap
        Using fs As FileStream = File.Open(mapPath, FileMode.Open)
            Dim serializer As DataContractSerializer = New DataContractSerializer(GetType(DynamicUpdateMap))
            Dim updateMap = serializer.ReadObject(fs)
            If updateMap Is Nothing Then
                Throw New ApplicationException("DynamicUpdateMap is null.")
            End If

            map = updateMap
        End Using

        Return map
    End Function
    ```

    ```csharp
    static DynamicUpdateMap LoadMap(string mapName)
    {
        string path = Path.Combine(@"..\..\..\PreviousVersions", mapName);

        DynamicUpdateMap map;
        using (FileStream fs = File.Open(path, FileMode.Open))
        {
            DataContractSerializer serializer = new DataContractSerializer(typeof(DynamicUpdateMap));
            object updateMap = serializer.ReadObject(fs);
            if (updateMap == null)
            {
                throw new ApplicationException("DynamicUpdateMap is null.");
            }

            map = updateMap as DynamicUpdateMap;
        }

        return map;
    }
    ```

18. <span data-ttu-id="063e2-227">Agregue el siguiente método `LoadMaps` a la clase `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="063e2-227">Add the following `LoadMaps` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="063e2-228">Este método carga las tres asignaciones de actualización y crea un diccionario que asigna las identidades de flujo de trabajo de `v1` a las asignaciones de actualización.</span><span class="sxs-lookup"><span data-stu-id="063e2-228">This method loads the three update maps and creates a dictionary that maps `v1` workflow identities to the update maps.</span></span>

    ```vb
    Function LoadMaps() As IDictionary(Of WorkflowIdentity, DynamicUpdateInfo)
        'There are 3 update maps to describe the changes to update v1 workflows,
        'one for reach of the 3 workflow types in the tutorial.
        Dim maps = New Dictionary(Of WorkflowIdentity, DynamicUpdateInfo)()

        Dim sequentialMap As DynamicUpdateMap = LoadMap("SequentialNumberGuessWorkflow.map")
        Dim sequentialInfo = New DynamicUpdateInfo With
        {
            .updateMap = sequentialMap,
            .newIdentity = WorkflowVersionMap.SequentialNumberGuessIdentity_v15
        }
        maps.Add(WorkflowVersionMap.SequentialNumberGuessIdentity_v1, sequentialInfo)

        Dim stateMap As DynamicUpdateMap = LoadMap("StateMachineNumberGuessWorkflow.map")
        Dim stateInfo = New DynamicUpdateInfo With
        {
            .updateMap = stateMap,
            .newIdentity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v15
        }
        maps.Add(WorkflowVersionMap.StateMachineNumberGuessIdentity_v1, stateInfo)

        Dim flowchartMap As DynamicUpdateMap = LoadMap("FlowchartNumberGuessWorkflow.map")
        Dim flowchartInfo = New DynamicUpdateInfo With
        {
            .updateMap = flowchartMap,
            .newIdentity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v15
        }
        maps.Add(WorkflowVersionMap.FlowchartNumberGuessIdentity_v1, flowchartInfo)

        Return maps
    End Function
    ```

    ```csharp
    static IDictionary<WorkflowIdentity, DynamicUpdateInfo> LoadMaps()
    {
        // There are 3 update maps to describe the changes to update v1 workflows,
        // one for reach of the 3 workflow types in the tutorial.
        Dictionary<WorkflowIdentity, DynamicUpdateInfo> maps =
            new Dictionary<WorkflowIdentity, DynamicUpdateInfo>();

        DynamicUpdateMap sequentialMap = LoadMap("SequentialNumberGuessWorkflow.map");
        DynamicUpdateInfo sequentialInfo = new DynamicUpdateInfo
        {
            updateMap = sequentialMap,
            newIdentity = WorkflowVersionMap.SequentialNumberGuessIdentity_v15
        };
        maps.Add(WorkflowVersionMap.SequentialNumberGuessIdentity_v1, sequentialInfo);

        DynamicUpdateMap stateMap = LoadMap("StateMachineNumberGuessWorkflow.map");
        DynamicUpdateInfo stateInfo = new DynamicUpdateInfo
        {
            updateMap = stateMap,
            newIdentity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v15
        };
        maps.Add(WorkflowVersionMap.StateMachineNumberGuessIdentity_v1, stateInfo);

        DynamicUpdateMap flowchartMap = LoadMap("FlowchartNumberGuessWorkflow.map");
        DynamicUpdateInfo flowchartInfo = new DynamicUpdateInfo
        {
            updateMap = flowchartMap,
            newIdentity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v15
        };
        maps.Add(WorkflowVersionMap.FlowchartNumberGuessIdentity_v1, flowchartInfo);

        return maps;
    }
    ```

19. <span data-ttu-id="063e2-229">Agregue el siguiente código a `Main`.</span><span class="sxs-lookup"><span data-stu-id="063e2-229">Add the following code to `Main`.</span></span> <span data-ttu-id="063e2-230">Este código repite las instancias de flujo de trabajo persistentes y examina cada `WorkflowIdentity`.</span><span class="sxs-lookup"><span data-stu-id="063e2-230">This code iterates the persisted workflow instances and examines each `WorkflowIdentity`.</span></span> <span data-ttu-id="063e2-231">Si `WorkflowIdentity` se asigna a una instancia de flujo de trabajo de `v1`, se configura un `WorkflowApplication` con la definición de flujo de trabajo actualizada y una identidad de flujo de trabajo actualizada.</span><span class="sxs-lookup"><span data-stu-id="063e2-231">If the `WorkflowIdentity` maps to a `v1` workflow instance, a `WorkflowApplication` is configured with the updated workflow definition and an updated workflow identity.</span></span> <span data-ttu-id="063e2-232">A continuación, se llama a `WorkflowApplication.Load` con la instancia y la asignación de actualización, que aplica la asignación de actualización dinámica.</span><span class="sxs-lookup"><span data-stu-id="063e2-232">Next, `WorkflowApplication.Load` is called with the instance and the update map, which applies the dynamic update map.</span></span> <span data-ttu-id="063e2-233">Una vez aplicada la actualización, la instancia actualizada es persistente con una llamada a `Unload`.</span><span class="sxs-lookup"><span data-stu-id="063e2-233">Once the update is applied, the updated instance is persisted with a call to `Unload`.</span></span>

    ```vb
    Dim store = New SqlWorkflowInstanceStore(connectionString)
    WorkflowApplication.CreateDefaultInstanceOwner(store, Nothing, WorkflowIdentityFilter.Any)

    Dim updateMaps As IDictionary(Of WorkflowIdentity, DynamicUpdateInfo) = LoadMaps()

    For Each id As Guid In GetIds()
        'Get a proxy to the instance.
        Dim instance As WorkflowApplicationInstance = WorkflowApplication.GetInstance(id, store)

        Console.WriteLine("Inspecting: {0}", instance.DefinitionIdentity)

        'Only update v1 workflows.
        If Not instance.DefinitionIdentity Is Nothing AndAlso _
            instance.DefinitionIdentity.Version.Equals(New Version(1, 0, 0, 0)) Then

            Dim info As DynamicUpdateInfo = updateMaps(instance.DefinitionIdentity)

            'Associate the persisted WorkflowApplicationInstance with
            'a WorkflowApplication that is configured with the updated
            'definition and updated WorkflowIdentity.
            Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(info.newIdentity)
            Dim wfApp = New WorkflowApplication(wf, info.newIdentity)

            'Apply the Dynamic Update.
            wfApp.Load(instance, info.updateMap)

            'Persist the updated instance.
            wfApp.Unload()

            Console.WriteLine("Updated to: {0}", info.newIdentity)
        Else
            'Not updating this instance, so unload it.
            instance.Abandon()
        End If
    Next
    ```

    ```csharp
    SqlWorkflowInstanceStore store = new SqlWorkflowInstanceStore(connectionString);
    WorkflowApplication.CreateDefaultInstanceOwner(store, null, WorkflowIdentityFilter.Any);

    IDictionary<WorkflowIdentity, DynamicUpdateInfo> updateMaps = LoadMaps();

    foreach (Guid id in GetIds())
    {
        // Get a proxy to the instance.
        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(id, store);

        Console.WriteLine("Inspecting: {0}", instance.DefinitionIdentity);

        // Only update v1 workflows.
        if (instance.DefinitionIdentity != null &&
            instance.DefinitionIdentity.Version.Equals(new Version(1, 0, 0, 0)))
        {
            DynamicUpdateInfo info = updateMaps[instance.DefinitionIdentity];

            // Associate the persisted WorkflowApplicationInstance with
            // a WorkflowApplication that is configured with the updated
            // definition and updated WorkflowIdentity.
            Activity wf = WorkflowVersionMap.GetWorkflowDefinition(info.newIdentity);
            WorkflowApplication wfApp =
                new WorkflowApplication(wf, info.newIdentity);

            // Apply the Dynamic Update.
            wfApp.Load(instance, info.updateMap);

            // Persist the updated instance.
            wfApp.Unload();

            Console.WriteLine("Updated to: {0}", info.newIdentity);
        }
        else
        {
            // Not updating this instance, so unload it.
            instance.Abandon();
        }
    }
    ```

20. <span data-ttu-id="063e2-234">Haga clic con el botón derecho en **ApplyDynamicUpdate** en **Explorador de soluciones** y elija **establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="063e2-234">Right-click **ApplyDynamicUpdate** in **Solution Explorer** and choose **Set as StartUp Project**.</span></span>

21. <span data-ttu-id="063e2-235">Presione CTRL+MAYÚS+B para compilar la solución y, a continuación, presione CTRL+F5 para ejecutar la aplicación `ApplyDynamicUpdate` y actualizar las instancias de flujo de trabajo persistentes.</span><span class="sxs-lookup"><span data-stu-id="063e2-235">Press CTRL+SHIFT+B to build the solution, and then press CTRL+F5 to run the `ApplyDynamicUpdate` application and update the persisted workflow instances.</span></span> <span data-ttu-id="063e2-236">Debería ver una salida similar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="063e2-236">You should see output similar to the following.</span></span> <span data-ttu-id="063e2-237">Los flujos de trabajo de la versión 1.0.0.0 se actualizan a la versión 1.5.0.0, mientras que los flujos de trabajo de la versión 2.0.0.0 no se actualizan.</span><span class="sxs-lookup"><span data-stu-id="063e2-237">The version 1.0.0.0 workflows are updated to version 1.5.0.0, while the version 2.0.0.0 workflows are not updated.</span></span>

    <span data-ttu-id="063e2-238">**Inspeccionando: StateMachineNumberGuessWorkflow; Versión = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-238">**Inspecting: StateMachineNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="063e2-239">**Actualizado a: StateMachineNumberGuessWorkflow; Versión = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-239">**Updated to: StateMachineNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="063e2-240">**Inspeccionando: StateMachineNumberGuessWorkflow; Versión = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-240">**Inspecting: StateMachineNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="063e2-241">**Actualizado a: StateMachineNumberGuessWorkflow; Versión = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-241">**Updated to: StateMachineNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="063e2-242">**Inspeccionando: FlowchartNumberGuessWorkflow; Versión = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-242">**Inspecting: FlowchartNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="063e2-243">**Actualizado a: FlowchartNumberGuessWorkflow; Versión = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-243">**Updated to: FlowchartNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="063e2-244">**Inspeccionando: FlowchartNumberGuessWorkflow; Versión = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-244">**Inspecting: FlowchartNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="063e2-245">**Actualizado a: FlowchartNumberGuessWorkflow; Versión = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-245">**Updated to: FlowchartNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="063e2-246">**Inspeccionando: SequentialNumberGuessWorkflow; Versión = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-246">**Inspecting: SequentialNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="063e2-247">**Actualizado a: SequentialNumberGuessWorkflow; Versión = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-247">**Updated to: SequentialNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="063e2-248">**Inspeccionando: SequentialNumberGuessWorkflow; Versión = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-248">**Inspecting: SequentialNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="063e2-249">**Actualizado a: SequentialNumberGuessWorkflow; Versión = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-249">**Updated to: SequentialNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="063e2-250">**Inspeccionando: SequentialNumberGuessWorkflow; Versión = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-250">**Inspecting: SequentialNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="063e2-251">**Actualizado a: SequentialNumberGuessWorkflow; Versión = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-251">**Updated to: SequentialNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="063e2-252">**Inspeccionando: StateMachineNumberGuessWorkflow; Versión = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-252">**Inspecting: StateMachineNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="063e2-253">**Actualizado a: StateMachineNumberGuessWorkflow; Versión = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-253">**Updated to: StateMachineNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="063e2-254">**Inspeccionando: FlowchartNumberGuessWorkflow; Versión = 1.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-254">**Inspecting: FlowchartNumberGuessWorkflow; Version=1.0.0.0**</span></span>\
    <span data-ttu-id="063e2-255">**Actualizado a: FlowchartNumberGuessWorkflow; Versión = 1.5.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-255">**Updated to: FlowchartNumberGuessWorkflow; Version=1.5.0.0**</span></span>\
    <span data-ttu-id="063e2-256">**Inspeccionando: StateMachineNumberGuessWorkflow; Versión = 2.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-256">**Inspecting: StateMachineNumberGuessWorkflow; Version=2.0.0.0**</span></span>\
    <span data-ttu-id="063e2-257">**Inspeccionando: StateMachineNumberGuessWorkflow; Versión = 2.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-257">**Inspecting: StateMachineNumberGuessWorkflow; Version=2.0.0.0**</span></span>\
    <span data-ttu-id="063e2-258">**Inspeccionando: FlowchartNumberGuessWorkflow; Versión = 2.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-258">**Inspecting: FlowchartNumberGuessWorkflow; Version=2.0.0.0**</span></span>\
    <span data-ttu-id="063e2-259">**Inspeccionando: FlowchartNumberGuessWorkflow; Versión = 2.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-259">**Inspecting: FlowchartNumberGuessWorkflow; Version=2.0.0.0**</span></span>\
    <span data-ttu-id="063e2-260">**Inspeccionando: SequentialNumberGuessWorkflow; Versión = 2.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-260">**Inspecting: SequentialNumberGuessWorkflow; Version=2.0.0.0**</span></span>\
    <span data-ttu-id="063e2-261">**Inspeccionando: SequentialNumberGuessWorkflow; Versión = 2.0.0.0**</span><span class="sxs-lookup"><span data-stu-id="063e2-261">**Inspecting: SequentialNumberGuessWorkflow; Version=2.0.0.0**</span></span>\
    <span data-ttu-id="063e2-262">**Presione cualquier tecla para continuar...**</span><span class="sxs-lookup"><span data-stu-id="063e2-262">**Press any key to continue . . .**</span></span>

### <a name="to-run-the-application-with-the-updated-workflows"></a><a name="BKMK_BuildAndRun"></a> <span data-ttu-id="063e2-263">Para ejecutar la aplicación con los flujos de trabajo actualizados</span><span class="sxs-lookup"><span data-stu-id="063e2-263">To run the application with the updated workflows</span></span>

1. <span data-ttu-id="063e2-264">Haga clic con el botón derecho en **NumberGuessWorkflowHost** en **Explorador de soluciones** y elija **establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="063e2-264">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Set as StartUp Project**.</span></span>

2. <span data-ttu-id="063e2-265">Presione CTRL+F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="063e2-265">Press CTRL+F5 to run the application.</span></span>

3. <span data-ttu-id="063e2-266">Haga clic en **nuevo juego** para iniciar un nuevo flujo de trabajo y anote la información de versión que se encuentra debajo de la ventana de estado que indica que el flujo de trabajo es un `v2` flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="063e2-266">Click **New Game** to start a new workflow and note the version information below the status window that indicates the workflow is a `v2` workflow.</span></span>

4. <span data-ttu-id="063e2-267">Seleccione uno de los `v1` flujos de trabajo que inició al principio del tema [Cómo hospedar varias versiones de un flujo de trabajo en paralelo](how-to-host-multiple-versions-of-a-workflow-side-by-side.md) .</span><span class="sxs-lookup"><span data-stu-id="063e2-267">Select one of the `v1` workflows you started at the beginning of the [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md) topic.</span></span> <span data-ttu-id="063e2-268">Tenga en cuenta que la información de versión de la ventana de estado indica que el flujo de trabajo es un flujo de trabajo de versión **1.5.0.0** .</span><span class="sxs-lookup"><span data-stu-id="063e2-268">Note that the version information under the status window indicates that the workflow is a version **1.5.0.0** workflow.</span></span> <span data-ttu-id="063e2-269">Observe que no hay información indicada sobre intentos anteriores aparte de si eran demasiado altos o demasiado bajos.</span><span class="sxs-lookup"><span data-stu-id="063e2-269">Note that there is no information indicated about previous guesses other than whether they were too high or too low.</span></span>

    <span data-ttu-id="063e2-270">**Escriba un número entre 1 y 10.**</span><span class="sxs-lookup"><span data-stu-id="063e2-270">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="063e2-271">**Su intento es demasiado bajo.**</span><span class="sxs-lookup"><span data-stu-id="063e2-271">**Your guess is too low.**</span></span>

5. <span data-ttu-id="063e2-272">Anote `InstanceId` y, a continuación, escriba números hasta que se complete el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="063e2-272">Make a note of the `InstanceId` and then enter guesses until the workflow completes.</span></span> <span data-ttu-id="063e2-273">La ventana de estado muestra información sobre el contenido del intento porque la actualización dinámica ha actualizado las actividades `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="063e2-273">The status window displays information about the content of the guess because the `WriteLine` activities were updated by the dynamic update.</span></span>

    <span data-ttu-id="063e2-274">**Escriba un número entre 1 y 10.**</span><span class="sxs-lookup"><span data-stu-id="063e2-274">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="063e2-275">**Su estimación es demasiado baja.**</span><span class="sxs-lookup"><span data-stu-id="063e2-275">**Your guess is too low.**</span></span>\
    <span data-ttu-id="063e2-276">**Escriba un número entre 1 y 10.**</span><span class="sxs-lookup"><span data-stu-id="063e2-276">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="063e2-277">**5 es demasiado bajo.**</span><span class="sxs-lookup"><span data-stu-id="063e2-277">**5 is too low.**</span></span>\
    <span data-ttu-id="063e2-278">**Escriba un número entre 1 y 10.**</span><span class="sxs-lookup"><span data-stu-id="063e2-278">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="063e2-279">**7 es demasiado alto.**</span><span class="sxs-lookup"><span data-stu-id="063e2-279">**7 is too high.**</span></span>\
    <span data-ttu-id="063e2-280">**Escriba un número entre 1 y 10.**</span><span class="sxs-lookup"><span data-stu-id="063e2-280">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="063e2-281">**Enhorabuena, acertó el número en 4 intentos.**</span><span class="sxs-lookup"><span data-stu-id="063e2-281">**Congratulations, you guessed the number in 4 turns.**</span></span>

6. <span data-ttu-id="063e2-282">Abra el explorador de Windows y navegue hasta la carpeta **NumberGuessWorkflowHost\bin\debug** (o **bin\release** según la configuración del proyecto) y abra el archivo de seguimiento con el Bloc de notas correspondiente al flujo de trabajo completado.</span><span class="sxs-lookup"><span data-stu-id="063e2-282">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings) and open the tracking file using Notepad that corresponds to the completed workflow.</span></span> <span data-ttu-id="063e2-283">Si no ha anotado el `InstanceId` , es posible que pueda identificar el archivo de seguimiento correcto mediante la información de **fecha de modificación** en el explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="063e2-283">If you did not make a note of the `InstanceId` you may be able to identify the correct tracking file by using the **Date modified** information in Windows Explorer.</span></span> <span data-ttu-id="063e2-284">La última línea de la información de seguimiento contiene el resultado de la actividad `WriteLine` agregada recientemente.</span><span class="sxs-lookup"><span data-stu-id="063e2-284">The last line of the tracking information contains the output of the newly added `WriteLine` activity.</span></span>

    <span data-ttu-id="063e2-285">**Escriba un número entre 1 y 10.**</span><span class="sxs-lookup"><span data-stu-id="063e2-285">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="063e2-286">**Su estimación es demasiado baja.**</span><span class="sxs-lookup"><span data-stu-id="063e2-286">**Your guess is too low.**</span></span>\
    <span data-ttu-id="063e2-287">**Escriba un número entre 1 y 10.**</span><span class="sxs-lookup"><span data-stu-id="063e2-287">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="063e2-288">**5 es demasiado bajo.**</span><span class="sxs-lookup"><span data-stu-id="063e2-288">**5 is too low.**</span></span>\
    <span data-ttu-id="063e2-289">**Escriba un número entre 1 y 10.**</span><span class="sxs-lookup"><span data-stu-id="063e2-289">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="063e2-290">**7 es demasiado alto.**</span><span class="sxs-lookup"><span data-stu-id="063e2-290">**7 is too high.**</span></span>\
    <span data-ttu-id="063e2-291">**Escriba un número entre 1 y 10.**</span><span class="sxs-lookup"><span data-stu-id="063e2-291">**Please enter a number between 1 and 10**</span></span>\
    <span data-ttu-id="063e2-292">**6 es correcto. Lo ha adivinado en 4 turnos.**</span><span class="sxs-lookup"><span data-stu-id="063e2-292">**6 is correct. You guessed it in 4 turns.**</span></span>

### <a name="to-enable-starting-previous-versions-of-the-workflows"></a><a name="BKMK_StartPreviousVersions"></a> <span data-ttu-id="063e2-293">Para habilitar el inicio de versiones anteriores de los flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="063e2-293">To enable starting previous versions of the workflows</span></span>

<span data-ttu-id="063e2-294">Si ya no le quedan flujos de trabajo que actualizar, puede modificar la aplicación `NumberGuessWorkflowHost` para habilitar el inicio de versiones anteriores de los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="063e2-294">If you run out of workflows to update, you can modify the `NumberGuessWorkflowHost` application to enable starting previous versions of the workflows.</span></span>

1. <span data-ttu-id="063e2-295">Haga doble clic en **WorkflowHostForm** en **Explorador de soluciones** y seleccione el cuadro combinado **WorkflowType** .</span><span class="sxs-lookup"><span data-stu-id="063e2-295">Double-click **WorkflowHostForm** in **Solution Explorer**, and select the **WorkflowType** combo box.</span></span>

2. <span data-ttu-id="063e2-296">En la ventana **propiedades** , seleccione la propiedad **elementos** y haga clic en el botón de puntos suspensivos para editar la colección de **elementos** .</span><span class="sxs-lookup"><span data-stu-id="063e2-296">In the **Properties** window, select the **Items** property and click the ellipsis button to edit the **Items** collection.</span></span>

3. <span data-ttu-id="063e2-297">Agregue los siguientes tres elementos a la colección.</span><span class="sxs-lookup"><span data-stu-id="063e2-297">Add the following three items to the collection.</span></span>

    ```
    StateMachineNumberGuessWorkflow v1
    FlowchartNumberGuessWorkflow v1
    SequentialNumberGuessWorkflow v1
    ```

    <span data-ttu-id="063e2-298">La colección `Items` completa tendrá seis elementos.</span><span class="sxs-lookup"><span data-stu-id="063e2-298">The completed `Items` collection will have six items.</span></span>

    ```
    StateMachineNumberGuessWorkflow
    FlowchartNumberGuessWorkflow
    SequentialNumberGuessWorkflow
    StateMachineNumberGuessWorkflow v1
    FlowchartNumberGuessWorkflow v1
    SequentialNumberGuessWorkflow v1
    ```

4. <span data-ttu-id="063e2-299">Haga doble clic en **WorkflowHostForm** en **Explorador de soluciones** y seleccione **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="063e2-299">Double-click **WorkflowHostForm** in **Solution Explorer**, and select **View Code**.</span></span>

5. <span data-ttu-id="063e2-300">Agregue tres nuevos casos a la `switch` instrucción (o `Select Case` ) en el `NewGame_Click` controlador para asignar los nuevos elementos del cuadro combinado **WorkflowType** a las identidades de flujo de trabajo coincidentes.</span><span class="sxs-lookup"><span data-stu-id="063e2-300">Add three new cases to the `switch` (or `Select Case`) statement in the `NewGame_Click` handler to map the new items in the **WorkflowType** combo box to the matching workflow identities.</span></span>

    ```vb
    Case "SequentialNumberGuessWorkflow v1"
        identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1

    Case "StateMachineNumberGuessWorkflow v1"
        identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1

    Case "FlowchartNumberGuessWorkflow v1"
        identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1
    ```

    ```csharp
    case "SequentialNumberGuessWorkflow v1":
        identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1;
        break;

    case "StateMachineNumberGuessWorkflow v1":
        identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1;
        break;

    case "FlowchartNumberGuessWorkflow v1":
        identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1;
        break;
    ```

    <span data-ttu-id="063e2-301">El ejemplo siguiente incluye la instrucción `switch` (o `Select Case`) completa.</span><span class="sxs-lookup"><span data-stu-id="063e2-301">The following example contains the complete `switch` (or `Select Case`) statement.</span></span>

    ```vb
    Select Case WorkflowType.SelectedItem.ToString()
        Case "SequentialNumberGuessWorkflow"
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity

        Case "StateMachineNumberGuessWorkflow"
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

        Case "FlowchartNumberGuessWorkflow"
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity

        Case "SequentialNumberGuessWorkflow v1"
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1

        Case "StateMachineNumberGuessWorkflow v1"
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1

        Case "FlowchartNumberGuessWorkflow v1"
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1
    End Select
    ```

    ```csharp
    switch (WorkflowType.SelectedItem.ToString())
    {
        case "SequentialNumberGuessWorkflow":
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity;
            break;

        case "StateMachineNumberGuessWorkflow":
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;
            break;

        case "FlowchartNumberGuessWorkflow":
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;
            break;

        case "SequentialNumberGuessWorkflow v1":
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1;
            break;

        case "StateMachineNumberGuessWorkflow v1":
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1;
            break;

        case "FlowchartNumberGuessWorkflow v1":
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1;
            break;
    };
    ```

6. <span data-ttu-id="063e2-302">Presione CTRL+F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="063e2-302">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="063e2-303">Ahora puede iniciar las versiones `v1` del flujo de trabajo así como las versiones actuales.</span><span class="sxs-lookup"><span data-stu-id="063e2-303">You can now start the `v1` versions of the workflow as well as the current versions.</span></span> <span data-ttu-id="063e2-304">Para actualizar dinámicamente estas nuevas instancias, ejecute la aplicación **ApplyDynamicUpdate** .</span><span class="sxs-lookup"><span data-stu-id="063e2-304">To dynamically update these new instances, run the **ApplyDynamicUpdate** application.</span></span>
