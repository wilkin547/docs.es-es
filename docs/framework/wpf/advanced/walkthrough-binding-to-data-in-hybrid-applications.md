---
title: 'Tutorial: Enlazar a datos en aplicaciones híbridas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
ms.openlocfilehash: 1bb38436049e338ab6033ae3b6370732a457d520
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794220"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a><span data-ttu-id="959a0-102">Tutorial: Enlazar a datos en aplicaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="959a0-102">Walkthrough: Binding to Data in Hybrid Applications</span></span>

<span data-ttu-id="959a0-103">Enlazar un origen de datos a un control es esencial para proporcionar a los usuarios acceso a los datos subyacentes, tanto si usa Windows Forms como si utiliza [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="959a0-103">Binding a data source to a control is essential for providing users with access to underlying data, whether you are using Windows Forms or [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="959a0-104">En este tutorial se muestra cómo se puede usar el enlace de datos en aplicaciones híbridas que incluyen controles Windows Forms y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="959a0-104">This walkthrough shows how you can use data binding in hybrid applications that include both Windows Forms and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls.</span></span>

<span data-ttu-id="959a0-105">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="959a0-105">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="959a0-106">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="959a0-106">Creating the project.</span></span>

- <span data-ttu-id="959a0-107">Definir la plantilla de datos.</span><span class="sxs-lookup"><span data-stu-id="959a0-107">Defining the data template.</span></span>

- <span data-ttu-id="959a0-108">Especificar el diseño del formulario.</span><span class="sxs-lookup"><span data-stu-id="959a0-108">Specifying the form layout.</span></span>

- <span data-ttu-id="959a0-109">Especificar los enlaces de datos.</span><span class="sxs-lookup"><span data-stu-id="959a0-109">Specifying data bindings.</span></span>

- <span data-ttu-id="959a0-110">Mostrar los datos mediante la interoperación.</span><span class="sxs-lookup"><span data-stu-id="959a0-110">Displaying data by using interoperation.</span></span>

- <span data-ttu-id="959a0-111">Agregar el origen de datos al proyecto.</span><span class="sxs-lookup"><span data-stu-id="959a0-111">Adding the data source to the project.</span></span>

- <span data-ttu-id="959a0-112">Enlazar al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="959a0-112">Binding to the data source.</span></span>

<span data-ttu-id="959a0-113">Para obtener una lista de código completa de las tareas ilustradas en este tutorial, consulte [Data Binding in Hybrid Applications Sample](https://go.microsoft.com/fwlink/?LinkID=159983).</span><span class="sxs-lookup"><span data-stu-id="959a0-113">For a complete code listing of the tasks illustrated in this walkthrough, see [Data Binding in Hybrid Applications Sample](https://go.microsoft.com/fwlink/?LinkID=159983).</span></span>

<span data-ttu-id="959a0-114">Cuando acabe, entenderá mejor las características de enlace de datos en aplicaciones híbridas.</span><span class="sxs-lookup"><span data-stu-id="959a0-114">When you are finished, you will have an understanding of data binding features in hybrid applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="959a0-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="959a0-115">Prerequisites</span></span>

<span data-ttu-id="959a0-116">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="959a0-116">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="959a0-117">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="959a0-117">Visual Studio.</span></span>

- <span data-ttu-id="959a0-118">Acceso a la base de datos de ejemplo Northwind que se ejecuta en Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="959a0-118">Access to the Northwind sample database running on Microsoft SQL Server.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="959a0-119">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="959a0-119">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="959a0-120">Para crear y configurar el proyecto</span><span class="sxs-lookup"><span data-stu-id="959a0-120">To create and set up the project</span></span>

1. <span data-ttu-id="959a0-121">Cree un proyecto de aplicación de WPF denominado `WPFWithWFAndDatabinding`.</span><span class="sxs-lookup"><span data-stu-id="959a0-121">Create a WPF Application project named `WPFWithWFAndDatabinding`.</span></span>

2. <span data-ttu-id="959a0-122">En el Explorador de soluciones, agregue referencias a los ensamblados siguientes.</span><span class="sxs-lookup"><span data-stu-id="959a0-122">In Solution Explorer, add references to the following assemblies.</span></span>

    - <span data-ttu-id="959a0-123">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="959a0-123">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="959a0-124">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="959a0-124">System.Windows.Forms</span></span>

3. <span data-ttu-id="959a0-125">Abra MainWindow. XAML en el diseñador de WPF.</span><span class="sxs-lookup"><span data-stu-id="959a0-125">Open MainWindow.xaml in the WPF Designer.</span></span>

4. <span data-ttu-id="959a0-126">En el elemento <xref:System.Windows.Window>, agregue la siguiente asignación de espacios de nombres de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="959a0-126">In the <xref:System.Windows.Window> element, add the following Windows Forms namespaces mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="959a0-127">Asigne al elemento <xref:System.Windows.Controls.Grid> predeterminado el nombre `mainGrid` asignando la propiedad <xref:System.Windows.FrameworkElement.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="959a0-127">Name the default <xref:System.Windows.Controls.Grid> element `mainGrid` by assigning the <xref:System.Windows.FrameworkElement.Name%2A> property.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]

## <a name="defining-the-data-template"></a><span data-ttu-id="959a0-128">Definir la plantilla de datos</span><span class="sxs-lookup"><span data-stu-id="959a0-128">Defining the Data Template</span></span>

<span data-ttu-id="959a0-129">La lista maestra de clientes se muestra en un control de <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="959a0-129">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="959a0-130">En el ejemplo de código siguiente se define un objeto de <xref:System.Windows.DataTemplate> denominado `ListItemsTemplate` que controla el árbol visual del control <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="959a0-130">The following code example defines a <xref:System.Windows.DataTemplate> object named `ListItemsTemplate` that controls the visual tree of the <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="959a0-131">Esta <xref:System.Windows.DataTemplate> se asigna a la propiedad <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> del control <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="959a0-131">This <xref:System.Windows.DataTemplate> is assigned to the <xref:System.Windows.Controls.ListBox> control's <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> property.</span></span>

### <a name="to-define-the-data-template"></a><span data-ttu-id="959a0-132">Para definir la plantilla de datos</span><span class="sxs-lookup"><span data-stu-id="959a0-132">To define the data template</span></span>

- <span data-ttu-id="959a0-133">Copie el código XAML siguiente en la declaración del elemento de <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="959a0-133">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]

## <a name="specifying-the-form-layout"></a><span data-ttu-id="959a0-134">Especificar el diseño del formulario</span><span class="sxs-lookup"><span data-stu-id="959a0-134">Specifying the Form Layout</span></span>

<span data-ttu-id="959a0-135">El diseño del formulario se define mediante una cuadrícula con tres filas y tres columnas.</span><span class="sxs-lookup"><span data-stu-id="959a0-135">The layout of the form is defined by a grid with three rows and three columns.</span></span> <span data-ttu-id="959a0-136">se proporcionan <xref:System.Windows.Controls.Label> controles para identificar cada columna de la tabla customers.</span><span class="sxs-lookup"><span data-stu-id="959a0-136"><xref:System.Windows.Controls.Label> controls are provided to identify each column in the Customers table.</span></span>

### <a name="to-set-up-the-grid-layout"></a><span data-ttu-id="959a0-137">Para configurar el diseño de cuadrícula</span><span class="sxs-lookup"><span data-stu-id="959a0-137">To set up the Grid layout</span></span>

- <span data-ttu-id="959a0-138">Copie el código XAML siguiente en la declaración del elemento de <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="959a0-138">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]

