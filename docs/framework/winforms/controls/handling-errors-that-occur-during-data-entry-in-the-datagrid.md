---
title: 'Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
ms.openlocfilehash: cee6fe3b049378fa7bbe2585a3607049eaf231bc
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046075"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="6ac01-102">Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6ac01-102">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>

<span data-ttu-id="6ac01-103">La administración de errores del almacén de datos subyacente es una característica necesaria para una aplicación de entrada de datos.</span><span class="sxs-lookup"><span data-stu-id="6ac01-103">Handling errors from the underlying data store is a required feature for a data-entry application.</span></span> <span data-ttu-id="6ac01-104">El control <xref:System.Windows.Forms.DataGridView> Windows Forms facilita esta tarea al exponer el <xref:System.Windows.Forms.DataGridView.DataError> evento, que se genera cuando el almacén de datos detecta una infracción de restricción o una regla de negocios interrumpida.</span><span class="sxs-lookup"><span data-stu-id="6ac01-104">The Windows Forms <xref:System.Windows.Forms.DataGridView> control makes this easy by exposing the <xref:System.Windows.Forms.DataGridView.DataError> event, which is raised when the data store detects a constraint violation or a broken business rule.</span></span>

<span data-ttu-id="6ac01-105">En este tutorial, recuperará las filas de la `Customers` tabla de la base de datos de ejemplo Northwind y las <xref:System.Windows.Forms.DataGridView> mostrará en un control.</span><span class="sxs-lookup"><span data-stu-id="6ac01-105">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="6ac01-106">Cuando se detecta `CustomerID` un valor duplicado en una fila nueva o en una fila existente modificada, se producirá el <xref:System.Windows.Forms.DataGridView.DataError> evento, que se controlará mostrando un <xref:System.Windows.Forms.MessageBox> que describe la excepción.</span><span class="sxs-lookup"><span data-stu-id="6ac01-106">When a duplicate `CustomerID` value is detected in a new row or an edited existing row, the <xref:System.Windows.Forms.DataGridView.DataError> event will occur, which will be handled by displaying a <xref:System.Windows.Forms.MessageBox> that describes the exception.</span></span>

<span data-ttu-id="6ac01-107">Para copiar el código de este tema como una sola lista, vea [Cómo: Controlar los errores que se producen durante la entrada de datos en](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)el control DataGridView Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6ac01-107">To copy the code in this topic as a single listing, see [How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6ac01-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6ac01-108">Prerequisites</span></span>

<span data-ttu-id="6ac01-109">Para poder completar este tutorial, necesitará:</span><span class="sxs-lookup"><span data-stu-id="6ac01-109">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="6ac01-110">Acceso a un servidor que tenga la base de datos de ejemplo Northwind SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6ac01-110">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="6ac01-111">Crear el formulario</span><span class="sxs-lookup"><span data-stu-id="6ac01-111">Creating the Form</span></span>

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a><span data-ttu-id="6ac01-112">Para controlar los errores de entrada de datos en el control DataGridView</span><span class="sxs-lookup"><span data-stu-id="6ac01-112">To handle data-entry errors in the DataGridView control</span></span>

1. <span data-ttu-id="6ac01-113">Cree una clase que derive de <xref:System.Windows.Forms.Form> y contenga un <xref:System.Windows.Forms.DataGridView> control y un <xref:System.Windows.Forms.BindingSource> componente.</span><span class="sxs-lookup"><span data-stu-id="6ac01-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>

    <span data-ttu-id="6ac01-114">El siguiente ejemplo de código proporciona una inicialización básica `Main` e incluye un método.</span><span class="sxs-lookup"><span data-stu-id="6ac01-114">The following code example provides basic initialization and includes a `Main` method.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. <span data-ttu-id="6ac01-115">Implemente un método en la definición de clase del formulario para controlar los detalles de la conexión a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6ac01-115">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>

    <span data-ttu-id="6ac01-116">En este ejemplo de código `GetData` se usa un método que <xref:System.Data.DataTable> devuelve un objeto rellenado.</span><span class="sxs-lookup"><span data-stu-id="6ac01-116">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="6ac01-117">Asegúrese de establecer la `connectionString` variable en un valor que sea adecuado para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6ac01-117">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6ac01-118">Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ac01-118">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="6ac01-119">El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="6ac01-119">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="6ac01-120">Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="6ac01-120">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. <span data-ttu-id="6ac01-121">Implemente un controlador para el evento <xref:System.Windows.Forms.Form.Load> del formulario que inicializa <xref:System.Windows.Forms.DataGridView> y <xref:System.Windows.Forms.BindingSource> y configura el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="6ac01-121">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. <span data-ttu-id="6ac01-122">Controle <xref:System.Windows.Forms.DataGridView.DataError> el evento <xref:System.Windows.Forms.DataGridView>en.</span><span class="sxs-lookup"><span data-stu-id="6ac01-122">Handle the <xref:System.Windows.Forms.DataGridView.DataError> event on the <xref:System.Windows.Forms.DataGridView>.</span></span>

    <span data-ttu-id="6ac01-123">Si el contexto del error es una operación de confirmación, muestre el error en <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="6ac01-123">If the context for the error is a commit operation, display the error in a <xref:System.Windows.Forms.MessageBox>.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a><span data-ttu-id="6ac01-124">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="6ac01-124">Testing the Application</span></span>

