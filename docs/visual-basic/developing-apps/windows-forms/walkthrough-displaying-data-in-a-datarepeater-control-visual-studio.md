---
title: 'Tutorial: Mostrar los datos enlazados en un control DataRepeater (Visual Studio)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, walkthrough
ms.assetid: 65dcdb95-6c3e-47cc-987d-190000f71653
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 93072bf30c8ee2a4a44c4862de0882072c298f8b
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/10/2018
---
# <a name="walkthrough-displaying-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="a9f46-102">Tutorial: Mostrar los datos enlazados en un control DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="a9f46-102">Walkthrough: Displaying Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="a9f46-103">En este tutorial se proporciona un escenario básico de principio a fin para mostrar datos enlazados en un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a9f46-103">This walkthrough provides a basic start-to-finish scenario for displaying bound data in a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="a9f46-104">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="a9f46-104">Prerequisite</span></span>  
 <span data-ttu-id="a9f46-105">Este tutorial requiere la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="a9f46-105">This walkthrough requires the Northwind sample database.</span></span>  
  
 <span data-ttu-id="a9f46-106">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del [Centro de descarga de Microsoft](http://go.microsoft.com/fwlink/?LinkID=98088).</span><span class="sxs-lookup"><span data-stu-id="a9f46-106">If you do not have this database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088).</span></span> <span data-ttu-id="a9f46-107">Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="a9f46-107">For instructions, see [Downloading Sample Databases](../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="a9f46-108">Información general</span><span class="sxs-lookup"><span data-stu-id="a9f46-108">Overview</span></span>  
 <span data-ttu-id="a9f46-109">La primera parte de este tutorial se compone de cuatro tareas principales:</span><span class="sxs-lookup"><span data-stu-id="a9f46-109">The first part of this walkthrough consists of four main tasks:</span></span>  
  
-   <span data-ttu-id="a9f46-110">Crear una solución.</span><span class="sxs-lookup"><span data-stu-id="a9f46-110">Creating a solution.</span></span>  
  
-   <span data-ttu-id="a9f46-111">Agregar un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a9f46-111">Adding a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="a9f46-112">Agregar un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a9f46-112">Adding a data source.</span></span>  
  
-   <span data-ttu-id="a9f46-113">Agregar controles enlazados a datos.</span><span class="sxs-lookup"><span data-stu-id="a9f46-113">Adding data-bound controls.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-a-datarepeater-solution"></a><span data-ttu-id="a9f46-114">Crear una solución DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a9f46-114">Creating a DataRepeater Solution</span></span>  
 <span data-ttu-id="a9f46-115">En el primer paso, creará un proyecto y una solución.</span><span class="sxs-lookup"><span data-stu-id="a9f46-115">In the first step, you create a project and solution.</span></span>  
  
#### <a name="to-create-a-datarepeater-solution"></a><span data-ttu-id="a9f46-116">Para crear una solución DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a9f46-116">To create a DataRepeater solution</span></span>  
  
1.  <span data-ttu-id="a9f46-117">En el menú **Archivo** de Visual Studio, haga clic en **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="a9f46-117">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2.  <span data-ttu-id="a9f46-118">En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto** , expanda **Visual Basic**y, a continuación, haga clic en **Windows**.</span><span class="sxs-lookup"><span data-stu-id="a9f46-118">In the **Project types** pane in the **New Project** dialog box, expand **Visual Basic**, and then click **Windows**.</span></span>  
  
3.  <span data-ttu-id="a9f46-119">En el panel **Plantillas** , haga clic en **Aplicación de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="a9f46-119">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4.  <span data-ttu-id="a9f46-120">En el cuadro **Nombre** , escriba `DataRepeaterApp`.</span><span class="sxs-lookup"><span data-stu-id="a9f46-120">In the **Name** box, type `DataRepeaterApp`.</span></span>  
  
5.  <span data-ttu-id="a9f46-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a9f46-121">Click **OK**.</span></span>  
  
     <span data-ttu-id="a9f46-122">Se abre el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a9f46-122">The Windows Forms Designer opens.</span></span>  
  
6.  <span data-ttu-id="a9f46-123">Seleccione el formulario en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a9f46-123">Select the form in the Windows Forms Designer.</span></span> <span data-ttu-id="a9f46-124">En la ventana **Propiedades** , establezca la propiedad **Size** en `800, 700`.</span><span class="sxs-lookup"><span data-stu-id="a9f46-124">In the **Properties** window, set the **Size** property to `800, 700`.</span></span>  
  
## <a name="adding-a-datarepeater-control"></a><span data-ttu-id="a9f46-125">Agregar un control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a9f46-125">Adding a DataRepeater Control</span></span>  
 <span data-ttu-id="a9f46-126">En este paso, agregará un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> al formulario.</span><span class="sxs-lookup"><span data-stu-id="a9f46-126">In this step, you add a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to the form.</span></span>  
  
#### <a name="to-add-a-datarepeater-control"></a><span data-ttu-id="a9f46-127">Para agregar un control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a9f46-127">To add a DataRepeater control</span></span>  
  
1.  <span data-ttu-id="a9f46-128">En el menú **Ver** , haga clic en **Cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="a9f46-128">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="a9f46-129">Se abrirá el **Cuadro de herramientas** .</span><span class="sxs-lookup"><span data-stu-id="a9f46-129">The **Toolbox** opens.</span></span>  
  
2.  <span data-ttu-id="a9f46-130">Seleccionar la pestaña **Visual Basic PowerPacks** .</span><span class="sxs-lookup"><span data-stu-id="a9f46-130">Select the **Visual Basic PowerPacks** tab.</span></span>  
  
3.  <span data-ttu-id="a9f46-131">Arrastre un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> a **Form1**.</span><span class="sxs-lookup"><span data-stu-id="a9f46-131">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control onto **Form1**.</span></span>  
  
4.  <span data-ttu-id="a9f46-132">En la ventana Propiedades, establezca la propiedad **Location** en `0, 25`.</span><span class="sxs-lookup"><span data-stu-id="a9f46-132">In the Properties window, set the **Location** property to `0, 25`.</span></span>  
  
5.  <span data-ttu-id="a9f46-133">Establezca la propiedad **Size** en `460, 600`.</span><span class="sxs-lookup"><span data-stu-id="a9f46-133">Set the **Size** property to `460, 600`.</span></span>  
  
## <a name="adding-a-data-source"></a><span data-ttu-id="a9f46-134">Agregar un origen de datos</span><span class="sxs-lookup"><span data-stu-id="a9f46-134">Adding a Data Source</span></span>  
 <span data-ttu-id="a9f46-135">En este paso, agregará un origen de datos para el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a9f46-135">In this step, you add a data source for the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-add-a-data-source"></a><span data-ttu-id="a9f46-136">Para agregar un origen de datos</span><span class="sxs-lookup"><span data-stu-id="a9f46-136">To add a data source</span></span>  
  
1.  <span data-ttu-id="a9f46-137">En el menú **Datos** , haga clic en **Mostrar orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="a9f46-137">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
2.  <span data-ttu-id="a9f46-138">En la ventana **Orígenes de datos** , seleccione **Agregar nuevo origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="a9f46-138">In the **Data Sources** window, click **Add New Data Source**.</span></span>  
  
3.  <span data-ttu-id="a9f46-139">Seleccione **Base de datos** en la página **Elegir un tipo de datos de origen** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a9f46-139">Select **Database** on the **Choose a Data Source Type** page, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="a9f46-140">En la página **Elegir la conexión de datos** , siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="a9f46-140">On the **Choose Your Data Connection** page, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="a9f46-141">Si existe alguna conexión de datos a la base de datos de ejemplo Northwind disponible en el cuadro de lista desplegable, haga clic en ella.</span><span class="sxs-lookup"><span data-stu-id="a9f46-141">If a data connection to the Northwind sample database is available in the drop-down list, click it.</span></span>  
  
         <span data-ttu-id="a9f46-142">O bien</span><span class="sxs-lookup"><span data-stu-id="a9f46-142">-or-</span></span>  
  
    -   <span data-ttu-id="a9f46-143">Haga clic en **Nueva conexión** para configurar una nueva conexión de datos.</span><span class="sxs-lookup"><span data-stu-id="a9f46-143">Click **New Connection** to configure a new data connection.</span></span> <span data-ttu-id="a9f46-144">Para obtener más información, consulte [agregar nuevas conexiones](/visualstudio/data-tools/add-new-connections).</span><span class="sxs-lookup"><span data-stu-id="a9f46-144">For more information, see [Add new connections](/visualstudio/data-tools/add-new-connections).</span></span>  
  
5.  <span data-ttu-id="a9f46-145">Si la base de datos requiere una contraseña, seleccione la opción para incluir datos confidenciales y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a9f46-145">If the database requires a password, select the option to include sensitive data, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a9f46-146">Si aparece un cuadro de diálogo, haga clic en **Sí** para guardar el archivo en su proyecto.</span><span class="sxs-lookup"><span data-stu-id="a9f46-146">If a dialog box appears, click **Yes** to save the file to your project.</span></span>  
  
6.  <span data-ttu-id="a9f46-147">Haga clic en **Siguiente** en la página **Guardar la cadena de conexión en el archivo de configuración de la aplicación** .</span><span class="sxs-lookup"><span data-stu-id="a9f46-147">Click **Next** on the **Save Connection String to the Application Configuration file** page.</span></span>  
  
7.  <span data-ttu-id="a9f46-148">Expanda el nodo **Tablas** en la página **Elija los objetos de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="a9f46-148">Expand the **Tables** node on the **Choose Your Database Objects** page.</span></span>  
  
8.  <span data-ttu-id="a9f46-149">Seleccione las casillas situadas junto a las tablas **Customers** y **Orders** y después haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a9f46-149">Select the check boxes next to the **Customers** and **Orders** tables, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="a9f46-150">**NorthwindDataSet** se agrega al proyecto y las tablas **Customers** y **Orders** aparecen en la ventana **Orígenes de datos** .</span><span class="sxs-lookup"><span data-stu-id="a9f46-150">**NorthwindDataSet** is added to your project and the **Customers** and **Orders** tables appear in the **Data Sources** window.</span></span>  
  
## <a name="adding-data-bound-controls"></a><span data-ttu-id="a9f46-151">Agregar controles enlazados a datos</span><span class="sxs-lookup"><span data-stu-id="a9f46-151">Adding Data-Bound Controls</span></span>  
 <span data-ttu-id="a9f46-152">En este paso, agregará controles enlazados a datos a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span><span class="sxs-lookup"><span data-stu-id="a9f46-152">In this step, you add data-bound controls to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
#### <a name="to-add-data-bound-controls"></a><span data-ttu-id="a9f46-153">Para agregar controles enlazados a datos</span><span class="sxs-lookup"><span data-stu-id="a9f46-153">To add data-bound controls</span></span>  
  
1.  <span data-ttu-id="a9f46-154">En la ventana **Orígenes de datos** , seleccione el nodo de nivel superior para la tabla **Customers** .</span><span class="sxs-lookup"><span data-stu-id="a9f46-154">In the **Data Sources** window, select the top-level node for the **Customers** table.</span></span>  
  
2.  <span data-ttu-id="a9f46-155">Cambie el tipo de colocación de la tabla a **Detalles** haciendo clic en **Detalles** en la lista desplegable del nodo de la tabla.</span><span class="sxs-lookup"><span data-stu-id="a9f46-155">Change the drop type of the table to **Details** by clicking **Details** in the drop-down list on the table node.</span></span>  
  
3.  <span data-ttu-id="a9f46-156">Seleccione el nodo de la tabla **Customers** y arrástrelo a la región de la plantilla de elemento (la región superior) del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a9f46-156">Select the **Customers** table node and drag it onto the item template region (the upper region) of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="a9f46-157">Se agrega un control <xref:System.Windows.Forms.BindingNavigator> al formulario y se agregan los componentes **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**y **CustomersBindingNavigator** a la bandeja de componentes.</span><span class="sxs-lookup"><span data-stu-id="a9f46-157">A <xref:System.Windows.Forms.BindingNavigator> control is added to the form, and the **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**, and **CustomersBindingNavigator** components are added to the Component Tray.</span></span>  
  
4.  <span data-ttu-id="a9f46-158">Seleccione todos los campos y sus etiquetas asociadas y colóquelos cerca del borde izquierdo de la región de la plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="a9f46-158">Select all of the fields and their associated labels and position them near the left edge of the item template region.</span></span>  
  
5.  <span data-ttu-id="a9f46-159">Seleccione los cinco últimos campos (**Región**, **Código postal**, **País**, **Teléfono**y **Fax**) y sus etiquetas asociadas y muévalos arriba y a la derecha de los seis primeros campos.</span><span class="sxs-lookup"><span data-stu-id="a9f46-159">Select the last five fields (**Region**, **Postal Code**, **Country**, **Phone**, and **Fax**) and their associated labels and move them up and to the right of the first six fields.</span></span>  
  
6.  <span data-ttu-id="a9f46-160">Seleccione la plantilla de elemento (la región superior del control).</span><span class="sxs-lookup"><span data-stu-id="a9f46-160">Select the item template (the upper region of the control).</span></span>  
  
7.  <span data-ttu-id="a9f46-161">En la ventana Propiedades, establezca la propiedad **Size** en `427, 170`.</span><span class="sxs-lookup"><span data-stu-id="a9f46-161">In the Properties window, set the **Size** property to `427, 170`.</span></span>  
  
 <span data-ttu-id="a9f46-162">En este punto, tendrá una aplicación operativa que mostrará una lista repetitiva de clientes.</span><span class="sxs-lookup"><span data-stu-id="a9f46-162">At this point, you have a working application that will display a repeating list of customers.</span></span> <span data-ttu-id="a9f46-163">Puede presionar F5 para ejecutar la aplicación, cambiar los datos y agregar o eliminar registros de cliente.</span><span class="sxs-lookup"><span data-stu-id="a9f46-163">You can press F5 to run the application, change the data, and add or delete customer records.</span></span>  
  
 <span data-ttu-id="a9f46-164">En los siguientes pasos opcionales, obtendrá información sobre cómo personalizar el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a9f46-164">In the next optional steps, you will learn how to customize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="next-steps-optional"></a><span data-ttu-id="a9f46-165">Pasos siguientes (opcionales)</span><span class="sxs-lookup"><span data-stu-id="a9f46-165">Next Steps (Optional)</span></span>  
 <span data-ttu-id="a9f46-166">Esta parte del tutorial consta de cuatro tareas opcionales:</span><span class="sxs-lookup"><span data-stu-id="a9f46-166">This part of the walkthrough consists of four optional tasks:</span></span>  
  
-   <span data-ttu-id="a9f46-167">Cambiar la apariencia del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a9f46-167">Changing the appearance of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="a9f46-168">Impedir que los usuarios agreguen o eliminen registros.</span><span class="sxs-lookup"><span data-stu-id="a9f46-168">Preventing users from adding or deleting records.</span></span>  
  
-   <span data-ttu-id="a9f46-169">Agregar capacidad de búsqueda al control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a9f46-169">Adding search capability to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="a9f46-170">Agregar una tabla maestra y de detalles al control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a9f46-170">Adding a master and detail table to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="changing-the-appearance-of-the-datarepeater-control"></a><span data-ttu-id="a9f46-171">Cambiar la apariencia del control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a9f46-171">Changing the Appearance of the DataRepeater Control</span></span>  
 <span data-ttu-id="a9f46-172">En este paso opcional, cambiará el valor `BackColor` del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="a9f46-172">In this optional step, you change the `BackColor` of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at design time.</span></span> <span data-ttu-id="a9f46-173">También agregará código para mostrar las filas en colores alternos y cambiar el valor `ForeColor` de una etiqueta de manera condicional.</span><span class="sxs-lookup"><span data-stu-id="a9f46-173">You also add code to display rows in alternating colors and to change a label's `ForeColor` conditionally.</span></span>  
  
#### <a name="to-change-the-appearance-of-the-control"></a><span data-ttu-id="a9f46-174">Para cambiar la apariencia del control</span><span class="sxs-lookup"><span data-stu-id="a9f46-174">To change the appearance of the control</span></span>  
  
1.  <span data-ttu-id="a9f46-175">En el Diseñador de Windows Forms, seleccione la región principal (inferior) del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a9f46-175">In the Windows Forms Designer, select the main (lower) region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="a9f46-176">En la ventana Propiedades, establezca la propiedad `BackColor` en blanco.</span><span class="sxs-lookup"><span data-stu-id="a9f46-176">In the Properties window, set the `BackColor` property to white.</span></span>  
  
3.  <span data-ttu-id="a9f46-177">Haga doble clic en <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> para abrir el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="a9f46-177">Double-click the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> to open the Code Editor.</span></span>  
  
4.  <span data-ttu-id="a9f46-178">En el Editor de código, en la lista desplegable de eventos, haga clic en **DrawItem**.</span><span class="sxs-lookup"><span data-stu-id="a9f46-178">In the Code Editor, in the Event drop-down list, click **DrawItem**.</span></span>  
  
5.  <span data-ttu-id="a9f46-179">En el controlador de eventos de <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> , agregue el código siguiente para alternar el valor `BackColor`.</span><span class="sxs-lookup"><span data-stu-id="a9f46-179">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to alternate the `BackColor`:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]  
  
