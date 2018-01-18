---
title: 'Tutorial: Manipular datos (C#)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24adfbe0-0ad6-449f-997d-8808e0770d2e
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 60724967cccd1209aeec1bf53b4e6d4fa5051996
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="walkthrough-manipulating-data-c"></a><span data-ttu-id="7e479-102">Tutorial: Manipular datos (C#)</span><span class="sxs-lookup"><span data-stu-id="7e479-102">Walkthrough: Manipulating Data (C#)</span></span>
<span data-ttu-id="7e479-103">Este tutorial proporciona un escenario completo fundamental de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para agregar, modificar y eliminar datos en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="7e479-103">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for adding, modifying, and deleting data in a database.</span></span> <span data-ttu-id="7e479-104">Utilizará una copia de la base de datos de ejemplo Northwind para agregar un cliente, cambiar el nombre de un cliente y eliminar un pedido.</span><span class="sxs-lookup"><span data-stu-id="7e479-104">You will use a copy of the sample Northwind database to add a customer, change the name of a customer, and delete an order.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="7e479-105">Este tutorial se escribió con la configuración de desarrollo de Visual C#.</span><span class="sxs-lookup"><span data-stu-id="7e479-105">This walkthrough was written by using Visual C# Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7e479-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7e479-106">Prerequisites</span></span>  
 <span data-ttu-id="7e479-107">En este tutorial se requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7e479-107">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="7e479-108">Este tutorial utiliza una carpeta dedicada ("c:\linqtest6") que contiene los archivos.</span><span class="sxs-lookup"><span data-stu-id="7e479-108">This walkthrough uses a dedicated folder ("c:\linqtest6") to hold files.</span></span> <span data-ttu-id="7e479-109">Cree esta carpeta antes de empezar el tutorial.</span><span class="sxs-lookup"><span data-stu-id="7e479-109">Create this folder before you begin the walkthrough.</span></span>  
  
-   <span data-ttu-id="7e479-110">Base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="7e479-110">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="7e479-111">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del sitio web de descargas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7e479-111">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="7e479-112">Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="7e479-112">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="7e479-113">Después de haber descargado la base de datos, copie el archivo northwnd.mdf en la carpeta c:\linqtest6.</span><span class="sxs-lookup"><span data-stu-id="7e479-113">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest6 folder.</span></span>  
  
-   <span data-ttu-id="7e479-114">Un archivo de código de C# generado a partir de la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="7e479-114">A C# code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="7e479-115">Puede generar este archivo mediante el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] o la herramienta SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="7e479-115">You can generate this file by using either the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] or the SQLMetal tool.</span></span> <span data-ttu-id="7e479-116">Este tutorial se escribió utilizando la herramienta SQLMetal con la línea de comandos siguiente:</span><span class="sxs-lookup"><span data-stu-id="7e479-116">This walkthrough was written by using the SQLMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="7e479-117">**sqlmetal /code:"c:\linqtest6\northwind.cs" /language:csharp "C:\linqtest6\northwnd.mdf" /pluralize**</span><span class="sxs-lookup"><span data-stu-id="7e479-117">**sqlmetal /code:"c:\linqtest6\northwind.cs" /language:csharp "C:\linqtest6\northwnd.mdf" /pluralize**</span></span>  
  
     <span data-ttu-id="7e479-118">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="7e479-118">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="7e479-119">Información general</span><span class="sxs-lookup"><span data-stu-id="7e479-119">Overview</span></span>  
 <span data-ttu-id="7e479-120">Este tutorial se compone de seis tareas principales:</span><span class="sxs-lookup"><span data-stu-id="7e479-120">This walkthrough consists of six main tasks:</span></span>  
  
-   <span data-ttu-id="7e479-121">Crear la solución [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] en [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e479-121">Creating the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].</span></span>  
  
-   <span data-ttu-id="7e479-122">Agregar el archivo de código de la base de datos al proyecto.</span><span class="sxs-lookup"><span data-stu-id="7e479-122">Adding the database code file to the project.</span></span>  
  
-   <span data-ttu-id="7e479-123">Crear el nuevo objeto de cliente.</span><span class="sxs-lookup"><span data-stu-id="7e479-123">Creating a new customer object.</span></span>  
  
-   <span data-ttu-id="7e479-124">Modificar el nombre de contacto de un cliente.</span><span class="sxs-lookup"><span data-stu-id="7e479-124">Modifying the contact name of a customer.</span></span>  
  
-   <span data-ttu-id="7e479-125">Eliminar un pedido.</span><span class="sxs-lookup"><span data-stu-id="7e479-125">Deleting an order.</span></span>  
  
-   <span data-ttu-id="7e479-126">Enviar estos cambios a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="7e479-126">Submitting these changes to the Northwind database.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="7e479-127">Crear una solución LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7e479-127">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="7e479-128">En esta primera tarea, va a crear una solución de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] que contiene las referencias necesarias para compilar y ejecutar un proyecto de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e479-128">In this first task, you create a [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="7e479-129">Para crear una solución LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7e479-129">To create a LINQ to SQL solution</span></span>  
  
1.  <span data-ttu-id="7e479-130">En el [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="7e479-130">On the [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="7e479-131">En el **tipos de proyecto** panel en el **nuevo proyecto** cuadro de diálogo, haga clic en **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="7e479-131">In the **Project types** pane in the **New Project** dialog box, click **Visual C#**.</span></span>  
  
3.  <span data-ttu-id="7e479-132">En el panel **Plantillas**, haga clic en **Aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="7e479-132">In the **Templates** pane, click **Console Application**.</span></span>  
  
4.  <span data-ttu-id="7e479-133">En el **nombre** , escriba **LinqDataManipulationApp**.</span><span class="sxs-lookup"><span data-stu-id="7e479-133">In the **Name** box, type **LinqDataManipulationApp**.</span></span>  
  
5.  <span data-ttu-id="7e479-134">En el **ubicación** cuadro, compruebe dónde desea almacenar los archivos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="7e479-134">In the **Location** box, verify where you want to store your project files.</span></span>  
  
6.  <span data-ttu-id="7e479-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7e479-135">Click **OK**.</span></span>  
  
## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="7e479-136">Agregar referencias y directivas LINQ</span><span class="sxs-lookup"><span data-stu-id="7e479-136">Adding LINQ References and Directives</span></span>  
 <span data-ttu-id="7e479-137">En este tutorial se usan ensamblados que podrían no estar instalados en el proyecto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7e479-137">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="7e479-138">Si System.Data.Linq no se incluye como referencia en el proyecto, agréguelo, como se explica en los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="7e479-138">If System.Data.Linq is not listed as a reference in your project, add it, as explained in the following steps:</span></span>  
  
#### <a name="to-add-systemdatalinq"></a><span data-ttu-id="7e479-139">Para agregar System.Data.Linq</span><span class="sxs-lookup"><span data-stu-id="7e479-139">To add System.Data.Linq</span></span>  
  
1.  <span data-ttu-id="7e479-140">En **el Explorador de soluciones**, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="7e479-140">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="7e479-141">En el **Agregar referencia** cuadro de diálogo, haga clic en **.NET**, haga clic en el ensamblado System.Data.Linq y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7e479-141">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="7e479-142">El ensamblado se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="7e479-142">The assembly is added to the project.</span></span>  
  
3.  <span data-ttu-id="7e479-143">Agregue las directivas siguientes al principio de Program.cs:</span><span class="sxs-lookup"><span data-stu-id="7e479-143">Add the following directives at the top of Program.cs:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="7e479-144">Agregar el archivo de código de Northwind al proyecto</span><span class="sxs-lookup"><span data-stu-id="7e479-144">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="7e479-145">En estos pasos se asume que ha utilizado la herramienta SQLMetal para generar un archivo de código a partir de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="7e479-145">These steps assume that you have used the SQLMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="7e479-146">Para obtener más información, vea la sección Requisitos previos, anteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="7e479-146">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="7e479-147">Para agregar el archivo de código de Northwind al proyecto</span><span class="sxs-lookup"><span data-stu-id="7e479-147">To add the northwind code file to the project</span></span>  
  
1.  <span data-ttu-id="7e479-148">En el **proyecto** menú, haga clic en **Agregar elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="7e479-148">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2.  <span data-ttu-id="7e479-149">En el **Agregar elemento existente** cuadro de diálogo, vaya a c:\linqtest6\northwind.cs y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="7e479-149">In the **Add Existing Item** dialog box, navigate to c:\linqtest6\northwind.cs, and then click **Add**.</span></span>  
  
     <span data-ttu-id="7e479-150">El archivo northwind.cs se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="7e479-150">The northwind.cs file is added to the project.</span></span>  
  
## <a name="setting-up-the-database-connection"></a><span data-ttu-id="7e479-151">Configurar la conexión a la base de datos</span><span class="sxs-lookup"><span data-stu-id="7e479-151">Setting Up the Database Connection</span></span>  
 <span data-ttu-id="7e479-152">Primero, pruebe su conexión a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7e479-152">First, test your connection to the database.</span></span> <span data-ttu-id="7e479-153">Observe en particular que la base de datos, Northwnd, no tiene la i.</span><span class="sxs-lookup"><span data-stu-id="7e479-153">Note especially that the database, Northwnd, has no i character.</span></span> <span data-ttu-id="7e479-154">Si se generan errores en los pasos siguientes, revise el archivo northwind.cs para determinar cómo se escribe el nombre de la clase parcial de Northwind.</span><span class="sxs-lookup"><span data-stu-id="7e479-154">If you generate errors in the next steps, review the northwind.cs file to determine how the Northwind partial class is spelled.</span></span>  
  
#### <a name="to-set-up-and-test-the-database-connection"></a><span data-ttu-id="7e479-155">Para configurar y probar la conexión a la base de datos</span><span class="sxs-lookup"><span data-stu-id="7e479-155">To set up and test the database connection</span></span>  
  
1.  <span data-ttu-id="7e479-156">Escriba o pegue el código siguiente en el método `Main`, en la clase Program:</span><span class="sxs-lookup"><span data-stu-id="7e479-156">Type or paste the following code into the `Main` method in the Program class:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#2)]  
  
2.  <span data-ttu-id="7e479-157">Presione F5 para probar la aplicación en este punto.</span><span class="sxs-lookup"><span data-stu-id="7e479-157">Press F5 to test the application at this point.</span></span>  
  
     <span data-ttu-id="7e479-158">A **consola** abre la ventana.</span><span class="sxs-lookup"><span data-stu-id="7e479-158">A **Console** window opens.</span></span>  
  
     <span data-ttu-id="7e479-159">Puede cerrar la aplicación, presione ENTRAR en el **consola** ventana, o haga clic en **Detener depuración** en el [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **depurar** menú.</span><span class="sxs-lookup"><span data-stu-id="7e479-159">You can close the application by pressing Enter in the **Console** window, or by clicking **Stop Debugging** on the [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **Debug** menu.</span></span>  
  
## <a name="creating-a-new-entity"></a><span data-ttu-id="7e479-160">Crear una nueva entidad</span><span class="sxs-lookup"><span data-stu-id="7e479-160">Creating a New Entity</span></span>  
 <span data-ttu-id="7e479-161">Crear entidades es sencillo.</span><span class="sxs-lookup"><span data-stu-id="7e479-161">Creating a new entity is straightforward.</span></span> <span data-ttu-id="7e479-162">Puede crear objetos (como `Customer`) mediante la palabra clave `new`.</span><span class="sxs-lookup"><span data-stu-id="7e479-162">You can create objects (such as `Customer`) by using the `new` keyword.</span></span>  
  
 <span data-ttu-id="7e479-163">En esta sección y las siguientes, realizará cambios solo en la memoria caché local.</span><span class="sxs-lookup"><span data-stu-id="7e479-163">In this and the following sections, you are making changes only to the local cache.</span></span> <span data-ttu-id="7e479-164">No se enviarán cambios a la base de datos hasta que llame a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, casi al final del tutorial.</span><span class="sxs-lookup"><span data-stu-id="7e479-164">No changes are sent to the database until you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> toward the end of this walkthrough.</span></span>  
  
#### <a name="to-add-a-new-customer-entity-object"></a><span data-ttu-id="7e479-165">Para agregar un nuevo objeto entidad Customer</span><span class="sxs-lookup"><span data-stu-id="7e479-165">To add a new Customer entity object</span></span>  
  
1.  <span data-ttu-id="7e479-166">Cree un nuevo `Customer` agregando el código siguiente delante de `Console.ReadLine();` en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="7e479-166">Create a new `Customer` by adding the following code before `Console.ReadLine();` in the `Main` method:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#3)]  
  
2.  <span data-ttu-id="7e479-167">Presione F5 para depurar la solución.</span><span class="sxs-lookup"><span data-stu-id="7e479-167">Press F5 to debug the solution.</span></span>  
  
3.  <span data-ttu-id="7e479-168">Presione ENTRAR en el **consola** ventana para detener la depuración y continuar con el tutorial.</span><span class="sxs-lookup"><span data-stu-id="7e479-168">Press Enter in the **Console** window to stop debugging and continue the walkthrough.</span></span>  
  
## <a name="updating-an-entity"></a><span data-ttu-id="7e479-169">Actualizar una entidad</span><span class="sxs-lookup"><span data-stu-id="7e479-169">Updating an Entity</span></span>  
 <span data-ttu-id="7e479-170">En los pasos siguientes, recuperará un objeto `Customer` y modificará una de sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="7e479-170">In the following steps, you will retrieve a `Customer` object and modify one of its properties.</span></span>  
  
#### <a name="to-change-the-name-of-a-customer"></a><span data-ttu-id="7e479-171">Para cambiar el nombre de un cliente</span><span class="sxs-lookup"><span data-stu-id="7e479-171">To change the name of a Customer</span></span>  
  
-   <span data-ttu-id="7e479-172">Agregue el código siguiente encima de `Console.ReadLine();`:</span><span class="sxs-lookup"><span data-stu-id="7e479-172">Add the following code above `Console.ReadLine();`:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#4)]  
  
## <a name="deleting-an-entity"></a><span data-ttu-id="7e479-173">Eliminar una entidad</span><span class="sxs-lookup"><span data-stu-id="7e479-173">Deleting an Entity</span></span>  
 <span data-ttu-id="7e479-174">Con el mismo objeto de cliente, puede eliminar el primer pedido.</span><span class="sxs-lookup"><span data-stu-id="7e479-174">Using the same customer object, you can delete the first order.</span></span>  
  
 <span data-ttu-id="7e479-175">El código siguiente muestra cómo romper las relaciones entre las filas y cómo eliminar una fila de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7e479-175">The following code demonstrates how to sever relationships between rows, and how to delete a row from the database.</span></span> <span data-ttu-id="7e479-176">Agregue el código siguiente delante de `Console.ReadLine` para ver cómo se pueden eliminar los objetos:</span><span class="sxs-lookup"><span data-stu-id="7e479-176">Add the following code before `Console.ReadLine` to see how objects can be deleted:</span></span>  
  
#### <a name="to-delete-a-row"></a><span data-ttu-id="7e479-177">Para eliminar una fila</span><span class="sxs-lookup"><span data-stu-id="7e479-177">To delete a row</span></span>  
  
-   <span data-ttu-id="7e479-178">Agregue el código siguiente justo encima de `Console.ReadLine();`:</span><span class="sxs-lookup"><span data-stu-id="7e479-178">Add the following code just above `Console.ReadLine();`:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#5)]  
  
## <a name="submitting-changes-to-the-database"></a><span data-ttu-id="7e479-179">Enviar los cambios a la base de datos</span><span class="sxs-lookup"><span data-stu-id="7e479-179">Submitting Changes to the Database</span></span>  
 <span data-ttu-id="7e479-180">El último paso necesario para crear, actualizar y eliminar objetos es realmente enviar los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7e479-180">The final step required for creating, updating, and deleting objects, is to actually submit the changes to the database.</span></span> <span data-ttu-id="7e479-181">Sin este paso, los cambios se habrán realizado localmente y no aparecerán en los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="7e479-181">Without this step, your changes are only local and will not appear in query results.</span></span>  
  
#### <a name="to-submit-changes-to-the-database"></a><span data-ttu-id="7e479-182">Para enviar los cambios a la base de datos</span><span class="sxs-lookup"><span data-stu-id="7e479-182">To submit changes to the database</span></span>  
  
1.  <span data-ttu-id="7e479-183">Inserte el código siguiente justo encima de `Console.ReadLine`:</span><span class="sxs-lookup"><span data-stu-id="7e479-183">Insert the following code just above `Console.ReadLine`:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#6)]  
  
2.  <span data-ttu-id="7e479-184">Inserte el código siguiente (después de `SubmitChanges`) para ver el antes y el después de enviar los cambios:</span><span class="sxs-lookup"><span data-stu-id="7e479-184">Insert the following code (after `SubmitChanges`) to show the before and after effects of submitting the changes:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#7)]  
  
3.  <span data-ttu-id="7e479-185">Presione F5 para depurar la solución.</span><span class="sxs-lookup"><span data-stu-id="7e479-185">Press F5 to debug the solution.</span></span>  
  
4.  <span data-ttu-id="7e479-186">Presione ENTRAR en el **consola** ventana para cerrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7e479-186">Press Enter in the **Console** window to close the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e479-187">Después de haber agregado el nuevo cliente al enviar los cambios, no puede ejecutar de nuevo esta solución tal como está.</span><span class="sxs-lookup"><span data-stu-id="7e479-187">After you have added the new customer by submitting the changes, you cannot execute this solution again as is.</span></span> <span data-ttu-id="7e479-188">Para ejecutar de nuevo la solución, cambie el nombre del cliente y el identificador de cliente que se debe agregar.</span><span class="sxs-lookup"><span data-stu-id="7e479-188">To execute the solution again, change the name of the customer and customer ID to be added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e479-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e479-189">See Also</span></span>  
 [<span data-ttu-id="7e479-190">Aprendizaje con tutoriales</span><span class="sxs-lookup"><span data-stu-id="7e479-190">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
