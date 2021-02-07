---
description: 'Más información sobre: Tutorial: manipular datos (C#)'
title: 'Tutorial: Manipular datos (C#)'
ms.date: 03/30/2017
ms.assetid: 24adfbe0-0ad6-449f-997d-8808e0770d2e
ms.openlocfilehash: 6176709a2e02d8c06ec54b70cc6e0e4c302509c3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729593"
---
# <a name="walkthrough-manipulating-data-c"></a><span data-ttu-id="f1b88-103">Tutorial: Manipular datos (C#)</span><span class="sxs-lookup"><span data-stu-id="f1b88-103">Walkthrough: Manipulating Data (C#)</span></span>

<span data-ttu-id="f1b88-104">Este tutorial proporciona un escenario completo fundamental de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para agregar, modificar y eliminar datos en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="f1b88-104">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for adding, modifying, and deleting data in a database.</span></span> <span data-ttu-id="f1b88-105">Utilizará una copia de la base de datos de ejemplo Northwind para agregar un cliente, cambiar el nombre de un cliente y eliminar un pedido.</span><span class="sxs-lookup"><span data-stu-id="f1b88-105">You will use a copy of the sample Northwind database to add a customer, change the name of a customer, and delete an order.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="f1b88-106">Este tutorial se escribió con la configuración de desarrollo de Visual C#.</span><span class="sxs-lookup"><span data-stu-id="f1b88-106">This walkthrough was written by using Visual C# Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f1b88-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f1b88-107">Prerequisites</span></span>  

 <span data-ttu-id="f1b88-108">En este tutorial se requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1b88-108">This walkthrough requires the following:</span></span>  
  
- <span data-ttu-id="f1b88-109">Este tutorial utiliza una carpeta dedicada ("c:\linqtest6") que contiene los archivos.</span><span class="sxs-lookup"><span data-stu-id="f1b88-109">This walkthrough uses a dedicated folder ("c:\linqtest6") to hold files.</span></span> <span data-ttu-id="f1b88-110">Cree esta carpeta antes de empezar el tutorial.</span><span class="sxs-lookup"><span data-stu-id="f1b88-110">Create this folder before you begin the walkthrough.</span></span>  
  
- <span data-ttu-id="f1b88-111">Base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="f1b88-111">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="f1b88-112">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del sitio web de descargas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f1b88-112">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="f1b88-113">Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="f1b88-113">For instructions, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span> <span data-ttu-id="f1b88-114">Después de haber descargado la base de datos, copie el archivo northwnd.mdf en la carpeta c:\linqtest6.</span><span class="sxs-lookup"><span data-stu-id="f1b88-114">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest6 folder.</span></span>  
  
- <span data-ttu-id="f1b88-115">Un archivo de código de C# generado a partir de la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="f1b88-115">A C# code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="f1b88-116">Puede generar este archivo mediante el Object Relational Designer o la herramienta SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="f1b88-116">You can generate this file by using either the Object Relational Designer or the SQLMetal tool.</span></span> <span data-ttu-id="f1b88-117">Este tutorial se escribió utilizando la herramienta SQLMetal con la línea de comandos siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1b88-117">This walkthrough was written by using the SQLMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="f1b88-118">**sqlmetal /code:"c:\linqtest6\northwind.cs" /language:csharp "C:\linqtest6\northwnd.mdf" /pluralize**</span><span class="sxs-lookup"><span data-stu-id="f1b88-118">**sqlmetal /code:"c:\linqtest6\northwind.cs" /language:csharp "C:\linqtest6\northwnd.mdf" /pluralize**</span></span>  
  
     <span data-ttu-id="f1b88-119">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="f1b88-119">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="f1b88-120">Información general</span><span class="sxs-lookup"><span data-stu-id="f1b88-120">Overview</span></span>  

 <span data-ttu-id="f1b88-121">Este tutorial se compone de seis tareas principales:</span><span class="sxs-lookup"><span data-stu-id="f1b88-121">This walkthrough consists of six main tasks:</span></span>  
  
- <span data-ttu-id="f1b88-122">Crear la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solución en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f1b88-122">Creating the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
- <span data-ttu-id="f1b88-123">Agregar el archivo de código de la base de datos al proyecto.</span><span class="sxs-lookup"><span data-stu-id="f1b88-123">Adding the database code file to the project.</span></span>  
  
- <span data-ttu-id="f1b88-124">Crear el nuevo objeto de cliente.</span><span class="sxs-lookup"><span data-stu-id="f1b88-124">Creating a new customer object.</span></span>  
  
- <span data-ttu-id="f1b88-125">Modificar el nombre de contacto de un cliente.</span><span class="sxs-lookup"><span data-stu-id="f1b88-125">Modifying the contact name of a customer.</span></span>  
  