6.  <span data-ttu-id="a9f46-180">En el controlador de eventos de <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> , agregue el código siguiente para cambiar el valor `ForeColor` de una etiqueta según una condición:</span><span class="sxs-lookup"><span data-stu-id="a9f46-180">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to change the `ForeColor` of a label depending on a condition:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]  
  
7.  <span data-ttu-id="a9f46-181">Presione F5 para ejecutar la aplicación y ver las personalizaciones.</span><span class="sxs-lookup"><span data-stu-id="a9f46-181">Press F5 to run the application and see the customizations.</span></span>  
  
## <a name="preventing-users-from-adding-or-deleting-records"></a><span data-ttu-id="a9f46-182">Impedir que los usuarios agreguen o eliminen registros</span><span class="sxs-lookup"><span data-stu-id="a9f46-182">Preventing Users from Adding or Deleting Records</span></span>  
 <span data-ttu-id="a9f46-183">En este paso opcional, agregará código que impida que los usuarios agreguen o eliminen registros en el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a9f46-183">In this optional step, you add code that prevents users from adding or deleting records in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-prevent-users-from-adding-and-deleting-records"></a><span data-ttu-id="a9f46-184">Para impedir que los usuarios agreguen y eliminen registros</span><span class="sxs-lookup"><span data-stu-id="a9f46-184">To prevent users from adding and deleting records</span></span>  
  
