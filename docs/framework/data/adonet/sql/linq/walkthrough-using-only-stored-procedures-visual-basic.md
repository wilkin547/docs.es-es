---
description: 'Más información acerca de: Tutorial: usar solo procedimientos almacenados (Visual Basic)'
title: 'Tutorial: Usar solo procedimientos almacenados (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 5a736a30-ba66-4adb-b87c-57d19476e862
ms.openlocfilehash: b368bdd5717c0f424192c3eabb8058d633cac61e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791769"
---
# <a name="walkthrough-using-only-stored-procedures-visual-basic"></a><span data-ttu-id="9e8db-103">Tutorial: Usar solo procedimientos almacenados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e8db-103">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>

<span data-ttu-id="9e8db-104">Este tutorial proporciona un escenario completo básico de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para tener acceso a los datos utilizando procedimientos almacenados solamente.</span><span class="sxs-lookup"><span data-stu-id="9e8db-104">This walkthrough provides a basic end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for accessing data by using stored procedures only.</span></span> <span data-ttu-id="9e8db-105">Este enfoque suelen utilizarlo los administradores de bases de datos para limitar el acceso al almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="9e8db-105">This approach is often used by database administrators to limit how the datastore is accessed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e8db-106">También puede utilizar procedimientos almacenados en aplicaciones [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para invalidar el comportamiento predeterminado, especialmente para los procesos `Create`, `Update` y `Delete`.</span><span class="sxs-lookup"><span data-stu-id="9e8db-106">You can also use stored procedures in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications to override default behavior, especially for `Create`, `Update`, and `Delete` processes.</span></span> <span data-ttu-id="9e8db-107">Para obtener más información, vea [personalizar las operaciones de inserción, actualización y eliminación](customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="9e8db-107">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>  
  
 <span data-ttu-id="9e8db-108">En este tutorial, utilizará dos métodos asignados a procedimientos almacenados en la base de datos de ejemplo Northwind: CustOrdersDetail y CustOrderHist.</span><span class="sxs-lookup"><span data-stu-id="9e8db-108">For purposes of this walkthrough, you will use two methods that have been mapped to stored procedures in the Northwind sample database: CustOrdersDetail and CustOrderHist.</span></span> <span data-ttu-id="9e8db-109">La asignación se produce al ejecutar la herramienta de línea de comandos SqlMetal para generar un archivo de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9e8db-109">The mapping occurs when you run the SqlMetal command-line tool to generate a Visual Basic file.</span></span> <span data-ttu-id="9e8db-110">Para obtener más información, vea la sección Requisitos previos que se incluye posteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="9e8db-110">For more information, see the Prerequisites section later in this walkthrough.</span></span>  
  
 <span data-ttu-id="9e8db-111">Este tutorial no se basa en el Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="9e8db-111">This walkthrough does not rely on the Object Relational Designer.</span></span> <span data-ttu-id="9e8db-112">Los desarrolladores que usan Visual Studio también pueden usar O/R Designer para implementar la funcionalidad de procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="9e8db-112">Developers using Visual Studio can also use the O/R Designer to implement stored procedure functionality.</span></span> <span data-ttu-id="9e8db-113">Consulte [LINQ to SQL herramientas en Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span><span class="sxs-lookup"><span data-stu-id="9e8db-113">See [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="9e8db-114">Este tutorial se escribió con la configuración de desarrollo de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9e8db-114">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9e8db-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9e8db-115">Prerequisites</span></span>  

 <span data-ttu-id="9e8db-116">En este tutorial se requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e8db-116">This walkthrough requires the following:</span></span>  
  
- <span data-ttu-id="9e8db-117">Este tutorial utiliza una carpeta dedicada ("c:\linqtest3") que contiene los archivos.</span><span class="sxs-lookup"><span data-stu-id="9e8db-117">This walkthrough uses a dedicated folder ("c:\linqtest3") to hold files.</span></span> <span data-ttu-id="9e8db-118">Cree esta carpeta antes de empezar el tutorial.</span><span class="sxs-lookup"><span data-stu-id="9e8db-118">Create this folder before you begin the walkthrough.</span></span>  
  
- <span data-ttu-id="9e8db-119">Base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="9e8db-119">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="9e8db-120">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del sitio web de descargas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9e8db-120">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="9e8db-121">Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="9e8db-121">For instructions, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span> <span data-ttu-id="9e8db-122">Después de haber descargado la base de datos, copie el archivo northwnd.mdf en la carpeta c:\linqtest3.</span><span class="sxs-lookup"><span data-stu-id="9e8db-122">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest3 folder.</span></span>  
  
- <span data-ttu-id="9e8db-123">Archivo de código de Visual Basic generado a partir de la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="9e8db-123">A Visual Basic code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="9e8db-124">Este tutorial se escribió utilizando la herramienta SqlMetal con la línea de comandos siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e8db-124">This walkthrough was written by using the SqlMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="9e8db-125">**sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize**</span><span class="sxs-lookup"><span data-stu-id="9e8db-125">**sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize**</span></span>  
  
     <span data-ttu-id="9e8db-126">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="9e8db-126">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="9e8db-127">Información general</span><span class="sxs-lookup"><span data-stu-id="9e8db-127">Overview</span></span>  

 <span data-ttu-id="9e8db-128">Este tutorial se compone de seis tareas principales:</span><span class="sxs-lookup"><span data-stu-id="9e8db-128">This walkthrough consists of six main tasks:</span></span>  
  
- <span data-ttu-id="9e8db-129">Configuración de la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solución en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9e8db-129">Setting up the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
- <span data-ttu-id="9e8db-130">Agregar el ensamblado System.Data.Linq al proyecto.</span><span class="sxs-lookup"><span data-stu-id="9e8db-130">Adding the System.Data.Linq assembly to the project.</span></span>  
  
- <span data-ttu-id="9e8db-131">Agregar el archivo de código de la base de datos al proyecto.</span><span class="sxs-lookup"><span data-stu-id="9e8db-131">Adding the database code file to the project.</span></span>  
  
- <span data-ttu-id="9e8db-132">Crear una conexión con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9e8db-132">Creating a connection to the database.</span></span>  
  
- <span data-ttu-id="9e8db-133">Configurar la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="9e8db-133">Setting up the user interface.</span></span>  
  
- <span data-ttu-id="9e8db-134">Ejecutar y probar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9e8db-134">Running and testing the application.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="9e8db-135">Crear una solución LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="9e8db-135">Creating a LINQ to SQL Solution</span></span>  

 <span data-ttu-id="9e8db-136">En esta primera tarea, creará una solución de Visual Studio que contiene las referencias necesarias para compilar y ejecutar un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="9e8db-136">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="9e8db-137">Para crear una solución LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="9e8db-137">To create a LINQ to SQL solution</span></span>  
  
1. <span data-ttu-id="9e8db-138">En el menú **Archivo** de Visual Studio, haga clic en **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-138">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2. <span data-ttu-id="9e8db-139">En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto** , expanda **Visual Basic** y, a continuación, haga clic en **Windows**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-139">In the **Project types** pane in the **New Project** dialog box, expand **Visual Basic**, and then click **Windows**.</span></span>  
  
3. <span data-ttu-id="9e8db-140">En el panel **Plantillas** , haga clic en **Aplicación de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-140">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4. <span data-ttu-id="9e8db-141">En el cuadro **nombre** , escriba **SprocOnlyApp**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-141">In the **Name** box, type **SprocOnlyApp**.</span></span>  
  
5. <span data-ttu-id="9e8db-142">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-142">Click **OK**.</span></span>  
  
     <span data-ttu-id="9e8db-143">Se abre el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9e8db-143">The Windows Forms Designer opens.</span></span>  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a><span data-ttu-id="9e8db-144">Agregar la referencia al ensamblado de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="9e8db-144">Adding the LINQ to SQL Assembly Reference</span></span>  

 <span data-ttu-id="9e8db-145">El ensamblado de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no está incluido en la plantilla Aplicación de Windows Forms estándar.</span><span class="sxs-lookup"><span data-stu-id="9e8db-145">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly is not included in the standard Windows Forms Application template.</span></span> <span data-ttu-id="9e8db-146">Tendrá que agregar el ensamblado como se explica en los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9e8db-146">You will have to add the assembly yourself, as explained in the following steps:</span></span>  
  
### <a name="to-add-systemdatalinqdll"></a><span data-ttu-id="9e8db-147">Para agregar System.Data.Linq.dll</span><span class="sxs-lookup"><span data-stu-id="9e8db-147">To add System.Data.Linq.dll</span></span>  
  
1. <span data-ttu-id="9e8db-148">En **Explorador de soluciones**, haga clic en **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-148">In **Solution Explorer**, click **Show All Files**.</span></span>  
  
2. <span data-ttu-id="9e8db-149">En **Explorador de soluciones**, haga clic con el botón secundario en **referencias** y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-149">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
3. <span data-ttu-id="9e8db-150">En el cuadro de diálogo **Agregar referencia** , haga clic en **.net**, haga clic en el ensamblado System. Data. Linq y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-150">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="9e8db-151">El ensamblado se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="9e8db-151">The assembly is added to the project.</span></span>  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="9e8db-152">Agregar el archivo de código de Northwind al proyecto</span><span class="sxs-lookup"><span data-stu-id="9e8db-152">Adding the Northwind Code File to the Project</span></span>  

 <span data-ttu-id="9e8db-153">En este paso se asume que ha utilizado la herramienta SqlMetal para generar un archivo de código a partir de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="9e8db-153">This step assumes that you have used the SqlMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="9e8db-154">Para obtener más información, vea la sección Requisitos previos, anteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="9e8db-154">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="9e8db-155">Para agregar el archivo de código de Northwind al proyecto</span><span class="sxs-lookup"><span data-stu-id="9e8db-155">To add the northwind code file to the project</span></span>  
  
1. <span data-ttu-id="9e8db-156">En el menú **Proyecto** , haga clic en **Agregar elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-156">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2. <span data-ttu-id="9e8db-157">En el cuadro de diálogo **Agregar elemento existente** , desplácese a c:\linqtest3\northwind.VB y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-157">In the **Add Existing Item** dialog box, move to c:\linqtest3\northwind.vb, and then click **Add**.</span></span>  
  
     <span data-ttu-id="9e8db-158">El archivo northwind.vb se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="9e8db-158">The northwind.vb file is added to the project.</span></span>  
  
## <a name="creating-a-database-connection"></a><span data-ttu-id="9e8db-159">Crear una conexión de base de datos</span><span class="sxs-lookup"><span data-stu-id="9e8db-159">Creating a Database Connection</span></span>  

 <span data-ttu-id="9e8db-160">En este paso, definirá la conexión con la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="9e8db-160">In this step, you define the connection to the Northwind sample database.</span></span> <span data-ttu-id="9e8db-161">En este tutorial se utiliza "c:\linqtest3\northwnd.mdf" como ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="9e8db-161">This walkthrough uses "c:\linqtest3\northwnd.mdf" as the path.</span></span>  
  
### <a name="to-create-the-database-connection"></a><span data-ttu-id="9e8db-162">Para crear la conexión a la base de datos</span><span class="sxs-lookup"><span data-stu-id="9e8db-162">To create the database connection</span></span>  
  
1. <span data-ttu-id="9e8db-163">En **Explorador de soluciones**, haga clic con el botón secundario en **Form1. VB** y, a continuación, haga clic en **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-163">In **Solution Explorer**, right-click **Form1.vb**, and then click **View Code**.</span></span>  
  
     <span data-ttu-id="9e8db-164">`Class Form1` aparece en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="9e8db-164">`Class Form1` appears in the code editor.</span></span>  
  
2. <span data-ttu-id="9e8db-165">Escriba el código siguiente en el bloque de código `Form1`:</span><span class="sxs-lookup"><span data-stu-id="9e8db-165">Type the following code into the `Form1` code block:</span></span>  
  
     [!code-vb[DLinqWalk4VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#1)]  
  
## <a name="setting-up-the-user-interface"></a><span data-ttu-id="9e8db-166">Configurar la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="9e8db-166">Setting up the User Interface</span></span>  

 <span data-ttu-id="9e8db-167">En esta tarea creará una interfaz para que los usuarios puedan ejecutar procedimientos almacenados para tener acceso a los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9e8db-167">In this task you create an interface so that users can execute stored procedures to access data in the database.</span></span> <span data-ttu-id="9e8db-168">En la aplicación que desarrolla con este tutorial, los usuarios pueden tener acceso a los datos de la base de datos únicamente mediante los procedimientos almacenados que están incrustados en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9e8db-168">In the application that you are developing with this walkthrough, users can access data in the database only by using the stored procedures embedded in the application.</span></span>  
  
### <a name="to-set-up-the-user-interface"></a><span data-ttu-id="9e8db-169">Para configurar la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="9e8db-169">To set up the user interface</span></span>  
  
1. <span data-ttu-id="9e8db-170">Vuelva al Diseñador de Windows Forms (**Form1. VB [diseño]**).</span><span class="sxs-lookup"><span data-stu-id="9e8db-170">Return to the Windows Forms Designer (**Form1.vb[Design]**).</span></span>  
  
2. <span data-ttu-id="9e8db-171">En el menú **Ver** , haga clic en **Cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-171">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="9e8db-172">Se abrirá el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="9e8db-172">The toolbox opens.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9e8db-173">Haga clic en el marcador **Ocultar automáticamente** para mantener el cuadro de herramientas abierto mientras realiza los pasos restantes de esta sección.</span><span class="sxs-lookup"><span data-stu-id="9e8db-173">Click the **AutoHide** pushpin to keep the toolbox open while you perform the remaining steps in this section.</span></span>  
  
3. <span data-ttu-id="9e8db-174">Arrastre dos botones, dos cuadros de texto y dos etiquetas desde el cuadro de herramientas hasta **Form1**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-174">Drag two buttons, two text boxes, and two labels from the toolbox onto **Form1**.</span></span>  
  
     <span data-ttu-id="9e8db-175">Organice los controles como en la ilustración anexa.</span><span class="sxs-lookup"><span data-stu-id="9e8db-175">Arrange the controls as in the accompanying illustration.</span></span> <span data-ttu-id="9e8db-176">Expanda **Form1** para que los controles se ajusten fácilmente.</span><span class="sxs-lookup"><span data-stu-id="9e8db-176">Expand **Form1** so that the controls fit easily.</span></span>  
  
4. <span data-ttu-id="9e8db-177">Haga clic con el botón secundario en **Label1** y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-177">Right-click **Label1**, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="9e8db-178">Cambie la propiedad **Text** de **Label1** a **Enter OrderID:**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-178">Change the **Text** property from **Label1** to **Enter OrderID:**.</span></span>  
  
6. <span data-ttu-id="9e8db-179">Del mismo modo para **Label2**, cambie la propiedad **Text** de **Label2** a **Enter CustomerID:**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-179">In the same way for **Label2**, change the **Text** property from **Label2** to **Enter CustomerID:**.</span></span>  
  
7. <span data-ttu-id="9e8db-180">Del mismo modo, cambie la propiedad **Text** de **button1** a **Order Details**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-180">In the same way, change the **Text** property for **Button1** to **Order Details**.</span></span>  
  
8. <span data-ttu-id="9e8db-181">Cambie la propiedad **Text** de **BUTTON2** a **Order History**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-181">Change the **Text** property for **Button2** to **Order History**.</span></span>  
  
     <span data-ttu-id="9e8db-182">Amplíe los controles de botón para que todo el texto esté visible.</span><span class="sxs-lookup"><span data-stu-id="9e8db-182">Widen the button controls so that all the text is visible.</span></span>  
  
### <a name="to-handle-button-clicks"></a><span data-ttu-id="9e8db-183">Para administrar los clics de botón</span><span class="sxs-lookup"><span data-stu-id="9e8db-183">To handle button clicks</span></span>  
  
1. <span data-ttu-id="9e8db-184">Haga doble clic en **Order Details** en **Form1** para crear el `Button1` controlador de eventos y abrir el editor de código.</span><span class="sxs-lookup"><span data-stu-id="9e8db-184">Double-click **Order Details** on **Form1** to create the `Button1` event handler and open the code editor.</span></span>  
  
2. <span data-ttu-id="9e8db-185">Escriba el código siguiente en el controlador `Button1`:</span><span class="sxs-lookup"><span data-stu-id="9e8db-185">Type the following code into the `Button1` handler:</span></span>  
  
     [!code-vb[DLinqWalk4VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#2)]  
  
3. <span data-ttu-id="9e8db-186">Ahora haga doble clic en **BUTTON2** en Form1 para crear el `Button2` controlador de eventos y abrir el editor de código.</span><span class="sxs-lookup"><span data-stu-id="9e8db-186">Now double-click **Button2** on Form1 to create the `Button2` event handler and open the code editor.</span></span>  
  
4. <span data-ttu-id="9e8db-187">Escriba el código siguiente en el controlador `Button2`:</span><span class="sxs-lookup"><span data-stu-id="9e8db-187">Type the following code into the `Button2` handler:</span></span>  
  
     [!code-vb[DLinqWalk4VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#3)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="9e8db-188">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="9e8db-188">Testing the Application</span></span>  

 <span data-ttu-id="9e8db-189">Ha llegado el momento de probar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9e8db-189">Now it is time to test your application.</span></span> <span data-ttu-id="9e8db-190">Observe que su contacto con el almacén de datos se limita a las acciones que puedan realizar los dos procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="9e8db-190">Note that your contact with the datastore is limited to whatever actions the two stored procedures can take.</span></span> <span data-ttu-id="9e8db-191">Esas acciones son: devolver los productos incluidos para cualquier orderID que escriba o devolver un historial de los productos solicitados para cualquier CustomerID que escriba.</span><span class="sxs-lookup"><span data-stu-id="9e8db-191">Those actions are to return the products included for any orderID you enter, or to return a history of products ordered for any CustomerID you enter.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="9e8db-192">Para probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="9e8db-192">To test the application</span></span>  
  
1. <span data-ttu-id="9e8db-193">Presiona F5 para iniciar la depuración.</span><span class="sxs-lookup"><span data-stu-id="9e8db-193">Press F5 to start debugging.</span></span>  
  
     <span data-ttu-id="9e8db-194">Aparece Form1.</span><span class="sxs-lookup"><span data-stu-id="9e8db-194">Form1 appears.</span></span>  
  
2. <span data-ttu-id="9e8db-195">En el cuadro **Enter OrderID** , escriba **10249** y, a continuación, haga clic en **Order Details**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-195">In the **Enter OrderID** box, type **10249** and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="9e8db-196">Un cuadro de mensaje muestra los productos incluidos en el pedido 10249.</span><span class="sxs-lookup"><span data-stu-id="9e8db-196">A message box lists the products included in order 10249.</span></span>  
  
     <span data-ttu-id="9e8db-197">Haga clic en **Aceptar** para cerrar el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9e8db-197">Click **OK** to close the message box.</span></span>  
  
3. <span data-ttu-id="9e8db-198">En el cuadro **Escriba CustomerID** , escriba `ALFKI` y, a continuación, haga clic en **historial de pedidos**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-198">In the **Enter CustomerID** box, type `ALFKI`, and then click **Order History**.</span></span>  
  
     <span data-ttu-id="9e8db-199">Aparece un cuadro de mensaje con el historial de pedidos del cliente ALFKI.</span><span class="sxs-lookup"><span data-stu-id="9e8db-199">A message box lists the order history for customer ALFKI.</span></span>  
  
     <span data-ttu-id="9e8db-200">Haga clic en **Aceptar** para cerrar el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9e8db-200">Click **OK** to close the message box.</span></span>  
  
4. <span data-ttu-id="9e8db-201">En el cuadro **Enter OrderID** , escriba `123` y, a continuación, haga clic en **Order Details**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-201">In the **Enter OrderID** box, type `123`, and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="9e8db-202">Aparece un cuadro de mensaje con el texto "No results".</span><span class="sxs-lookup"><span data-stu-id="9e8db-202">A message box displays "No results."</span></span>  
  
     <span data-ttu-id="9e8db-203">Haga clic en **Aceptar** para cerrar el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9e8db-203">Click **OK** to close the message box.</span></span>  
  
5. <span data-ttu-id="9e8db-204">En el menú **depurar** , haga clic en **detener depuración**.</span><span class="sxs-lookup"><span data-stu-id="9e8db-204">On the **Debug** menu, click **Stop debugging**.</span></span>  
  
     <span data-ttu-id="9e8db-205">La sesión de depuración se cierra.</span><span class="sxs-lookup"><span data-stu-id="9e8db-205">The debug session closes.</span></span>  
  
6. <span data-ttu-id="9e8db-206">Si ha terminado de experimentar, puede hacer clic en **cerrar proyecto** en el menú **archivo** y guardar el proyecto cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="9e8db-206">If you have finished experimenting, you can click **Close Project** on the **File** menu, and save your project when you are prompted.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9e8db-207">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9e8db-207">Next Steps</span></span>  

 <span data-ttu-id="9e8db-208">Puede mejorar este proyecto realizando algunos cambios.</span><span class="sxs-lookup"><span data-stu-id="9e8db-208">You can enhance this project by making some changes.</span></span> <span data-ttu-id="9e8db-209">Por ejemplo, podría enumerar los procedimientos almacenados disponibles en un cuadro de lista y permitir que el usuario seleccione qué procedimientos debe ejecutar.</span><span class="sxs-lookup"><span data-stu-id="9e8db-209">For example, you could list available stored procedures in a list box and have the user select which procedures to execute.</span></span> <span data-ttu-id="9e8db-210">También podría transmitir el resultado de los informes a un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="9e8db-210">You could also stream the output of the reports to a text file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e8db-211">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e8db-211">See also</span></span>

- [<span data-ttu-id="9e8db-212">Aprender con tutoriales</span><span class="sxs-lookup"><span data-stu-id="9e8db-212">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
- [<span data-ttu-id="9e8db-213">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="9e8db-213">Stored Procedures</span></span>](stored-procedures.md)
