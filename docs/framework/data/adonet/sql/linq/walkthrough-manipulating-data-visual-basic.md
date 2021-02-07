---
description: 'Más información acerca de: Tutorial: manipular datos (Visual Basic)'
title: 'Tutorial: Manipular datos (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 1f6a54f6-ec33-452a-a37d-48122207bf14
ms.openlocfilehash: 22bef61c294a92984446402063bf14b06f5b2b2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729528"
---
# <a name="walkthrough-manipulating-data-visual-basic"></a><span data-ttu-id="5403b-103">Tutorial: Manipular datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5403b-103">Walkthrough: Manipulating Data (Visual Basic)</span></span>

<span data-ttu-id="5403b-104">Este tutorial proporciona un escenario completo fundamental de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para agregar, modificar y eliminar datos en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="5403b-104">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for adding, modifying, and deleting data in a database.</span></span> <span data-ttu-id="5403b-105">Utilizará una copia de la base de datos de ejemplo Northwind para agregar un cliente, cambiar el nombre de un cliente y eliminar un pedido.</span><span class="sxs-lookup"><span data-stu-id="5403b-105">You will use a copy of the sample Northwind database to add a customer, change the name of a customer, and delete an order.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="5403b-106">Este tutorial se escribió con la configuración de desarrollo de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5403b-106">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5403b-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5403b-107">Prerequisites</span></span>  

 <span data-ttu-id="5403b-108">En este tutorial se requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5403b-108">This walkthrough requires the following:</span></span>  
  
- <span data-ttu-id="5403b-109">Este tutorial utiliza una carpeta dedicada ("c:\linqtest2") que contiene los archivos.</span><span class="sxs-lookup"><span data-stu-id="5403b-109">This walkthrough uses a dedicated folder ("c:\linqtest2") to hold files.</span></span> <span data-ttu-id="5403b-110">Cree esta carpeta antes de empezar el tutorial.</span><span class="sxs-lookup"><span data-stu-id="5403b-110">Create this folder before you begin the walkthrough.</span></span>  
  
- <span data-ttu-id="5403b-111">Base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="5403b-111">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="5403b-112">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del sitio web de descargas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5403b-112">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="5403b-113">Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="5403b-113">For instructions, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span> <span data-ttu-id="5403b-114">Después de haber descargado la base de datos, copie el archivo northwnd.mdf en la carpeta c:\linqtest2.</span><span class="sxs-lookup"><span data-stu-id="5403b-114">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest2 folder.</span></span>  
  
- <span data-ttu-id="5403b-115">Archivo de código de Visual Basic generado a partir de la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="5403b-115">A Visual Basic code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="5403b-116">Puede generar este archivo mediante el Object Relational Designer o la herramienta SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="5403b-116">You can generate this file by using either the Object Relational Designer or the SQLMetal tool.</span></span> <span data-ttu-id="5403b-117">Este tutorial se escribió utilizando la herramienta SQLMetal con la línea de comandos siguiente:</span><span class="sxs-lookup"><span data-stu-id="5403b-117">This walkthrough was written by using the SQLMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="5403b-118">**sqlmetal /code:"c:\linqtest2\northwind.vb" /language:vb "C:\linqtest2\northwnd.mdf" /pluralize**</span><span class="sxs-lookup"><span data-stu-id="5403b-118">**sqlmetal /code:"c:\linqtest2\northwind.vb" /language:vb "C:\linqtest2\northwnd.mdf" /pluralize**</span></span>  
  
     <span data-ttu-id="5403b-119">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="5403b-119">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="5403b-120">Información general</span><span class="sxs-lookup"><span data-stu-id="5403b-120">Overview</span></span>  

 <span data-ttu-id="5403b-121">Este tutorial se compone de seis tareas principales:</span><span class="sxs-lookup"><span data-stu-id="5403b-121">This walkthrough consists of six main tasks:</span></span>  
  