1.  <span data-ttu-id="a9f46-185">En el Diseñador de Windows Forms, haga doble clic en el formulario para abrir el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="a9f46-185">In the Windows Forms Designer, double-click the form to open the Code Editor.</span></span>  
  
2.  <span data-ttu-id="a9f46-186">Agregue el código siguiente al evento `Form_Load` :</span><span class="sxs-lookup"><span data-stu-id="a9f46-186">Add the following code to the `Form_Load` event:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]  
  
3.  <span data-ttu-id="a9f46-187">En la lista desplegable Nombre de clase, haga clic en **BindingNavigatorDeleteItem**.</span><span class="sxs-lookup"><span data-stu-id="a9f46-187">In the Class Name drop-down list, click **BindingNavigatorDeleteItem**.</span></span> <span data-ttu-id="a9f46-188">En la lista desplegable Nombre de método, haga clic en **EnabledChanged**.</span><span class="sxs-lookup"><span data-stu-id="a9f46-188">In the Method Name drop-down list, click **EnabledChanged**.</span></span>  
  
4.  <span data-ttu-id="a9f46-189">Agregue el código siguiente al controlador de eventos `BindingNavigatorDeleteItem_EnabledChanged` :</span><span class="sxs-lookup"><span data-stu-id="a9f46-189">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="a9f46-190">Este paso es necesario porque <xref:System.Windows.Forms.BindingSource> habilitará el botón **DeleteItem** cada vez que cambie el registro actual.</span><span class="sxs-lookup"><span data-stu-id="a9f46-190">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
5.  <span data-ttu-id="a9f46-191">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9f46-191">Press F5 to run the application.</span></span> <span data-ttu-id="a9f46-192">Observe que el botón **DeleteItem** está deshabilitado y que no se pueden eliminar elementos presionando la tecla Supr.</span><span class="sxs-lookup"><span data-stu-id="a9f46-192">Notice that the **DeleteItem** button is disabled and that you cannot delete items by pressing the DELETE key.</span></span>  
  