### <a name="to-set-up-the-label-controls"></a><span data-ttu-id="959a0-139">Para configurar los controles de etiqueta</span><span class="sxs-lookup"><span data-stu-id="959a0-139">To set up the Label controls</span></span>

- <span data-ttu-id="959a0-140">Copie el código XAML siguiente en la declaración del elemento de <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="959a0-140">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]

## <a name="specifying-data-bindings"></a><span data-ttu-id="959a0-141">Especificar los enlaces de datos</span><span class="sxs-lookup"><span data-stu-id="959a0-141">Specifying Data Bindings</span></span>

<span data-ttu-id="959a0-142">La lista maestra de clientes se muestra en un control de <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="959a0-142">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="959a0-143">El `ListItemsTemplate` asociado enlaza un control <xref:System.Windows.Controls.TextBlock> al campo `ContactName` de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="959a0-143">The attached `ListItemsTemplate` binds a <xref:System.Windows.Controls.TextBlock> control to the `ContactName` field from the database.</span></span>

<span data-ttu-id="959a0-144">Los detalles de cada registro de cliente se muestran en varios controles <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="959a0-144">The details of each customer record are displayed in several <xref:System.Windows.Controls.TextBox> controls.</span></span>

### <a name="to-specify-data-bindings"></a><span data-ttu-id="959a0-145">Para especificar los enlaces de datos</span><span class="sxs-lookup"><span data-stu-id="959a0-145">To specify data bindings</span></span>