<span data-ttu-id="6ac01-125">Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.</span><span class="sxs-lookup"><span data-stu-id="6ac01-125">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="6ac01-126">Para comprobar el formulario</span><span class="sxs-lookup"><span data-stu-id="6ac01-126">To test the form</span></span>

- <span data-ttu-id="6ac01-127">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ac01-127">Press F5 to run the application.</span></span>

  <span data-ttu-id="6ac01-128">Verá un <xref:System.Windows.Forms.DataGridView> control rellenado con datos de la tabla customers.</span><span class="sxs-lookup"><span data-stu-id="6ac01-128">You will see a <xref:System.Windows.Forms.DataGridView> control filled with data from the Customers table.</span></span> <span data-ttu-id="6ac01-129">Si escribe un valor duplicado para `CustomerID` y confirma la edición, el valor de la celda se revertirá automáticamente y verá un <xref:System.Windows.Forms.MessageBox> mensaje que muestra el error de entrada de datos.</span><span class="sxs-lookup"><span data-stu-id="6ac01-129">If you enter a duplicate value for `CustomerID` and commit the edit, the cell value will revert automatically and you will see a <xref:System.Windows.Forms.MessageBox> that displays the data entry error.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6ac01-130">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6ac01-130">Next Steps</span></span>

<span data-ttu-id="6ac01-131">Esta aplicación ofrece una descripción básica de las <xref:System.Windows.Forms.DataGridView> capacidades del control.</span><span class="sxs-lookup"><span data-stu-id="6ac01-131">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="6ac01-132">Puede personalizar la apariencia y el comportamiento del <xref:System.Windows.Forms.DataGridView> control de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="6ac01-132">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="6ac01-133">Cambiar los estilos de borde y encabezado.</span><span class="sxs-lookup"><span data-stu-id="6ac01-133">Change border and header styles.</span></span> <span data-ttu-id="6ac01-134">Para obtener más información, consulte [Cómo Cambiar los estilos de borde y de línea de cuadrícula en](change-the-border-and-gridline-styles-in-the-datagrid.md)el control DataGridView Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6ac01-134">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="6ac01-135">Habilitar o restringir la entrada del <xref:System.Windows.Forms.DataGridView> usuario al control.</span><span class="sxs-lookup"><span data-stu-id="6ac01-135">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="6ac01-136">Para obtener más información, consulte [Cómo Impedir la adición y eliminación de filas en el control](prevent-row-addition-and-deletion-datagridview.md)DataGridView Windows Forms [y cómo: Haga que las columnas sean de solo lectura en el](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)control DataGridView Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6ac01-136">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="6ac01-137">Valide la entrada del <xref:System.Windows.Forms.DataGridView> usuario al control.</span><span class="sxs-lookup"><span data-stu-id="6ac01-137">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="6ac01-138">Para obtener más información, vea [Tutorial: Validar datos en el control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)DataGridView Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6ac01-138">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="6ac01-139">Administrar conjuntos de datos muy grandes mediante el modo virtual.</span><span class="sxs-lookup"><span data-stu-id="6ac01-139">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="6ac01-140">Para obtener más información, vea [Tutorial: Implementar el modo virtual en el control](implementing-virtual-mode-wf-datagridview-control.md)DataGridView Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6ac01-140">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="6ac01-141">Personalizar la apariencia de las celdas.</span><span class="sxs-lookup"><span data-stu-id="6ac01-141">Customize the appearance of cells.</span></span> <span data-ttu-id="6ac01-142">Para obtener más información, vea [Cómo: Personalice la apariencia de las celdas en el control](customize-the-appearance-of-cells-in-the-datagrid.md) DataGridView Windows Forms y [cómo: Establecer estilos de celda predeterminados para el](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)control DataGridView Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6ac01-142">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6ac01-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ac01-143">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="6ac01-144">Entrada de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6ac01-144">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="6ac01-145">Procedimientos: Controlar los errores que se producen durante la entrada de datos en el control DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6ac01-145">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="6ac01-146">Tutorial: Validar datos en el control DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6ac01-146">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="6ac01-147">Proteger la información de conexión</span><span class="sxs-lookup"><span data-stu-id="6ac01-147">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
