---
title: 'Tutorial: Usar solo procedimientos almacenados (C#)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ecde4bf2-fa4d-4252-b5e4-96a46b9e097d
caps.latest.revision: 4
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 4c13e4c12abf17f995bb819ddd7d6337407e3b28
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-using-only-stored-procedures-c"></a><span data-ttu-id="3eec6-102">Tutorial: Usar solo procedimientos almacenados (C#)</span><span class="sxs-lookup"><span data-stu-id="3eec6-102">Walkthrough: Using Only Stored Procedures (C#)</span></span>
<span data-ttu-id="3eec6-103">Este tutorial proporciona un escenario completo básico de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para tener acceso a los datos ejecutando procedimientos almacenados solamente.</span><span class="sxs-lookup"><span data-stu-id="3eec6-103">This walkthrough provides a basic end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for accessing data by executing stored procedures only.</span></span> <span data-ttu-id="3eec6-104">Este enfoque suelen utilizarlo los administradores de bases de datos para limitar el acceso al almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="3eec6-104">This approach is often used by database administrators to limit how the datastore is accessed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3eec6-105">También puede utilizar procedimientos almacenados en aplicaciones [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para invalidar el comportamiento predeterminado, especialmente para los procesos `Create`, `Update` y `Delete`.</span><span class="sxs-lookup"><span data-stu-id="3eec6-105">You can also use stored procedures in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications to override default behavior, especially for `Create`, `Update`, and `Delete` processes.</span></span> <span data-ttu-id="3eec6-106">Para obtener más información, consulte [personalizar operaciones de inserción, actualización y eliminar](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="3eec6-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
  
 <span data-ttu-id="3eec6-107">En este tutorial, utilizará dos métodos asignados a procedimientos almacenados en la base de datos de ejemplo Northwind: CustOrdersDetail y CustOrderHist.</span><span class="sxs-lookup"><span data-stu-id="3eec6-107">For purposes of this walkthrough, you will use two methods that have been mapped to stored procedures in the Northwind sample database: CustOrdersDetail and CustOrderHist.</span></span> <span data-ttu-id="3eec6-108">La asignación se produce al ejecutar la herramienta de línea de comandos SqlMetal para crear un archivo de C#.</span><span class="sxs-lookup"><span data-stu-id="3eec6-108">The mapping occurs when you run the SqlMetal command-line tool to generate a C# file.</span></span> <span data-ttu-id="3eec6-109">Para obtener más información, vea la sección Requisitos previos que se incluye posteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="3eec6-109">For more information, see the Prerequisites section later in this walkthrough.</span></span>  
  
 <span data-ttu-id="3eec6-110">En este tutorial no se utiliza el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3eec6-110">This walkthrough does not rely on the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span></span> <span data-ttu-id="3eec6-111">Los desarrolladores que utilizan Visual Studio también pueden usar el [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] para implementar la funcionalidad de procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="3eec6-111">Developers using Visual Studio can also use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to implement stored procedure functionality.</span></span> <span data-ttu-id="3eec6-112">Vea [LINQ a las herramientas SQL en Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span><span class="sxs-lookup"><span data-stu-id="3eec6-112">See [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="3eec6-113">Este tutorial se escribió con la configuración de desarrollo de Visual C#.</span><span class="sxs-lookup"><span data-stu-id="3eec6-113">This walkthrough was written by using Visual C# Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3eec6-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3eec6-114">Prerequisites</span></span>  
 <span data-ttu-id="3eec6-115">En este tutorial se requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3eec6-115">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="3eec6-116">Este tutorial utiliza una carpeta dedicada ("c:\linqtest7") que contiene los archivos.</span><span class="sxs-lookup"><span data-stu-id="3eec6-116">This walkthrough uses a dedicated folder ("c:\linqtest7") to hold files.</span></span> <span data-ttu-id="3eec6-117">Cree esta carpeta antes de empezar el tutorial.</span><span class="sxs-lookup"><span data-stu-id="3eec6-117">Create this folder before you begin the walkthrough.</span></span>  
  
-   <span data-ttu-id="3eec6-118">Base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="3eec6-118">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="3eec6-119">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del sitio web de descargas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3eec6-119">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="3eec6-120">Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="3eec6-120">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="3eec6-121">Después de haber descargado la base de datos, copie el archivo northwnd.mdf en la carpeta c:\linqtest7.</span><span class="sxs-lookup"><span data-stu-id="3eec6-121">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest7 folder.</span></span>  
  