- <span data-ttu-id="f1b88-126">Eliminar un pedido.</span><span class="sxs-lookup"><span data-stu-id="f1b88-126">Deleting an order.</span></span>  
  
- <span data-ttu-id="f1b88-127">Enviar estos cambios a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="f1b88-127">Submitting these changes to the Northwind database.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="f1b88-128">Crear una solución LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f1b88-128">Creating a LINQ to SQL Solution</span></span>  

 <span data-ttu-id="f1b88-129">En esta primera tarea, creará una solución de Visual Studio que contiene las referencias necesarias para compilar y ejecutar un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="f1b88-129">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="f1b88-130">Para crear una solución LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f1b88-130">To create a LINQ to SQL solution</span></span>  
  
1. <span data-ttu-id="f1b88-131">En el menú **archivo** de Visual Studio, elija **nuevo** y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="f1b88-131">On the Visual Studio **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="f1b88-132">En el panel **tipos de proyecto** del cuadro de diálogo **nuevo proyecto** , haga clic en **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="f1b88-132">In the **Project types** pane in the **New Project** dialog box, click **Visual C#**.</span></span>  
  
3. <span data-ttu-id="f1b88-133">En el panel **Plantillas**, haga clic en **Aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="f1b88-133">In the **Templates** pane, click **Console Application**.</span></span>  
  
4. <span data-ttu-id="f1b88-134">En el cuadro **nombre** , escriba **LinqDataManipulationApp**.</span><span class="sxs-lookup"><span data-stu-id="f1b88-134">In the **Name** box, type **LinqDataManipulationApp**.</span></span>  
  
5. <span data-ttu-id="f1b88-135">En el cuadro **Ubicación** , compruebe dónde desea almacenar los archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f1b88-135">In the **Location** box, verify where you want to store your project files.</span></span>  
  
6. <span data-ttu-id="f1b88-136">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f1b88-136">Click **OK**.</span></span>  
  
## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="f1b88-137">Agregar referencias y directivas LINQ</span><span class="sxs-lookup"><span data-stu-id="f1b88-137">Adding LINQ References and Directives</span></span>  

 <span data-ttu-id="f1b88-138">En este tutorial se usan ensamblados que podrían no estar instalados en el proyecto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f1b88-138">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="f1b88-139">Si System.Data.Linq no se incluye como referencia en el proyecto, agréguelo, como se explica en los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1b88-139">If System.Data.Linq is not listed as a reference in your project, add it, as explained in the following steps:</span></span>  
  
#### <a name="to-add-systemdatalinq"></a><span data-ttu-id="f1b88-140">Para agregar System.Data.Linq</span><span class="sxs-lookup"><span data-stu-id="f1b88-140">To add System.Data.Linq</span></span>  
  
1. <span data-ttu-id="f1b88-141">En **Explorador de soluciones**, haga clic con el botón secundario en **referencias** y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="f1b88-141">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2. <span data-ttu-id="f1b88-142">En el cuadro de diálogo **Agregar referencia** , haga clic en **.net**, haga clic en el ensamblado System. Data. Linq y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f1b88-142">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="f1b88-143">El ensamblado se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="f1b88-143">The assembly is added to the project.</span></span>  
  
3. <span data-ttu-id="f1b88-144">Agregue las directivas siguientes al principio de Program.cs:</span><span class="sxs-lookup"><span data-stu-id="f1b88-144">Add the following directives at the top of Program.cs:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="f1b88-145">Agregar el archivo de código de Northwind al proyecto</span><span class="sxs-lookup"><span data-stu-id="f1b88-145">Adding the Northwind Code File to the Project</span></span>  

 <span data-ttu-id="f1b88-146">En estos pasos se asume que ha utilizado la herramienta SQLMetal para generar un archivo de código a partir de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="f1b88-146">These steps assume that you have used the SQLMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="f1b88-147">Para obtener más información, vea la sección Requisitos previos, anteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="f1b88-147">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="f1b88-148">Para agregar el archivo de código de Northwind al proyecto</span><span class="sxs-lookup"><span data-stu-id="f1b88-148">To add the northwind code file to the project</span></span>  
  
1. <span data-ttu-id="f1b88-149">En el menú **Proyecto** , haga clic en **Agregar elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="f1b88-149">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2. <span data-ttu-id="f1b88-150">En el cuadro de diálogo **Agregar elemento existente** , desplácese a c:\linqtest6\northwind.CS y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f1b88-150">In the **Add Existing Item** dialog box, navigate to c:\linqtest6\northwind.cs, and then click **Add**.</span></span>  
  
     <span data-ttu-id="f1b88-151">El archivo northwind.cs se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="f1b88-151">The northwind.cs file is added to the project.</span></span>  
  
