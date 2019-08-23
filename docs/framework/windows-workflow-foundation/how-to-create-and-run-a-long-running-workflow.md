---
title: Procedimiento para crear y ejecutar un flujo de trabajo de larga duración
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c0043c89-2192-43c9-986d-3ecec4dd8c9c
ms.openlocfilehash: 75fa4fcdef9bf8e2773264fff4a8404330909e6b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962331"
---
# <a name="how-to-create-and-run-a-long-running-workflow"></a><span data-ttu-id="e1264-102">Procedimiento para crear y ejecutar un flujo de trabajo de larga duración</span><span class="sxs-lookup"><span data-stu-id="e1264-102">How to: Create and Run a Long Running Workflow</span></span>
<span data-ttu-id="e1264-103">Una de las características centrales de Windows Workflow Foundation (WF) es la capacidad del motor en tiempo de ejecución para conservar y descargar flujos de trabajo inactivos en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="e1264-103">One of the central features of Windows Workflow Foundation (WF) is the runtime’s ability to persist and unload idle workflows to a database.</span></span> <span data-ttu-id="e1264-104">Los pasos que [se describen en How to: Ejecutar un flujo](how-to-run-a-workflow.md) de trabajo demostró los aspectos básicos del hospedaje de flujos de trabajo mediante una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="e1264-104">The steps in [How to: Run a Workflow](how-to-run-a-workflow.md) demonstrated the basics of workflow hosting using a console application.</span></span> <span data-ttu-id="e1264-105">Se mostraron ejemplos de cómo iniciar flujos de trabajo, de los controladores de ciclo de vida de los flujos de trabajo y de los marcadores de reanudación.</span><span class="sxs-lookup"><span data-stu-id="e1264-105">Examples were shown of starting workflows, workflow lifecycle handlers, and resuming bookmarks.</span></span> <span data-ttu-id="e1264-106">Para demostrar la persistencia del flujo de trabajo con efectividad, es necesario un host de flujo de trabajo más complejo que admita el inicio y la reanudación de varias instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1264-106">In order to demonstrate workflow persistence effectively, a more complex workflow host is required that supports starting and resuming multiple workflow instances.</span></span> <span data-ttu-id="e1264-107">En este paso del tutorial se muestra cómo crear una aplicación host de Windows Forms que admita iniciar y reanudar varias instancias de flujo de trabajo o la persistencia del flujo de trabajo, y que proporcione una base para características avanzadas como el seguimiento y el control de versiones mostrado en los siguientes pasos del tutorial.</span><span class="sxs-lookup"><span data-stu-id="e1264-107">This step in the tutorial demonstrates how to create a Windows form host application that supports starting and resuming multiple workflow instances, workflow persistence, and provides a basis for the advanced features such as tracking and versioning that are demonstrated in subsequent tutorial steps.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1264-108">En este paso del tutorial y en los pasos siguientes se usan los [tres tipos de flujo de trabajo de cómo: crear un flujo de trabajo](how-to-create-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="e1264-108">This tutorial step and the subsequent steps use all three workflow types from [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span> <span data-ttu-id="e1264-109">Si no completó los tres tipos, puede descargar una versión completada de los pasos del [tutorial de introducción de Windows Workflow Foundation (WF45)](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="e1264-109">If you did not complete all three types you can download a completed version of the steps from [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1264-110">Para descargar una versión completada o ver un tutorial en vídeo del tutorial, consulte [Windows Workflow Foundation (WF45)-Introducción tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="e1264-110">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-topic"></a><span data-ttu-id="e1264-111">En este tema</span><span class="sxs-lookup"><span data-stu-id="e1264-111">In this topic</span></span>  
  
- [<span data-ttu-id="e1264-112">Para crear la base de datos de persistencia</span><span class="sxs-lookup"><span data-stu-id="e1264-112">To create the persistence database</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_CreatePersistenceDatabase)  
  
- [<span data-ttu-id="e1264-113">Para agregar la referencia a los ensamblados de DurableInstancing</span><span class="sxs-lookup"><span data-stu-id="e1264-113">To add the reference to the DurableInstancing assemblies</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_AddReference)  
  
- [<span data-ttu-id="e1264-114">Para crear el formulario de host de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e1264-114">To create the workflow host form</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_CreateForm)  
  
- [<span data-ttu-id="e1264-115">Para agregar las propiedades y los métodos auxiliares del formulario</span><span class="sxs-lookup"><span data-stu-id="e1264-115">To add the properties and helper methods of the form</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_AddHelperMethods)  
  
- [<span data-ttu-id="e1264-116">Para configurar el almacén de instancias, los controladores de ciclo de vida del flujo de trabajo y las extensiones</span><span class="sxs-lookup"><span data-stu-id="e1264-116">To configure the instance store, workflow lifecycle handlers, and extensions</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_ConfigureWorkflowApplication)  
  
- [<span data-ttu-id="e1264-117">Para habilitar el inicio y la reanudación de varios tipos de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e1264-117">To enable starting and resuming multiple workflow types</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_WorkflowVersionMap)  
  
- [<span data-ttu-id="e1264-118">Para iniciar un nuevo flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e1264-118">To start a new workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_StartWorkflow)  
  
- [<span data-ttu-id="e1264-119">Para reanudar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e1264-119">To resume a workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_ResumeWorkflow)  
  
- [<span data-ttu-id="e1264-120">Para finalizar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e1264-120">To terminate a workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_TerminateWorkflow)  
  
- [<span data-ttu-id="e1264-121">Para compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="e1264-121">To build and run the application</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_BuildAndRun)  
  
### <a name="BKMK_CreatePersistenceDatabase"></a><span data-ttu-id="e1264-122">Para crear la base de datos de persistencia</span><span class="sxs-lookup"><span data-stu-id="e1264-122">To create the persistence database</span></span>  
  
1. <span data-ttu-id="e1264-123">Abra SQL Server Management Studio y conéctese al servidor local, por ejemplo **.\SQLEXPRESS**.</span><span class="sxs-lookup"><span data-stu-id="e1264-123">Open SQL Server Management Studio and connect to the local server, for example **.\SQLEXPRESS**.</span></span> <span data-ttu-id="e1264-124">Haga clic con el botón secundario en el nodo **bases** de datos del servidor local y seleccione **nueva base de datos**.</span><span class="sxs-lookup"><span data-stu-id="e1264-124">Right-click the **Databases** node on the local server, and select **New Database**.</span></span> <span data-ttu-id="e1264-125">Asigne a la nueva base de datos el nombre **WF45GettingStartedTutorial**, acepte el resto de valores y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e1264-125">Name the new database **WF45GettingStartedTutorial**, accept all other values, and select **OK**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e1264-126">Asegúrese de que tiene el permiso **Create Database** en el servidor local antes de crear la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e1264-126">Ensure that you have **Create Database** permission on the local server before creating the database.</span></span>  
  
2. <span data-ttu-id="e1264-127">Elija **abrir**, **archivo** en el menú **archivo** .</span><span class="sxs-lookup"><span data-stu-id="e1264-127">Choose **Open**, **File** from the **File** menu.</span></span> <span data-ttu-id="e1264-128">Busque la siguiente carpeta: `C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en`</span><span class="sxs-lookup"><span data-stu-id="e1264-128">Browse to the following folder: `C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en`</span></span>  
  
     <span data-ttu-id="e1264-129">Seleccione los dos archivos siguientes y haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="e1264-129">Select the following two files and click **Open**.</span></span>  
  
    - <span data-ttu-id="e1264-130">SqlWorkflowInstanceStoreLogic.sql</span><span class="sxs-lookup"><span data-stu-id="e1264-130">SqlWorkflowInstanceStoreLogic.sql</span></span>  
  
    - <span data-ttu-id="e1264-131">SqlWorkflowInstanceStoreSchema.sql</span><span class="sxs-lookup"><span data-stu-id="e1264-131">SqlWorkflowInstanceStoreSchema.sql</span></span>  
  
3. <span data-ttu-id="e1264-132">Elija **SqlWorkflowInstanceStoreSchema. SQL** en el menú **ventana** .</span><span class="sxs-lookup"><span data-stu-id="e1264-132">Choose **SqlWorkflowInstanceStoreSchema.sql** from the **Window** menu.</span></span> <span data-ttu-id="e1264-133">Asegúrese de que **WF45GettingStartedTutorial** está seleccionado en la lista desplegable **bases de datos disponibles** y elija **Ejecutar** en el menú **consulta** .</span><span class="sxs-lookup"><span data-stu-id="e1264-133">Ensure that **WF45GettingStartedTutorial** is selected in the **Available Databases** drop-down and choose **Execute** from the **Query** menu.</span></span>  
  
4. <span data-ttu-id="e1264-134">Elija **SqlWorkflowInstanceStoreLogic. SQL** en el menú **ventana** .</span><span class="sxs-lookup"><span data-stu-id="e1264-134">Choose **SqlWorkflowInstanceStoreLogic.sql** from the **Window** menu.</span></span> <span data-ttu-id="e1264-135">Asegúrese de que **WF45GettingStartedTutorial** está seleccionado en la lista desplegable **bases de datos disponibles** y elija **Ejecutar** en el menú **consulta** .</span><span class="sxs-lookup"><span data-stu-id="e1264-135">Ensure that **WF45GettingStartedTutorial** is selected in the **Available Databases** drop-down and choose **Execute** from the **Query** menu.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="e1264-136">Es importante realizar los dos pasos anteriores en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="e1264-136">It is important to perform the previous two steps in the correct order.</span></span> <span data-ttu-id="e1264-137">Si las consultas se ejecutan de manera desordenada, aparecerán errores y la base de datos de persistencia no se configurará correctamente.</span><span class="sxs-lookup"><span data-stu-id="e1264-137">If the queries are executed out of order, errors occur and the persistence database is not configured correctly.</span></span>  
  
### <a name="BKMK_AddReference"></a><span data-ttu-id="e1264-138">Para agregar la referencia a los ensamblados de DurableInstancing</span><span class="sxs-lookup"><span data-stu-id="e1264-138">To add the reference to the DurableInstancing assemblies</span></span>  
  
1. <span data-ttu-id="e1264-139">Haga clic con el botón secundario en **NumberGuessWorkflowHost** en **Explorador de soluciones** y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="e1264-139">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and select **Add Reference**.</span></span>  
  
2. <span data-ttu-id="e1264-140">Seleccione **ensamblados** en la lista **Agregar referencia** y escriba `DurableInstancing` en el cuadro **buscar ensamblados** .</span><span class="sxs-lookup"><span data-stu-id="e1264-140">Select **Assemblies** from the **Add Reference** list, and type `DurableInstancing` into the **Search Assemblies** box.</span></span> <span data-ttu-id="e1264-141">Esto filtrará los ensamblados y simplificará la selección de las referencias deseadas.</span><span class="sxs-lookup"><span data-stu-id="e1264-141">This filters the assemblies and makes the desired references easier to select.</span></span>  
  
3. <span data-ttu-id="e1264-142">Active la casilla situada junto a **System. Activities. DurableInstancing** y **System. Runtime. DurableInstancing** de la lista de resultados de la **búsqueda** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e1264-142">Check the checkbox beside **System.Activities.DurableInstancing** and **System.Runtime.DurableInstancing** from the **Search Results** list, and click **OK**.</span></span>  
  
### <a name="BKMK_CreateForm"></a><span data-ttu-id="e1264-143">Para crear el formulario de host de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e1264-143">To create the workflow host form</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1264-144">Los pasos de este procedimiento describen cómo agregar y configurar el formulario manualmente.</span><span class="sxs-lookup"><span data-stu-id="e1264-144">The steps in this procedure describe how to add and configure the form manually.</span></span> <span data-ttu-id="e1264-145">Si lo desea, puede descargar los archivos de solución para el tutorial y agregar el formulario completo al proyecto.</span><span class="sxs-lookup"><span data-stu-id="e1264-145">If desired, you can download the solution files for the tutorial and add the completed form to the project.</span></span> <span data-ttu-id="e1264-146">Para descargar los archivos del tutorial, consulte [Windows Workflow Foundation (WF45)-Introducción tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="e1264-146">To download the tutorial files, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span> <span data-ttu-id="e1264-147">Una vez descargados los archivos, haga clic con el botón derecho en **NumberGuessWorkflowHost** y elija **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="e1264-147">Once the files are downloaded, right-click **NumberGuessWorkflowHost** and choose **Add Reference**.</span></span> <span data-ttu-id="e1264-148">Agregue una referencia a **System. Windows. Forms** y **System. Drawing**.</span><span class="sxs-lookup"><span data-stu-id="e1264-148">Add a reference to **System.Windows.Forms** and **System.Drawing**.</span></span> <span data-ttu-id="e1264-149">Estas referencias se agregan automáticamente si agrega un nuevo formulario desde el menú **Agregar**, **nuevo elemento** , pero se debe agregar manualmente al importar un formulario.</span><span class="sxs-lookup"><span data-stu-id="e1264-149">These references are added automatically if you add a new form from the **Add**, **New Item** menu, but must be added manually when importing a form.</span></span> <span data-ttu-id="e1264-150">Una vez agregadas las referencias, haga clic con el botón derecho en **NumberGuessWorkflowHost** en **Explorador de soluciones** y elija **Agregar**, **elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="e1264-150">Once the references are added, right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Existing Item**.</span></span> <span data-ttu-id="e1264-151">Vaya a la `Form` carpeta en los archivos de proyecto, seleccione **WorkflowHostForm.CS** (o **WorkflowHostForm. VB**) y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e1264-151">Browse to the `Form` folder in the project files, select **WorkflowHostForm.cs** (or **WorkflowHostForm.vb**), and click **Add**.</span></span> <span data-ttu-id="e1264-152">Si decide importar el formulario, puede omitir hasta la sección siguiente [para agregar las propiedades y los métodos auxiliares del formulario](how-to-create-and-run-a-long-running-workflow.md#BKMK_AddHelperMethods).</span><span class="sxs-lookup"><span data-stu-id="e1264-152">If you choose to import the form, then you can skip down to the next section, [To add the properties and helper methods of the form](how-to-create-and-run-a-long-running-workflow.md#BKMK_AddHelperMethods).</span></span>  
  
1. <span data-ttu-id="e1264-153">Haga clic con el botón secundario en **NumberGuessWorkflowHost** en **Explorador de soluciones** y elija **Agregar**, **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="e1264-153">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="e1264-154">En la lista plantillas instaladas, elija **Windows**Forms `WorkflowHostForm` , escriba en el cuadro **nombre** y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e1264-154">In the **Installed** templates list, choose **Windows Form**, type `WorkflowHostForm` in the **Name** box, and click **Add**.</span></span>  
  
3. <span data-ttu-id="e1264-155">Configure las siguientes propiedades en el formulario.</span><span class="sxs-lookup"><span data-stu-id="e1264-155">Configure the following properties on the form.</span></span>  
  
    |<span data-ttu-id="e1264-156">Propiedad</span><span class="sxs-lookup"><span data-stu-id="e1264-156">Property</span></span>|<span data-ttu-id="e1264-157">Valor</span><span class="sxs-lookup"><span data-stu-id="e1264-157">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="e1264-158">FormBorderStyle</span><span class="sxs-lookup"><span data-stu-id="e1264-158">FormBorderStyle</span></span>|<span data-ttu-id="e1264-159">FixedSingle</span><span class="sxs-lookup"><span data-stu-id="e1264-159">FixedSingle</span></span>|  
    |<span data-ttu-id="e1264-160">MaximizeBox</span><span class="sxs-lookup"><span data-stu-id="e1264-160">MaximizeBox</span></span>|<span data-ttu-id="e1264-161">False</span><span class="sxs-lookup"><span data-stu-id="e1264-161">False</span></span>|  
    |<span data-ttu-id="e1264-162">Tamaño</span><span class="sxs-lookup"><span data-stu-id="e1264-162">Size</span></span>|<span data-ttu-id="e1264-163">400, 420</span><span class="sxs-lookup"><span data-stu-id="e1264-163">400, 420</span></span>|  
  
4. <span data-ttu-id="e1264-164">Agregue los siguientes controles al formulario en el orden especificado y configure las propiedades como dirigidas.</span><span class="sxs-lookup"><span data-stu-id="e1264-164">Add the following controls to the form in the order specified and configure the properties as directed.</span></span>  
  
    |<span data-ttu-id="e1264-165">Control</span><span class="sxs-lookup"><span data-stu-id="e1264-165">Control</span></span>|<span data-ttu-id="e1264-166">Propiedad Valor</span><span class="sxs-lookup"><span data-stu-id="e1264-166">Property: Value</span></span>|  
    |-------------|---------------------|  
    |<span data-ttu-id="e1264-167">**Button**</span><span class="sxs-lookup"><span data-stu-id="e1264-167">**Button**</span></span>|<span data-ttu-id="e1264-168">Nombre: NewGame</span><span class="sxs-lookup"><span data-stu-id="e1264-168">Name: NewGame</span></span><br /><br /> <span data-ttu-id="e1264-169">Ubicación: 13, 13</span><span class="sxs-lookup"><span data-stu-id="e1264-169">Location: 13, 13</span></span><br /><br /> <span data-ttu-id="e1264-170">Tamaño: 75, 23</span><span class="sxs-lookup"><span data-stu-id="e1264-170">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="e1264-171">Negrita Nuevo juego</span><span class="sxs-lookup"><span data-stu-id="e1264-171">Text: New Game</span></span>|  
    |<span data-ttu-id="e1264-172">**Label**</span><span class="sxs-lookup"><span data-stu-id="e1264-172">**Label**</span></span>|<span data-ttu-id="e1264-173">Ubicación: 94, 18</span><span class="sxs-lookup"><span data-stu-id="e1264-173">Location: 94, 18</span></span><br /><br /> <span data-ttu-id="e1264-174">Negrita Adivine un número del 1 al</span><span class="sxs-lookup"><span data-stu-id="e1264-174">Text: Guess a number from 1 to</span></span>|  
    |<span data-ttu-id="e1264-175">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="e1264-175">**ComboBox**</span></span>|<span data-ttu-id="e1264-176">Nombre: NumberRange</span><span class="sxs-lookup"><span data-stu-id="e1264-176">Name: NumberRange</span></span><br /><br /> <span data-ttu-id="e1264-177">DropDownStyle: DropDownList</span><span class="sxs-lookup"><span data-stu-id="e1264-177">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="e1264-178">Elementos: 10, 100, 1000</span><span class="sxs-lookup"><span data-stu-id="e1264-178">Items: 10, 100, 1000</span></span><br /><br /> <span data-ttu-id="e1264-179">Ubicación: 228, 12</span><span class="sxs-lookup"><span data-stu-id="e1264-179">Location: 228, 12</span></span><br /><br /> <span data-ttu-id="e1264-180">Tamaño: 143, 21</span><span class="sxs-lookup"><span data-stu-id="e1264-180">Size: 143, 21</span></span>|  
    |<span data-ttu-id="e1264-181">**Label**</span><span class="sxs-lookup"><span data-stu-id="e1264-181">**Label**</span></span>|<span data-ttu-id="e1264-182">Ubicación: 13, 43</span><span class="sxs-lookup"><span data-stu-id="e1264-182">Location: 13, 43</span></span><br /><br /> <span data-ttu-id="e1264-183">Negrita Tipo de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e1264-183">Text: Workflow type</span></span>|  
    |<span data-ttu-id="e1264-184">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="e1264-184">**ComboBox**</span></span>|<span data-ttu-id="e1264-185">Nombre: WorkflowType</span><span class="sxs-lookup"><span data-stu-id="e1264-185">Name: WorkflowType</span></span><br /><br /> <span data-ttu-id="e1264-186">DropDownStyle: DropDownList</span><span class="sxs-lookup"><span data-stu-id="e1264-186">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="e1264-187">Elementos: StateMachineNumberGuessWorkflow, FlowchartNumberGuessWorkflow, SequentialNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="e1264-187">Items: StateMachineNumberGuessWorkflow, FlowchartNumberGuessWorkflow, SequentialNumberGuessWorkflow</span></span><br /><br /> <span data-ttu-id="e1264-188">Ubicación: 94, 40</span><span class="sxs-lookup"><span data-stu-id="e1264-188">Location: 94, 40</span></span><br /><br /> <span data-ttu-id="e1264-189">Tamaño: 277, 21</span><span class="sxs-lookup"><span data-stu-id="e1264-189">Size: 277, 21</span></span>|  
    |<span data-ttu-id="e1264-190">**Label**</span><span class="sxs-lookup"><span data-stu-id="e1264-190">**Label**</span></span>|<span data-ttu-id="e1264-191">Nombre: WorkflowVersion</span><span class="sxs-lookup"><span data-stu-id="e1264-191">Name: WorkflowVersion</span></span><br /><br /> <span data-ttu-id="e1264-192">Ubicación: 13, 362</span><span class="sxs-lookup"><span data-stu-id="e1264-192">Location: 13, 362</span></span><br /><br /> <span data-ttu-id="e1264-193">Negrita Versión del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e1264-193">Text: Workflow version</span></span>|  
    |<span data-ttu-id="e1264-194">**GroupBox**</span><span class="sxs-lookup"><span data-stu-id="e1264-194">**GroupBox**</span></span>|<span data-ttu-id="e1264-195">Ubicación: 13, 67</span><span class="sxs-lookup"><span data-stu-id="e1264-195">Location: 13, 67</span></span><br /><br /> <span data-ttu-id="e1264-196">Tamaño: 358, 287</span><span class="sxs-lookup"><span data-stu-id="e1264-196">Size: 358, 287</span></span><br /><br /> <span data-ttu-id="e1264-197">Negrita Juego</span><span class="sxs-lookup"><span data-stu-id="e1264-197">Text: Game</span></span>|  
  
    > [!NOTE]
    > <span data-ttu-id="e1264-198">Al agregar los controles siguientes, colóquelos en el GroupBox.</span><span class="sxs-lookup"><span data-stu-id="e1264-198">When adding the following controls, put them into the GroupBox.</span></span>  
  
    |<span data-ttu-id="e1264-199">Control</span><span class="sxs-lookup"><span data-stu-id="e1264-199">Control</span></span>|<span data-ttu-id="e1264-200">Propiedad Valor</span><span class="sxs-lookup"><span data-stu-id="e1264-200">Property: Value</span></span>|  
    |-------------|---------------------|  
    |<span data-ttu-id="e1264-201">**Label**</span><span class="sxs-lookup"><span data-stu-id="e1264-201">**Label**</span></span>|<span data-ttu-id="e1264-202">Ubicación: 7, 20</span><span class="sxs-lookup"><span data-stu-id="e1264-202">Location: 7, 20</span></span><br /><br /> <span data-ttu-id="e1264-203">Negrita Identificador de instancia de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e1264-203">Text: Workflow Instance Id</span></span>|  
    |<span data-ttu-id="e1264-204">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="e1264-204">**ComboBox**</span></span>|<span data-ttu-id="e1264-205">Nombre: InstanceId</span><span class="sxs-lookup"><span data-stu-id="e1264-205">Name: InstanceId</span></span><br /><br /> <span data-ttu-id="e1264-206">DropDownStyle: DropDownList</span><span class="sxs-lookup"><span data-stu-id="e1264-206">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="e1264-207">Ubicación: 121, 17</span><span class="sxs-lookup"><span data-stu-id="e1264-207">Location: 121, 17</span></span><br /><br /> <span data-ttu-id="e1264-208">Tamaño: 227, 21</span><span class="sxs-lookup"><span data-stu-id="e1264-208">Size: 227, 21</span></span>|  
    |<span data-ttu-id="e1264-209">**Label**</span><span class="sxs-lookup"><span data-stu-id="e1264-209">**Label**</span></span>|<span data-ttu-id="e1264-210">Ubicación: 7, 47</span><span class="sxs-lookup"><span data-stu-id="e1264-210">Location: 7, 47</span></span><br /><br /> <span data-ttu-id="e1264-211">Negrita Adivinanza</span><span class="sxs-lookup"><span data-stu-id="e1264-211">Text: Guess</span></span>|  
    |<span data-ttu-id="e1264-212">**TextBox**</span><span class="sxs-lookup"><span data-stu-id="e1264-212">**TextBox**</span></span>|<span data-ttu-id="e1264-213">Nombre: Adivinanza</span><span class="sxs-lookup"><span data-stu-id="e1264-213">Name: Guess</span></span><br /><br /> <span data-ttu-id="e1264-214">Ubicación: 50, 44</span><span class="sxs-lookup"><span data-stu-id="e1264-214">Location: 50, 44</span></span><br /><br /> <span data-ttu-id="e1264-215">Tamaño: 65, 20</span><span class="sxs-lookup"><span data-stu-id="e1264-215">Size: 65, 20</span></span>|  
    |<span data-ttu-id="e1264-216">**Button**</span><span class="sxs-lookup"><span data-stu-id="e1264-216">**Button**</span></span>|<span data-ttu-id="e1264-217">Nombre: EnterGuess</span><span class="sxs-lookup"><span data-stu-id="e1264-217">Name: EnterGuess</span></span><br /><br /> <span data-ttu-id="e1264-218">Ubicación: 121, 42</span><span class="sxs-lookup"><span data-stu-id="e1264-218">Location: 121, 42</span></span><br /><br /> <span data-ttu-id="e1264-219">Tamaño: 75, 23</span><span class="sxs-lookup"><span data-stu-id="e1264-219">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="e1264-220">Negrita Escriba la adivinanza</span><span class="sxs-lookup"><span data-stu-id="e1264-220">Text: Enter Guess</span></span>|  
    |<span data-ttu-id="e1264-221">**Button**</span><span class="sxs-lookup"><span data-stu-id="e1264-221">**Button**</span></span>|<span data-ttu-id="e1264-222">Nombre: QuitGame</span><span class="sxs-lookup"><span data-stu-id="e1264-222">Name: QuitGame</span></span><br /><br /> <span data-ttu-id="e1264-223">Ubicación: 274, 42</span><span class="sxs-lookup"><span data-stu-id="e1264-223">Location: 274, 42</span></span><br /><br /> <span data-ttu-id="e1264-224">Tamaño: 75, 23</span><span class="sxs-lookup"><span data-stu-id="e1264-224">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="e1264-225">Negrita Salir</span><span class="sxs-lookup"><span data-stu-id="e1264-225">Text: Quit</span></span>|  
    |<span data-ttu-id="e1264-226">**TextBox**</span><span class="sxs-lookup"><span data-stu-id="e1264-226">**TextBox**</span></span>|<span data-ttu-id="e1264-227">Nombre: WorkflowStatus</span><span class="sxs-lookup"><span data-stu-id="e1264-227">Name: WorkflowStatus</span></span><br /><br /> <span data-ttu-id="e1264-228">Ubicación: 10, 73</span><span class="sxs-lookup"><span data-stu-id="e1264-228">Location: 10, 73</span></span><br /><br /> <span data-ttu-id="e1264-229">Ocupa True</span><span class="sxs-lookup"><span data-stu-id="e1264-229">Multiline: True</span></span><br /><br /> <span data-ttu-id="e1264-230">ReadOnly True</span><span class="sxs-lookup"><span data-stu-id="e1264-230">ReadOnly: True</span></span><br /><br /> <span data-ttu-id="e1264-231">Barras Vertical</span><span class="sxs-lookup"><span data-stu-id="e1264-231">ScrollBars: Vertical</span></span><br /><br /> <span data-ttu-id="e1264-232">Tamaño: 338, 208</span><span class="sxs-lookup"><span data-stu-id="e1264-232">Size: 338, 208</span></span>|  
  
5. <span data-ttu-id="e1264-233">Establezca la propiedad **AcceptButton** del formulario en **EnterGuess**.</span><span class="sxs-lookup"><span data-stu-id="e1264-233">Set the **AcceptButton** property of the form to **EnterGuess**.</span></span>  
  
 <span data-ttu-id="e1264-234">En el siguiente ejemplo se muestra el formulario completado.</span><span class="sxs-lookup"><span data-stu-id="e1264-234">The following example illustrates the completed form.</span></span>  
  
 ![Captura de pantalla de un formulario de host de flujo de trabajo Windows Workflow Foundation.](./media/how-to-create-and-run-a-long-running-workflow/windows-workflow-foundation-workflowhostform.png)  
  
### <a name="BKMK_AddHelperMethods"></a><span data-ttu-id="e1264-236">Para agregar las propiedades y los métodos auxiliares del formulario</span><span class="sxs-lookup"><span data-stu-id="e1264-236">To add the properties and helper methods of the form</span></span>  
 <span data-ttu-id="e1264-237">Los pasos de esta sección agregan propiedades y métodos del asistente a la clase de formulario que configuran la interfaz de usuario del formulario para que se admita la ejecución y la reanudación de flujos de trabajo de acierto de números.</span><span class="sxs-lookup"><span data-stu-id="e1264-237">The steps in this section add properties and helper methods to the form class that configure the UI of the form to support running and resuming number guess workflows.</span></span>  
  
1. <span data-ttu-id="e1264-238">Haga clic con el botón secundario en **WorkflowHostForm** en **Explorador de soluciones** y elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="e1264-238">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span></span>  
  
2. <span data-ttu-id="e1264-239">Agregue las siguientes instrucciones `using` (o `Imports`) al principio del archivo con las demás instrucciones `using` (o `Imports`).</span><span class="sxs-lookup"><span data-stu-id="e1264-239">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Windows.Forms  
    Imports System.Activities.DurableInstancing  
    Imports System.Activities  
    Imports System.Data.SqlClient  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Windows.Forms;  
    using System.Activities.DurableInstancing;  
    using System.Activities;  
    using System.Data.SqlClient;  
    using System.IO;  
    ```  
  
3. <span data-ttu-id="e1264-240">Agregue las declaraciones de miembro siguientes a la clase **WorkflowHostForm** .</span><span class="sxs-lookup"><span data-stu-id="e1264-240">Add the following member declarations to the **WorkflowHostForm** class.</span></span>  
  
    ```vb  
    Const connectionString = "Server=.\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI"  
    Dim store As SqlWorkflowInstanceStore  
    Dim WorkflowStarting As Boolean  
    ```  
  
    ```csharp  
    const string connectionString = "Server=.\\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI";  
    SqlWorkflowInstanceStore store;  
    bool WorkflowStarting;  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="e1264-241">Si la cadena de conexión es diferente, actualice `connectionString` para consultar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e1264-241">If your connection string is different, update `connectionString` to refer to your database.</span></span>  
  
4. <span data-ttu-id="e1264-242">Agregue una propiedad `WorkflowInstanceId` a la clase `WorkflowFormHost`.</span><span class="sxs-lookup"><span data-stu-id="e1264-242">Add a `WorkflowInstanceId` property to the `WorkflowFormHost` class.</span></span>  
  
    ```vb  
    Public ReadOnly Property WorkflowInstanceId() As Guid  
        Get  
            If InstanceId.SelectedIndex = -1 Then  
                Return Guid.Empty  
            Else  
                Return New Guid(InstanceId.SelectedItem.ToString())  
            End If  
        End Get  
    End Property  
    ```  
  
    ```csharp  
    public Guid WorkflowInstanceId  
    {  
        get  
        {  
            return InstanceId.SelectedIndex == -1 ? Guid.Empty : (Guid)InstanceId.SelectedItem;  
        }  
    }  
    ```  
  
     <span data-ttu-id="e1264-243">En `InstanceId` el cuadro combinado se muestra una lista de los identificadores de instancia de `WorkflowInstanceId` flujo de trabajo persistentes y la propiedad devuelve el flujo de trabajo seleccionado actualmente.</span><span class="sxs-lookup"><span data-stu-id="e1264-243">The `InstanceId` combo box displays a list of persisted workflow instance ids, and the `WorkflowInstanceId` property returns the currently selected workflow.</span></span>  
  
5. <span data-ttu-id="e1264-244">Agregue un controlador para el evento del formulario `Load`.</span><span class="sxs-lookup"><span data-stu-id="e1264-244">Add a handler for the form `Load` event.</span></span> <span data-ttu-id="e1264-245">Para agregar el controlador, cambie a la **vista Diseño** para el formulario, haga clic en el icono **eventos** en la parte superior de la ventana **propiedades** y haga doble clic en **cargar**.</span><span class="sxs-lookup"><span data-stu-id="e1264-245">To add the handler, switch to **Design View** for the form, click the **Events** icon at the top of the **Properties** window, and double-click **Load**.</span></span>  
  
    ```vb  
    Private Sub WorkflowHostForm_Load(sender As Object, e As EventArgs) Handles Me.Load  
  
    End Sub  
    ```  
  
    ```csharp  
    private void WorkflowHostForm_Load(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
6. <span data-ttu-id="e1264-246">Agregue el código siguiente a `WorkflowHostForm_Load`.</span><span class="sxs-lookup"><span data-stu-id="e1264-246">Add the following code to `WorkflowHostForm_Load`.</span></span>  
  
    ```vb  
    'Initialize the store and configure it so that it can be used for  
    'multiple WorkflowApplication instances.  
    store = New SqlWorkflowInstanceStore(connectionString)  
    WorkflowApplication.CreateDefaultInstanceOwner(store, Nothing, WorkflowIdentityFilter.Any)  
  
    'Set default ComboBox selections.  
    NumberRange.SelectedIndex = 0  
    WorkflowType.SelectedIndex = 0  
  
    ListPersistedWorkflows()  
    ```  
  
    ```csharp  
    // Initialize the store and configure it so that it can be used for  
    // multiple WorkflowApplication instances.  
    store = new SqlWorkflowInstanceStore(connectionString);  
    WorkflowApplication.CreateDefaultInstanceOwner(store, null, WorkflowIdentityFilter.Any);  
  
    // Set default ComboBox selections.  
    NumberRange.SelectedIndex = 0;  
    WorkflowType.SelectedIndex = 0;  
  
    ListPersistedWorkflows();  
    ```  
  
     <span data-ttu-id="e1264-247">Cuando el formulario se carga, se configura `SqlWorkflowInstanceStore`, los intervalos y los cuadros combinados de tipo de flujo de trabajo se establecen en valores predeterminados y las instancias de flujo de trabajo persistentes se agregan al cuadro combinado `InstanceId`.</span><span class="sxs-lookup"><span data-stu-id="e1264-247">When the form loads, the `SqlWorkflowInstanceStore` is configured, the range and workflow type combo boxes are set to default values, and the persisted workflow instances are added to the `InstanceId` combo box.</span></span>  
  
7. <span data-ttu-id="e1264-248">Agregue un controlador `SelectedIndexChanged` para `InstanceId`.</span><span class="sxs-lookup"><span data-stu-id="e1264-248">Add a `SelectedIndexChanged` handler for `InstanceId`.</span></span> <span data-ttu-id="e1264-249">Para agregar el controlador, cambie a la **vista Diseño** para el formulario, seleccione `InstanceId` el cuadro combinado, haga clic en el icono **eventos** en la parte superior de la ventana **propiedades** y haga doble clic en **SelectedIndexChanged**.</span><span class="sxs-lookup"><span data-stu-id="e1264-249">To add the handler, switch to **Design View** for the form, select the `InstanceId` combo box, click the **Events** icon at the top of the **Properties** window, and double-click **SelectedIndexChanged**.</span></span>  
  
    ```vb  
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged  
  
    End Sub  
    ```  
  
    ```csharp  
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
8. <span data-ttu-id="e1264-250">Agregue el código siguiente a `InstanceId_SelectedIndexChanged`.</span><span class="sxs-lookup"><span data-stu-id="e1264-250">Add the following code to `InstanceId_SelectedIndexChanged`.</span></span> <span data-ttu-id="e1264-251">Siempre que el usuario selecciona un flujo de trabajo mediante el cuadro combinado, este controlador actualiza la ventana de estado.</span><span class="sxs-lookup"><span data-stu-id="e1264-251">Whenever the user selects a workflow by using the combo box this handler updates the status window.</span></span>  
  
    ```vb  
    If InstanceId.SelectedIndex = -1 Then  
        Return  
    End If  
  
    'Clear the status window.  
    WorkflowStatus.Clear()  
  
    'Get the workflow version and display it.  
    'If the workflow is just starting then this info will not  
    'be available in the persistence store so do not try and retrieve it.  
    If Not WorkflowStarting Then  
        Dim instance As WorkflowApplicationInstance = _  
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
        WorkflowVersion.Text = _  
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity)  
  
        'Unload the instance.  
        instance.Abandon()  
    End If  
    ```  
  
    ```csharp  
    if (InstanceId.SelectedIndex == -1)  
    {  
        return;  
    }  
  
    // Clear the status window.  
    WorkflowStatus.Clear();  
  
    // Get the workflow version and display it.  
    // If the workflow is just starting then this info will not  
    // be available in the persistence store so do not try and retrieve it.  
    if (!WorkflowStarting)  
    {  
        WorkflowApplicationInstance instance =  
            WorkflowApplication.GetInstance(this.WorkflowInstanceId, store);  
  
        WorkflowVersion.Text =  
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity);  
  
        // Unload the instance.  
        instance.Abandon();  
    }  
    ```  
  
9. <span data-ttu-id="e1264-252">Agregue el siguiente método `ListPersistedWorkflows` a la clase de formulario.</span><span class="sxs-lookup"><span data-stu-id="e1264-252">Add the following `ListPersistedWorkflows` method to the form class.</span></span>  
  
    ```vb  
    Private Sub ListPersistedWorkflows()  
        Using localCon As New SqlConnection(connectionString)  
            Dim localCmd As String = _  
                "Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]"  
  
            Dim cmd As SqlCommand = localCon.CreateCommand()  
            cmd.CommandText = localCmd  
            localCon.Open()  
            Using reader As SqlDataReader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
  
                While (reader.Read())  
                    'Get the InstanceId of the persisted Workflow.  
                    Dim id As Guid = Guid.Parse(reader(0).ToString())  
                    InstanceId.Items.Add(id)  
                End While  
            End Using  
        End Using  
    End Sub  
    ```  
  
    ```csharp  
    using (SqlConnection localCon = new SqlConnection(connectionString))  
    {  
        string localCmd =  
            "Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]";  
  
        SqlCommand cmd = localCon.CreateCommand();  
        cmd.CommandText = localCmd;  
        localCon.Open();  
        using (SqlDataReader reader = cmd.ExecuteReader(CommandBehavior.CloseConnection))  
        {  
            while (reader.Read())  
            {  
                // Get the InstanceId of the persisted Workflow  
                Guid id = Guid.Parse(reader[0].ToString());  
                InstanceId.Items.Add(id);  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="e1264-253">`ListPersistedWorkflows` consulta el almacén de instancias con respecto a las instancias de flujo de trabajo persistentes y agrega los identificadores de instancia al cuadro combinado `cboInstanceId`.</span><span class="sxs-lookup"><span data-stu-id="e1264-253">`ListPersistedWorkflows` queries the instance store for persisted workflow instances, and adds the instance ids to the `cboInstanceId` combo box.</span></span>  
  
10. <span data-ttu-id="e1264-254">Agregue el siguiente método `UpdateStatus` y el delegado correspondiente a la clase de formulario.</span><span class="sxs-lookup"><span data-stu-id="e1264-254">Add the following `UpdateStatus` method and corresponding delegate to the form class.</span></span> <span data-ttu-id="e1264-255">Este método actualiza la ventana de estado en el formulario con el estado del flujo de trabajo en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="e1264-255">This method updates the status window on the form with the status of the currently running workflow.</span></span>  
  
    ```vb  
    Private Delegate Sub UpdateStatusDelegate(msg As String)  
    Public Sub UpdateStatus(msg As String)  
        'We may be on a different thread so we need to  
        'make this call using BeginInvoke.  
        If InvokeRequired Then  
            BeginInvoke(New UpdateStatusDelegate(AddressOf UpdateStatus), msg)  
        Else  
            If Not msg.EndsWith(vbCrLf) Then  
                msg = msg & vbCrLf  
            End If  
  
            WorkflowStatus.AppendText(msg)  
  
            'Ensure that the newly added status is visible.  
            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length  
            WorkflowStatus.ScrollToCaret()  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private delegate void UpdateStatusDelegate(string msg);  
    public void UpdateStatus(string msg)  
    {  
        // We may be on a different thread so we need to  
        // make this call using BeginInvoke.  
        if (InvokeRequired)  
        {  
            BeginInvoke(new UpdateStatusDelegate(UpdateStatus), msg);  
        }  
        else  
        {  
            if (!msg.EndsWith("\r\n"))  
            {  
                msg += "\r\n";  
            }  
            WorkflowStatus.AppendText(msg);  
  
            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length;  
            WorkflowStatus.ScrollToCaret();  
        }  
    }  
    ```  
  
11. <span data-ttu-id="e1264-256">Agregue el siguiente método `GameOver` y el delegado correspondiente a la clase de formulario.</span><span class="sxs-lookup"><span data-stu-id="e1264-256">Add the following `GameOver` method and corresponding delegate to the form class.</span></span> <span data-ttu-id="e1264-257">Cuando se completa un flujo de trabajo, este método actualiza la interfaz de usuario del formulario quitando el identificador de instancia del flujo de trabajo completado del cuadro combinado **InstanceID** .</span><span class="sxs-lookup"><span data-stu-id="e1264-257">When a workflow completes, this method updates the form UI by removing the instance id of the completed workflow from the **InstanceId** combo box.</span></span>  
  
    ```vb  
    Private Delegate Sub GameOverDelegate()  
    Private Sub GameOver()  
        If InvokeRequired Then  
            BeginInvoke(New GameOverDelegate(AddressOf GameOver))  
        Else  
            'Remove this instance from the InstanceId combo box.  
            InstanceId.Items.Remove(InstanceId.SelectedItem)  
            InstanceId.SelectedIndex = -1  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private delegate void GameOverDelegate();  
    private void GameOver()  
    {  
        if (InvokeRequired)  
        {  
            BeginInvoke(new GameOverDelegate(GameOver));  
        }  
        else  
        {  
            // Remove this instance from the combo box  
            InstanceId.Items.Remove(InstanceId.SelectedItem);  
            InstanceId.SelectedIndex = -1;  
        }  
    }  
    ```  
  
### <a name="BKMK_ConfigureWorkflowApplication"></a><span data-ttu-id="e1264-258">Para configurar el almacén de instancias, los controladores de ciclo de vida del flujo de trabajo y las extensiones</span><span class="sxs-lookup"><span data-stu-id="e1264-258">To configure the instance store, workflow lifecycle handlers, and extensions</span></span>  
  
1. <span data-ttu-id="e1264-259">Agregue un método `ConfigureWorkflowApplication` a la clase de formulario.</span><span class="sxs-lookup"><span data-stu-id="e1264-259">Add a `ConfigureWorkflowApplication` method to the form class.</span></span>  
  
    ```vb  
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)  
  
    End Sub  
    ```  
  
    ```csharp  
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)  
    {      
    }  
    ```  
  
     <span data-ttu-id="e1264-260">Este método configura `WorkflowApplication`, agrega las extensiones deseadas y agrega los controladores para los eventos de ciclo de vida de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1264-260">This method configures the `WorkflowApplication`, adds the desired extensions, and adds handlers for the workflow lifecycle events.</span></span>  
  
2. <span data-ttu-id="e1264-261">En `ConfigureWorkflowApplication`, especifique `SqlWorkflowInstanceStore` para la `WorkflowApplication`.</span><span class="sxs-lookup"><span data-stu-id="e1264-261">In `ConfigureWorkflowApplication`, specify the `SqlWorkflowInstanceStore` for the `WorkflowApplication`.</span></span>  
  
    ```vb  
    'Configure the persistence store.  
    wfApp.InstanceStore = store  
    ```  
  
    ```csharp  
    // Configure the persistence store.  
    wfApp.InstanceStore = store;  
    ```  
  
3. <span data-ttu-id="e1264-262">A continuación, cree una instancia `StringWriter` y agréguela a la colección `Extensions` de `WorkflowApplication`.</span><span class="sxs-lookup"><span data-stu-id="e1264-262">Next, create a `StringWriter` instance and add it to the `Extensions` collection of the `WorkflowApplication`.</span></span> <span data-ttu-id="e1264-263">Cuando se agrega a las extensiones, captura todos los `WriteLine` resultados de la actividad. `StringWriter`</span><span class="sxs-lookup"><span data-stu-id="e1264-263">When a `StringWriter` is added to the extensions it captures all `WriteLine` activity output.</span></span> <span data-ttu-id="e1264-264">Cuando el flujo de trabajo se vuelve inactivo, el resultado de `WriteLine` puede extraerse desde `StringWriter` y mostrarse en el formulario.</span><span class="sxs-lookup"><span data-stu-id="e1264-264">When the workflow becomes idle, the `WriteLine` output can be extracted from the `StringWriter` and displayed on the form.</span></span>  
  
    ```vb  
    'Add a StringWriter to the extensions. This captures the output  
    'from the WriteLine activities so we can display it in the form.  
    Dim sw As New StringWriter()  
    wfApp.Extensions.Add(sw)  
    ```  
  
    ```csharp  
    // Add a StringWriter to the extensions. This captures the output  
    // from the WriteLine activities so we can display it in the form.  
    StringWriter sw = new StringWriter();  
    wfApp.Extensions.Add(sw);  
    ```  
  
4. <span data-ttu-id="e1264-265">Agregue el controlador siguiente para el evento `Completed`.</span><span class="sxs-lookup"><span data-stu-id="e1264-265">Add the following handler for the `Completed` event.</span></span> <span data-ttu-id="e1264-266">Cuando un flujo de trabajo se ha completado con éxito, el número de intentos que han sido necesarios para acertar el número se muestra en la ventana de estado.</span><span class="sxs-lookup"><span data-stu-id="e1264-266">When a workflow successfully completes, the number of turns taken to guess the number is displayed to the status window.</span></span> <span data-ttu-id="e1264-267">Si el flujo de trabajo finaliza, se muestra la información de excepción que ha provocado la finalización.</span><span class="sxs-lookup"><span data-stu-id="e1264-267">If the workflow terminates, the exception information that caused the termination is displayed.</span></span> <span data-ttu-id="e1264-268">Al final del controlador se llama al método `GameOver`, que quita el flujo de trabajo completado de la lista de flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1264-268">At the end of the handler the `GameOver` method is called, which removes the completed workflow from the workflow list.</span></span>  
  
    ```vb  
    wfApp.Completed = _  
        Sub(e As WorkflowApplicationCompletedEventArgs)  
            If e.CompletionState = ActivityInstanceState.Faulted Then  
                UpdateStatus(String.Format("Workflow Terminated. Exception: {0}" & vbCrLf & "{1}", _  
                    e.TerminationException.GetType().FullName, _  
                    e.TerminationException.Message))  
            ElseIf e.CompletionState = ActivityInstanceState.Canceled Then  
                UpdateStatus("Workflow Canceled.")  
            Else  
                Dim Turns As Integer = Convert.ToInt32(e.Outputs("Turns"))  
                UpdateStatus(String.Format("Congratulations, you guessed the number in {0} turns.", Turns))  
            End If  
            GameOver()  
        End Sub  
    ```  
  
    ```csharp  
    wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)  
    {  
        if (e.CompletionState == ActivityInstanceState.Faulted)  
        {  
            UpdateStatus(string.Format("Workflow Terminated. Exception: {0}\r\n{1}",  
                e.TerminationException.GetType().FullName,  
                e.TerminationException.Message));  
        }  
        else if (e.CompletionState == ActivityInstanceState.Canceled)  
        {  
            UpdateStatus("Workflow Canceled.");  
        }  
        else  
        {  
            int Turns = Convert.ToInt32(e.Outputs["Turns"]);  
            UpdateStatus(string.Format("Congratulations, you guessed the number in {0} turns.", Turns));  
        }  
        GameOver();  
    };  
    ```  
  
5. <span data-ttu-id="e1264-269">Agregue los siguientes controladores `Aborted` y `OnUnhandledException`.</span><span class="sxs-lookup"><span data-stu-id="e1264-269">Add the following `Aborted` and `OnUnhandledException` handlers.</span></span> <span data-ttu-id="e1264-270">No se llama al método de `GameOver` desde el controlador `Aborted` porque cuando una instancia de flujo de trabajo se anula, no se finaliza y es posible reanudar la instancia posteriormente.</span><span class="sxs-lookup"><span data-stu-id="e1264-270">The `GameOver` method is not called from the `Aborted` handler because when a workflow instance is aborted, it does not terminate, and it is possible to resume the instance at a later time.</span></span>  
  
    ```vb  
    wfApp.Aborted = _  
        Sub(e As WorkflowApplicationAbortedEventArgs)  
            UpdateStatus(String.Format("Workflow Aborted. Exception: {0}" & vbCrLf & "{1}", _  
                e.Reason.GetType().FullName, _  
                e.Reason.Message))  
        End Sub  
  
    wfApp.OnUnhandledException = _  
        Function(e As WorkflowApplicationUnhandledExceptionEventArgs)  
            UpdateStatus(String.Format("Unhandled Exception: {0}" & vbCrLf & "{1}", _  
                e.UnhandledException.GetType().FullName, _  
                e.UnhandledException.Message))  
            GameOver()  
            Return UnhandledExceptionAction.Terminate  
        End Function  
    ```  
  
    ```csharp  
    wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)  
    {  
        UpdateStatus(string.Format("Workflow Aborted. Exception: {0}\r\n{1}",  
                e.Reason.GetType().FullName,  
                e.Reason.Message));  
    };  
  
    wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)  
    {  
        UpdateStatus(string.Format("Unhandled Exception: {0}\r\n{1}",  
                e.UnhandledException.GetType().FullName,  
                e.UnhandledException.Message));  
        GameOver();  
        return UnhandledExceptionAction.Terminate;  
    };  
    ```  
  
6. <span data-ttu-id="e1264-271">Agregue el siguiente controlador `PersistableIdle`.</span><span class="sxs-lookup"><span data-stu-id="e1264-271">Add the following `PersistableIdle` handler.</span></span> <span data-ttu-id="e1264-272">Este controlador recupera la extensión `StringWriter` que se había agregado, extrae la salida de las actividades de `WriteLine` y la muestra en la ventana de estado.</span><span class="sxs-lookup"><span data-stu-id="e1264-272">This handler retrieves the `StringWriter` extension that was added, extracts the output from the `WriteLine` activities, and displays it in the status window.</span></span>  
  
    ```vb  
    wfApp.PersistableIdle = _  
        Function(e As WorkflowApplicationIdleEventArgs)  
            'Send the current WriteLine outputs to the status window.  
            Dim writers = e.GetInstanceExtensions(Of StringWriter)()  
            For Each writer In writers  
                UpdateStatus(writer.ToString())  
            Next  
            Return PersistableIdleAction.Unload  
        End Function  
    ```  
  
    ```csharp  
    wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)  
    {  
        // Send the current WriteLine outputs to the status window.  
        var writers = e.GetInstanceExtensions<StringWriter>();  
        foreach (var writer in writers)  
        {  
            UpdateStatus(writer.ToString());  
        }  
        return PersistableIdleAction.Unload;  
    };  
    ```  
  
     <span data-ttu-id="e1264-273">La enumeración <xref:System.Activities.PersistableIdleAction> tiene tres valores: <xref:System.Activities.PersistableIdleAction.None>, <xref:System.Activities.PersistableIdleAction.Persist> y <xref:System.Activities.PersistableIdleAction.Unload>.</span><span class="sxs-lookup"><span data-stu-id="e1264-273">The <xref:System.Activities.PersistableIdleAction> enumeration has three values: <xref:System.Activities.PersistableIdleAction.None>, <xref:System.Activities.PersistableIdleAction.Persist>, and <xref:System.Activities.PersistableIdleAction.Unload>.</span></span> <span data-ttu-id="e1264-274"><xref:System.Activities.PersistableIdleAction.Persist> hace que el flujo de trabajo sea persistente pero no hace que se descargue.</span><span class="sxs-lookup"><span data-stu-id="e1264-274"><xref:System.Activities.PersistableIdleAction.Persist> causes the workflow to persist but it does not cause the workflow to unload.</span></span> <span data-ttu-id="e1264-275"><xref:System.Activities.PersistableIdleAction.Unload> hace que el flujo de trabajo sea persistente y se descargue.</span><span class="sxs-lookup"><span data-stu-id="e1264-275"><xref:System.Activities.PersistableIdleAction.Unload> causes the workflow to persist and be unloaded.</span></span>  
  
     <span data-ttu-id="e1264-276">El siguiente ejemplo es el método `ConfigureWorkflowApplication` completado.</span><span class="sxs-lookup"><span data-stu-id="e1264-276">The following example is the completed `ConfigureWorkflowApplication` method.</span></span>  
  
    ```vb  
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)  
        'Configure the persistence store.  
        wfApp.InstanceStore = store  
  
        'Add a StringWriter to the extensions. This captures the output  
        'from the WriteLine activities so we can display it in the form.  
        Dim sw As New StringWriter()  
        wfApp.Extensions.Add(sw)  
  
        wfApp.Completed = _  
            Sub(e As WorkflowApplicationCompletedEventArgs)  
                If e.CompletionState = ActivityInstanceState.Faulted Then  
                    UpdateStatus(String.Format("Workflow Terminated. Exception: {0}" & vbCrLf & "{1}", _  
                        e.TerminationException.GetType().FullName, _  
                        e.TerminationException.Message))  
                ElseIf e.CompletionState = ActivityInstanceState.Canceled Then  
                    UpdateStatus("Workflow Canceled.")  
                Else  
                    Dim Turns As Integer = Convert.ToInt32(e.Outputs("Turns"))  
                    UpdateStatus(String.Format("Congratulations, you guessed the number in {0} turns.", Turns))  
                End If  
                GameOver()  
            End Sub  
  
        wfApp.Aborted = _  
            Sub(e As WorkflowApplicationAbortedEventArgs)  
                UpdateStatus(String.Format("Workflow Aborted. Exception: {0}" & vbCrLf & "{1}", _  
                    e.Reason.GetType().FullName, _  
                    e.Reason.Message))  
            End Sub  
  
        wfApp.OnUnhandledException = _  
            Function(e As WorkflowApplicationUnhandledExceptionEventArgs)  
                UpdateStatus(String.Format("Unhandled Exception: {0}" & vbCrLf & "{1}", _  
                    e.UnhandledException.GetType().FullName, _  
                    e.UnhandledException.Message))  
                GameOver()  
                Return UnhandledExceptionAction.Terminate  
            End Function  
  
        wfApp.PersistableIdle = _  
            Function(e As WorkflowApplicationIdleEventArgs)  
                'Send the current WriteLine outputs to the status window.  
                Dim writers = e.GetInstanceExtensions(Of StringWriter)()  
                For Each writer In writers  
                    UpdateStatus(writer.ToString())  
                Next  
                Return PersistableIdleAction.Unload  
            End Function  
    End Sub  
    ```  
  
    ```csharp  
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)  
    {  
        // Configure the persistence store.  
        wfApp.InstanceStore = store;  
  
        // Add a StringWriter to the extensions. This captures the output  
        // from the WriteLine activities so we can display it in the form.  
        StringWriter sw = new StringWriter();  
        wfApp.Extensions.Add(sw);  
  
        wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)  
        {  
            if (e.CompletionState == ActivityInstanceState.Faulted)  
            {  
                UpdateStatus(string.Format("Workflow Terminated. Exception: {0}\r\n{1}",  
                    e.TerminationException.GetType().FullName,  
                    e.TerminationException.Message));  
            }  
            else if (e.CompletionState == ActivityInstanceState.Canceled)  
            {  
                UpdateStatus("Workflow Canceled.");  
            }  
            else  
            {  
                int Turns = Convert.ToInt32(e.Outputs["Turns"]);  
                UpdateStatus(string.Format("Congratulations, you guessed the number in {0} turns.", Turns));  
            }  
            GameOver();  
        };  
  
        wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)  
        {  
            UpdateStatus(string.Format("Workflow Aborted. Exception: {0}\r\n{1}",  
                    e.Reason.GetType().FullName,  
                    e.Reason.Message));  
        };  
  
        wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)  
        {  
            UpdateStatus(string.Format("Unhandled Exception: {0}\r\n{1}",  
                    e.UnhandledException.GetType().FullName,  
                    e.UnhandledException.Message));  
            GameOver();  
            return UnhandledExceptionAction.Terminate;  
        };  
  
        wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)  
        {  
            // Send the current WriteLine outputs to the status window.  
            var writers = e.GetInstanceExtensions<StringWriter>();  
            foreach (var writer in writers)  
            {  
                UpdateStatus(writer.ToString());  
            }  
            return PersistableIdleAction.Unload;  
        };  
    }  
    ```  
  
### <a name="BKMK_WorkflowVersionMap"></a><span data-ttu-id="e1264-277">Para habilitar el inicio y la reanudación de varios tipos de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e1264-277">To enable starting and resuming multiple workflow types</span></span>  
 <span data-ttu-id="e1264-278">Para reanudar una instancia de flujo de trabajo, el host tiene que proporcionar la definición de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1264-278">In order to resume a workflow instance, the host has to provide the workflow definition.</span></span> <span data-ttu-id="e1264-279">En este tutorial hay tres tipos de flujo de trabajo, y los pasos siguientes del tutorial presentan varias versiones de estos tipos.</span><span class="sxs-lookup"><span data-stu-id="e1264-279">In this tutorial there are three workflow types, and subsequent tutorial steps introduce multiple versions of these types.</span></span> <span data-ttu-id="e1264-280">`WorkflowIdentity` proporciona una manera para que una aplicación de host asocie información de identificación con una instancia de flujo de trabajo persistente.</span><span class="sxs-lookup"><span data-stu-id="e1264-280">`WorkflowIdentity` provides a way for a host application to associate identifying information with a persisted workflow instance.</span></span> <span data-ttu-id="e1264-281">Los pasos de esta sección muestran cómo crear una clase de utilidad para contribuir a la asignación de la identidad de flujo de trabajo desde una instancia de flujo de trabajo persistente a la definición de flujo de trabajo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e1264-281">The steps in this section demonstrate how to create a utility class to assist with mapping the workflow identity from a persisted workflow instance to the corresponding workflow definition.</span></span> <span data-ttu-id="e1264-282">Para obtener más información `WorkflowIdentity` sobre y el control de versiones, vea [usar WorkflowIdentity y control de versiones](using-workflowidentity-and-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="e1264-282">For more information about `WorkflowIdentity` and versioning, see [Using WorkflowIdentity and Versioning](using-workflowidentity-and-versioning.md).</span></span>  
  
1. <span data-ttu-id="e1264-283">Haga clic con el botón secundario en **NumberGuessWorkflowHost** en **Explorador de soluciones** y elija **Agregar**, **clase**.</span><span class="sxs-lookup"><span data-stu-id="e1264-283">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Class**.</span></span> <span data-ttu-id="e1264-284">Escriba `WorkflowVersionMap` en el cuadro **nombre** y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e1264-284">Type `WorkflowVersionMap` into the **Name** box and click **Add**.</span></span>  
  
2. <span data-ttu-id="e1264-285">Agregue las siguientes instrucciones `using` (o `Imports`) al principio del archivo con las demás instrucciones `using` o `Imports`.</span><span class="sxs-lookup"><span data-stu-id="e1264-285">Add the following `using` or `Imports` statements at the top of the file with the other `using` or `Imports` statements.</span></span>  
  
    ```vb  
    Imports NumberGuessWorkflowActivities  
    Imports System.Activities  
    ```  
  
    ```csharp  
    using NumberGuessWorkflowActivities;  
    using System.Activities;  
    ```  
  
3. <span data-ttu-id="e1264-286">Reemplace la declaración de clase `WorkflowVersionMap` por la declaración siguiente.</span><span class="sxs-lookup"><span data-stu-id="e1264-286">Replace the `WorkflowVersionMap` class declaration with the following declaration.</span></span>  
  
    ```vb  
    Public Module WorkflowVersionMap  
        Dim map As Dictionary(Of WorkflowIdentity, Activity)  
  
        'Current version identities.  
        Public StateMachineNumberGuessIdentity As WorkflowIdentity  
        Public FlowchartNumberGuessIdentity As WorkflowIdentity  
        Public SequentialNumberGuessIdentity As WorkflowIdentity  
  
        Sub New()  
            map = New Dictionary(Of WorkflowIdentity, Activity)  
  
            'Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "StateMachineNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            FlowchartNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "FlowchartNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            SequentialNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "SequentialNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())  
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())  
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())  
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
  
        static WorkflowVersionMap()  
        {  
            map = new Dictionary<WorkflowIdentity, Activity>();  
  
            // Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "StateMachineNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            FlowchartNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "FlowchartNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            SequentialNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "SequentialNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());  
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());  
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());  
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
  
     <span data-ttu-id="e1264-287">`WorkflowVersionMap` contiene tres identidades de flujo de trabajo que se asignan a las tres definiciones de flujo de trabajo de este tutorial y se usan en las secciones siguientes al iniciar o al reanudar los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1264-287">`WorkflowVersionMap` contains three workflow identities that map to the three workflow definitions from this tutorial and is used in the following sections when workflows are started and resumed.</span></span>  
  