- <span data-ttu-id="959a0-146">Copie el código XAML siguiente en la declaración del elemento de <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="959a0-146">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     <span data-ttu-id="959a0-147">La clase <xref:System.Windows.Data.Binding> enlaza los controles de <xref:System.Windows.Controls.TextBox> a los campos adecuados en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="959a0-147">The <xref:System.Windows.Data.Binding> class binds the <xref:System.Windows.Controls.TextBox> controls to the appropriate fields in the database.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]

## <a name="displaying-data-by-using-interoperation"></a><span data-ttu-id="959a0-148">Mostrar los datos mediante la interoperación</span><span class="sxs-lookup"><span data-stu-id="959a0-148">Displaying Data by Using Interoperation</span></span>

<span data-ttu-id="959a0-149">Los pedidos correspondientes al cliente seleccionado se muestran en un control de <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="959a0-149">The orders corresponding to the selected customer are displayed in a <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> control named `dataGridView1`.</span></span> <span data-ttu-id="959a0-150">El control `dataGridView1` está enlazado al origen de datos en el archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="959a0-150">The `dataGridView1` control is bound to the data source in the code-behind file.</span></span> <span data-ttu-id="959a0-151">Un control <xref:System.Windows.Forms.Integration.WindowsFormsHost> es el elemento primario de este control Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="959a0-151">A <xref:System.Windows.Forms.Integration.WindowsFormsHost> control is the parent of this Windows Forms control.</span></span>

### <a name="to-display-data-in-the-datagridview-control"></a><span data-ttu-id="959a0-152">Para mostrar los datos en el control DataGridView</span><span class="sxs-lookup"><span data-stu-id="959a0-152">To display data in the DataGridView control</span></span>

- <span data-ttu-id="959a0-153">Copie el código XAML siguiente en la declaración del elemento de <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="959a0-153">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]

## <a name="adding-the-data-source-to-the-project"></a><span data-ttu-id="959a0-154">Agregar el origen de datos al proyecto</span><span class="sxs-lookup"><span data-stu-id="959a0-154">Adding the Data Source to the Project</span></span>

<span data-ttu-id="959a0-155">Con Visual Studio, puede agregar fácilmente un origen de datos al proyecto.</span><span class="sxs-lookup"><span data-stu-id="959a0-155">With Visual Studio, you can easily add a data source to your project.</span></span> <span data-ttu-id="959a0-156">Este procedimiento agrega un conjunto de datos fuertemente tipados a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="959a0-156">This procedure adds a strongly typed data set to your project.</span></span> <span data-ttu-id="959a0-157">También se agregan otras clases de compatibilidad, como adaptadores de tabla para cada una de las tablas elegidas.</span><span class="sxs-lookup"><span data-stu-id="959a0-157">Several other support classes, such as table adapters for each of the chosen tables, are also added.</span></span>

### <a name="to-add-the-data-source"></a><span data-ttu-id="959a0-158">Para agregar el origen de datos</span><span class="sxs-lookup"><span data-stu-id="959a0-158">To add the data source</span></span>

1. <span data-ttu-id="959a0-159">En el menú **datos** , seleccione **Agregar nuevo origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="959a0-159">From the **Data** menu, select **Add New Data Source**.</span></span>

2. <span data-ttu-id="959a0-160">En el **Asistente para la configuración de orígenes de datos**, cree una conexión a la base de datos Northwind mediante un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="959a0-160">In the **Data Source Configuration Wizard**, create a connection to the Northwind database by using a dataset.</span></span> <span data-ttu-id="959a0-161">Para obtener más información, consulta [How to: Connect to Data in a Database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="959a0-161">For more information, see [How to: Connect to Data in a Database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120)).</span></span>

