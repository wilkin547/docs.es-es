---
title: Crear una tabla de búsqueda con el componente BindingSource
ms.date: 03/30/2017
helpviewer_keywords:
- lookup tables
- tables [Windows Forms], creating lookup tables
- BindingSource component [Windows Forms], creating a lookup table
- BindingSource component [Windows Forms], examples
ms.assetid: 622fce80-879d-44be-abbf-8350ec22ca2b
ms.openlocfilehash: ccf2bfa6cf3f56a38b55f8c87004c42a46172891
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736812"
---
# <a name="how-to-create-a-lookup-table-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="fcb41-102">Cómo: Crear una tabla de búsqueda con el componente BindingSource de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fcb41-102">How to: Create a Lookup Table with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="fcb41-103">Una tabla de búsqueda es una tabla de datos con una columna que muestra los datos de los registros de una tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="fcb41-103">A lookup table is a table of data that has a column that displays data from records in a related table.</span></span> <span data-ttu-id="fcb41-104">En los procedimientos siguientes se usa un control <xref:System.Windows.Forms.ComboBox> para mostrar el campo con la relación de clave externa desde la tabla primaria a la tabla secundaria.</span><span class="sxs-lookup"><span data-stu-id="fcb41-104">In the following procedures, a <xref:System.Windows.Forms.ComboBox> control is used to display the field with the foreign-key relationship from the parent to the child table.</span></span>  
  
 <span data-ttu-id="fcb41-105">Aquí se ofrece un ejemplo de una tabla primaria y una tabla secundaria para ayudar a visualizar estas dos tablas y su relación:</span><span class="sxs-lookup"><span data-stu-id="fcb41-105">To help visualize these two tables and this relationship, here is an example of a parent and child table:</span></span>  
  
 <span data-ttu-id="fcb41-106">CustomersTable (tabla primaria)</span><span class="sxs-lookup"><span data-stu-id="fcb41-106">CustomersTable (parent table)</span></span>  
  
|<span data-ttu-id="fcb41-107">CustomerID</span><span class="sxs-lookup"><span data-stu-id="fcb41-107">CustomerID</span></span>|<span data-ttu-id="fcb41-108">CustomerName</span><span class="sxs-lookup"><span data-stu-id="fcb41-108">CustomerName</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="fcb41-109">712</span><span class="sxs-lookup"><span data-stu-id="fcb41-109">712</span></span>|<span data-ttu-id="fcb41-110">Paul Koch</span><span class="sxs-lookup"><span data-stu-id="fcb41-110">Paul Koch</span></span>|  
|<span data-ttu-id="fcb41-111">713</span><span class="sxs-lookup"><span data-stu-id="fcb41-111">713</span></span>|<span data-ttu-id="fcb41-112">Tamara Johnston</span><span class="sxs-lookup"><span data-stu-id="fcb41-112">Tamara Johnston</span></span>|  
  
 <span data-ttu-id="fcb41-113">OrdersTable (tabla secundaria)</span><span class="sxs-lookup"><span data-stu-id="fcb41-113">OrdersTable (child table)</span></span>  
  
