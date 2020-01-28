---
title: 'Tutorial: controlar los errores que se producen durante la entrada de datos en el control DataGridView'
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
ms.openlocfilehash: 77a4dcd9cf069ed8bbee6c49aa41db619c8e12ff
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738738"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d587f-102">Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d587f-102">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>

<span data-ttu-id="d587f-103">La administración de errores del almacén de datos subyacente es una característica necesaria para una aplicación de entrada de datos.</span><span class="sxs-lookup"><span data-stu-id="d587f-103">Handling errors from the underlying data store is a required feature for a data-entry application.</span></span> <span data-ttu-id="d587f-104">El control <xref:System.Windows.Forms.DataGridView> de Windows Forms facilita esta tarea al exponer el evento <xref:System.Windows.Forms.DataGridView.DataError>, que se genera cuando el almacén de datos detecta una infracción de restricción o una regla de negocios interrumpida.</span><span class="sxs-lookup"><span data-stu-id="d587f-104">The Windows Forms <xref:System.Windows.Forms.DataGridView> control makes this easy by exposing the <xref:System.Windows.Forms.DataGridView.DataError> event, which is raised when the data store detects a constraint violation or a broken business rule.</span></span>

<span data-ttu-id="d587f-105">En este tutorial, recuperará filas de la tabla `Customers` en la base de datos de ejemplo Northwind y las mostrará en un control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="d587f-105">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d587f-106">Cuando se detecta un valor de `CustomerID` duplicado en una fila nueva o en una fila existente modificada, se producirá el evento <xref:System.Windows.Forms.DataGridView.DataError>, que se controlará mostrando un <xref:System.Windows.Forms.MessageBox> que describe la excepción.</span><span class="sxs-lookup"><span data-stu-id="d587f-106">When a duplicate `CustomerID` value is detected in a new row or an edited existing row, the <xref:System.Windows.Forms.DataGridView.DataError> event will occur, which will be handled by displaying a <xref:System.Windows.Forms.MessageBox> that describes the exception.</span></span>

