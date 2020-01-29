---
title: Crear una tabla de búsqueda para el control ComboBox, ListBox o CheckedListBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CheckedListBox control [Windows Forms], creating lookup tables
- lookup tables
- list boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], lookup tables
- ComboBox control [Windows Forms], lookup table
- lookup tables [Windows Forms], creating for controls
- combo boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], creating lookup tables
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
ms.openlocfilehash: 4bbbc66a56c7ce269c2dabd593db88f96907d755
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737368"
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="0d401-102">Cómo: Crear una tabla de búsqueda para un control ComboBox, ListBox o CheckedListBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0d401-102">How to: Create a Lookup Table for a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="0d401-103">A veces resulta útil mostrar datos en un formato fácil de usar en un formulario de Windows Forms y, no obstante, almacenar los datos en un formato más coherente para su programa.</span><span class="sxs-lookup"><span data-stu-id="0d401-103">Sometimes it is useful to display data in a user-friendly format on a Windows Form, but store the data in a format that is more meaningful to your program.</span></span> <span data-ttu-id="0d401-104">Por ejemplo, un formulario de pedido de comida puede mostrar los elementos del menú por nombre en un cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="0d401-104">For example, an order form for food might display the menu items by name in a list box.</span></span> <span data-ttu-id="0d401-105">Sin embargo, la tabla de datos que registra el pedido contendría los números de identificador únicos que representan la comida.</span><span class="sxs-lookup"><span data-stu-id="0d401-105">However, the data table recording the order would contain the unique ID numbers representing the food.</span></span> <span data-ttu-id="0d401-106">En las siguientes tablas se proporciona un ejemplo en el que se indica cómo almacenar y mostrar datos de formulario de pedido de comida.</span><span class="sxs-lookup"><span data-stu-id="0d401-106">The following tables show an example of how to store and display order-form data for food.</span></span>  
  
### <a name="orderdetailstable"></a><span data-ttu-id="0d401-107">OrderDetailsTable</span><span class="sxs-lookup"><span data-stu-id="0d401-107">OrderDetailsTable</span></span>  
  
|<span data-ttu-id="0d401-108">OrderID</span><span class="sxs-lookup"><span data-stu-id="0d401-108">OrderID</span></span>|<span data-ttu-id="0d401-109">ItemID</span><span class="sxs-lookup"><span data-stu-id="0d401-109">ItemID</span></span>|<span data-ttu-id="0d401-110">Cantidad</span><span class="sxs-lookup"><span data-stu-id="0d401-110">Quantity</span></span>|  
|-------------|------------|--------------|  
|<span data-ttu-id="0d401-111">4085</span><span class="sxs-lookup"><span data-stu-id="0d401-111">4085</span></span>|<span data-ttu-id="0d401-112">12</span><span class="sxs-lookup"><span data-stu-id="0d401-112">12</span></span>|<span data-ttu-id="0d401-113">1</span><span class="sxs-lookup"><span data-stu-id="0d401-113">1</span></span>|  
|<span data-ttu-id="0d401-114">4086</span><span class="sxs-lookup"><span data-stu-id="0d401-114">4086</span></span>|<span data-ttu-id="0d401-115">13</span><span class="sxs-lookup"><span data-stu-id="0d401-115">13</span></span>|<span data-ttu-id="0d401-116">3</span><span class="sxs-lookup"><span data-stu-id="0d401-116">3</span></span>|  
  
### <a name="itemtable"></a><span data-ttu-id="0d401-117">ItemTable</span><span class="sxs-lookup"><span data-stu-id="0d401-117">ItemTable</span></span>  
  