## <a name="adding-search-capability-to-the-datarepeater-control"></a><span data-ttu-id="a9f46-193">Agregar capacidad de búsqueda al control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a9f46-193">Adding Search Capability to the DataRepeater Control</span></span>  
 <span data-ttu-id="a9f46-194">En este paso opcional, implementará la capacidad de búsqueda de un valor en el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a9f46-194">In this optional step, you implement the capability to search for a value in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="a9f46-195">Si se encuentra la cadena de búsqueda, el control selecciona el elemento que contiene el valor y desplaza el elemento en la vista.</span><span class="sxs-lookup"><span data-stu-id="a9f46-195">If the search string is found, the control selects the item that contains the value and scrolls the item into view.</span></span>  
  
#### <a name="to-add-search-capability"></a><span data-ttu-id="a9f46-196">Para agregar capacidad de búsqueda</span><span class="sxs-lookup"><span data-stu-id="a9f46-196">To add search capability</span></span>  
  
1.  <span data-ttu-id="a9f46-197">Arrastre un control <xref:System.Windows.Forms.TextBox> desde el **Cuadro de herramientas** hasta el formulario que contenga el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a9f46-197">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="a9f46-198">Colóquelo bajo el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a9f46-198">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="a9f46-199">En la ventana Propiedades, cambie la propiedad **Name** a **SearchTextBox**.</span><span class="sxs-lookup"><span data-stu-id="a9f46-199">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="a9f46-200">Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** hasta el formulario que contenga el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a9f46-200">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="a9f46-201">Colóquelo bajo el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a9f46-201">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="a9f46-202">En la ventana Propiedades, cambie la propiedad **Name** a **SearchButton**.</span><span class="sxs-lookup"><span data-stu-id="a9f46-202">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="a9f46-203">Cambie la propiedad **Text** a **Search**.</span><span class="sxs-lookup"><span data-stu-id="a9f46-203">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="a9f46-204">Haga doble clic en el control <xref:System.Windows.Forms.Button> para abrir el Editor de código y agregue el código siguiente al controlador de eventos `SearchButton_Click` .</span><span class="sxs-lookup"><span data-stu-id="a9f46-204">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]  
  
