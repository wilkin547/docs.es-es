---
title: 'Tutorial: implementar el modo virtual en el control DataGridView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode [Windows Forms], walkthroughs
- DataGridView control [Windows Forms], large data sets
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
ms.openlocfilehash: 5db97b321238bc371c94e627a387bd83ca31b58a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746517"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="91d0f-102">Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91d0f-102">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="91d0f-103">Si desea mostrar grandes cantidades de datos tabulares en un control <xref:System.Windows.Forms.DataGridView>, puede establecer la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> en `true` y administrar explícitamente la interacción del control con su almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="91d0f-103">When you want to display very large quantities of tabular data in a <xref:System.Windows.Forms.DataGridView> control, you can set the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property to `true` and explicitly manage the control's interaction with its data store.</span></span> <span data-ttu-id="91d0f-104">Esto le permite ajustar el rendimiento del control en esta situación.</span><span class="sxs-lookup"><span data-stu-id="91d0f-104">This lets you fine-tune the performance of the control in this situation.</span></span>  
  
 <span data-ttu-id="91d0f-105">El control <xref:System.Windows.Forms.DataGridView> proporciona varios eventos que se pueden controlar para interactuar con un almacén de datos personalizado.</span><span class="sxs-lookup"><span data-stu-id="91d0f-105">The <xref:System.Windows.Forms.DataGridView> control provides several events that you can handle to interact with a custom data store.</span></span> <span data-ttu-id="91d0f-106">Este tutorial le guía a través del proceso de implementación de estos controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="91d0f-106">This walkthrough guides you through the process of implementing these event handlers.</span></span> <span data-ttu-id="91d0f-107">En el ejemplo de código de este tema se usa un origen de datos muy simple con fines ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="91d0f-107">The code example in this topic uses a very simple data source for illustration purposes.</span></span> <span data-ttu-id="91d0f-108">En una configuración de producción, normalmente solo se cargan las filas que se deben mostrar en una memoria caché y se controla <xref:System.Windows.Forms.DataGridView> eventos para interactuar con la memoria caché y actualizarla.</span><span class="sxs-lookup"><span data-stu-id="91d0f-108">In a production setting, you will typically load only the rows you need to display into a cache, and handle <xref:System.Windows.Forms.DataGridView> events to interact with and update the cache.</span></span> <span data-ttu-id="91d0f-109">Para obtener más información, vea [implementar el modo virtual con la carga de datos Just-in-Time en el control DataGridView Windows Forms](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span><span class="sxs-lookup"><span data-stu-id="91d0f-109">For more information, see [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span></span>  
  
 <span data-ttu-id="91d0f-110">Para copiar el código de este tema como una sola lista, vea [Cómo: implementar el modo virtual en el control DataGridView Windows Forms](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="91d0f-110">To copy the code in this topic as a single listing, see [How to: Implement Virtual Mode in the Windows Forms DataGridView Control](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="91d0f-111">Crear el formulario</span><span class="sxs-lookup"><span data-stu-id="91d0f-111">Creating the Form</span></span>  
  
#### <a name="to-implement-virtual-mode"></a><span data-ttu-id="91d0f-112">Para implementar el modo virtual</span><span class="sxs-lookup"><span data-stu-id="91d0f-112">To implement virtual mode</span></span>  
  
1. <span data-ttu-id="91d0f-113">Cree una clase que derive de <xref:System.Windows.Forms.Form> y contenga un control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="91d0f-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="91d0f-114">El código siguiente contiene alguna inicialización básica.</span><span class="sxs-lookup"><span data-stu-id="91d0f-114">The following code contains some basic initialization.</span></span> <span data-ttu-id="91d0f-115">Declara algunas variables que se usarán en pasos posteriores, proporciona un método `Main` y proporciona un diseño de formulario simple en el constructor de clase.</span><span class="sxs-lookup"><span data-stu-id="91d0f-115">It declares some variables that will be used in later steps, provides a `Main` method, and provides a simple form layout in the class constructor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. <span data-ttu-id="91d0f-116">Implemente un controlador para el evento de <xref:System.Windows.Forms.Form.Load> del formulario que inicializa el control <xref:System.Windows.Forms.DataGridView> y rellena el almacén de datos con valores de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="91d0f-116">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> control and populates the data store with sample values.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. <span data-ttu-id="91d0f-117">Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellValueNeeded> que recupera el valor de la celda solicitada del almacén de datos o el objeto `Customer` actualmente en edición.</span><span class="sxs-lookup"><span data-stu-id="91d0f-117">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValueNeeded> event that retrieves the requested cell value from the data store or the `Customer` object currently in edit.</span></span>  
  
     <span data-ttu-id="91d0f-118">Este evento se produce siempre que el control de <xref:System.Windows.Forms.DataGridView> necesita pintar una celda.</span><span class="sxs-lookup"><span data-stu-id="91d0f-118">This event occurs whenever the <xref:System.Windows.Forms.DataGridView> control needs to paint a cell.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. <span data-ttu-id="91d0f-119">Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellValuePushed> que almacena un valor de celda editado en el objeto `Customer` que representa la fila modificada.</span><span class="sxs-lookup"><span data-stu-id="91d0f-119">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValuePushed> event that stores an edited cell value in the `Customer` object representing the edited row.</span></span> <span data-ttu-id="91d0f-120">Este evento se produce siempre que el usuario confirma un cambio en el valor de una celda.</span><span class="sxs-lookup"><span data-stu-id="91d0f-120">This event occurs whenever the user commits a cell value change.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. <span data-ttu-id="91d0f-121">Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.NewRowNeeded> que crea un nuevo objeto `Customer` que representa una fila recién creada.</span><span class="sxs-lookup"><span data-stu-id="91d0f-121">Implement a handler for the <xref:System.Windows.Forms.DataGridView.NewRowNeeded> event that creates a new `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="91d0f-122">Este evento se produce siempre que el usuario escribe la fila de nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="91d0f-122">This event occurs whenever the user enters the row for new records.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. <span data-ttu-id="91d0f-123">Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.RowValidated> que guarde las filas nuevas o modificadas en el almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="91d0f-123">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowValidated> event that saves new or modified rows to the data store.</span></span>  
  
     <span data-ttu-id="91d0f-124">Este evento se produce siempre que el usuario cambia la fila actual.</span><span class="sxs-lookup"><span data-stu-id="91d0f-124">This event occurs whenever the user changes the current row.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. <span data-ttu-id="91d0f-125">Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> que indica si el evento de <xref:System.Windows.Forms.DataGridView.CancelRowEdit> se producirá cuando el usuario señale la reversión de la fila presionando ESC dos veces en modo de edición o una vez fuera del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="91d0f-125">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event that indicates whether the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event will occur when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span>  
  
     <span data-ttu-id="91d0f-126">De forma predeterminada, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> se produce tras la reversión de las filas cuando se modifican las celdas de la fila actual, a menos que la propiedad <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> esté establecida en `true` en el controlador de eventos <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>.</span><span class="sxs-lookup"><span data-stu-id="91d0f-126">By default, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> occurs upon row reversion when any cells in the current row have been modified unless the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property is set to `true` in the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span> <span data-ttu-id="91d0f-127">Este evento es útil cuando el ámbito de confirmación se determina en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="91d0f-127">This event is useful when the commit scope is determined at run time.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. <span data-ttu-id="91d0f-128">Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.CancelRowEdit> que descarte los valores del objeto `Customer` que representa la fila actual.</span><span class="sxs-lookup"><span data-stu-id="91d0f-128">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event that discards the values of the `Customer` object representing the current row.</span></span>  
  
     <span data-ttu-id="91d0f-129">Este evento se produce cuando el usuario señala la reversión de la fila presionando ESC dos veces en modo de edición o una vez fuera del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="91d0f-129">This event occurs when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span> <span data-ttu-id="91d0f-130">Este evento no se produce si no se ha modificado ninguna celda de la fila actual o si se ha establecido el valor de la propiedad <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> en `false` en un controlador de eventos <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>.</span><span class="sxs-lookup"><span data-stu-id="91d0f-130">This event does not occur if no cells in the current row have been modified or if the value of the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property has been set to `false` in a <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. <span data-ttu-id="91d0f-131">Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.UserDeletingRow> que elimina un objeto `Customer` existente del almacén de datos o descarta un objeto `Customer` no guardado que representa una fila recién creada.</span><span class="sxs-lookup"><span data-stu-id="91d0f-131">Implement a handler for the <xref:System.Windows.Forms.DataGridView.UserDeletingRow> event that deletes an existing `Customer` object from the data store or discards an unsaved `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="91d0f-132">Este evento se produce cuando el usuario elimina una fila haciendo clic en un encabezado de fila y presionando la tecla Supr.</span><span class="sxs-lookup"><span data-stu-id="91d0f-132">This event occurs whenever the user deletes a row by clicking a row header and pressing the DELETE key.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. <span data-ttu-id="91d0f-133">Implemente una clase de `Customers` simple para representar los elementos de datos utilizados en este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="91d0f-133">Implement a simple `Customers` class to represent the data items used by this code example.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="91d0f-134">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="91d0f-134">Testing the Application</span></span>  
 <span data-ttu-id="91d0f-135">Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.</span><span class="sxs-lookup"><span data-stu-id="91d0f-135">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="91d0f-136">Para comprobar el formulario</span><span class="sxs-lookup"><span data-stu-id="91d0f-136">To test the form</span></span>  
  
- <span data-ttu-id="91d0f-137">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="91d0f-137">Compile and run the application.</span></span>  
  
     <span data-ttu-id="91d0f-138">Verá un control de <xref:System.Windows.Forms.DataGridView> rellenado con tres registros de cliente.</span><span class="sxs-lookup"><span data-stu-id="91d0f-138">You will see a <xref:System.Windows.Forms.DataGridView> control populated with three customer records.</span></span> <span data-ttu-id="91d0f-139">Puede modificar los valores de varias celdas de una fila y presionar ESC dos veces en modo de edición y una vez fuera del modo de edición para revertir toda la fila a sus valores originales.</span><span class="sxs-lookup"><span data-stu-id="91d0f-139">You can modify the values of multiple cells in a row and press ESC twice in edit mode and once outside of edit mode to revert the entire row to its original values.</span></span> <span data-ttu-id="91d0f-140">Cuando se modifican, agregan o eliminan filas en el control, `Customer` objetos del almacén de datos también se modifican, agregan o eliminan.</span><span class="sxs-lookup"><span data-stu-id="91d0f-140">When you modify, add, or delete rows in the control, `Customer` objects in the data store are modified, added, or deleted as well.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="91d0f-141">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="91d0f-141">Next Steps</span></span>  
 <span data-ttu-id="91d0f-142">Esta aplicación le proporciona una descripción básica de los eventos que debe controlar para implementar el modo virtual en el control de <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="91d0f-142">This application gives you a basic understanding of the events you must handle to implement virtual mode in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="91d0f-143">Puede mejorar esta aplicación básica de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="91d0f-143">You can improve this basic application in a number of ways:</span></span>  
  
- <span data-ttu-id="91d0f-144">Implemente un almacén de datos que almacene en memoria caché los valores de una base de datos externa.</span><span class="sxs-lookup"><span data-stu-id="91d0f-144">Implement a data store that caches values from an external database.</span></span> <span data-ttu-id="91d0f-145">La memoria caché debe recuperar y descartar los valores según sea necesario para que solo contengan lo necesario para la presentación y consumir una pequeña cantidad de memoria en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="91d0f-145">The cache should retrieve and discard values as necessary so that it only contains what is necessary for display while consuming a small amount of memory on the client computer.</span></span>  
  
- <span data-ttu-id="91d0f-146">Ajuste el rendimiento del almacén de datos en función de sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="91d0f-146">Fine-tune the performance of the data store depending on your requirements.</span></span> <span data-ttu-id="91d0f-147">Por ejemplo, puede que desee compensar las conexiones de red lentas en lugar de las limitaciones de memoria del equipo cliente con un tamaño de caché mayor y minimizar el número de consultas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="91d0f-147">For example, you might want to compensate for slow network connections rather than client-computer memory limitations by using a larger cache size and minimizing the number of database queries.</span></span>  
  
 <span data-ttu-id="91d0f-148">Para obtener más información acerca de los valores de almacenamiento en caché de una base de datos externa, consulte [Cómo: implementar el modo virtual con la carga de datos Just-in-Time en el control DataGridView Windows Forms](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="91d0f-148">For more information about caching values from an external database, see [How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91d0f-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="91d0f-149">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="91d0f-150">Ajuste del rendimiento del control DataGridView en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91d0f-150">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="91d0f-151">Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91d0f-151">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="91d0f-152">Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91d0f-152">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [<span data-ttu-id="91d0f-153">Implementar el modo virtual en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91d0f-153">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