|<span data-ttu-id="0d401-118">ID.</span><span class="sxs-lookup"><span data-stu-id="0d401-118">ID</span></span>|<span data-ttu-id="0d401-119">Name</span><span class="sxs-lookup"><span data-stu-id="0d401-119">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="0d401-120">12</span><span class="sxs-lookup"><span data-stu-id="0d401-120">12</span></span>|<span data-ttu-id="0d401-121">Patata</span><span class="sxs-lookup"><span data-stu-id="0d401-121">Potato</span></span>|  
|<span data-ttu-id="0d401-122">13</span><span class="sxs-lookup"><span data-stu-id="0d401-122">13</span></span>|<span data-ttu-id="0d401-123">Pollo</span><span class="sxs-lookup"><span data-stu-id="0d401-123">Chicken</span></span>|  
  
 <span data-ttu-id="0d401-124">En este escenario, una tabla, **tabla orderdetailstable**, almacena la información real que le preocupa Mostrar y guardar.</span><span class="sxs-lookup"><span data-stu-id="0d401-124">In this scenario, one table, **OrderDetailsTable**, stores the actual information you are concerned with displaying and saving.</span></span> <span data-ttu-id="0d401-125">Pero para ahorrar espacio, lo hace en un modo bastante críptico.</span><span class="sxs-lookup"><span data-stu-id="0d401-125">But to save space, it does so in a fairly cryptic fashion.</span></span> <span data-ttu-id="0d401-126">La otra tabla, **ItemTable**, solo contiene información relacionada con la apariencia sobre el número de identificación equivalente al nombre de comida y nada sobre los pedidos de comida reales.</span><span class="sxs-lookup"><span data-stu-id="0d401-126">The other table, **ItemTable**, contains only appearance-related information about which ID number is equivalent to which food name, and nothing about the actual food orders.</span></span>  
  
 <span data-ttu-id="0d401-127">**ItemTable** está conectado al control <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>o <xref:System.Windows.Forms.CheckedListBox> a través de tres propiedades.</span><span class="sxs-lookup"><span data-stu-id="0d401-127">The **ItemTable** is connected to the <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control through three properties.</span></span> <span data-ttu-id="0d401-128">La propiedad `DataSource` contiene el nombre de esta tabla.</span><span class="sxs-lookup"><span data-stu-id="0d401-128">The `DataSource` property contains the name of this table.</span></span> <span data-ttu-id="0d401-129">La propiedad `DisplayMember` contiene la columna de datos de esa tabla que desea mostrar en el control (el nombre del alimento).</span><span class="sxs-lookup"><span data-stu-id="0d401-129">The `DisplayMember` property contains the data column of that table that you want to display in the control (the food name).</span></span> <span data-ttu-id="0d401-130">La propiedad `ValueMember` contiene la columna de datos de esa tabla con la información almacenada (el número de identificación).</span><span class="sxs-lookup"><span data-stu-id="0d401-130">The `ValueMember` property contains the data column of that table with the stored information (the ID number).</span></span>  
  
 <span data-ttu-id="0d401-131">La **tabla orderdetailstable** se conecta al control mediante su colección de enlaces, a la que se obtiene acceso a través de la propiedad <xref:System.Windows.Forms.Control.DataBindings%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d401-131">The **OrderDetailsTable** is connected to the control by its bindings collection, accessed through the <xref:System.Windows.Forms.Control.DataBindings%2A> property.</span></span> <span data-ttu-id="0d401-132">Al agregar un objeto de enlace a la colección, se conecta una propiedad de control a un miembro de datos específico (la columna de números de ID.) en un origen de datos ( **tabla orderdetailstable**).</span><span class="sxs-lookup"><span data-stu-id="0d401-132">When you add a binding object to the collection, you connect a control property to a specific data member (the column of ID numbers) in a data source (the **OrderDetailsTable**).</span></span> <span data-ttu-id="0d401-133">Cuando se realiza una selección en el control, la entrada de formulario se guarda en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="0d401-133">When a selection is made in the control, this table is where the form input is saved.</span></span>  
  
### <a name="to-create-a-lookup-table"></a><span data-ttu-id="0d401-134">Para crear una tabla de búsqueda</span><span class="sxs-lookup"><span data-stu-id="0d401-134">To create a lookup table</span></span>  
  
1. <span data-ttu-id="0d401-135">Agregue un control <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> o <xref:System.Windows.Forms.CheckedListBox> al formulario.</span><span class="sxs-lookup"><span data-stu-id="0d401-135">Add a <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control to the form.</span></span>  
  
2. <span data-ttu-id="0d401-136">Conéctese a su origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0d401-136">Connect to your data source.</span></span>  
  
3. <span data-ttu-id="0d401-137">Establezca a una relación de datos entre las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="0d401-137">Establish a data relation between the two tables.</span></span> <span data-ttu-id="0d401-138">Vea [Introducción a los objetos DataRelation](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="0d401-138">See [Introduction to DataRelation Objects](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120)).</span></span>  
  