6.  <span data-ttu-id="a9f46-205">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9f46-205">Press F5 to run the application.</span></span> <span data-ttu-id="a9f46-206">Escriba un identificador de cliente en **SearchTextBox** y haga clic en el botón **Buscar** .</span><span class="sxs-lookup"><span data-stu-id="a9f46-206">Type a customer ID in **SearchTextBox** and click the **Search** button.</span></span>  
  
## <a name="adding-a-master-and-detail-table-to-the-datarepeater"></a><span data-ttu-id="a9f46-207">Agregar una tabla maestra y de detalles a DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a9f46-207">Adding a Master and Detail Table to the DataRepeater</span></span>  
 <span data-ttu-id="a9f46-208">En este paso opcional, agregará un segundo control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> para mostrar los pedidos relacionados para cada cliente.</span><span class="sxs-lookup"><span data-stu-id="a9f46-208">In this optional step, you add a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to display related orders for each customer.</span></span>  
  
#### <a name="to-add-a-master-and-detail-table"></a><span data-ttu-id="a9f46-209">Para agregar una tabla maestra y de detalles</span><span class="sxs-lookup"><span data-stu-id="a9f46-209">To add a master and detail table</span></span>  
  
1.  <span data-ttu-id="a9f46-210">Arrastre un segundo control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> de la pestaña **Visual Basic PowerPacks** del **Cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="a9f46-210">Drag a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** onto the form.</span></span>  
  