-   <span data-ttu-id="3eec6-122">Un archivo de código de C# generado a partir de la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="3eec6-122">A C# code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="3eec6-123">Este tutorial se escribió utilizando la herramienta SqlMetal con la línea de comandos siguiente:</span><span class="sxs-lookup"><span data-stu-id="3eec6-123">This walkthrough was written by using the SqlMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="3eec6-124">**SqlMetal /code:"c:\linqtest7\northwind.cs" /language:csharp "c:\linqtest7\northwnd.mdf" /sprocs /functions / plural**</span><span class="sxs-lookup"><span data-stu-id="3eec6-124">**sqlmetal /code:"c:\linqtest7\northwind.cs" /language:csharp "c:\linqtest7\northwnd.mdf" /sprocs /functions /pluralize**</span></span>  
  
     <span data-ttu-id="3eec6-125">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="3eec6-125">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="3eec6-126">Información general</span><span class="sxs-lookup"><span data-stu-id="3eec6-126">Overview</span></span>  
 <span data-ttu-id="3eec6-127">Este tutorial se compone de seis tareas principales:</span><span class="sxs-lookup"><span data-stu-id="3eec6-127">This walkthrough consists of six main tasks:</span></span>  
  
-   <span data-ttu-id="3eec6-128">Configurar la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solución en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3eec6-128">Setting up the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
-   <span data-ttu-id="3eec6-129">Agregar el ensamblado System.Data.Linq al proyecto.</span><span class="sxs-lookup"><span data-stu-id="3eec6-129">Adding the System.Data.Linq assembly to the project.</span></span>  
  
-   <span data-ttu-id="3eec6-130">Agregar el archivo de código de la base de datos al proyecto.</span><span class="sxs-lookup"><span data-stu-id="3eec6-130">Adding the database code file to the project.</span></span>  
  
-   <span data-ttu-id="3eec6-131">Crear una conexión con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3eec6-131">Creating a connection with the database.</span></span>  
  
-   <span data-ttu-id="3eec6-132">Configurar la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="3eec6-132">Setting up the user interface.</span></span>  
  
-   <span data-ttu-id="3eec6-133">Ejecutar y probar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3eec6-133">Running and testing the application.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="3eec6-134">Crear una solución LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="3eec6-134">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="3eec6-135">En esta primera tarea, se creará una solución de Visual Studio que contiene las referencias necesarias para compilar y ejecutar un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="3eec6-135">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="3eec6-136">Para crear una solución LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="3eec6-136">To create a LINQ to SQL solution</span></span>  
  
1.  <span data-ttu-id="3eec6-137">En Visual Studio **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-137">On the Visual Studio **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="3eec6-138">En el **tipos de proyecto** panel en el **nuevo proyecto** cuadro de diálogo, haga clic en **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-138">In the **Project types** pane in the **New Project** dialog box, click **Visual C#**.</span></span>  
  
3.  <span data-ttu-id="3eec6-139">En el panel **Plantillas** , haga clic en **Aplicación de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-139">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4.  <span data-ttu-id="3eec6-140">En el **nombre** , escriba **SprocOnlyApp**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-140">In the **Name** box, type **SprocOnlyApp**.</span></span>  
  
5.  <span data-ttu-id="3eec6-141">En el **ubicación** cuadro, compruebe dónde desea almacenar los archivos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="3eec6-141">In the **Location** box, verify where you want to store your project files.</span></span>  
  
6.  <span data-ttu-id="3eec6-142">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-142">Click **OK**.</span></span>  
  
     <span data-ttu-id="3eec6-143">Se abre el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3eec6-143">The Windows Forms Designer opens.</span></span>  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a><span data-ttu-id="3eec6-144">Agregar la referencia al ensamblado de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="3eec6-144">Adding the LINQ to SQL Assembly Reference</span></span>  
 <span data-ttu-id="3eec6-145">El ensamblado de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no está incluido en la plantilla Aplicación de Windows Forms estándar.</span><span class="sxs-lookup"><span data-stu-id="3eec6-145">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly is not included in the standard Windows Forms Application template.</span></span> <span data-ttu-id="3eec6-146">Tendrá que agregar el ensamblado como se explica en los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3eec6-146">You will have to add the assembly yourself, as explained in the following steps:</span></span>  
  
#### <a name="to-add-systemdatalinqdll"></a><span data-ttu-id="3eec6-147">Para agregar System.Data.Linq.dll</span><span class="sxs-lookup"><span data-stu-id="3eec6-147">To add System.Data.Linq.dll</span></span>  
  