<span data-ttu-id="d587f-107">Para copiar el código de este tema como una sola lista, vea [Cómo: controlar los errores que se producen durante la entrada de datos en el control DataGridView Windows Forms](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="d587f-107">To copy the code in this topic as a single listing, see [How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d587f-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d587f-108">Prerequisites</span></span>

<span data-ttu-id="d587f-109">Para poder completar este tutorial, necesitará:</span><span class="sxs-lookup"><span data-stu-id="d587f-109">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="d587f-110">Acceso a un servidor que tenga la base de datos de ejemplo Northwind SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d587f-110">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="d587f-111">Crear el formulario</span><span class="sxs-lookup"><span data-stu-id="d587f-111">Creating the Form</span></span>

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a><span data-ttu-id="d587f-112">Para controlar los errores de entrada de datos en el control DataGridView</span><span class="sxs-lookup"><span data-stu-id="d587f-112">To handle data-entry errors in the DataGridView control</span></span>

1. <span data-ttu-id="d587f-113">Cree una clase que derive de <xref:System.Windows.Forms.Form> y contenga un control <xref:System.Windows.Forms.DataGridView> y un componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="d587f-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>

    <span data-ttu-id="d587f-114">El siguiente ejemplo de código proporciona una inicialización básica e incluye un método `Main`.</span><span class="sxs-lookup"><span data-stu-id="d587f-114">The following code example provides basic initialization and includes a `Main` method.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. <span data-ttu-id="d587f-115">Implemente un método en la definición de clase del formulario para controlar los detalles de la conexión a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d587f-115">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>

    <span data-ttu-id="d587f-116">En este ejemplo de código se usa un método `GetData` que devuelve un objeto <xref:System.Data.DataTable> rellenado.</span><span class="sxs-lookup"><span data-stu-id="d587f-116">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="d587f-117">Asegúrese de establecer la variable de `connectionString` en un valor que sea adecuado para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d587f-117">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d587f-118">Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d587f-118">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="d587f-119">El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="d587f-119">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="d587f-120">Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="d587f-120">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. <span data-ttu-id="d587f-121">Implemente un controlador para el evento de <xref:System.Windows.Forms.Form.Load> del formulario que inicializa el <xref:System.Windows.Forms.DataGridView> y <xref:System.Windows.Forms.BindingSource> y configura el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="d587f-121">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. <span data-ttu-id="d587f-122">Controle el evento de <xref:System.Windows.Forms.DataGridView.DataError> en el <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="d587f-122">Handle the <xref:System.Windows.Forms.DataGridView.DataError> event on the <xref:System.Windows.Forms.DataGridView>.</span></span>

    <span data-ttu-id="d587f-123">Si el contexto del error es una operación de confirmación, muestra el error en un <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="d587f-123">If the context for the error is a commit operation, display the error in a <xref:System.Windows.Forms.MessageBox>.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a><span data-ttu-id="d587f-124">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="d587f-124">Testing the Application</span></span>

<span data-ttu-id="d587f-125">Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.</span><span class="sxs-lookup"><span data-stu-id="d587f-125">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="d587f-126">Para comprobar el formulario</span><span class="sxs-lookup"><span data-stu-id="d587f-126">To test the form</span></span>

- <span data-ttu-id="d587f-127">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d587f-127">Press F5 to run the application.</span></span>

  <span data-ttu-id="d587f-128">Verá un control de <xref:System.Windows.Forms.DataGridView> rellenado con los datos de la tabla customers.</span><span class="sxs-lookup"><span data-stu-id="d587f-128">You will see a <xref:System.Windows.Forms.DataGridView> control filled with data from the Customers table.</span></span> <span data-ttu-id="d587f-129">Si escribe un valor duplicado para `CustomerID` y confirma la edición, el valor de la celda se revertirá automáticamente y verá una <xref:System.Windows.Forms.MessageBox> que muestra el error de entrada de datos.</span><span class="sxs-lookup"><span data-stu-id="d587f-129">If you enter a duplicate value for `CustomerID` and commit the edit, the cell value will revert automatically and you will see a <xref:System.Windows.Forms.MessageBox> that displays the data entry error.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d587f-130">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d587f-130">Next Steps</span></span>

<span data-ttu-id="d587f-131">Esta aplicación ofrece una descripción básica de las capacidades del control de <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="d587f-131">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="d587f-132">Puede personalizar la apariencia y el comportamiento del control de <xref:System.Windows.Forms.DataGridView> de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="d587f-132">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="d587f-133">Cambiar los estilos de borde y encabezado.</span><span class="sxs-lookup"><span data-stu-id="d587f-133">Change border and header styles.</span></span> <span data-ttu-id="d587f-134">Para obtener más información, vea [Cómo: cambiar los estilos de borde y de línea de cuadrícula en el control DataGridView Windows Forms](change-the-border-and-gridline-styles-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="d587f-134">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="d587f-135">Habilitar o restringir la entrada del usuario al control de <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="d587f-135">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d587f-136">Para obtener más información, vea [Cómo: impedir la adición y eliminación de filas en el control datagridview Windows Forms](prevent-row-addition-and-deletion-datagridview.md)y [Cómo: crear columnas de solo lectura en el control DataGridView Windows Forms](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="d587f-136">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="d587f-137">Valide los datos proporcionados por el usuario al control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="d587f-137">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d587f-138">Para obtener más información, vea [Tutorial: validar datos en el control DataGridView Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="d587f-138">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="d587f-139">Administrar conjuntos de datos muy grandes mediante el modo virtual.</span><span class="sxs-lookup"><span data-stu-id="d587f-139">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="d587f-140">Para obtener más información, vea [Tutorial: implementar el modo virtual en el control DataGridView de Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="d587f-140">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="d587f-141">Personalizar la apariencia de las celdas.</span><span class="sxs-lookup"><span data-stu-id="d587f-141">Customize the appearance of cells.</span></span> <span data-ttu-id="d587f-142">Para obtener más información, vea [Cómo: personalizar la apariencia de las celdas en el control datagridview Windows Forms](customize-the-appearance-of-cells-in-the-datagrid.md) y [Cómo: establecer estilos de celda predeterminados para el control DataGridView Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="d587f-142">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d587f-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="d587f-143">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="d587f-144">Entrada de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d587f-144">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d587f-145">Controlar los errores que se producen durante la entrada de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d587f-145">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="d587f-146">Tutorial: Validar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d587f-146">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d587f-147">Proteger la información de conexión</span><span class="sxs-lookup"><span data-stu-id="d587f-147">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