2.  <span data-ttu-id="a9f46-211">En la ventana Propiedades, establezca la propiedad **Location** en `465, 25`.</span><span class="sxs-lookup"><span data-stu-id="a9f46-211">In the Properties window, set the **Location** property to `465, 25`.</span></span>  
  
3.  <span data-ttu-id="a9f46-212">Establezca la propiedad **Size** en `315, 600`.</span><span class="sxs-lookup"><span data-stu-id="a9f46-212">Set the **Size** property to `315, 600`.</span></span>  
  
4.  <span data-ttu-id="a9f46-213">En la ventana **Orígenes de datos** , expanda el nodo de la tabla **Customers** y seleccione el nodo de detalle de la tabla **Orders** .</span><span class="sxs-lookup"><span data-stu-id="a9f46-213">In the **Data Sources** window, expand the **Customers** table node and select the detail node for the **Orders** table.</span></span>  
  
5.  <span data-ttu-id="a9f46-214">Cambie el tipo de colocación de esta tabla **Orders** a Detalles haciendo clic en **Detalles** en la lista desplegable del nodo de la tabla.</span><span class="sxs-lookup"><span data-stu-id="a9f46-214">Change the drop type of this **Orders** table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="a9f46-215">Arrastre este nodo de la tabla **Orders** a la región de la plantilla de elemento (la región superior) del segundo control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a9f46-215">Drag this **Orders** table node onto the item template region (the upper region) of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="a9f46-216">Se agregan un componente **OrdersBindingSource** y un componente **OrdersTableAdapter** a la bandeja de componentes.</span><span class="sxs-lookup"><span data-stu-id="a9f46-216">An **OrdersBindingSource** component and an **OrdersTableAdapter** component are added to the Component Tray.</span></span>  
  