|<span data-ttu-id="fcb41-114">OrderID</span><span class="sxs-lookup"><span data-stu-id="fcb41-114">OrderID</span></span>|<span data-ttu-id="fcb41-115">OrderDate</span><span class="sxs-lookup"><span data-stu-id="fcb41-115">OrderDate</span></span>|<span data-ttu-id="fcb41-116">CustomerID</span><span class="sxs-lookup"><span data-stu-id="fcb41-116">CustomerID</span></span>|  
|-------------|---------------|----------------|  
|<span data-ttu-id="fcb41-117">903</span><span class="sxs-lookup"><span data-stu-id="fcb41-117">903</span></span>|<span data-ttu-id="fcb41-118">12.02.04</span><span class="sxs-lookup"><span data-stu-id="fcb41-118">February 12, 2004</span></span>|<span data-ttu-id="fcb41-119">712</span><span class="sxs-lookup"><span data-stu-id="fcb41-119">712</span></span>|  
|<span data-ttu-id="fcb41-120">904</span><span class="sxs-lookup"><span data-stu-id="fcb41-120">904</span></span>|<span data-ttu-id="fcb41-121">13.02.04</span><span class="sxs-lookup"><span data-stu-id="fcb41-121">February 13, 2004</span></span>|<span data-ttu-id="fcb41-122">713</span><span class="sxs-lookup"><span data-stu-id="fcb41-122">713</span></span>|  
  
 <span data-ttu-id="fcb41-123">En este escenario, una tabla, CustomersTable, almacena la información real que quiere mostrar y guardar.</span><span class="sxs-lookup"><span data-stu-id="fcb41-123">In this scenario, one table, CustomersTable, stores the actual information you want to display and save.</span></span> <span data-ttu-id="fcb41-124">Pero, para ahorrar espacio, la tabla deja fuera los datos que aportan claridad.</span><span class="sxs-lookup"><span data-stu-id="fcb41-124">But to save space, the table leaves out data that adds clarity.</span></span> <span data-ttu-id="fcb41-125">La otra tabla, OrdersTable, contienen solo la información relativa al aspecto sobre qué número de identificación de cliente equivale a qué fecha de pedido e identificador de pedido.</span><span class="sxs-lookup"><span data-stu-id="fcb41-125">The other table, OrdersTable, contains only appearance-related information about which customer ID number is equivalent to which order date and order ID.</span></span> <span data-ttu-id="fcb41-126">No hay ninguna mención a los nombres de los clientes.</span><span class="sxs-lookup"><span data-stu-id="fcb41-126">There is no mention of the customers' names.</span></span>  
  
 <span data-ttu-id="fcb41-127">En el control [ComboBox Control](combobox-control-windows-forms.md) se establecen cuatro propiedades importantes para crear la tabla de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="fcb41-127">Four important properties are set on the [ComboBox Control](combobox-control-windows-forms.md) control to create the lookup table.</span></span>  
  
- <span data-ttu-id="fcb41-128">La propiedad <xref:System.Windows.Forms.ComboBox.DataSource%2A> contiene el nombre de la tabla.</span><span class="sxs-lookup"><span data-stu-id="fcb41-128">The <xref:System.Windows.Forms.ComboBox.DataSource%2A> property contains the name of the table.</span></span>  
  
