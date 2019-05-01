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
ms.openlocfilehash: 9e803b6450fb8c9ade4adde5bf98fb1c3c62c861
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971280"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="4cf7c-102">Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cf7c-102">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4cf7c-103">Control de errores del almacén de datos subyacente es una característica necesaria para una aplicación de entrada de datos.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-103">Handling errors from the underlying data store is a required feature for a data-entry application.</span></span> <span data-ttu-id="4cf7c-104">Los formularios de Windows <xref:System.Windows.Forms.DataGridView> control facilita esta tarea mediante la exposición de la <xref:System.Windows.Forms.DataGridView.DataError> evento, que se produce cuando el almacén de datos detecta una infracción de restricción o una regla de negocios roto.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-104">The Windows Forms <xref:System.Windows.Forms.DataGridView> control makes this easy by exposing the <xref:System.Windows.Forms.DataGridView.DataError> event, which is raised when the data store detects a constraint violation or a broken business rule.</span></span>  
  
 <span data-ttu-id="4cf7c-105">En este tutorial, va a recuperar las filas de la `Customers` de tabla en la base de datos de ejemplo Northwind y mostrarlos en un <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-105">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="4cf7c-106">Cuando un duplicado `CustomerID` se detecta el valor en una nueva fila o una fila existente editada, el <xref:System.Windows.Forms.DataGridView.DataError> se produce un evento que se controlarán mostrando un <xref:System.Windows.Forms.MessageBox> que describe la excepción.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-106">When a duplicate `CustomerID` value is detected in a new row or an edited existing row, the <xref:System.Windows.Forms.DataGridView.DataError> event will occur, which will be handled by displaying a <xref:System.Windows.Forms.MessageBox> that describes the exception.</span></span>  
  
 <span data-ttu-id="4cf7c-107">Para copiar el código de este tema como una sola lista, vea [Cómo: Controlar los errores que se producen durante la entrada de datos en la Windows Forms DataGridView Control](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="4cf7c-107">To copy the code in this topic as a single listing, see [How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4cf7c-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4cf7c-108">Prerequisites</span></span>  
 <span data-ttu-id="4cf7c-109">Para poder completar este tutorial, necesitará:</span><span class="sxs-lookup"><span data-stu-id="4cf7c-109">In order to complete this walkthrough, you will need:</span></span>  
  
- <span data-ttu-id="4cf7c-110">Acceso a un servidor que tenga la base de datos de ejemplo Northwind de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-110">Access to a server that has the Northwind SQL Server sample database.</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="4cf7c-111">Crear el formulario</span><span class="sxs-lookup"><span data-stu-id="4cf7c-111">Creating the Form</span></span>  
  
#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a><span data-ttu-id="4cf7c-112">Para controlar los errores de entrada de datos en el control DataGridView</span><span class="sxs-lookup"><span data-stu-id="4cf7c-112">To handle data-entry errors in the DataGridView control</span></span>  
  
1. <span data-ttu-id="4cf7c-113">Cree una clase que deriva de <xref:System.Windows.Forms.Form> y contiene un <xref:System.Windows.Forms.DataGridView> control y un <xref:System.Windows.Forms.BindingSource> componente.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
     <span data-ttu-id="4cf7c-114">En el ejemplo de código siguiente se proporciona la inicialización básica e incluye un `Main` método.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-114">The following code example provides basic initialization and includes a `Main` method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2. <span data-ttu-id="4cf7c-115">Implemente un método en la definición de clase del formulario para controlar los detalles de la conexión a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-115">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>  
  
     <span data-ttu-id="4cf7c-116">Este ejemplo de código se usa un `GetData` método que devuelva un rellenado <xref:System.Data.DataTable> objeto.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-116">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="4cf7c-117">Asegúrese de establecer el `connectionString` variable en un valor que sea adecuado para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-117">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4cf7c-118">Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-118">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="4cf7c-119">El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-119">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="4cf7c-120">Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="4cf7c-120">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3. <span data-ttu-id="4cf7c-121">Implementar un controlador para el formulario <xref:System.Windows.Forms.Form.Load> eventos que inicializa el <xref:System.Windows.Forms.DataGridView> y <xref:System.Windows.Forms.BindingSource> y configura el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-121">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4. <span data-ttu-id="4cf7c-122">Controlar la <xref:System.Windows.Forms.DataGridView.DataError> eventos en el <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-122">Handle the <xref:System.Windows.Forms.DataGridView.DataError> event on the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     <span data-ttu-id="4cf7c-123">Si el contexto del error es una operación de confirmación, se mostrará el error en un <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-123">If the context for the error is a commit operation, display the error in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="4cf7c-124">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="4cf7c-124">Testing the Application</span></span>  
 <span data-ttu-id="4cf7c-125">Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-125">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="4cf7c-126">Para comprobar el formulario</span><span class="sxs-lookup"><span data-stu-id="4cf7c-126">To test the form</span></span>  
  
- <span data-ttu-id="4cf7c-127">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-127">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="4cf7c-128">Verá un <xref:System.Windows.Forms.DataGridView> control rellenado con datos de la tabla Customers.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-128">You will see a <xref:System.Windows.Forms.DataGridView> control filled with data from the Customers table.</span></span> <span data-ttu-id="4cf7c-129">Si escribe un valor duplicado para `CustomerID` y confirmar la edición, el valor de celda se restablecerá automáticamente y aparecerá un <xref:System.Windows.Forms.MessageBox> que muestra el error de entrada de datos.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-129">If you enter a duplicate value for `CustomerID` and commit the edit, the cell value will revert automatically and you will see a <xref:System.Windows.Forms.MessageBox> that displays the data entry error.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4cf7c-130">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4cf7c-130">Next Steps</span></span>  
 <span data-ttu-id="4cf7c-131">Esta aplicación le ofrece un conocimiento básico de la <xref:System.Windows.Forms.DataGridView> capacidades del control.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-131">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="4cf7c-132">Puede personalizar la apariencia y comportamiento de la <xref:System.Windows.Forms.DataGridView> control de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="4cf7c-132">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>  
  
- <span data-ttu-id="4cf7c-133">Cambiar los estilos de borde y encabezado.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-133">Change border and header styles.</span></span> <span data-ttu-id="4cf7c-134">Para obtener más información, vea [Cómo: Cambiar el borde y los estilos de línea de cuadrícula en la Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="4cf7c-134">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="4cf7c-135">Habilitar o restringir la entrada del usuario a la <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-135">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="4cf7c-136">Para obtener más información, vea [Cómo: Impedir la adición de la fila y la eliminación en la Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), y [Cómo: Crear columnas de sólo lectura en la Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="4cf7c-136">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>  
  
- <span data-ttu-id="4cf7c-137">Validar la entrada del usuario a la <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-137">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="4cf7c-138">Para obtener más información, vea [Tutorial: Validar datos en el Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="4cf7c-138">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
- <span data-ttu-id="4cf7c-139">Controlar grandes conjuntos de datos utilizando el modo virtual.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-139">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="4cf7c-140">Para obtener más información, vea [Tutorial: Implementar el modo Virtual en el Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="4cf7c-140">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
- <span data-ttu-id="4cf7c-141">Personalizar la apariencia de celdas.</span><span class="sxs-lookup"><span data-stu-id="4cf7c-141">Customize the appearance of cells.</span></span> <span data-ttu-id="4cf7c-142">Para obtener más información, vea [Cómo: Personalizar la apariencia de celdas en el Control DataGridView de formularios de Windows](customize-the-appearance-of-cells-in-the-datagrid.md) y [Cómo: Establecer estilos de celda predeterminados para los Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="4cf7c-142">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cf7c-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cf7c-143">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="4cf7c-144">Entrada de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cf7c-144">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="4cf7c-145">Cómo: Controlar los errores que se producen durante la entrada de datos en el Control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cf7c-145">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="4cf7c-146">Tutorial: Validar datos en el Control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cf7c-146">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="4cf7c-147">Proteger la información de conexión</span><span class="sxs-lookup"><span data-stu-id="4cf7c-147">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