- <span data-ttu-id="5403b-122">Crear la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solución en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5403b-122">Creating the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
- <span data-ttu-id="5403b-123">Agregar el archivo de código de la base de datos al proyecto.</span><span class="sxs-lookup"><span data-stu-id="5403b-123">Adding the database code file to the project.</span></span>  
  
- <span data-ttu-id="5403b-124">Crear el nuevo objeto de cliente.</span><span class="sxs-lookup"><span data-stu-id="5403b-124">Creating a new customer object.</span></span>  
  
- <span data-ttu-id="5403b-125">Modificar el nombre de contacto de un cliente.</span><span class="sxs-lookup"><span data-stu-id="5403b-125">Modifying the contact name of a customer.</span></span>  
  
- <span data-ttu-id="5403b-126">Eliminar un pedido.</span><span class="sxs-lookup"><span data-stu-id="5403b-126">Deleting an order.</span></span>  
  
- <span data-ttu-id="5403b-127">Enviar estos cambios a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="5403b-127">Submitting these changes to the Northwind database.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="5403b-128">Crear una solución LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5403b-128">Creating a LINQ to SQL Solution</span></span>  

 <span data-ttu-id="5403b-129">En esta primera tarea, creará una solución de Visual Studio que contiene las referencias necesarias para compilar y ejecutar un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="5403b-129">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="5403b-130">Para crear una solución LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5403b-130">To create a LINQ to SQL solution</span></span>  
  
1. <span data-ttu-id="5403b-131">En el menú **Archivo** de Visual Studio, haga clic en **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="5403b-131">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2. <span data-ttu-id="5403b-132">En el panel **tipos de proyecto** del cuadro de diálogo **nuevo proyecto** , haga clic en **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="5403b-132">In the **Project types** pane in the **New Project** dialog box, click **Visual Basic**.</span></span>  
  
3. <span data-ttu-id="5403b-133">En el panel **Plantillas**, haga clic en **Aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="5403b-133">In the **Templates** pane, click **Console Application**.</span></span>  
  
4. <span data-ttu-id="5403b-134">En el cuadro **nombre** , escriba **LinqDataManipulationApp**.</span><span class="sxs-lookup"><span data-stu-id="5403b-134">In the **Name** box, type **LinqDataManipulationApp**.</span></span>  
  
5. <span data-ttu-id="5403b-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5403b-135">Click **OK**.</span></span>  
  
## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="5403b-136">Agregar referencias y directivas LINQ</span><span class="sxs-lookup"><span data-stu-id="5403b-136">Adding LINQ References and Directives</span></span>  

 <span data-ttu-id="5403b-137">En este tutorial se usan ensamblados que podrían no estar instalados en el proyecto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5403b-137">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="5403b-138">Si `System.Data.Linq` no aparece como referencia en el proyecto (haga clic en **Mostrar todos los archivos** en **Explorador de soluciones** y expanda el nodo **referencias** ), agréguelo, como se explica en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="5403b-138">If `System.Data.Linq` is not listed as a reference in your project (click **Show All Files** in **Solution Explorer** and expand the **References** node), add it, as explained in the following steps.</span></span>  
  
#### <a name="to-add-systemdatalinq"></a><span data-ttu-id="5403b-139">Para agregar System.Data.Linq</span><span class="sxs-lookup"><span data-stu-id="5403b-139">To add System.Data.Linq</span></span>  
  
1. <span data-ttu-id="5403b-140">En **Explorador de soluciones**, haga clic con el botón secundario en **referencias** y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="5403b-140">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2. <span data-ttu-id="5403b-141">En el cuadro de diálogo **Agregar referencia** , haga clic en **.net**, haga clic en el ensamblado System. Data. Linq y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5403b-141">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="5403b-142">El ensamblado se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="5403b-142">The assembly is added to the project.</span></span>  
  