4. <span data-ttu-id="0d401-139">Establezca las siguientes propiedades.</span><span class="sxs-lookup"><span data-stu-id="0d401-139">Set the following properties.</span></span> <span data-ttu-id="0d401-140">Puede establecerse en código o en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="0d401-140">They can be set in code or in the designer.</span></span>  
  
    |<span data-ttu-id="0d401-141">La propiedad</span><span class="sxs-lookup"><span data-stu-id="0d401-141">Property</span></span>|<span data-ttu-id="0d401-142">Configuración de</span><span class="sxs-lookup"><span data-stu-id="0d401-142">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|<span data-ttu-id="0d401-143">La tabla que contiene la información sobre qué número de identificador equivale a qué elemento.</span><span class="sxs-lookup"><span data-stu-id="0d401-143">The table that contains information about which ID number is equivalent to which item.</span></span> <span data-ttu-id="0d401-144">En el escenario anterior, esto se `ItemTable`.</span><span class="sxs-lookup"><span data-stu-id="0d401-144">In the previous scenario, this is `ItemTable`.</span></span>|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|<span data-ttu-id="0d401-145">La columna de la tabla de origen de datos que desea mostrar en el control.</span><span class="sxs-lookup"><span data-stu-id="0d401-145">The column of the data source table that you want to display in the control.</span></span> <span data-ttu-id="0d401-146">En el escenario anterior, esto es `"Name"` (para establecer en el código, use comillas).</span><span class="sxs-lookup"><span data-stu-id="0d401-146">In the previous scenario, this is `"Name"` (to set in code, use quotation marks).</span></span>|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|<span data-ttu-id="0d401-147">La columna de la tabla de origen de datos que contiene la información almacenada.</span><span class="sxs-lookup"><span data-stu-id="0d401-147">The column of the data source table that contains the stored information.</span></span> <span data-ttu-id="0d401-148">En el escenario anterior, esto es `"ID"` (para establecer en el código, use comillas).</span><span class="sxs-lookup"><span data-stu-id="0d401-148">In the previous scenario, this is `"ID"` (to set in code, use quotation marks).</span></span>|  
  
5. <span data-ttu-id="0d401-149">En un procedimiento llame al método <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> de la clase <xref:System.Windows.Forms.ControlBindingsCollection> para enlazar la propiedad <xref:System.Windows.Forms.ListControl.SelectedValue%2A> del control a la tabla que registra la entrada de formulario.</span><span class="sxs-lookup"><span data-stu-id="0d401-149">In a procedure, call the <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> method of the <xref:System.Windows.Forms.ControlBindingsCollection> class to bind the control's <xref:System.Windows.Forms.ListControl.SelectedValue%2A> property to the table recording the form input.</span></span> <span data-ttu-id="0d401-150">También puede hacerlo en el diseñador en lugar de en el código, al tener acceso a la propiedad <xref:System.Windows.Forms.Control.DataBindings%2A> del control en la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="0d401-150">You can also do this in the Designer instead of in code, by accessing the control's <xref:System.Windows.Forms.Control.DataBindings%2A> property in the **Properties** window.</span></span> <span data-ttu-id="0d401-151">En el escenario anterior, esto es `OrderDetailsTable`y la columna se `"ItemID"`.</span><span class="sxs-lookup"><span data-stu-id="0d401-151">In the previous scenario, this is `OrderDetailsTable`, and the column is `"ItemID"`.</span></span>  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0d401-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d401-152">See also</span></span>

- [<span data-ttu-id="0d401-153">Enlace de datos y Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0d401-153">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="0d401-154">Información general sobre ListBox (Control)</span><span class="sxs-lookup"><span data-stu-id="0d401-154">ListBox Control Overview</span></span>](listbox-control-overview-windows-forms.md)
- [<span data-ttu-id="0d401-155">Información general sobre el control ComboBox</span><span class="sxs-lookup"><span data-stu-id="0d401-155">ComboBox Control Overview</span></span>](combobox-control-overview-windows-forms.md)
- [<span data-ttu-id="0d401-156">CheckedListBox Control Overview</span><span class="sxs-lookup"><span data-stu-id="0d401-156">CheckedListBox Control Overview</span></span>](checkedlistbox-control-overview-windows-forms.md)
- [<span data-ttu-id="0d401-157">Controles de formularios Windows Forms usados para mostrar opciones</span><span class="sxs-lookup"><span data-stu-id="0d401-157">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