## <a name="setting-up-the-database-connection"></a><span data-ttu-id="f1b88-152">Configurar la conexión a la base de datos</span><span class="sxs-lookup"><span data-stu-id="f1b88-152">Setting Up the Database Connection</span></span>  

 <span data-ttu-id="f1b88-153">Primero, pruebe su conexión a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f1b88-153">First, test your connection to the database.</span></span> <span data-ttu-id="f1b88-154">Observe en particular que la base de datos, Northwnd, no tiene la i.</span><span class="sxs-lookup"><span data-stu-id="f1b88-154">Note especially that the database, Northwnd, has no i character.</span></span> <span data-ttu-id="f1b88-155">Si se generan errores en los pasos siguientes, revise el archivo northwind.cs para determinar cómo se escribe el nombre de la clase parcial de Northwind.</span><span class="sxs-lookup"><span data-stu-id="f1b88-155">If you generate errors in the next steps, review the northwind.cs file to determine how the Northwind partial class is spelled.</span></span>  
  
#### <a name="to-set-up-and-test-the-database-connection"></a><span data-ttu-id="f1b88-156">Para configurar y probar la conexión a la base de datos</span><span class="sxs-lookup"><span data-stu-id="f1b88-156">To set up and test the database connection</span></span>  
  
1. <span data-ttu-id="f1b88-157">Escriba o pegue el código siguiente en el método `Main`, en la clase Program:</span><span class="sxs-lookup"><span data-stu-id="f1b88-157">Type or paste the following code into the `Main` method in the Program class:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#2)]  
  
2. <span data-ttu-id="f1b88-158">Presione F5 para probar la aplicación en este punto.</span><span class="sxs-lookup"><span data-stu-id="f1b88-158">Press F5 to test the application at this point.</span></span>  
  
     <span data-ttu-id="f1b88-159">Se abre una ventana de **consola** .</span><span class="sxs-lookup"><span data-stu-id="f1b88-159">A **Console** window opens.</span></span>  
  
     <span data-ttu-id="f1b88-160">Para cerrar la aplicación, presione Entrar en la ventana de la **consola** o haga clic en **detener depuración** en el menú **depurar** de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f1b88-160">You can close the application by pressing Enter in the **Console** window, or by clicking **Stop Debugging** on the Visual Studio **Debug** menu.</span></span>  
  
## <a name="creating-a-new-entity"></a><span data-ttu-id="f1b88-161">Crear una nueva entidad</span><span class="sxs-lookup"><span data-stu-id="f1b88-161">Creating a New Entity</span></span>  

 <span data-ttu-id="f1b88-162">Crear entidades es sencillo.</span><span class="sxs-lookup"><span data-stu-id="f1b88-162">Creating a new entity is straightforward.</span></span> <span data-ttu-id="f1b88-163">Puede crear objetos (como `Customer`) mediante la palabra clave `new`.</span><span class="sxs-lookup"><span data-stu-id="f1b88-163">You can create objects (such as `Customer`) by using the `new` keyword.</span></span>  
  
 <span data-ttu-id="f1b88-164">En esta sección y las siguientes, realizará cambios solo en la memoria caché local.</span><span class="sxs-lookup"><span data-stu-id="f1b88-164">In this and the following sections, you are making changes only to the local cache.</span></span> <span data-ttu-id="f1b88-165">No se enviarán cambios a la base de datos hasta que llame a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, casi al final del tutorial.</span><span class="sxs-lookup"><span data-stu-id="f1b88-165">No changes are sent to the database until you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> toward the end of this walkthrough.</span></span>  
  
#### <a name="to-add-a-new-customer-entity-object"></a><span data-ttu-id="f1b88-166">Para agregar un nuevo objeto entidad Customer</span><span class="sxs-lookup"><span data-stu-id="f1b88-166">To add a new Customer entity object</span></span>  
  
1. <span data-ttu-id="f1b88-167">Cree un nuevo `Customer` agregando el código siguiente delante de `Console.ReadLine();` en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="f1b88-167">Create a new `Customer` by adding the following code before `Console.ReadLine();` in the `Main` method:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#3)]  
  
2. <span data-ttu-id="f1b88-168">Presione F5 para depurar la solución.</span><span class="sxs-lookup"><span data-stu-id="f1b88-168">Press F5 to debug the solution.</span></span>  
  
3. <span data-ttu-id="f1b88-169">Presione entrar en la ventana de la **consola** para detener la depuración y continuar con el tutorial.</span><span class="sxs-lookup"><span data-stu-id="f1b88-169">Press Enter in the **Console** window to stop debugging and continue the walkthrough.</span></span>  
  
## <a name="updating-an-entity"></a><span data-ttu-id="f1b88-170">Actualización de una entidad</span><span class="sxs-lookup"><span data-stu-id="f1b88-170">Updating an Entity</span></span>  

 <span data-ttu-id="f1b88-171">En los pasos siguientes, recuperará un objeto `Customer` y modificará una de sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="f1b88-171">In the following steps, you will retrieve a `Customer` object and modify one of its properties.</span></span>  
  
