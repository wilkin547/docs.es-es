---
title: Obtener acceso a los objetos en la lista desplegable DataGridViewComboBoxCell
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], accessing objects in combo box cells
- combo boxes [Windows Forms], in DataGridView control
- combo boxes [Windows Forms], accessing objects in DataGridViewComboBoxCell drop-down lists
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
ms.openlocfilehash: 7e76ab1ac9089778e4371f4ee65b06d5ebc570bf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746314"
---
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a><span data-ttu-id="3d25f-102">Cómo: Obtener acceso a objetos de una lista desplegable DataGridViewComboBoxCell en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3d25f-102">How to: Access Objects in a Windows Forms DataGridViewComboBoxCell Drop-Down List</span></span>
<span data-ttu-id="3d25f-103">Al igual que el control <xref:System.Windows.Forms.ComboBox>, los tipos <xref:System.Windows.Forms.DataGridViewComboBoxColumn> y <xref:System.Windows.Forms.DataGridViewComboBoxCell> permiten agregar objetos arbitrarios a sus listas desplegables.</span><span class="sxs-lookup"><span data-stu-id="3d25f-103">Like the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and <xref:System.Windows.Forms.DataGridViewComboBoxCell> types enable you to add arbitrary objects to their drop-down lists.</span></span> <span data-ttu-id="3d25f-104">Con esta característica, puede representar Estados complejos en una lista desplegable sin tener que almacenar los objetos correspondientes en una colección independiente.</span><span class="sxs-lookup"><span data-stu-id="3d25f-104">With this feature, you can represent complex states in a drop-down list without having to store corresponding objects in a separate collection.</span></span>  
  
 <span data-ttu-id="3d25f-105">A diferencia del control de <xref:System.Windows.Forms.ComboBox>, los tipos de <xref:System.Windows.Forms.DataGridView> no tienen una propiedad <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> para recuperar el objeto actualmente seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3d25f-105">Unlike the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridView> types do not have a <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> property for retrieving the currently selected object.</span></span> <span data-ttu-id="3d25f-106">En su lugar, debe establecer la propiedad <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> en el nombre de una propiedad del objeto comercial.</span><span class="sxs-lookup"><span data-stu-id="3d25f-106">Instead, you must set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> or <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> property to the name of a property on your business object.</span></span> <span data-ttu-id="3d25f-107">Cuando el usuario realiza una selección, la propiedad indicada del objeto comercial establece la celda <xref:System.Windows.Forms.DataGridViewCell.Value%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="3d25f-107">When the user makes a selection, the indicated property of the business object sets the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
 <span data-ttu-id="3d25f-108">Para recuperar el objeto comercial a través del valor de la celda, la propiedad `ValueMember` debe indicar una propiedad que devuelva una referencia al propio objeto comercial.</span><span class="sxs-lookup"><span data-stu-id="3d25f-108">To retrieve the business object through the cell value, the `ValueMember` property must indicate a property that returns a reference to the business object itself.</span></span> <span data-ttu-id="3d25f-109">Por consiguiente, si el tipo del objeto comercial no está bajo el control, debe agregar este tipo de propiedad extendiendo el tipo a través de la herencia.</span><span class="sxs-lookup"><span data-stu-id="3d25f-109">Therefore, if the type of the business object is not under your control, you must add such a property by extending the type through inheritance.</span></span>  
  
 <span data-ttu-id="3d25f-110">Los procedimientos siguientes muestran cómo rellenar una lista desplegable con objetos comerciales y recuperar los objetos a través de la celda <xref:System.Windows.Forms.DataGridViewCell.Value%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="3d25f-110">The following procedures demonstrate how to populate a drop-down list with business objects and retrieve the objects through the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a><span data-ttu-id="3d25f-111">Para agregar objetos comerciales a la lista desplegable</span><span class="sxs-lookup"><span data-stu-id="3d25f-111">To add business objects to the drop-down list</span></span>  
  
1. <span data-ttu-id="3d25f-112">Cree una nueva <xref:System.Windows.Forms.DataGridViewComboBoxColumn> y rellene su colección <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="3d25f-112">Create a new <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and populate its <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> collection.</span></span> <span data-ttu-id="3d25f-113">Como alternativa, puede establecer la propiedad <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> de la columna en la colección de objetos comerciales.</span><span class="sxs-lookup"><span data-stu-id="3d25f-113">Alternatively, you can set the column <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property to the collection of business objects.</span></span> <span data-ttu-id="3d25f-114">Sin embargo, en ese caso, no se puede Agregar "sin asignar" a la lista desplegable sin crear un objeto comercial correspondiente en la colección.</span><span class="sxs-lookup"><span data-stu-id="3d25f-114">In that case, however, you cannot add "unassigned" to the drop-down list without creating a corresponding business object in your collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2. <span data-ttu-id="3d25f-115">Establezca las propiedades <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> y <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>.</span><span class="sxs-lookup"><span data-stu-id="3d25f-115">Set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> and <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> properties.</span></span> <span data-ttu-id="3d25f-116"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> indica la propiedad del objeto comercial que se va a mostrar en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="3d25f-116"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> indicates the property of the business object to display in the drop-down list.</span></span> <span data-ttu-id="3d25f-117"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> indica la propiedad que devuelve una referencia al objeto comercial.</span><span class="sxs-lookup"><span data-stu-id="3d25f-117"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> indicates the property that returns a reference to the business object.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3. <span data-ttu-id="3d25f-118">Asegúrese de que el tipo de objeto de negocio contiene una propiedad que devuelve una referencia a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="3d25f-118">Make sure that your business object type contains a property that returns a reference to the current instance.</span></span> <span data-ttu-id="3d25f-119">Esta propiedad se debe denominar con el valor asignado a <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="3d25f-119">This property must be named with the value assigned to <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> in the previous step.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a><span data-ttu-id="3d25f-120">Para recuperar el objeto comercial seleccionado actualmente</span><span class="sxs-lookup"><span data-stu-id="3d25f-120">To retrieve the currently selected business object</span></span>  
  