### <a name="BKMK_StartWorkflow"></a><span data-ttu-id="e1264-288">Para iniciar un nuevo flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e1264-288">To start a new workflow</span></span>  
  
1. <span data-ttu-id="e1264-289">Agregue un controlador `Click` para `NewGame`.</span><span class="sxs-lookup"><span data-stu-id="e1264-289">Add a `Click` handler for `NewGame`.</span></span> <span data-ttu-id="e1264-290">Para agregar el controlador, cambie a la **vista Diseño** del formulario y haga doble clic en `NewGame`.</span><span class="sxs-lookup"><span data-stu-id="e1264-290">To add the handler, switch to **Design View** for the form, and double-click `NewGame`.</span></span> <span data-ttu-id="e1264-291">Se agrega un controlador `NewGame_Click` y la vista cambia a vista de código para el formulario.</span><span class="sxs-lookup"><span data-stu-id="e1264-291">A `NewGame_Click` handler is added and the view switches to code view for the form.</span></span> <span data-ttu-id="e1264-292">Siempre que el usuario haga clic en este botón se inicia un nuevo flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1264-292">Whenever the user clicks this button a new workflow is started.</span></span>  
  
    ```vb  
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click  
  
    End Sub  
    ```  
  
    ```csharp  
    private void NewGame_Click(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
2. <span data-ttu-id="e1264-293">Agregue el código siguiente al controlador de clic.</span><span class="sxs-lookup"><span data-stu-id="e1264-293">Add the following code to the click handler.</span></span> <span data-ttu-id="e1264-294">Este código crea un diccionario de argumentos de entrada para el flujo de trabajo, por clave de nombre de argumento.</span><span class="sxs-lookup"><span data-stu-id="e1264-294">This code creates a dictionary of input arguments for the workflow, keyed by argument name.</span></span> <span data-ttu-id="e1264-295">Este diccionario tiene una entrada que contiene el intervalo del número generado aleatoriamente recuperado en el cuadro combinado del intervalo.</span><span class="sxs-lookup"><span data-stu-id="e1264-295">This dictionary has one entry that contains the range of the randomly generated number retrieved from the range combo box.</span></span>  
  
    ```vb  
    Dim inputs As New Dictionary(Of String, Object)()  
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))  
    ```  
  
    ```csharp  
    var inputs = new Dictionary<string, object>();  
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));  
    ```  
  
3. <span data-ttu-id="e1264-296">A continuación, agregue el siguiente código que inicia el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1264-296">Next, add the following code that starts the workflow.</span></span> <span data-ttu-id="e1264-297">`WorkflowIdentity` y la definición de flujo de trabajo correspondiente al tipo de flujo de trabajo seleccionado se recuperan mediante la clase del asistente `WorkflowVersionMap`.</span><span class="sxs-lookup"><span data-stu-id="e1264-297">The `WorkflowIdentity` and workflow definition corresponding to the type of workflow selected are retrieved using the `WorkflowVersionMap` helper class.</span></span> <span data-ttu-id="e1264-298">A continuación, se crea una nueva instancia de `WorkflowApplication` mediante la definición de flujo de trabajo, `WorkflowIdentity`, y el diccionario de argumentos de entrada.</span><span class="sxs-lookup"><span data-stu-id="e1264-298">Next, a new `WorkflowApplication` instance is created using the workflow definition, `WorkflowIdentity`, and dictionary of input arguments.</span></span>  
  
    ```vb  
    Dim identity As WorkflowIdentity = Nothing  
    Select Case WorkflowType.SelectedItem.ToString()  
        Case "SequentialNumberGuessWorkflow"  
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity  
  
        Case "StateMachineNumberGuessWorkflow"  
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity  
  
        Case "FlowchartNumberGuessWorkflow"  
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity  
    End Select  
  
    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)  
  
    Dim wfApp = New WorkflowApplication(wf, inputs, identity)  
    ```  
  
    ```csharp  
    WorkflowIdentity identity = null;  
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
    };  
  
    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);  
  
    WorkflowApplication wfApp = new WorkflowApplication(wf, inputs, identity);  
    ```  
  
4. <span data-ttu-id="e1264-299">A continuación, agregue el siguiente código que agrega el flujo de trabajo a la lista de flujos de trabajo y muestra la información de la versión del flujo de trabajo en el formulario.</span><span class="sxs-lookup"><span data-stu-id="e1264-299">Next, add the following code which adds the workflow to the workflow list and displays the workflow's version information on the form.</span></span>  
  
    ```vb  
    'Add the workflow to the list and display the version information.  
    WorkflowStarting = True  
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)  
    WorkflowVersion.Text = identity.ToString()  
    WorkflowStarting = False  
    ```  
  
    ```csharp  
    // Add the workflow to the list and display the version information.  
    WorkflowStarting = true;  
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);  
    WorkflowVersion.Text = identity.ToString();  
    WorkflowStarting = false;  
    ```  
  
5. <span data-ttu-id="e1264-300">Llame a `ConfigureWorkflowApplication` para configurar el almacén de instancias, las extensiones y los controladores de ciclo de vida del flujo de trabajo para esta instancia `WorkflowApplication`.</span><span class="sxs-lookup"><span data-stu-id="e1264-300">Call `ConfigureWorkflowApplication` to configure the instance store, extensions, and workflow lifecycle handlers for this `WorkflowApplication` instance.</span></span>  
  
    ```vb  
    'Configure the instance store, extensions, and   
    'workflow lifecycle handlers.  
    ConfigureWorkflowApplication(wfApp)  
    ```  
  
    ```csharp  
    // Configure the instance store, extensions, and   
    // workflow lifecycle handlers.  
    ConfigureWorkflowApplication(wfApp);  
    ```  
  
6. <span data-ttu-id="e1264-301">Por último, llame a `Run`.</span><span class="sxs-lookup"><span data-stu-id="e1264-301">Finally, call `Run`.</span></span>  
  
    ```vb  
    'Start the workflow.  
    wfApp.Run()  
    ```  
  
    ```  
    // Start the workflow.  
    wfApp.Run();  
    ```  
  
     <span data-ttu-id="e1264-302">El siguiente ejemplo es el controlador `NewGame_Click` completado.</span><span class="sxs-lookup"><span data-stu-id="e1264-302">The following example is the completed `NewGame_Click` handler.</span></span>  
  
    ```vb  
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click  
        'Start a new workflow.  
        Dim inputs As New Dictionary(Of String, Object)()  
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))  
  
        Dim identity As WorkflowIdentity = Nothing  
        Select Case WorkflowType.SelectedItem.ToString()  
            Case "SequentialNumberGuessWorkflow"  
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity  
  
            Case "StateMachineNumberGuessWorkflow"  
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity  
  
            Case "FlowchartNumberGuessWorkflow"  
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity  
        End Select  
  
        Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)  
  
        Dim wfApp = New WorkflowApplication(wf, inputs, identity)  
  
        'Add the workflow to the list and display the version information.  
        WorkflowStarting = True  
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)  
        WorkflowVersion.Text = identity.ToString()  
        WorkflowStarting = False  
  
        'Configure the instance store, extensions, and   
        'workflow lifecycle handlers.  
        ConfigureWorkflowApplication(wfApp)  
  
        'Start the workflow.  
        wfApp.Run()  
    End Sub  
    ```  
  
    ```csharp  
    private void NewGame_Click(object sender, EventArgs e)  
    {  
        var inputs = new Dictionary<string, object>();  
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));  
  
        WorkflowIdentity identity = null;  
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
        };  
  
        Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);  
  
        WorkflowApplication wfApp = new WorkflowApplication(wf, inputs, identity);  
  
        // Add the workflow to the list and display the version information.  
        WorkflowStarting = true;  
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);  
        WorkflowVersion.Text = identity.ToString();  
        WorkflowStarting = false;  
  
        // Configure the instance store, extensions, and   
        // workflow lifecycle handlers.  
        ConfigureWorkflowApplication(wfApp);  
  
        // Start the workflow.  
        wfApp.Run();  
    }  
    ```  
  
### <a name="BKMK_ResumeWorkflow"></a><span data-ttu-id="e1264-303">Para reanudar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e1264-303">To resume a workflow</span></span>  
  
1. <span data-ttu-id="e1264-304">Agregue un controlador `Click` para `EnterGuess`.</span><span class="sxs-lookup"><span data-stu-id="e1264-304">Add a `Click` handler for `EnterGuess`.</span></span> <span data-ttu-id="e1264-305">Para agregar el controlador, cambie a la **vista Diseño** del formulario y haga doble clic en `EnterGuess`.</span><span class="sxs-lookup"><span data-stu-id="e1264-305">To add the handler, switch to **Design View** for the form, and double-click `EnterGuess`.</span></span> <span data-ttu-id="e1264-306">Siempre que el usuario haga clic en este botón se reanudará un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1264-306">Whenever the user clicks this button a workflow is resumed.</span></span>  
  
    ```vb  
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click  
  
    End Sub  
    ```  
  
    ```csharp  
    private void EnterGuess_Click(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
2. <span data-ttu-id="e1264-307">Agregue el código siguiente para asegurarse de que un flujo de trabajo está seleccionado en la lista de flujos de trabajo y de que el acierto del usuario es válido.</span><span class="sxs-lookup"><span data-stu-id="e1264-307">Add the following code to ensure that a workflow is selected in the workflow list, and that the user's guess is valid.</span></span>  
  
    ```vb  
    If WorkflowInstanceId = Guid.Empty Then  
        MessageBox.Show("Please select a workflow.")  
        Return  
    End If  
  
    Dim userGuess As Integer  
    If Not Int32.TryParse(Guess.Text, userGuess) Then  
        MessageBox.Show("Please enter an integer.")  
        Guess.SelectAll()  
        Guess.Focus()  
        Return  
    End If  
    ```  
  
    ```csharp  
    if (WorkflowInstanceId == Guid.Empty)  
    {  
        MessageBox.Show("Please select a workflow.");  
        return;  
    }  
  
    int guess;  
    if (!Int32.TryParse(Guess.Text, out guess))  
    {  
        MessageBox.Show("Please enter an integer.");  
        Guess.SelectAll();  
        Guess.Focus();  
        return;  
    }  
    ```  
  
3. <span data-ttu-id="e1264-308">A continuación, recupere `WorkflowApplicationInstance` de la instancia de flujo de trabajo persistente.</span><span class="sxs-lookup"><span data-stu-id="e1264-308">Next, retrieve the `WorkflowApplicationInstance` of the persisted workflow instance.</span></span> <span data-ttu-id="e1264-309">`WorkflowApplicationInstance` representa una instancia de flujo de trabajo persistente que aún no se ha asociado a una definición de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1264-309">A `WorkflowApplicationInstance` represents a persisted workflow instance that has not yet been associated with a workflow definition.</span></span> <span data-ttu-id="e1264-310">`DefinitionIdentity` de `WorkflowApplicationInstance` contiene `WorkflowIdentity` de la instancia de flujo de trabajo persistente.</span><span class="sxs-lookup"><span data-stu-id="e1264-310">The `DefinitionIdentity` of the `WorkflowApplicationInstance` contains the `WorkflowIdentity` of the persisted workflow instance.</span></span> <span data-ttu-id="e1264-311">En este tutorial, la clase de utilidad de `WorkflowVersionMap` se usa para asignar `WorkflowIdentity` a la definición de flujo de trabajo correcta.</span><span class="sxs-lookup"><span data-stu-id="e1264-311">In this tutorial, the `WorkflowVersionMap` utility class is used to map the `WorkflowIdentity` to the correct workflow definition.</span></span> <span data-ttu-id="e1264-312">Una vez que se recupera la definición de flujo de trabajo, se crea `WorkflowApplication`, mediante la definición de flujo de trabajo correcta.</span><span class="sxs-lookup"><span data-stu-id="e1264-312">Once the workflow definition is retrieved, a `WorkflowApplication` is created, using the correct workflow definition.</span></span>  
  
    ```vb  
    Dim instance As WorkflowApplicationInstance = _  
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
    'Use the persisted WorkflowIdentity to retrieve the correct workflow  
    'definition from the dictionary.  
    Dim wf As Activity = _  
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)  
  
    'Associate the WorkflowApplication with the correct definition  
    Dim wfApp As WorkflowApplication = _  
        New WorkflowApplication(wf, instance.DefinitionIdentity)  
    ```  
  
    ```csharp  
    WorkflowApplicationInstance instance =  
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);  
  
    // Use the persisted WorkflowIdentity to retrieve the correct workflow  
    // definition from the dictionary.  
    Activity wf =  
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);  
  
    // Associate the WorkflowApplication with the correct definition  
    WorkflowApplication wfApp =  
        new WorkflowApplication(wf, instance.DefinitionIdentity);  
    ```  
  
4. <span data-ttu-id="e1264-313">Una vez que se ha creado `WorkflowApplication`, configure el almacén de instancias, los controladores de ciclo de vida del flujo de trabajo y las extensiones mediante una llamada a `ConfigureWorkflowApplication`.</span><span class="sxs-lookup"><span data-stu-id="e1264-313">Once the `WorkflowApplication` is created, configure the instance store, workflow lifecycle handlers, and extensions by calling `ConfigureWorkflowApplication`.</span></span> <span data-ttu-id="e1264-314">Deben llevarse a cabo estos pasos cada vez que se crea un nuevo objeto `WorkflowApplication` y antes de que se cargue la instancia de flujo de trabajo en `WorkflowApplication`.</span><span class="sxs-lookup"><span data-stu-id="e1264-314">These steps must be done every time a new `WorkflowApplication` is created, and they must be done before the workflow instance is loaded into the `WorkflowApplication`.</span></span> <span data-ttu-id="e1264-315">Cuando el flujo de trabajo ya está cargado, se reanuda con el intento del usuario.</span><span class="sxs-lookup"><span data-stu-id="e1264-315">After the workflow is loaded, it is resumed with the user's guess.</span></span>  
  
    ```vb  
    'Configure the extensions and lifecycle handlers.  
    'Do this before the instance is loaded. Once the instance is  
    'loaded it is too late to add extensions.  
    ConfigureWorkflowApplication(wfApp)  
  
    'Load the workflow.  
    wfApp.Load(instance)  
  
    'Resume the workflow.  
    wfApp.ResumeBookmark("EnterGuess", userGuess)  
    ```  
  
    ```csharp  
    // Configure the extensions and lifecycle handlers.  
    // Do this before the instance is loaded. Once the instance is  
    // loaded it is too late to add extensions.  
    ConfigureWorkflowApplication(wfApp);  
  
    // Load the workflow.  
    wfApp.Load(instance);  
  
    // Resume the workflow.  
    wfApp.ResumeBookmark("EnterGuess", guess);  
    ```  
  
5. <span data-ttu-id="e1264-316">Finalmente, desactive el cuadro donde se indica el número y prepare el formulario para aceptar otro intento.</span><span class="sxs-lookup"><span data-stu-id="e1264-316">Finally, clear the guess textbox and prepare the form to accept another guess.</span></span>  
  
    ```vb  
    'Clear the Guess textbox.  
    Guess.Clear()  
    Guess.Focus()  
    ```  
  
    ```csharp  
    // Clear the Guess textbox.  
    Guess.Clear();  
    Guess.Focus();  
    ```  
  
     <span data-ttu-id="e1264-317">El siguiente ejemplo es el controlador `EnterGuess_Click` completado.</span><span class="sxs-lookup"><span data-stu-id="e1264-317">The following example is the completed `EnterGuess_Click` handler.</span></span>  
  
    ```vb  
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click  
        If WorkflowInstanceId = Guid.Empty Then  
            MessageBox.Show("Please select a workflow.")  
            Return  
        End If  
  
        Dim userGuess As Integer  
        If Not Int32.TryParse(Guess.Text, userGuess) Then  
            MessageBox.Show("Please enter an integer.")  
            Guess.SelectAll()  
            Guess.Focus()  
            Return  
        End If  
  
        Dim instance As WorkflowApplicationInstance = _  
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
        'Use the persisted WorkflowIdentity to retrieve the correct workflow  
        'definition from the dictionary.  
        Dim wf As Activity = _  
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)  
  
        'Associate the WorkflowApplication with the correct definition  
        Dim wfApp As WorkflowApplication = _  
            New WorkflowApplication(wf, instance.DefinitionIdentity)  
  
        'Configure the extensions and lifecycle handlers.  
        'Do this before the instance is loaded. Once the instance is  
        'loaded it is too late to add extensions.  
        ConfigureWorkflowApplication(wfApp)  
  
        'Load the workflow.  
        wfApp.Load(instance)  
  
        'Resume the workflow.  
        wfApp.ResumeBookmark("EnterGuess", userGuess)  
  
        'Clear the Guess textbox.  
        Guess.Clear()  
        Guess.Focus()  
    End Sub  
    ```  
  
    ```csharp  
    private void EnterGuess_Click(object sender, EventArgs e)  
    {  
        if (WorkflowInstanceId == Guid.Empty)  
        {  
            MessageBox.Show("Please select a workflow.");  
            return;  
        }  
  
        int guess;  
        if (!Int32.TryParse(Guess.Text, out guess))  
        {  
            MessageBox.Show("Please enter an integer.");  
            Guess.SelectAll();  
            Guess.Focus();  
            return;  
        }  
  
        WorkflowApplicationInstance instance =  
            WorkflowApplication.GetInstance(WorkflowInstanceId, store);  
  
        // Use the persisted WorkflowIdentity to retrieve the correct workflow  
        // definition from the dictionary.  
        Activity wf =  
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);  
  
        // Associate the WorkflowApplication with the correct definition  
        WorkflowApplication wfApp =  
            new WorkflowApplication(wf, instance.DefinitionIdentity);  
  
        // Configure the extensions and lifecycle handlers.  
        // Do this before the instance is loaded. Once the instance is  
        // loaded it is too late to add extensions.  
        ConfigureWorkflowApplication(wfApp);  
  
        // Load the workflow.  
        wfApp.Load(instance);  
  
        // Resume the workflow.  
        wfApp.ResumeBookmark("EnterGuess", guess);  
  
        // Clear the Guess textbox.  
        Guess.Clear();  
        Guess.Focus();  
    }  
    ```  
  
### <a name="BKMK_TerminateWorkflow"></a><span data-ttu-id="e1264-318">Para finalizar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e1264-318">To terminate a workflow</span></span>  
  
1. <span data-ttu-id="e1264-319">Agregue un controlador `Click` para `QuitGame`.</span><span class="sxs-lookup"><span data-stu-id="e1264-319">Add a `Click` handler for `QuitGame`.</span></span> <span data-ttu-id="e1264-320">Para agregar el controlador, cambie a la **vista Diseño** del formulario y haga doble clic en `QuitGame`.</span><span class="sxs-lookup"><span data-stu-id="e1264-320">To add the handler, switch to **Design View** for the form, and double-click `QuitGame`.</span></span> <span data-ttu-id="e1264-321">Siempre que el usuario haga clic en este botón se finalizará el flujo de trabajo seleccionado actualmente.</span><span class="sxs-lookup"><span data-stu-id="e1264-321">Whenever the user clicks this button the currently selected workflow is terminated.</span></span>  
  
    ```vb  
    Private Sub QuitGame_Click(sender As Object, e As EventArgs) Handles QuitGame.Click  
  
    End Sub  
    ```  
  
    ```csharp  
    private void QuitGame_Click(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
2. <span data-ttu-id="e1264-322">Agregue el código siguiente al controlador `QuitGame_Click`.</span><span class="sxs-lookup"><span data-stu-id="e1264-322">Add the following code to the `QuitGame_Click` handler.</span></span> <span data-ttu-id="e1264-323">Este código primero comprueba que un flujo de trabajo está seleccionado en la lista de flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1264-323">This code first checks to ensure that a workflow is selected in the workflow list.</span></span> <span data-ttu-id="e1264-324">Después, carga la instancia persistente en `WorkflowApplicationInstance`, usa `DefinitionIdentity` para determinar la definición correcta de flujo de trabajo e inicializa `WorkflowApplication`.</span><span class="sxs-lookup"><span data-stu-id="e1264-324">Then it loads the persisted instance into a `WorkflowApplicationInstance`, uses the `DefinitionIdentity` to determine the correct workflow definition, and then initializes the `WorkflowApplication`.</span></span> <span data-ttu-id="e1264-325">A continuación, las extensiones y los controladores de ciclo de vida de flujo de trabajo se configuran mediante una llamada a `ConfigureWorkflowApplication`.</span><span class="sxs-lookup"><span data-stu-id="e1264-325">Next the extensions and workflow lifecycle handlers are configured with a call to `ConfigureWorkflowApplication`.</span></span> <span data-ttu-id="e1264-326">Una vez se ha configurado `WorkflowApplication`, se carga y, a continuación, `Terminate` recibe una llamada.</span><span class="sxs-lookup"><span data-stu-id="e1264-326">Once the `WorkflowApplication` is configured, it is loaded, and then `Terminate` is called.</span></span>  
  
    ```vb  
    If WorkflowInstanceId = Guid.Empty Then  
        MessageBox.Show("Please select a workflow.")  
        Return  
    End If  
  
    Dim instance As WorkflowApplicationInstance = _  
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
    'Use the persisted WorkflowIdentity to retrieve the correct workflow  
    'definition from the dictionary.  
    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)  
  
    'Associate the WorkflowApplication with the correct definition.  
    Dim wfApp As WorkflowApplication = _  
        New WorkflowApplication(wf, instance.DefinitionIdentity)  
  
    'Configure the extensions and lifecycle handlers.  
    ConfigureWorkflowApplication(wfApp)  
  
    'Load the workflow.  
    wfApp.Load(instance)  
  
    'Terminate the workflow.  
    wfApp.Terminate("User resigns.")  
    ```  
  
    ```csharp  
    if (WorkflowInstanceId == Guid.Empty)  
    {  
        MessageBox.Show("Please select a workflow.");  
        return;  
    }  
  
    WorkflowApplicationInstance instance =  
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);  
  
    // Use the persisted WorkflowIdentity to retrieve the correct workflow  
    // definition from the dictionary.  
    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);  
  
    // Associate the WorkflowApplication with the correct definition  
    WorkflowApplication wfApp =  
        new WorkflowApplication(wf, instance.DefinitionIdentity);  
  
    // Configure the extensions and lifecycle handlers  
    ConfigureWorkflowApplication(wfApp);  
  
    // Load the workflow.  
    wfApp.Load(instance);  
  
    // Terminate the workflow.  
    wfApp.Terminate("User resigns.");  
    ```  
  
### <a name="BKMK_BuildAndRun"></a> <span data-ttu-id="e1264-327">Para compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="e1264-327">To build and run the application</span></span>  
  
1. <span data-ttu-id="e1264-328">Haga doble clic en **Program.CS** (o **Module1. vb**) en **Explorador de soluciones** para mostrar el código.</span><span class="sxs-lookup"><span data-stu-id="e1264-328">Double-click **Program.cs** (or **Module1.vb**) in **Solution Explorer** to display the code.</span></span>  
  
2. <span data-ttu-id="e1264-329">Agregue las siguientes instrucciones `using` (o `Imports`) al principio del archivo con las demás instrucciones `using` (o `Imports`).</span><span class="sxs-lookup"><span data-stu-id="e1264-329">Add the following `using` (or `Imports`) statement at the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Windows.Forms  
    ```  
  
    ```csharp  
    using System.Windows.Forms;  
    ```  
  