1.  <span data-ttu-id="3eec6-148">En **el Explorador de soluciones**, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-148">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="3eec6-149">En el **Agregar referencia** cuadro de diálogo, haga clic en **.NET**, haga clic en el ensamblado System.Data.Linq y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-149">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="3eec6-150">El ensamblado se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="3eec6-150">The assembly is added to the project.</span></span>  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="3eec6-151">Agregar el archivo de código de Northwind al proyecto</span><span class="sxs-lookup"><span data-stu-id="3eec6-151">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="3eec6-152">En este paso se asume que ha utilizado la herramienta SqlMetal para generar un archivo de código a partir de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="3eec6-152">This step assumes that you have used the SqlMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="3eec6-153">Para obtener más información, vea la sección Requisitos previos, anteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="3eec6-153">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="3eec6-154">Para agregar el archivo de código de Northwind al proyecto</span><span class="sxs-lookup"><span data-stu-id="3eec6-154">To add the northwind code file to the project</span></span>  
  
1.  <span data-ttu-id="3eec6-155">En el **proyecto** menú, haga clic en **Agregar elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-155">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2.  <span data-ttu-id="3eec6-156">En el **Agregar elemento existente** cuadro de diálogo Mover a c:\linqtest7\northwind.cs y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-156">In the **Add Existing Item** dialog box, move to c:\linqtest7\northwind.cs, and then click **Add**.</span></span>  
  
     <span data-ttu-id="3eec6-157">El archivo northwind.cs se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="3eec6-157">The northwind.cs file is added to the project.</span></span>  
  
## <a name="creating-a-database-connection"></a><span data-ttu-id="3eec6-158">Crear una conexión de base de datos</span><span class="sxs-lookup"><span data-stu-id="3eec6-158">Creating a Database Connection</span></span>  
 <span data-ttu-id="3eec6-159">En este paso, definirá la conexión con la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="3eec6-159">In this step, you define the connection to the Northwind sample database.</span></span> <span data-ttu-id="3eec6-160">En este tutorial se utiliza "c:\linqtest7\northwnd.mdf" como ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="3eec6-160">This walkthrough uses "c:\linqtest7\northwnd.mdf" as the path.</span></span>  
  
#### <a name="to-create-the-database-connection"></a><span data-ttu-id="3eec6-161">Para crear la conexión a la base de datos</span><span class="sxs-lookup"><span data-stu-id="3eec6-161">To create the database connection</span></span>  
  
1.  <span data-ttu-id="3eec6-162">En **el Explorador de soluciones**, haga clic en **Form1.cs**y, a continuación, haga clic en **ver código**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-162">In **Solution Explorer**, right-click **Form1.cs**, and then click **View Code**.</span></span>  
  