- <span data-ttu-id="fcb41-129">La propiedad <xref:System.Windows.Forms.ListControl.DisplayMember%2A> contiene la columna de datos de esa tabla que quiere mostrar para el texto del control (nombre del cliente).</span><span class="sxs-lookup"><span data-stu-id="fcb41-129">The <xref:System.Windows.Forms.ListControl.DisplayMember%2A> property contains the data column of that table that you want to display for the control text (the customer's name).</span></span>  
  
- <span data-ttu-id="fcb41-130">La propiedad <xref:System.Windows.Forms.ListControl.ValueMember%2A> contiene la columna de datos de esa con la información almacenada (número de identificación en la tabla primaria).</span><span class="sxs-lookup"><span data-stu-id="fcb41-130">The <xref:System.Windows.Forms.ListControl.ValueMember%2A> property contains the data column of that table with the stored information (the ID number in the parent table).</span></span>  
  
- <span data-ttu-id="fcb41-131">La propiedad <xref:System.Windows.Forms.ListControl.SelectedValue%2A> proporciona el valor de búsqueda de la tabla secundaria, basado en <xref:System.Windows.Forms.ListControl.ValueMember%2A>.</span><span class="sxs-lookup"><span data-stu-id="fcb41-131">The <xref:System.Windows.Forms.ListControl.SelectedValue%2A> property provides the lookup value for the child table, based on the <xref:System.Windows.Forms.ListControl.ValueMember%2A>.</span></span>  
  
 <span data-ttu-id="fcb41-132">Los procedimientos siguientes muestran cómo diseñar el formulario como una tabla de búsqueda y enlazar datos a controles en ella.</span><span class="sxs-lookup"><span data-stu-id="fcb41-132">The procedures below show you how to lay out your form as a lookup table and bind data to the controls on it.</span></span> <span data-ttu-id="fcb41-133">Para realizar correctamente los procedimientos, debe tener un origen de datos con tablas primarias y secundarias que tengan una relación de clave externa, tal y como se indicó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fcb41-133">To successfully complete the procedures, you must have a data source with parent and child tables that have a foreign-key relationship, as mentioned previously.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="fcb41-134">Para crear la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="fcb41-134">To create the user interface</span></span>  
  
1. <span data-ttu-id="fcb41-135">En el **cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.ComboBox> al formulario.</span><span class="sxs-lookup"><span data-stu-id="fcb41-135">From the **ToolBox**, drag a <xref:System.Windows.Forms.ComboBox> control onto the form.</span></span>  
  
     <span data-ttu-id="fcb41-136">Este control mostrará la columna de la tabla primaria.</span><span class="sxs-lookup"><span data-stu-id="fcb41-136">This control will display the column from parent table.</span></span>  
  
2. <span data-ttu-id="fcb41-137">Arrastre otros controles para mostrar detalles de la tabla secundaria.</span><span class="sxs-lookup"><span data-stu-id="fcb41-137">Drag other controls to display details from the child table.</span></span> <span data-ttu-id="fcb41-138">El formato de los datos en la tabla debe determinar qué controles elegirá.</span><span class="sxs-lookup"><span data-stu-id="fcb41-138">The format of the data in the table should determine which controls you choose.</span></span> <span data-ttu-id="fcb41-139">Para más información, consulte [Controles de Windows Forms por función](windows-forms-controls-by-function.md).</span><span class="sxs-lookup"><span data-stu-id="fcb41-139">For more information, see [Windows Forms Controls by Function](windows-forms-controls-by-function.md).</span></span>  
  
3. <span data-ttu-id="fcb41-140">Arrastre un control <xref:System.Windows.Forms.BindingNavigator> al formulario; esto le permitirá navegar por los datos de la tabla secundaria.</span><span class="sxs-lookup"><span data-stu-id="fcb41-140">Drag a <xref:System.Windows.Forms.BindingNavigator> control onto the form; this will allow you to navigate the data in the child table.</span></span>  
  
### <a name="to-connect-to-the-data-and-bind-it-to-controls"></a><span data-ttu-id="fcb41-141">Para conectar con los datos y enlazarlos a controles</span><span class="sxs-lookup"><span data-stu-id="fcb41-141">To connect to the data and bind it to controls</span></span>  
  
1. <span data-ttu-id="fcb41-142">Seleccione el <xref:System.Windows.Forms.ComboBox> y haga clic en el glifo Tarea inteligente para mostrar el cuadro de diálogo Tarea inteligente.</span><span class="sxs-lookup"><span data-stu-id="fcb41-142">Select the <xref:System.Windows.Forms.ComboBox> and click the Smart Task glyph to display the Smart Task dialog box.</span></span>  
  
2. <span data-ttu-id="fcb41-143">Seleccione **Usar elementos enlazados a datos**.</span><span class="sxs-lookup"><span data-stu-id="fcb41-143">Select **Use data bound items**.</span></span>  
  
3. <span data-ttu-id="fcb41-144">Haga clic en la flecha junto al cuadro desplegable **Origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="fcb41-144">Click the arrow next to the **Data Source** drop-down box.</span></span> <span data-ttu-id="fcb41-145">Si ya se ha configurado un origen de datos para el proyecto o formulario, aparecerá; de lo contrario, realice los pasos siguientes. (En este ejemplo se usan las tablas Customers y Orders de la base de datos de muestra Northwind y se hace referencia a ellas entre paréntesis).</span><span class="sxs-lookup"><span data-stu-id="fcb41-145">If a data source has previously been configured for the project or form, it will appear; otherwise, complete the following steps (This example uses the Customers and Orders tables of the Northwind sample database and refers to them in parentheses).</span></span>  
  
    1. <span data-ttu-id="fcb41-146">Haga clic en **Agregar origen de datos del proyecto** para conectar con los datos y crear un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="fcb41-146">Click **Add Project Data Source** to connect to data and create a data source.</span></span>  
  
    2. <span data-ttu-id="fcb41-147">En la página principal del **Asistente para la configuración de orígenes de datos**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fcb41-147">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>  
  
    3. <span data-ttu-id="fcb41-148">Seleccione **Base de datos** en la página **Elegir un tipo de origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="fcb41-148">Select **Database** on the **Choose a Data Source Type** page.</span></span>  
  
    4. <span data-ttu-id="fcb41-149">Seleccione una conexión de datos en la lista de conexiones disponibles, en la página **Elegir la conexión de datos**.</span><span class="sxs-lookup"><span data-stu-id="fcb41-149">Select a data connection from the list of available connections on the **Choose Your Data Connection** page.</span></span> <span data-ttu-id="fcb41-150">Si los datos que quiere no están disponibles, seleccione **Nueva conexión** para crear una nueva conexión de datos.</span><span class="sxs-lookup"><span data-stu-id="fcb41-150">If your desired data connection is not available, select **New Connection** to create a new data connection.</span></span>  
  
    5. <span data-ttu-id="fcb41-151">Haga clic en **Sí, guardar la conexión** para guardar la cadena de conexión en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fcb41-151">Click **Yes, save the connection** to save the connection string in the application configuration file.</span></span>  
  
    6. <span data-ttu-id="fcb41-152">Seleccione los objetos de base de datos que va a traer a su aplicación.</span><span class="sxs-lookup"><span data-stu-id="fcb41-152">Select the database objects to bring into your application.</span></span> <span data-ttu-id="fcb41-153">En este caso, seleccione una tabla primaria y una tabla secundaria (por ejemplo, Customers y Orders) con una relación de clave externa.</span><span class="sxs-lookup"><span data-stu-id="fcb41-153">In this case, select a parent table and child table (for example, Customers and Orders) with a foreign key relationship.</span></span>  
  
    7. <span data-ttu-id="fcb41-154">Reemplace el nombre del conjunto de datos predeterminado, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="fcb41-154">Replace the default dataset name if you want.</span></span>  
  
    8. <span data-ttu-id="fcb41-155">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="fcb41-155">Click **Finish**.</span></span>  
  
4. <span data-ttu-id="fcb41-156">En el cuadro desplegable **Mostrar miembro**, seleccione el nombre de la columna (por ejemplo, ContactName) que se mostrará en el cuadro combinado.</span><span class="sxs-lookup"><span data-stu-id="fcb41-156">In the **Display Member** drop-down box, select the column name (for example, ContactName) to be displayed in the combo box.</span></span>  
  
5. <span data-ttu-id="fcb41-157">En el cuadro desplegable **Miembro de valor**, seleccione la columna (por ejemplo, CustomerID) para realizar la operación de búsqueda en la tabla secundaria.</span><span class="sxs-lookup"><span data-stu-id="fcb41-157">In the **Value Member** drop-down box, select the column (for example, CustomerID) to perform the lookup operation in the child table.</span></span>  
  
6. <span data-ttu-id="fcb41-158">En el cuadro desplegable **Valor seleccionado**, navegue a **Orígenes de datos del proyecto** y al conjunto de datos recién creado que contiene las tablas primaria y secundaria.</span><span class="sxs-lookup"><span data-stu-id="fcb41-158">In the **Selected Value** drop-down box, navigate to **Project Data Sources** and the dataset you just created that contains the parent and child tables.</span></span> <span data-ttu-id="fcb41-159">Seleccione la misma propiedad de la tabla secundaria que sea el Miembro de valor de la tabla primaria (por ejemplo, Orders.CustomerID).</span><span class="sxs-lookup"><span data-stu-id="fcb41-159">Select the same property of the child table that is the Value Member of the parent table (for example, Orders.CustomerID).</span></span> <span data-ttu-id="fcb41-160">Se crearán el <xref:System.Windows.Forms.BindingSource>, el conjunto de datos y los componentes de adaptador de tabla correspondientes, y se agregarán al formulario.</span><span class="sxs-lookup"><span data-stu-id="fcb41-160">The appropriate <xref:System.Windows.Forms.BindingSource> , data set, and table adapter components will be created and added to the form.</span></span>  
  
7. <span data-ttu-id="fcb41-161">Enlace el control <xref:System.Windows.Forms.BindingNavigator> al <xref:System.Windows.Forms.BindingSource> de la tabla secundaria (por ejemplo, `OrdersBindingSource`).</span><span class="sxs-lookup"><span data-stu-id="fcb41-161">Bind the <xref:System.Windows.Forms.BindingNavigator> control to the <xref:System.Windows.Forms.BindingSource> of the child table (for example, `OrdersBindingSource`).</span></span>  
  
8. <span data-ttu-id="fcb41-162">Enlace otros controles, aparte de <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.BindingNavigator>, a los campos de detalles del <xref:System.Windows.Forms.BindingSource> de la tabla secundaria (por ejemplo, `OrdersBindingSource`) que quiera mostrar.</span><span class="sxs-lookup"><span data-stu-id="fcb41-162">Bind the controls other than the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.BindingNavigator> control to the details fields from the child table's <xref:System.Windows.Forms.BindingSource> (for example, `OrdersBindingSource`) that you want to display.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcb41-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="fcb41-163">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="fcb41-164">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="fcb41-164">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="fcb41-165">ComboBox (control)</span><span class="sxs-lookup"><span data-stu-id="fcb41-165">ComboBox Control</span></span>](combobox-control-windows-forms.md)
- [<span data-ttu-id="fcb41-166">Enlazar controles a los datos en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fcb41-166">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