3. <span data-ttu-id="e1264-330">Quite o comente el código de hospedaje del flujo de [trabajo existente de cómo: Ejecute un flujo](how-to-run-a-workflow.md)de trabajo y reemplácelo por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e1264-330">Remove or comment out the existing workflow hosting code from [How to: Run a Workflow](how-to-run-a-workflow.md), and replace it with the following code.</span></span>  
  
    ```vb  
    Sub Main()  
        Application.EnableVisualStyles()  
        Application.Run(New WorkflowHostForm())  
    End Sub  
    ```  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        Application.EnableVisualStyles();  
        Application.Run(new WorkflowHostForm());  
    }  
    ```  
  
4. <span data-ttu-id="e1264-331">Haga clic con el botón secundario en **NumberGuessWorkflowHost** en **Explorador de soluciones** y elija **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e1264-331">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Properties**.</span></span> <span data-ttu-id="e1264-332">En la pestaña **aplicación** , especifique **aplicación para Windows** para el **tipo de salida**.</span><span class="sxs-lookup"><span data-stu-id="e1264-332">In the **Application** tab, specify **Windows Application** for the **Output type**.</span></span> <span data-ttu-id="e1264-333">Este paso es opcional, pero si no se realiza la ventana de la consola se muestra además del formulario.</span><span class="sxs-lookup"><span data-stu-id="e1264-333">This step is optional, but if it is not followed the console window is displayed in addition to the form.</span></span>  
  
5. <span data-ttu-id="e1264-334">Presione Ctrl+Mayús+B para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e1264-334">Press Ctrl+Shift+B to build the application.</span></span>  
  
6. <span data-ttu-id="e1264-335">Asegúrese de que **NumberGuessWorkflowHost** está establecido como aplicación de inicio y presione Ctrl + F5 para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e1264-335">Ensure that **NumberGuessWorkflowHost** is set as the startup application, and press Ctrl+F5 to start the application.</span></span>  
  
7. <span data-ttu-id="e1264-336">Seleccione un intervalo para el juego de adivinación y el tipo de flujo de trabajo que se va a iniciar y haga clic en **nuevo juego**.</span><span class="sxs-lookup"><span data-stu-id="e1264-336">Select a range for the guessing game and the type of workflow to start, and click **New Game**.</span></span> <span data-ttu-id="e1264-337">Escriba una estimación en el cuadro de **estimación** y haga clic en **ir** para enviar su estimación.</span><span class="sxs-lookup"><span data-stu-id="e1264-337">Enter a guess in the **Guess** box and click **Go** to submit your guess.</span></span> <span data-ttu-id="e1264-338">Observe que el resultado de las actividades `WriteLine` se muestra en el formulario.</span><span class="sxs-lookup"><span data-stu-id="e1264-338">Note that the output from the `WriteLine` activities is displayed on the form.</span></span>  
  
8. <span data-ttu-id="e1264-339">Inicie varios flujos de trabajo con distintos tipos de flujo de trabajo e intervalos de números, escriba algunas conjeturas y cambie entre los flujos de trabajo seleccionando en la lista ID. de **instancia de flujo de trabajo** .</span><span class="sxs-lookup"><span data-stu-id="e1264-339">Start several workflows using different workflow types and number ranges, enter some guesses, and switch between the workflows by selecting from the **Workflow Instance Id** list.</span></span>  
  
     <span data-ttu-id="e1264-340">Observe que al cambiar a un nuevo flujo de trabajo, los intentos anteriores y el progreso del flujo de trabajo no aparecen en la ventana de estado.</span><span class="sxs-lookup"><span data-stu-id="e1264-340">Note that when you switch to a new workflow, the previous guesses and progress of the workflow are not displayed in the status window.</span></span> <span data-ttu-id="e1264-341">El estado no está disponible porque no se captura ni guarda en ningún lugar.</span><span class="sxs-lookup"><span data-stu-id="e1264-341">The reason the status is not available is because it is not captured and saved anywhere.</span></span> <span data-ttu-id="e1264-342">En el siguiente paso del tutorial, [cómo: Crear un participante](how-to-create-a-custom-tracking-participant.md)de seguimiento personalizado, se crea un participante de seguimiento personalizado que guarda esta información.</span><span class="sxs-lookup"><span data-stu-id="e1264-342">In the next step of the tutorial, [How to: Create a Custom Tracking Participant](how-to-create-a-custom-tracking-participant.md), you create a custom tracking participant that saves this information.</span></span>