- <span data-ttu-id="3d25f-121">Obtiene la propiedad <xref:System.Windows.Forms.DataGridViewCell.Value%2A> de la celda y la convierte al tipo de objeto comercial.</span><span class="sxs-lookup"><span data-stu-id="3d25f-121">Get the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property and cast it to the business object type.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a><span data-ttu-id="3d25f-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d25f-122">Example</span></span>  
 <span data-ttu-id="3d25f-123">En el ejemplo completo se muestra el uso de objetos comerciales en una lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="3d25f-123">The complete example demonstrates the use of business objects in a drop-down list.</span></span> <span data-ttu-id="3d25f-124">En el ejemplo, un control <xref:System.Windows.Forms.DataGridView> se enlaza a una colección de objetos `Task`.</span><span class="sxs-lookup"><span data-stu-id="3d25f-124">In the example, a <xref:System.Windows.Forms.DataGridView> control is bound to a collection of `Task` objects.</span></span> <span data-ttu-id="3d25f-125">Cada `Task` objeto tiene una propiedad `AssignedTo` que indica el objeto `Employee` actualmente asignado a esa tarea.</span><span class="sxs-lookup"><span data-stu-id="3d25f-125">Each `Task` object has an `AssignedTo` property that indicates the `Employee` object currently assigned to that task.</span></span> <span data-ttu-id="3d25f-126">En la columna `Assigned To` se muestra el valor de la propiedad `Name` de cada empleado asignado o "sin asignar" si el valor de la propiedad `Task.AssignedTo` es `null`.</span><span class="sxs-lookup"><span data-stu-id="3d25f-126">The `Assigned To` column displays the `Name` property value for each assigned employee, or "unassigned" if the `Task.AssignedTo` property value is `null`.</span></span>  
  
 <span data-ttu-id="3d25f-127">Para ver el comportamiento de este ejemplo, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3d25f-127">To view the behavior of this example, perform the following steps:</span></span>  
  
1. <span data-ttu-id="3d25f-128">Para cambiar las asignaciones de la columna `Assigned To`, seleccione valores diferentes en las listas desplegables o presione CTRL + 0 en una celda de cuadro combinado.</span><span class="sxs-lookup"><span data-stu-id="3d25f-128">Change assignments in the `Assigned To` column by selecting different values from the drop-down lists or pressing CTRL+0 in a combo-box cell.</span></span>  
  
2. <span data-ttu-id="3d25f-129">Haga clic en `Generate Report` para mostrar las asignaciones actuales.</span><span class="sxs-lookup"><span data-stu-id="3d25f-129">Click `Generate Report` to display the current assignments.</span></span> <span data-ttu-id="3d25f-130">Esto demuestra que un cambio en la columna `Assigned To` actualiza automáticamente la colección `tasks`.</span><span class="sxs-lookup"><span data-stu-id="3d25f-130">This demonstrates that a change in the `Assigned To` column automatically updates the `tasks` collection.</span></span>  
  
3. <span data-ttu-id="3d25f-131">Haga clic en un botón de `Request Status` para llamar al método `RequestStatus` del objeto `Employee` actual de esa fila.</span><span class="sxs-lookup"><span data-stu-id="3d25f-131">Click a `Request Status` button to call the `RequestStatus` method of the current `Employee` object for that row.</span></span> <span data-ttu-id="3d25f-132">Esto demuestra que el objeto seleccionado se ha recuperado correctamente.</span><span class="sxs-lookup"><span data-stu-id="3d25f-132">This demonstrates that the selected object has been successfully retrieved.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3d25f-133">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="3d25f-133">Compiling the Code</span></span>  
 <span data-ttu-id="3d25f-134">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="3d25f-134">This example requires:</span></span>  
  
- <span data-ttu-id="3d25f-135">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="3d25f-135">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d25f-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3d25f-136">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ComboBox>
- [<span data-ttu-id="3d25f-137">Mostrar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3d25f-137">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
