---
description: 'Más información sobre: Tutorial: usar solo procedimientos almacenados (C#)'
title: 'Tutorial: Usar solo procedimientos almacenados (C#)'
ms.date: 03/30/2017
ms.assetid: ecde4bf2-fa4d-4252-b5e4-96a46b9e097d
ms.openlocfilehash: 89cb6da9ec4e8d144726b6e3575a32c04d6aeec0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791782"
---
# <a name="walkthrough-using-only-stored-procedures-c"></a><span data-ttu-id="0c0b5-103">Tutorial: Usar solo procedimientos almacenados (C#)</span><span class="sxs-lookup"><span data-stu-id="0c0b5-103">Walkthrough: Using Only Stored Procedures (C#)</span></span>

<span data-ttu-id="0c0b5-104">Este tutorial proporciona un escenario completo básico de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para tener acceso a los datos ejecutando procedimientos almacenados solamente.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-104">This walkthrough provides a basic end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for accessing data by executing stored procedures only.</span></span> <span data-ttu-id="0c0b5-105">Este enfoque suelen utilizarlo los administradores de bases de datos para limitar el acceso al almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-105">This approach is often used by database administrators to limit how the datastore is accessed.</span></span>

> [!NOTE]
> <span data-ttu-id="0c0b5-106">También puede utilizar procedimientos almacenados en aplicaciones [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para invalidar el comportamiento predeterminado, especialmente para los procesos `Create`, `Update` y `Delete`.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-106">You can also use stored procedures in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications to override default behavior, especially for `Create`, `Update`, and `Delete` processes.</span></span> <span data-ttu-id="0c0b5-107">Para obtener más información, vea [personalizar las operaciones de inserción, actualización y eliminación](customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="0c0b5-107">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>

<span data-ttu-id="0c0b5-108">En este tutorial, utilizará dos métodos asignados a procedimientos almacenados en la base de datos de ejemplo Northwind: CustOrdersDetail y CustOrderHist.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-108">For purposes of this walkthrough, you will use two methods that have been mapped to stored procedures in the Northwind sample database: CustOrdersDetail and CustOrderHist.</span></span> <span data-ttu-id="0c0b5-109">La asignación se produce al ejecutar la herramienta de línea de comandos SqlMetal para crear un archivo de C#.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-109">The mapping occurs when you run the SqlMetal command-line tool to generate a C# file.</span></span> <span data-ttu-id="0c0b5-110">Para obtener más información, vea la sección Requisitos previos que se incluye posteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-110">For more information, see the Prerequisites section later in this walkthrough.</span></span>

<span data-ttu-id="0c0b5-111">Este tutorial no se basa en el Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-111">This walkthrough does not rely on the Object Relational Designer.</span></span> <span data-ttu-id="0c0b5-112">Los desarrolladores que usan Visual Studio también pueden usar O/R Designer para implementar la funcionalidad de procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-112">Developers using Visual Studio can also use the O/R Designer to implement stored procedure functionality.</span></span> <span data-ttu-id="0c0b5-113">Consulte [LINQ to SQL herramientas en Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span><span class="sxs-lookup"><span data-stu-id="0c0b5-113">See [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>

[!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]

<span data-ttu-id="0c0b5-114">Este tutorial se escribió con la configuración de desarrollo de Visual C#.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-114">This walkthrough was written by using Visual C# Development Settings.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0c0b5-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0c0b5-115">Prerequisites</span></span>

<span data-ttu-id="0c0b5-116">En este tutorial se requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c0b5-116">This walkthrough requires the following:</span></span>

- <span data-ttu-id="0c0b5-117">Este tutorial utiliza una carpeta dedicada ("c:\linqtest7") que contiene los archivos.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-117">This walkthrough uses a dedicated folder ("c:\linqtest7") to hold files.</span></span> <span data-ttu-id="0c0b5-118">Cree esta carpeta antes de empezar el tutorial.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-118">Create this folder before you begin the walkthrough.</span></span>

- <span data-ttu-id="0c0b5-119">Base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-119">The Northwind sample database.</span></span>

     <span data-ttu-id="0c0b5-120">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del sitio web de descargas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-120">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="0c0b5-121">Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="0c0b5-121">For instructions, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span> <span data-ttu-id="0c0b5-122">Después de haber descargado la base de datos, copie el archivo northwnd.mdf en la carpeta c:\linqtest7.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-122">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest7 folder.</span></span>

- <span data-ttu-id="0c0b5-123">Un archivo de código de C# generado a partir de la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-123">A C# code file generated from the Northwind database.</span></span>

     <span data-ttu-id="0c0b5-124">Este tutorial se escribió utilizando la herramienta SqlMetal con la línea de comandos siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c0b5-124">This walkthrough was written by using the SqlMetal tool with the following command line:</span></span>

     <span data-ttu-id="0c0b5-125">**sqlmetal /code:"c:\linqtest7\northwind.cs" /language:csharp "c:\linqtest7\northwnd.mdf" /sprocs /functions /pluralize**</span><span class="sxs-lookup"><span data-stu-id="0c0b5-125">**sqlmetal /code:"c:\linqtest7\northwind.cs" /language:csharp "c:\linqtest7\northwnd.mdf" /sprocs /functions /pluralize**</span></span>

     <span data-ttu-id="0c0b5-126">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="0c0b5-126">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>

## <a name="overview"></a><span data-ttu-id="0c0b5-127">Información general</span><span class="sxs-lookup"><span data-stu-id="0c0b5-127">Overview</span></span>

<span data-ttu-id="0c0b5-128">Este tutorial se compone de seis tareas principales:</span><span class="sxs-lookup"><span data-stu-id="0c0b5-128">This walkthrough consists of six main tasks:</span></span>

- <span data-ttu-id="0c0b5-129">Configuración de la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solución en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-129">Setting up the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>

- <span data-ttu-id="0c0b5-130">Agregar el ensamblado System.Data.Linq al proyecto.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-130">Adding the System.Data.Linq assembly to the project.</span></span>

- <span data-ttu-id="0c0b5-131">Agregar el archivo de código de la base de datos al proyecto.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-131">Adding the database code file to the project.</span></span>

- <span data-ttu-id="0c0b5-132">Crear una conexión con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-132">Creating a connection with the database.</span></span>

- <span data-ttu-id="0c0b5-133">Configurar la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-133">Setting up the user interface.</span></span>

- <span data-ttu-id="0c0b5-134">Ejecutar y probar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-134">Running and testing the application.</span></span>

## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="0c0b5-135">Crear una solución LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0c0b5-135">Creating a LINQ to SQL Solution</span></span>

<span data-ttu-id="0c0b5-136">En esta primera tarea, creará una solución de Visual Studio que contiene las referencias necesarias para compilar y ejecutar un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-136">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>

### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="0c0b5-137">Para crear una solución LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0c0b5-137">To create a LINQ to SQL solution</span></span>

1. <span data-ttu-id="0c0b5-138">En el menú **archivo** de Visual Studio, elija **nuevo** y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-138">On the Visual Studio **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="0c0b5-139">En el panel **tipos de proyecto** del cuadro de diálogo **nuevo proyecto** , haga clic en **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-139">In the **Project types** pane in the **New Project** dialog box, click **Visual C#**.</span></span>

3. <span data-ttu-id="0c0b5-140">En el panel **Plantillas** , haga clic en **Aplicación de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-140">In the **Templates** pane, click **Windows Forms Application**.</span></span>

4. <span data-ttu-id="0c0b5-141">En el cuadro **nombre** , escriba **SprocOnlyApp**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-141">In the **Name** box, type **SprocOnlyApp**.</span></span>

5. <span data-ttu-id="0c0b5-142">En el cuadro **Ubicación** , compruebe dónde desea almacenar los archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-142">In the **Location** box, verify where you want to store your project files.</span></span>

6. <span data-ttu-id="0c0b5-143">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-143">Click **OK**.</span></span>

     <span data-ttu-id="0c0b5-144">Se abre el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-144">The Windows Forms Designer opens.</span></span>

## <a name="adding-the-linq-to-sql-assembly-reference"></a><span data-ttu-id="0c0b5-145">Agregar la referencia al ensamblado de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0c0b5-145">Adding the LINQ to SQL Assembly Reference</span></span>

<span data-ttu-id="0c0b5-146">El ensamblado de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no está incluido en la plantilla Aplicación de Windows Forms estándar.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-146">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly is not included in the standard Windows Forms Application template.</span></span> <span data-ttu-id="0c0b5-147">Tendrá que agregar el ensamblado como se explica en los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0c0b5-147">You will have to add the assembly yourself, as explained in the following steps:</span></span>

### <a name="to-add-systemdatalinqdll"></a><span data-ttu-id="0c0b5-148">Para agregar System.Data.Linq.dll</span><span class="sxs-lookup"><span data-stu-id="0c0b5-148">To add System.Data.Linq.dll</span></span>

1. <span data-ttu-id="0c0b5-149">En **Explorador de soluciones**, haga clic con el botón secundario en **referencias** y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-149">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>

2. <span data-ttu-id="0c0b5-150">En el cuadro de diálogo **Agregar referencia** , haga clic en **.net**, haga clic en el ensamblado System. Data. Linq y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-150">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>

     <span data-ttu-id="0c0b5-151">El ensamblado se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-151">The assembly is added to the project.</span></span>

## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="0c0b5-152">Agregar el archivo de código de Northwind al proyecto</span><span class="sxs-lookup"><span data-stu-id="0c0b5-152">Adding the Northwind Code File to the Project</span></span>

<span data-ttu-id="0c0b5-153">En este paso se asume que ha utilizado la herramienta SqlMetal para generar un archivo de código a partir de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-153">This step assumes that you have used the SqlMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="0c0b5-154">Para obtener más información, vea la sección Requisitos previos, anteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-154">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>

### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="0c0b5-155">Para agregar el archivo de código de Northwind al proyecto</span><span class="sxs-lookup"><span data-stu-id="0c0b5-155">To add the northwind code file to the project</span></span>

1. <span data-ttu-id="0c0b5-156">En el menú **Proyecto** , haga clic en **Agregar elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-156">On the **Project** menu, click **Add Existing Item**.</span></span>

2. <span data-ttu-id="0c0b5-157">En el cuadro de diálogo **Agregar elemento existente** , desplácese a c:\linqtest7\northwind.CS y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-157">In the **Add Existing Item** dialog box, move to c:\linqtest7\northwind.cs, and then click **Add**.</span></span>

     <span data-ttu-id="0c0b5-158">El archivo northwind.cs se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-158">The northwind.cs file is added to the project.</span></span>

## <a name="creating-a-database-connection"></a><span data-ttu-id="0c0b5-159">Crear una conexión de base de datos</span><span class="sxs-lookup"><span data-stu-id="0c0b5-159">Creating a Database Connection</span></span>

<span data-ttu-id="0c0b5-160">En este paso, definirá la conexión con la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-160">In this step, you define the connection to the Northwind sample database.</span></span> <span data-ttu-id="0c0b5-161">En este tutorial se utiliza "c:\linqtest7\northwnd.mdf" como ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-161">This walkthrough uses "c:\linqtest7\northwnd.mdf" as the path.</span></span>

### <a name="to-create-the-database-connection"></a><span data-ttu-id="0c0b5-162">Para crear la conexión a la base de datos</span><span class="sxs-lookup"><span data-stu-id="0c0b5-162">To create the database connection</span></span>

1. <span data-ttu-id="0c0b5-163">En **Explorador de soluciones**, haga clic con el botón secundario en **Form1.CS** y, a continuación, haga clic en **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-163">In **Solution Explorer**, right-click **Form1.cs**, and then click **View Code**.</span></span>

2. <span data-ttu-id="0c0b5-164">Escriba el código siguiente en la clase `Form1`:</span><span class="sxs-lookup"><span data-stu-id="0c0b5-164">Type the following code into the `Form1` class:</span></span>

     [!code-csharp[DLinqWalk4CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#1)]

## <a name="setting-up-the-user-interface"></a><span data-ttu-id="0c0b5-165">Configurar la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="0c0b5-165">Setting up the User Interface</span></span>

<span data-ttu-id="0c0b5-166">En esta tarea preparará una interfaz para que los usuarios puedan ejecutar procedimientos almacenados para tener acceso a los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-166">In this task you set up an interface so that users can execute stored procedures to access data in the database.</span></span> <span data-ttu-id="0c0b5-167">En las aplicaciones que desarrolla con este tutorial, los usuarios pueden tener acceso a los datos de la base de datos únicamente mediante los procedimientos almacenados que están incrustados en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-167">In the applications that you are developing with this walkthrough, users can access data in the database only by using the stored procedures embedded in the application.</span></span>

### <a name="to-set-up-the-user-interface"></a><span data-ttu-id="0c0b5-168">Para configurar la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="0c0b5-168">To set up the user interface</span></span>

1. <span data-ttu-id="0c0b5-169">Vuelva al Diseñador de Windows Forms (**Form1. CS [diseño]**).</span><span class="sxs-lookup"><span data-stu-id="0c0b5-169">Return to the Windows Forms Designer (**Form1.cs[Design]**).</span></span>

2. <span data-ttu-id="0c0b5-170">En el menú **Ver** , haga clic en **Cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-170">On the **View** menu, click **Toolbox**.</span></span>

     <span data-ttu-id="0c0b5-171">Se abrirá el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-171">The toolbox opens.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0c0b5-172">Haga clic en el marcador **Ocultar automáticamente** para mantener el cuadro de herramientas abierto mientras realiza los pasos restantes de esta sección.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-172">Click the **AutoHide** pushpin to keep the toolbox open while you perform the remaining steps in this section.</span></span>

3. <span data-ttu-id="0c0b5-173">Arrastre dos botones, dos cuadros de texto y dos etiquetas desde el cuadro de herramientas hasta **Form1**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-173">Drag two buttons, two text boxes, and two labels from the toolbox onto **Form1**.</span></span>

     <span data-ttu-id="0c0b5-174">Organice los controles como en la ilustración anexa.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-174">Arrange the controls as in the accompanying illustration.</span></span> <span data-ttu-id="0c0b5-175">Expanda **Form1** para que los controles se ajusten fácilmente.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-175">Expand **Form1** so that the controls fit easily.</span></span>

4. <span data-ttu-id="0c0b5-176">Haga clic con el botón secundario en **Label1** y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-176">Right-click **label1**, and then click **Properties**.</span></span>

5. <span data-ttu-id="0c0b5-177">Cambie la propiedad **Text** de **Label1** a **Enter OrderID:**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-177">Change the **Text** property from **label1** to **Enter OrderID:**.</span></span>

6. <span data-ttu-id="0c0b5-178">Del mismo modo para **Label2**, cambie la propiedad **Text** de **Label2** a **Enter CustomerID:**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-178">In the same way for **label2**, change the **Text** property from **label2** to **Enter CustomerID:**.</span></span>

7. <span data-ttu-id="0c0b5-179">Del mismo modo, cambie la propiedad **Text** de **button1** a **Order Details**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-179">In the same way, change the **Text** property for **button1** to **Order Details**.</span></span>

8. <span data-ttu-id="0c0b5-180">Cambie la propiedad **Text** de **BUTTON2** a **Order History**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-180">Change the **Text** property for **button2** to **Order History**.</span></span>

     <span data-ttu-id="0c0b5-181">Amplíe los controles de botón para que todo el texto esté visible.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-181">Widen the button controls so that all the text is visible.</span></span>

### <a name="to-handle-button-clicks"></a><span data-ttu-id="0c0b5-182">Para administrar los clics de botón</span><span class="sxs-lookup"><span data-stu-id="0c0b5-182">To handle button clicks</span></span>

1. <span data-ttu-id="0c0b5-183">Haga doble clic en **Order Details** en **Form1** para abrir el controlador de eventos de button1 en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-183">Double-click **Order Details** on **Form1** to open the button1 event handler in the code editor.</span></span>

2. <span data-ttu-id="0c0b5-184">Escriba el código siguiente en el controlador `button1`:</span><span class="sxs-lookup"><span data-stu-id="0c0b5-184">Type the following code into the `button1` handler:</span></span>

     [!code-csharp[DLinqWalk4CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#2)]

3. <span data-ttu-id="0c0b5-185">Ahora haga doble clic en **BUTTON2** en **Form1** para abrir el `button2` controlador</span><span class="sxs-lookup"><span data-stu-id="0c0b5-185">Now double-click **button2** on **Form1** to open the `button2` handler</span></span>

4. <span data-ttu-id="0c0b5-186">Escriba el código siguiente en el controlador `button2`:</span><span class="sxs-lookup"><span data-stu-id="0c0b5-186">Type the following code into the `button2` handler:</span></span>

     [!code-csharp[DLinqWalk4CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#3)]

## <a name="testing-the-application"></a><span data-ttu-id="0c0b5-187">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="0c0b5-187">Testing the Application</span></span>

<span data-ttu-id="0c0b5-188">Ha llegado el momento de probar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-188">Now it is time to test your application.</span></span> <span data-ttu-id="0c0b5-189">Observe que su contacto con el almacén de datos se limita a las acciones que puedan realizar los dos procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-189">Note that your contact with the datastore is limited to whatever actions the two stored procedures can take.</span></span> <span data-ttu-id="0c0b5-190">Esas acciones son: devolver los productos incluidos para cualquier orderID que escriba o devolver un historial de los productos solicitados para cualquier CustomerID que escriba.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-190">Those actions are to return the products included for any orderID you enter, or to return a history of products ordered for any CustomerID you enter.</span></span>

### <a name="to-test-the-application"></a><span data-ttu-id="0c0b5-191">Para probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="0c0b5-191">To test the application</span></span>

1. <span data-ttu-id="0c0b5-192">Presiona F5 para iniciar la depuración.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-192">Press F5 to start debugging.</span></span>

     <span data-ttu-id="0c0b5-193">Aparece Form1.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-193">Form1 appears.</span></span>

2. <span data-ttu-id="0c0b5-194">En el cuadro **Enter OrderID** , escriba `10249` y, a continuación, haga clic en **Order Details**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-194">In the **Enter OrderID** box, type `10249`, and then click **Order Details**.</span></span>

     <span data-ttu-id="0c0b5-195">Un cuadro de mensaje muestra los productos incluidos en el pedido 10249.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-195">A message box lists the products included in order 10249.</span></span>

     <span data-ttu-id="0c0b5-196">Haga clic en **Aceptar** para cerrar el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-196">Click **OK** to close the message box.</span></span>

3. <span data-ttu-id="0c0b5-197">En el cuadro **Escriba CustomerID** , escriba `ALFKI` y, a continuación, haga clic en **historial de pedidos**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-197">In the **Enter CustomerID** box, type `ALFKI`, and then click **Order History**.</span></span>

     <span data-ttu-id="0c0b5-198">Aparece un cuadro de mensaje con el historial de pedidos del cliente ALFKI.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-198">A message box appears that lists the order history for customer ALFKI.</span></span>

     <span data-ttu-id="0c0b5-199">Haga clic en **Aceptar** para cerrar el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-199">Click **OK** to close the message box.</span></span>

4. <span data-ttu-id="0c0b5-200">En el cuadro **Enter OrderID** , escriba `123` y, a continuación, haga clic en **Order Details**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-200">In the **Enter OrderID** box, type `123`, and then click **Order Details**.</span></span>

     <span data-ttu-id="0c0b5-201">Aparece un cuadro de mensaje con el texto "No results".</span><span class="sxs-lookup"><span data-stu-id="0c0b5-201">A message box appears that displays "No results."</span></span>

     <span data-ttu-id="0c0b5-202">Haga clic en **Aceptar** para cerrar el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-202">Click **OK** to close the message box.</span></span>

5. <span data-ttu-id="0c0b5-203">En el menú **depurar** , haga clic en **detener depuración**.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-203">On the **Debug** menu, click **Stop debugging**.</span></span>

     <span data-ttu-id="0c0b5-204">La sesión de depuración se cierra.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-204">The debug session closes.</span></span>

6. <span data-ttu-id="0c0b5-205">Si ha terminado de experimentar, puede hacer clic en **cerrar proyecto** en el menú **archivo** y guardar el proyecto cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-205">If you have finished experimenting, you can click **Close Project** on the **File** menu, and save your project when you are prompted.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0c0b5-206">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="0c0b5-206">Next Steps</span></span>

<span data-ttu-id="0c0b5-207">Puede mejorar este proyecto realizando algunos cambios.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-207">You can enhance this project by making some changes.</span></span> <span data-ttu-id="0c0b5-208">Por ejemplo, podría enumerar los procedimientos almacenados disponibles en un cuadro de lista y permitir que el usuario seleccione qué procedimientos debe ejecutar.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-208">For example, you could list available stored procedures in a list box and have the user select which procedures to execute.</span></span> <span data-ttu-id="0c0b5-209">También podría transmitir el resultado de los informes a un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="0c0b5-209">You could also stream the output of the reports to a text file.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c0b5-210">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c0b5-210">See also</span></span>

- [<span data-ttu-id="0c0b5-211">Aprender con tutoriales</span><span class="sxs-lookup"><span data-stu-id="0c0b5-211">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
- [<span data-ttu-id="0c0b5-212">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="0c0b5-212">Stored Procedures</span></span>](stored-procedures.md)