3. <span data-ttu-id="5403b-143">En el editor de código, agregue las siguientes directivas sobre **Module1**:</span><span class="sxs-lookup"><span data-stu-id="5403b-143">In the code editor, add the following directives above **Module1**:</span></span>  
  
     [!code-vb[DLinqWalk3VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="5403b-144">Agregar el archivo de código de Northwind al proyecto</span><span class="sxs-lookup"><span data-stu-id="5403b-144">Adding the Northwind Code File to the Project</span></span>  

 <span data-ttu-id="5403b-145">En estos pasos se asume que ha utilizado la herramienta SQLMetal para generar un archivo de código a partir de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="5403b-145">These steps assume that you have used the SQLMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="5403b-146">Para obtener más información, vea la sección Requisitos previos, anteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="5403b-146">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="5403b-147">Para agregar el archivo de código de Northwind al proyecto</span><span class="sxs-lookup"><span data-stu-id="5403b-147">To add the northwind code file to the project</span></span>  
  
1. <span data-ttu-id="5403b-148">En el menú **Proyecto** , haga clic en **Agregar elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="5403b-148">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2. <span data-ttu-id="5403b-149">En el cuadro de diálogo **Agregar elemento existente** , desplácese a c:\linqtest2\northwind.VB y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5403b-149">In the **Add Existing Item** dialog box, navigate to c:\linqtest2\northwind.vb, and then click **Add**.</span></span>  
  
     <span data-ttu-id="5403b-150">El archivo northwind.vb se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="5403b-150">The northwind.vb file is added to the project.</span></span>  
  
## <a name="setting-up-the-database-connection"></a><span data-ttu-id="5403b-151">Configurar la conexión a la base de datos</span><span class="sxs-lookup"><span data-stu-id="5403b-151">Setting Up the Database Connection</span></span>  

 <span data-ttu-id="5403b-152">Primero, pruebe su conexión a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5403b-152">First, test your connection to the database.</span></span> <span data-ttu-id="5403b-153">Observe en particular que el nombre de la base de datos, Northwnd, no tiene la i.</span><span class="sxs-lookup"><span data-stu-id="5403b-153">Note especially that the name of the database, Northwnd, has no i character.</span></span> <span data-ttu-id="5403b-154">Si se generan errores en los pasos siguientes, revise el archivo northwind.vb para determinar cómo se escribe el nombre de la clase parcial de Northwind.</span><span class="sxs-lookup"><span data-stu-id="5403b-154">If you generate errors in the next steps, review the northwind.vb file to determine how the Northwind partial class is spelled.</span></span>  
  
#### <a name="to-set-up-and-test-the-database-connection"></a><span data-ttu-id="5403b-155">Para configurar y probar la conexión a la base de datos</span><span class="sxs-lookup"><span data-stu-id="5403b-155">To set up and test the database connection</span></span>  
  
1. <span data-ttu-id="5403b-156">Escriba o pegue el código siguiente en la clase `Sub Main`:</span><span class="sxs-lookup"><span data-stu-id="5403b-156">Type or paste the following code into `Sub Main`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#2)]  
  
2. <span data-ttu-id="5403b-157">Presione F5 para probar la aplicación en este punto.</span><span class="sxs-lookup"><span data-stu-id="5403b-157">Press F5 to test the application at this point.</span></span>  
  
     <span data-ttu-id="5403b-158">Se abre una ventana de **consola** .</span><span class="sxs-lookup"><span data-stu-id="5403b-158">A **Console** window opens.</span></span>  
  
     <span data-ttu-id="5403b-159">Para cerrar la aplicación, presione Entrar en la ventana de la **consola** o haga clic en **detener depuración** en el menú **depurar** de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5403b-159">Close the application by pressing Enter in the **Console** window, or by clicking **Stop Debugging** on the Visual Studio **Debug** menu.</span></span>  
  
## <a name="creating-a-new-entity"></a><span data-ttu-id="5403b-160">Crear una nueva entidad</span><span class="sxs-lookup"><span data-stu-id="5403b-160">Creating a New Entity</span></span>  

 <span data-ttu-id="5403b-161">Crear entidades es sencillo.</span><span class="sxs-lookup"><span data-stu-id="5403b-161">Creating a new entity is straightforward.</span></span> <span data-ttu-id="5403b-162">Puede crear objetos (como `Customer`) mediante la palabra clave `New`.</span><span class="sxs-lookup"><span data-stu-id="5403b-162">You can create objects (such as `Customer`) by using the `New` keyword.</span></span>  
  
 <span data-ttu-id="5403b-163">En esta sección y las siguientes, realizará cambios solo en la memoria caché local.</span><span class="sxs-lookup"><span data-stu-id="5403b-163">In this and the following sections, you are making changes only to the local cache.</span></span> <span data-ttu-id="5403b-164">No se enviarán cambios a la base de datos hasta que llame a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, casi al final del tutorial.</span><span class="sxs-lookup"><span data-stu-id="5403b-164">No changes are sent to the database until you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> toward the end of this walkthrough.</span></span>  
  
#### <a name="to-add-a-new-customer-entity-object"></a><span data-ttu-id="5403b-165">Para agregar un nuevo objeto entidad Customer</span><span class="sxs-lookup"><span data-stu-id="5403b-165">To add a new Customer entity object</span></span>  
  
1. <span data-ttu-id="5403b-166">Cree un nuevo `Customer` agregando el código siguiente delante de `Console.ReadLine` en `Sub Main`:</span><span class="sxs-lookup"><span data-stu-id="5403b-166">Create a new `Customer` by adding the following code before `Console.ReadLine` in `Sub Main`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#3)]  
  
2. <span data-ttu-id="5403b-167">Presione F5 para depurar la solución.</span><span class="sxs-lookup"><span data-stu-id="5403b-167">Press F5 to debug the solution.</span></span>  
  
     <span data-ttu-id="5403b-168">Los resultados que se muestran en la ventana de la consola son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="5403b-168">The results that are shown in the console window are as follows:</span></span>  
  
     `Customers matching CA before insert:`  
  
     `Customer ID: CACTU`  
  
     `Customer ID: RICAR`  
  
     <span data-ttu-id="5403b-169">Observe que la nueva fila no aparece en los resultados.</span><span class="sxs-lookup"><span data-stu-id="5403b-169">Note that the new row does not appear in the results.</span></span> <span data-ttu-id="5403b-170">Los nuevos datos no se han enviado todavía a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5403b-170">The new data has not yet been submitted to the database.</span></span>  
  
3. <span data-ttu-id="5403b-171">Presione entrar en la ventana de la **consola** para detener la depuración.</span><span class="sxs-lookup"><span data-stu-id="5403b-171">Press Enter in the **Console** window to stop debugging.</span></span>  
  
## <a name="updating-an-entity"></a><span data-ttu-id="5403b-172">Actualización de una entidad</span><span class="sxs-lookup"><span data-stu-id="5403b-172">Updating an Entity</span></span>  

 <span data-ttu-id="5403b-173">En los pasos siguientes, recuperará un objeto `Customer` y modificará una de sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="5403b-173">In the following steps, you will retrieve a `Customer` object and modify one of its properties.</span></span>  
  
#### <a name="to-change-the-name-of-a-customer"></a><span data-ttu-id="5403b-174">Para cambiar el nombre de un cliente</span><span class="sxs-lookup"><span data-stu-id="5403b-174">To change the name of a Customer</span></span>  
  
- <span data-ttu-id="5403b-175">Agregue el código siguiente encima de `Console.ReadLine()`:</span><span class="sxs-lookup"><span data-stu-id="5403b-175">Add the following code above `Console.ReadLine()`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#4)]  
  
## <a name="deleting-an-entity"></a><span data-ttu-id="5403b-176">Eliminación de una entidad</span><span class="sxs-lookup"><span data-stu-id="5403b-176">Deleting an Entity</span></span>  

 <span data-ttu-id="5403b-177">Con el mismo objeto de cliente, puede eliminar el primer pedido.</span><span class="sxs-lookup"><span data-stu-id="5403b-177">Using the same customer object, you can delete the first order.</span></span>  
  
 <span data-ttu-id="5403b-178">El código siguiente muestra cómo romper las relaciones entre las filas y cómo eliminar una fila de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5403b-178">The following code demonstrates how to sever relationships between rows, and how to delete a row from the database.</span></span>  
  
#### <a name="to-delete-a-row"></a><span data-ttu-id="5403b-179">Para eliminar una fila</span><span class="sxs-lookup"><span data-stu-id="5403b-179">To delete a row</span></span>  
  
- <span data-ttu-id="5403b-180">Agregue el código siguiente justo encima de `Console.ReadLine()`:</span><span class="sxs-lookup"><span data-stu-id="5403b-180">Add the following code just above `Console.ReadLine()`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#5)]  
  
## <a name="submitting-changes-to-the-database"></a><span data-ttu-id="5403b-181">Enviar los cambios a la base de datos</span><span class="sxs-lookup"><span data-stu-id="5403b-181">Submitting Changes to the Database</span></span>  

 <span data-ttu-id="5403b-182">El último paso necesario para crear, actualizar y eliminar objetos es realmente enviar los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5403b-182">The final step required for creating, updating, and deleting objects is to actually submit the changes to the database.</span></span> <span data-ttu-id="5403b-183">Sin este paso, los cambios se habrán realizado localmente y no aparecerán en los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="5403b-183">Without this step, your changes are only local and will not appear in query results.</span></span>  
  
#### <a name="to-submit-changes-to-the-database"></a><span data-ttu-id="5403b-184">Para enviar los cambios a la base de datos</span><span class="sxs-lookup"><span data-stu-id="5403b-184">To submit changes to the database</span></span>  
  
1. <span data-ttu-id="5403b-185">Inserte el código siguiente justo encima de `Console.ReadLine`:</span><span class="sxs-lookup"><span data-stu-id="5403b-185">Insert the following code just above `Console.ReadLine`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#6)]  
  
2. <span data-ttu-id="5403b-186">Inserte el código siguiente (después de `SubmitChanges`) para ver el antes y el después de enviar los cambios:</span><span class="sxs-lookup"><span data-stu-id="5403b-186">Insert the following code (after `SubmitChanges`) to show the before and after effects of submitting the changes:</span></span>  
  
     [!code-vb[DLinqWalk3VB#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#7)]  
  
3. <span data-ttu-id="5403b-187">Presione F5 para depurar la solución.</span><span class="sxs-lookup"><span data-stu-id="5403b-187">Press F5 to debug the solution.</span></span>  
  
     <span data-ttu-id="5403b-188">En la ventana de la consola aparece lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5403b-188">The console window appears as follows:</span></span>  
  
    ```console
    Customers matching CA before update:  
    Customer ID: CACTU  
    Customer ID: RICAR  
  
    The Order Detail to be deleted is: OrderID = 10643  
  
    Customers matching CA after update:  
    Customer ID: A3VCA  
    Customer ID: CACTU  
    Customer ID: RICAR  
    ```  
  
4. <span data-ttu-id="5403b-189">Presione entrar en la ventana de la **consola** para detener la depuración.</span><span class="sxs-lookup"><span data-stu-id="5403b-189">Press Enter in the **Console** window to stop debugging.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5403b-190">Después de haber agregado el nuevo cliente al enviar los cambios, no puede ejecutar de nuevo esta solución tal como está, porque no puede agregar el mismo cliente de nuevo tal como está.</span><span class="sxs-lookup"><span data-stu-id="5403b-190">After you have added the new customer by submitting the changes, you cannot execute this solution again as is, because you cannot add the same customer again as is.</span></span> <span data-ttu-id="5403b-191">Para ejecutar de nuevo la solución, cambie el valor del identificador de cliente que se debe agregar.</span><span class="sxs-lookup"><span data-stu-id="5403b-191">To execute the solution again, change the value of the customer ID to be added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5403b-192">Vea también</span><span class="sxs-lookup"><span data-stu-id="5403b-192">See also</span></span>

- [<span data-ttu-id="5403b-193">Aprender con tutoriales</span><span class="sxs-lookup"><span data-stu-id="5403b-193">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