3. <span data-ttu-id="959a0-162">Cuando el **Asistente para la configuración de orígenes de datos**le pida, guarde la cadena de conexión como `NorthwindConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="959a0-162">When you are prompted by the **Data Source Configuration Wizard**, save the connection string as `NorthwindConnectionString`.</span></span>

4. <span data-ttu-id="959a0-163">Cuando se le pida que elija los objetos de base de datos, seleccione las tablas `Customers` y `Orders` y asigne el nombre `NorthwindDataSet`al conjunto de datos generado.</span><span class="sxs-lookup"><span data-stu-id="959a0-163">When you are prompted to choose your database objects, select the `Customers` and `Orders` tables, and name the generated data set `NorthwindDataSet`.</span></span>

## <a name="binding-to-the-data-source"></a><span data-ttu-id="959a0-164">Enlazar al origen de datos</span><span class="sxs-lookup"><span data-stu-id="959a0-164">Binding to the Data Source</span></span>

<span data-ttu-id="959a0-165">El componente <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> proporciona una interfaz uniforme para el origen de datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="959a0-165">The <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> component provides a uniform interface for the application's data source.</span></span> <span data-ttu-id="959a0-166">El enlace al origen de datos se implementa en el archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="959a0-166">Binding to the data source is implemented in the code-behind file.</span></span>

### <a name="to-bind-to-the-data-source"></a><span data-ttu-id="959a0-167">Para enlazar al origen de datos</span><span class="sxs-lookup"><span data-stu-id="959a0-167">To bind to the data source</span></span>

1. <span data-ttu-id="959a0-168">Abra el archivo de código subyacente, denominado MainWindow.xaml.vb o MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="959a0-168">Open the code-behind file, which is named MainWindow.xaml.vb or MainWindow.xaml.cs.</span></span>

2. <span data-ttu-id="959a0-169">Copie el código siguiente en la definición de clase `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="959a0-169">Copy the following code into the `MainWindow` class definition.</span></span>

     <span data-ttu-id="959a0-170">Este código declara el componente de <xref:System.Windows.Forms.BindingSource> y las clases auxiliares asociadas que se conectan a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="959a0-170">This code declares the <xref:System.Windows.Forms.BindingSource> component and associated helper classes that connect to the database.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3. <span data-ttu-id="959a0-171">Copie el siguiente código en el constructor.</span><span class="sxs-lookup"><span data-stu-id="959a0-171">Copy the following code into the constructor.</span></span>

     <span data-ttu-id="959a0-172">Este código crea e inicializa el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="959a0-172">This code creates and initializes the <xref:System.Windows.Forms.BindingSource> component.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4. <span data-ttu-id="959a0-173">Abra MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="959a0-173">Open MainWindow.xaml.</span></span>

5. <span data-ttu-id="959a0-174">En Vista de diseño o en la vista XAML, seleccione el elemento <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="959a0-174">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="959a0-175">En el ventana Propiedades, haga clic en la pestaña **eventos** .</span><span class="sxs-lookup"><span data-stu-id="959a0-175">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="959a0-176">Haga doble clic en el evento <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="959a0-176">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="959a0-177">Copie el código siguiente en el controlador de eventos <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="959a0-177">Copy the following code into the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

     <span data-ttu-id="959a0-178">Este código asigna el componente de <xref:System.Windows.Forms.BindingSource> como contexto de datos y rellena los objetos de adaptador de `Customers` y `Orders`.</span><span class="sxs-lookup"><span data-stu-id="959a0-178">This code assigns the <xref:System.Windows.Forms.BindingSource> component as the data context and populates the `Customers` and `Orders` adapter objects.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. <span data-ttu-id="959a0-179">Copie el código siguiente en la definición de clase `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="959a0-179">Copy the following code into the `MainWindow` class definition.</span></span>

     <span data-ttu-id="959a0-180">Este método controla el evento de <xref:System.Windows.Data.CollectionView.CurrentChanged> y actualiza el elemento actual del enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="959a0-180">This method handles the <xref:System.Windows.Data.CollectionView.CurrentChanged> event and updates the current item of the data binding.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]

10. <span data-ttu-id="959a0-181">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="959a0-181">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="959a0-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="959a0-182">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="959a0-183">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="959a0-183">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="959a0-184">Ejemplo de enlace de datos en aplicaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="959a0-184">Data Binding in Hybrid Applications Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159983)
- [<span data-ttu-id="959a0-185">Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="959a0-185">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="959a0-186">Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="959a0-186">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