#### <a name="to-change-the-name-of-a-customer"></a><span data-ttu-id="f1b88-172">Para cambiar el nombre de un cliente</span><span class="sxs-lookup"><span data-stu-id="f1b88-172">To change the name of a Customer</span></span>  
  
- <span data-ttu-id="f1b88-173">Agregue el código siguiente encima de `Console.ReadLine();`:</span><span class="sxs-lookup"><span data-stu-id="f1b88-173">Add the following code above `Console.ReadLine();`:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#4)]  
  
## <a name="deleting-an-entity"></a><span data-ttu-id="f1b88-174">Eliminación de una entidad</span><span class="sxs-lookup"><span data-stu-id="f1b88-174">Deleting an Entity</span></span>  

 <span data-ttu-id="f1b88-175">Con el mismo objeto de cliente, puede eliminar el primer pedido.</span><span class="sxs-lookup"><span data-stu-id="f1b88-175">Using the same customer object, you can delete the first order.</span></span>  
  
 <span data-ttu-id="f1b88-176">El código siguiente muestra cómo romper las relaciones entre las filas y cómo eliminar una fila de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f1b88-176">The following code demonstrates how to sever relationships between rows, and how to delete a row from the database.</span></span> <span data-ttu-id="f1b88-177">Agregue el código siguiente delante de `Console.ReadLine` para ver cómo se pueden eliminar los objetos:</span><span class="sxs-lookup"><span data-stu-id="f1b88-177">Add the following code before `Console.ReadLine` to see how objects can be deleted:</span></span>  
  
#### <a name="to-delete-a-row"></a><span data-ttu-id="f1b88-178">Para eliminar una fila</span><span class="sxs-lookup"><span data-stu-id="f1b88-178">To delete a row</span></span>  
  
- <span data-ttu-id="f1b88-179">Agregue el código siguiente justo encima de `Console.ReadLine();`:</span><span class="sxs-lookup"><span data-stu-id="f1b88-179">Add the following code just above `Console.ReadLine();`:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#5)]  
  
## <a name="submitting-changes-to-the-database"></a><span data-ttu-id="f1b88-180">Enviar los cambios a la base de datos</span><span class="sxs-lookup"><span data-stu-id="f1b88-180">Submitting Changes to the Database</span></span>  

 <span data-ttu-id="f1b88-181">El último paso necesario para crear, actualizar y eliminar objetos es realmente enviar los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f1b88-181">The final step required for creating, updating, and deleting objects, is to actually submit the changes to the database.</span></span> <span data-ttu-id="f1b88-182">Sin este paso, los cambios se habrán realizado localmente y no aparecerán en los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="f1b88-182">Without this step, your changes are only local and will not appear in query results.</span></span>  
  
#### <a name="to-submit-changes-to-the-database"></a><span data-ttu-id="f1b88-183">Para enviar los cambios a la base de datos</span><span class="sxs-lookup"><span data-stu-id="f1b88-183">To submit changes to the database</span></span>  
  
1. <span data-ttu-id="f1b88-184">Inserte el código siguiente justo encima de `Console.ReadLine`:</span><span class="sxs-lookup"><span data-stu-id="f1b88-184">Insert the following code just above `Console.ReadLine`:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#6)]  
  
2. <span data-ttu-id="f1b88-185">Inserte el código siguiente (después de `SubmitChanges`) para ver el antes y el después de enviar los cambios:</span><span class="sxs-lookup"><span data-stu-id="f1b88-185">Insert the following code (after `SubmitChanges`) to show the before and after effects of submitting the changes:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#7)]  
  
3. <span data-ttu-id="f1b88-186">Presione F5 para depurar la solución.</span><span class="sxs-lookup"><span data-stu-id="f1b88-186">Press F5 to debug the solution.</span></span>  
  
4. <span data-ttu-id="f1b88-187">Presione entrar en la ventana de la **consola** para cerrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f1b88-187">Press Enter in the **Console** window to close the application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1b88-188">Después de haber agregado el nuevo cliente al enviar los cambios, no puede ejecutar de nuevo esta solución tal como está.</span><span class="sxs-lookup"><span data-stu-id="f1b88-188">After you have added the new customer by submitting the changes, you cannot execute this solution again as is.</span></span> <span data-ttu-id="f1b88-189">Para ejecutar de nuevo la solución, cambie el nombre del cliente y el identificador de cliente que se debe agregar.</span><span class="sxs-lookup"><span data-stu-id="f1b88-189">To execute the solution again, change the name of the customer and customer ID to be added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1b88-190">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1b88-190">See also</span></span>

- [<span data-ttu-id="f1b88-191">Aprender con tutoriales</span><span class="sxs-lookup"><span data-stu-id="f1b88-191">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