2.  <span data-ttu-id="3eec6-163">Escriba el código siguiente en la clase `Form1`:</span><span class="sxs-lookup"><span data-stu-id="3eec6-163">Type the following code into the `Form1` class:</span></span>  
  
     [!code-csharp[DLinqWalk4CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#1)]  
  
## <a name="setting-up-the-user-interface"></a><span data-ttu-id="3eec6-164">Configurar la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="3eec6-164">Setting up the User Interface</span></span>  
 <span data-ttu-id="3eec6-165">En esta tarea preparará una interfaz para que los usuarios puedan ejecutar procedimientos almacenados para tener acceso a los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3eec6-165">In this task you set up an interface so that users can execute stored procedures to access data in the database.</span></span> <span data-ttu-id="3eec6-166">En las aplicaciones que desarrolla con este tutorial, los usuarios pueden tener acceso a los datos de la base de datos únicamente mediante los procedimientos almacenados que están incrustados en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3eec6-166">In the applications that you are developing with this walkthrough, users can access data in the database only by using the stored procedures embedded in the application.</span></span>  
  
#### <a name="to-set-up-the-user-interface"></a><span data-ttu-id="3eec6-167">Para configurar la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="3eec6-167">To set up the user interface</span></span>  
  
1.  <span data-ttu-id="3eec6-168">Volver a las ventanas de diseñador de formularios (**Form1.cs [Diseño]**).</span><span class="sxs-lookup"><span data-stu-id="3eec6-168">Return to the Windows Forms Designer (**Form1.cs[Design]**).</span></span>  
  
2.  <span data-ttu-id="3eec6-169">En el menú **Ver** , haga clic en **Cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-169">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="3eec6-170">Se abrirá el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="3eec6-170">The toolbox opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3eec6-171">Haga clic en el **Ocultar automáticamente** PIN para mantener abierto el cuadro de herramientas mientras realiza los demás pasos de esta sección.</span><span class="sxs-lookup"><span data-stu-id="3eec6-171">Click the **AutoHide** pushpin to keep the toolbox open while you perform the remaining steps in this section.</span></span>  
  
3.  <span data-ttu-id="3eec6-172">Arrastre dos botones, dos cuadros de texto y dos etiquetas desde el cuadro de herramientas en **Form1**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-172">Drag two buttons, two text boxes, and two labels from the toolbox onto **Form1**.</span></span>  
  
     <span data-ttu-id="3eec6-173">Organice los controles como en la ilustración anexa.</span><span class="sxs-lookup"><span data-stu-id="3eec6-173">Arrange the controls as in the accompanying illustration.</span></span> <span data-ttu-id="3eec6-174">Expanda **Form1** para que los controles tengan el espacio necesario.</span><span class="sxs-lookup"><span data-stu-id="3eec6-174">Expand **Form1** so that the controls fit easily.</span></span>  
  
4.  <span data-ttu-id="3eec6-175">Haga clic en **label1**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-175">Right-click **label1**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="3eec6-176">Cambiar el **texto** propiedad de **label1** a **Enter OrderID:**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-176">Change the **Text** property from **label1** to **Enter OrderID:**.</span></span>  
  
6.  <span data-ttu-id="3eec6-177">En la misma manera para **label2**, cambie la **texto** propiedad de **label2** a **Enter CustomerID:**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-177">In the same way for **label2**, change the **Text** property from **label2** to **Enter CustomerID:**.</span></span>  
  
7.  <span data-ttu-id="3eec6-178">En la misma manera, cambie la **texto** propiedad **button1** a **Order Details**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-178">In the same way, change the **Text** property for **button1** to **Order Details**.</span></span>  
  
8.  <span data-ttu-id="3eec6-179">Cambiar el **texto** propiedad **button2** a **el historial de pedidos**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-179">Change the **Text** property for **button2** to **Order History**.</span></span>  
  
     <span data-ttu-id="3eec6-180">Amplíe los controles de botón para que todo el texto esté visible.</span><span class="sxs-lookup"><span data-stu-id="3eec6-180">Widen the button controls so that all the text is visible.</span></span>  
  
#### <a name="to-handle-button-clicks"></a><span data-ttu-id="3eec6-181">Para administrar los clics de botón</span><span class="sxs-lookup"><span data-stu-id="3eec6-181">To handle button clicks</span></span>  
  
1.  <span data-ttu-id="3eec6-182">Haga doble clic en **Order Details** en **Form1** para abrir el controlador de eventos de button1 en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="3eec6-182">Double-click **Order Details** on **Form1** to open the button1 event handler in the code editor.</span></span>  
  
2.  <span data-ttu-id="3eec6-183">Escriba el código siguiente en el controlador `button1`:</span><span class="sxs-lookup"><span data-stu-id="3eec6-183">Type the following code into the `button1` handler:</span></span>  
  
     [!code-csharp[DLinqWalk4CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#2)]  
  
3.  <span data-ttu-id="3eec6-184">Ahora haga doble clic en **button2** en **Form1** para abrir el `button2` controlador</span><span class="sxs-lookup"><span data-stu-id="3eec6-184">Now double-click **button2** on **Form1** to open the `button2` handler</span></span>  
  
4.  <span data-ttu-id="3eec6-185">Escriba el código siguiente en el controlador `button2`:</span><span class="sxs-lookup"><span data-stu-id="3eec6-185">Type the following code into the `button2` handler:</span></span>  
  
     [!code-csharp[DLinqWalk4CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#3)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="3eec6-186">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="3eec6-186">Testing the Application</span></span>  
 <span data-ttu-id="3eec6-187">Ha llegado el momento de probar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3eec6-187">Now it is time to test your application.</span></span> <span data-ttu-id="3eec6-188">Observe que su contacto con el almacén de datos se limita a las acciones que puedan realizar los dos procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="3eec6-188">Note that your contact with the datastore is limited to whatever actions the two stored procedures can take.</span></span> <span data-ttu-id="3eec6-189">Esas acciones son: devolver los productos incluidos para cualquier orderID que escriba o devolver un historial de los productos solicitados para cualquier CustomerID que escriba.</span><span class="sxs-lookup"><span data-stu-id="3eec6-189">Those actions are to return the products included for any orderID you enter, or to return a history of products ordered for any CustomerID you enter.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="3eec6-190">Para probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="3eec6-190">To test the application</span></span>  
  
1.  <span data-ttu-id="3eec6-191">Presione F5 para iniciar la depuración.</span><span class="sxs-lookup"><span data-stu-id="3eec6-191">Press F5 to start debugging.</span></span>  
  
     <span data-ttu-id="3eec6-192">Aparece Form1.</span><span class="sxs-lookup"><span data-stu-id="3eec6-192">Form1 appears.</span></span>  
  
2.  <span data-ttu-id="3eec6-193">En el **Enter OrderID** , escriba `10249`y, a continuación, haga clic en **Order Details**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-193">In the **Enter OrderID** box, type `10249`, and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="3eec6-194">Un cuadro de mensaje muestra los productos incluidos en el pedido 10249.</span><span class="sxs-lookup"><span data-stu-id="3eec6-194">A message box lists the products included in order 10249.</span></span>  
  
     <span data-ttu-id="3eec6-195">Haga clic en **Aceptar** para cerrar el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="3eec6-195">Click **OK** to close the message box.</span></span>  
  
3.  <span data-ttu-id="3eec6-196">En el **Enter CustomerID** , escriba `ALFKI`y, a continuación, haga clic en **el historial de pedidos**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-196">In the **Enter CustomerID** box, type `ALFKI`, and then click **Order History**.</span></span>  
  
     <span data-ttu-id="3eec6-197">Aparece un cuadro de mensaje con el historial de pedidos del cliente ALFKI.</span><span class="sxs-lookup"><span data-stu-id="3eec6-197">A message box appears that lists the order history for customer ALFKI.</span></span>  
  
     <span data-ttu-id="3eec6-198">Haga clic en **Aceptar** para cerrar el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="3eec6-198">Click **OK** to close the message box.</span></span>  
  
4.  <span data-ttu-id="3eec6-199">En el **Enter OrderID** , escriba `123`y, a continuación, haga clic en **Order Details**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-199">In the **Enter OrderID** box, type `123`, and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="3eec6-200">Aparece un cuadro de mensaje con el texto "No results".</span><span class="sxs-lookup"><span data-stu-id="3eec6-200">A message box appears that displays "No results."</span></span>  
  
     <span data-ttu-id="3eec6-201">Haga clic en **Aceptar** para cerrar el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="3eec6-201">Click **OK** to close the message box.</span></span>  
  
5.  <span data-ttu-id="3eec6-202">En el **depurar** menú, haga clic en **detener la depuración**.</span><span class="sxs-lookup"><span data-stu-id="3eec6-202">On the **Debug** menu, click **Stop debugging**.</span></span>  
  
     <span data-ttu-id="3eec6-203">La sesión de depuración se cierra.</span><span class="sxs-lookup"><span data-stu-id="3eec6-203">The debug session closes.</span></span>  
  
6.  <span data-ttu-id="3eec6-204">Cuando termine de experimentar, haga clic en **cerrar proyecto** en el **archivo** menú y guarde el proyecto cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="3eec6-204">If you have finished experimenting, you can click **Close Project** on the **File** menu, and save your project when you are prompted.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3eec6-205">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3eec6-205">Next Steps</span></span>  
 <span data-ttu-id="3eec6-206">Puede mejorar este proyecto realizando algunos cambios.</span><span class="sxs-lookup"><span data-stu-id="3eec6-206">You can enhance this project by making some changes.</span></span> <span data-ttu-id="3eec6-207">Por ejemplo, podría enumerar los procedimientos almacenados disponibles en un cuadro de lista y permitir que el usuario seleccione qué procedimientos debe ejecutar.</span><span class="sxs-lookup"><span data-stu-id="3eec6-207">For example, you could list available stored procedures in a list box and have the user select which procedures to execute.</span></span> <span data-ttu-id="3eec6-208">También podría transmitir el resultado de los informes a un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="3eec6-208">You could also stream the output of the reports to a text file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eec6-209">Vea también</span><span class="sxs-lookup"><span data-stu-id="3eec6-209">See Also</span></span>  
 [<span data-ttu-id="3eec6-210">Aprendizaje con tutoriales</span><span class="sxs-lookup"><span data-stu-id="3eec6-210">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)  
 [<span data-ttu-id="3eec6-211">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="3eec6-211">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