7.  <span data-ttu-id="a9f46-217">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9f46-217">Press F5 to run the application.</span></span> <span data-ttu-id="a9f46-218">Al seleccionar cada cliente en el primer control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> , los pedidos de ese cliente se muestran en el segundo control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="a9f46-218">When you select each customer in the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control, the orders for that customer are displayed in the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9f46-219">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9f46-219">See Also</span></span>  
 [<span data-ttu-id="a9f46-220">Introducción al control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a9f46-220">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="a9f46-221">Mostrar los datos enlazados en un control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a9f46-221">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="a9f46-222">Mostrar controles no enlazados en un control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a9f46-222">How to: Display Unbound Controls in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="a9f46-223">Cambiar el diseño de un control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a9f46-223">How to: Change the Layout of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="a9f46-224">Mostrar los encabezados de los elementos en un control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a9f46-224">How to: Display Item Headers in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="a9f46-225">Buscar datos en un control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a9f46-225">How to: Search Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="a9f46-226">Cómo: crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="a9f46-226">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [<span data-ttu-id="a9f46-227">Cambiar la apariencia de un control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a9f46-227">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="a9f46-228">Deshabilitar las operaciones de agregar y eliminar elementos DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a9f46-228">How to: Disable Adding and Deleting DataRepeater Items</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)  
 [<span data-ttu-id="a9f46-229">Solución de problemas del control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="a9f46-229">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
