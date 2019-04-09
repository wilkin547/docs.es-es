---
title: 'Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms'
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
ms.openlocfilehash: 7509e2f5035cb05c20af379f9f6a141177d540d4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127054"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="a9e24-102">Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a9e24-102">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a9e24-103">Cuando desea mostrar grandes cantidades de datos tabulares en una <xref:System.Windows.Forms.DataGridView> control, puede establecer el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad `true` y administrar explícitamente la interacción del control con su almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="a9e24-103">When you want to display very large quantities of tabular data in a <xref:System.Windows.Forms.DataGridView> control, you can set the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property to `true` and explicitly manage the control's interaction with its data store.</span></span> <span data-ttu-id="a9e24-104">Esto le permite ajustar el rendimiento del control en esta situación.</span><span class="sxs-lookup"><span data-stu-id="a9e24-104">This lets you fine-tune the performance of the control in this situation.</span></span>  
  
 <span data-ttu-id="a9e24-105">El <xref:System.Windows.Forms.DataGridView> control proporciona varios eventos que puede controlar para interactuar con un almacén de datos personalizado.</span><span class="sxs-lookup"><span data-stu-id="a9e24-105">The <xref:System.Windows.Forms.DataGridView> control provides several events that you can handle to interact with a custom data store.</span></span> <span data-ttu-id="a9e24-106">En este tutorial le guiará a través del proceso de implementación de estos controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="a9e24-106">This walkthrough guides you through the process of implementing these event handlers.</span></span> <span data-ttu-id="a9e24-107">El ejemplo de código en este tema usa un origen de datos muy sencillo con fines meramente ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="a9e24-107">The code example in this topic uses a very simple data source for illustration purposes.</span></span> <span data-ttu-id="a9e24-108">En una configuración de producción, normalmente se cargará solo las filas que se debe mostrar en una memoria caché y controlar <xref:System.Windows.Forms.DataGridView> eventos e interactuar con actualizar la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="a9e24-108">In a production setting, you will typically load only the rows you need to display into a cache, and handle <xref:System.Windows.Forms.DataGridView> events to interact with and update the cache.</span></span> <span data-ttu-id="a9e24-109">Para obtener más información, consulte [implementar el modo Virtual con la carga de datos Just In Time en el DataGridView Control de formularios de Windows](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span><span class="sxs-lookup"><span data-stu-id="a9e24-109">For more information, see [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span></span>  
  
 <span data-ttu-id="a9e24-110">Para copiar el código de este tema como una sola lista, vea [Cómo: Implementar el modo Virtual en el Windows Forms DataGridView Control](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="a9e24-110">To copy the code in this topic as a single listing, see [How to: Implement Virtual Mode in the Windows Forms DataGridView Control](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="a9e24-111">Crear el formulario</span><span class="sxs-lookup"><span data-stu-id="a9e24-111">Creating the Form</span></span>  
  
#### <a name="to-implement-virtual-mode"></a><span data-ttu-id="a9e24-112">Para implementar el modo virtual</span><span class="sxs-lookup"><span data-stu-id="a9e24-112">To implement virtual mode</span></span>  
  
1.  <span data-ttu-id="a9e24-113">Cree una clase que deriva de <xref:System.Windows.Forms.Form> y contiene un <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="a9e24-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="a9e24-114">El siguiente código contiene alguna inicialización básica.</span><span class="sxs-lookup"><span data-stu-id="a9e24-114">The following code contains some basic initialization.</span></span> <span data-ttu-id="a9e24-115">Declara algunas variables que se usará en pasos posteriores, se proporciona un `Main` método y proporciona un diseño de forma sencilla en el constructor de clase.</span><span class="sxs-lookup"><span data-stu-id="a9e24-115">It declares some variables that will be used in later steps, provides a `Main` method, and provides a simple form layout in the class constructor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2.  <span data-ttu-id="a9e24-116">Implementar un controlador para el formulario <xref:System.Windows.Forms.Form.Load> eventos que inicializa el <xref:System.Windows.Forms.DataGridView> controlar y rellena el almacén de datos con valores de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a9e24-116">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> control and populates the data store with sample values.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3.  <span data-ttu-id="a9e24-117">Implementar un controlador para el <xref:System.Windows.Forms.DataGridView.CellValueNeeded> eventos que recupera el valor de celda solicitado desde el almacén de datos o el `Customer` objeto actualmente en la edición.</span><span class="sxs-lookup"><span data-stu-id="a9e24-117">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValueNeeded> event that retrieves the requested cell value from the data store or the `Customer` object currently in edit.</span></span>  
  
     <span data-ttu-id="a9e24-118">Este evento se produce siempre que el <xref:System.Windows.Forms.DataGridView> control necesita dibujar una celda.</span><span class="sxs-lookup"><span data-stu-id="a9e24-118">This event occurs whenever the <xref:System.Windows.Forms.DataGridView> control needs to paint a cell.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4.  <span data-ttu-id="a9e24-119">Implementar un controlador para el <xref:System.Windows.Forms.DataGridView.CellValuePushed> eventos que almacena un valor de celda modificada en el `Customer` objeto que representa la fila editada.</span><span class="sxs-lookup"><span data-stu-id="a9e24-119">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValuePushed> event that stores an edited cell value in the `Customer` object representing the edited row.</span></span> <span data-ttu-id="a9e24-120">Este evento se produce cada vez que el usuario confirma un cambio del valor de celda.</span><span class="sxs-lookup"><span data-stu-id="a9e24-120">This event occurs whenever the user commits a cell value change.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5.  <span data-ttu-id="a9e24-121">Implementar un controlador para el <xref:System.Windows.Forms.DataGridView.NewRowNeeded> eventos que crea un nuevo `Customer` objeto que representa una fila recién creada.</span><span class="sxs-lookup"><span data-stu-id="a9e24-121">Implement a handler for the <xref:System.Windows.Forms.DataGridView.NewRowNeeded> event that creates a new `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="a9e24-122">Este evento se produce cada vez que el usuario escribe la fila para los nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="a9e24-122">This event occurs whenever the user enters the row for new records.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6.  <span data-ttu-id="a9e24-123">Implementar un controlador para el <xref:System.Windows.Forms.DataGridView.RowValidated> eventos que guarda filas nuevas o modificadas en el almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="a9e24-123">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowValidated> event that saves new or modified rows to the data store.</span></span>  
  
     <span data-ttu-id="a9e24-124">Este evento se produce cuando el usuario cambia la fila actual.</span><span class="sxs-lookup"><span data-stu-id="a9e24-124">This event occurs whenever the user changes the current row.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7.  <span data-ttu-id="a9e24-125">Implementar un controlador para el <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> evento que indica si el <xref:System.Windows.Forms.DataGridView.CancelRowEdit> se producirá un evento cuando el usuario señala la reversión de la fila, presione ESC dos veces en modo de edición o una vez fuera del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="a9e24-125">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event that indicates whether the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event will occur when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span>  
  
     <span data-ttu-id="a9e24-126">De forma predeterminada, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> se produce al crear una nueva versión de fila cuando se han modificado las celdas de la fila actual a menos que el <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> propiedad está establecida en `true` en el <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="a9e24-126">By default, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> occurs upon row reversion when any cells in the current row have been modified unless the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property is set to `true` in the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span> <span data-ttu-id="a9e24-127">Este evento es útil cuando el ámbito de confirmación se determina en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a9e24-127">This event is useful when the commit scope is determined at run time.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8.  <span data-ttu-id="a9e24-128">Implementar un controlador para el <xref:System.Windows.Forms.DataGridView.CancelRowEdit> eventos que descartan los valores de la `Customer` objeto que representa la fila actual.</span><span class="sxs-lookup"><span data-stu-id="a9e24-128">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event that discards the values of the `Customer` object representing the current row.</span></span>  
  
     <span data-ttu-id="a9e24-129">Este evento se produce cuando el usuario señala la reversión de la fila, presione ESC dos veces en modo de edición o una vez fuera del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="a9e24-129">This event occurs when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span> <span data-ttu-id="a9e24-130">Este evento no se produce si no hay ninguna celda en la fila actual se han modificado o si el valor de la <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> se ha establecido la propiedad en `false` en un <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="a9e24-130">This event does not occur if no cells in the current row have been modified or if the value of the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property has been set to `false` in a <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. <span data-ttu-id="a9e24-131">Implementar un controlador para el <xref:System.Windows.Forms.DataGridView.UserDeletingRow> eventos que se eliminan una existente `Customer` objeto desde el almacén de datos o un no guardados se perderán `Customer` objeto que representa una fila recién creada.</span><span class="sxs-lookup"><span data-stu-id="a9e24-131">Implement a handler for the <xref:System.Windows.Forms.DataGridView.UserDeletingRow> event that deletes an existing `Customer` object from the data store or discards an unsaved `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="a9e24-132">Este evento se produce cada vez que el usuario elimina una fila haciendo clic en un encabezado de fila y presione la tecla SUPR.</span><span class="sxs-lookup"><span data-stu-id="a9e24-132">This event occurs whenever the user deletes a row by clicking a row header and pressing the DELETE key.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. <span data-ttu-id="a9e24-133">Implementar una sencilla `Customers` clase para representar los elementos de datos utilizados en este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="a9e24-133">Implement a simple `Customers` class to represent the data items used by this code example.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="a9e24-134">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="a9e24-134">Testing the Application</span></span>  
 <span data-ttu-id="a9e24-135">Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.</span><span class="sxs-lookup"><span data-stu-id="a9e24-135">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="a9e24-136">Para comprobar el formulario</span><span class="sxs-lookup"><span data-stu-id="a9e24-136">To test the form</span></span>  
  
-   <span data-ttu-id="a9e24-137">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9e24-137">Compile and run the application.</span></span>  
  
     <span data-ttu-id="a9e24-138">Verá un <xref:System.Windows.Forms.DataGridView> rellenado con tres registros de cliente del control.</span><span class="sxs-lookup"><span data-stu-id="a9e24-138">You will see a <xref:System.Windows.Forms.DataGridView> control populated with three customer records.</span></span> <span data-ttu-id="a9e24-139">Puede modificar los valores de varias celdas en una fila y presione ESC dos veces en modo de edición y una vez fuera del modo de edición para revertir toda la fila a sus valores originales.</span><span class="sxs-lookup"><span data-stu-id="a9e24-139">You can modify the values of multiple cells in a row and press ESC twice in edit mode and once outside of edit mode to revert the entire row to its original values.</span></span> <span data-ttu-id="a9e24-140">Al modificar, agregar o eliminar filas en el control, `Customer` objetos en el almacén de datos se puede modificar, se agregan o se eliminan también.</span><span class="sxs-lookup"><span data-stu-id="a9e24-140">When you modify, add, or delete rows in the control, `Customer` objects in the data store are modified, added, or deleted as well.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a9e24-141">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a9e24-141">Next Steps</span></span>  
 <span data-ttu-id="a9e24-142">Esta aplicación le ofrece un conocimiento básico de los eventos que se debe controlar para implementar el modo virtual en el <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="a9e24-142">This application gives you a basic understanding of the events you must handle to implement virtual mode in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a9e24-143">Puede mejorar esta aplicación básica de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="a9e24-143">You can improve this basic application in a number of ways:</span></span>  
  
-   <span data-ttu-id="a9e24-144">Implementar un almacén de datos que almacena en caché los valores de una base de datos externo.</span><span class="sxs-lookup"><span data-stu-id="a9e24-144">Implement a data store that caches values from an external database.</span></span> <span data-ttu-id="a9e24-145">La memoria caché debe recuperar y descartar los valores según sea necesario para que solo contiene lo que es necesario para su presentación y consume una pequeña cantidad de memoria en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="a9e24-145">The cache should retrieve and discard values as necessary so that it only contains what is necessary for display while consuming a small amount of memory on the client computer.</span></span>  
  
-   <span data-ttu-id="a9e24-146">Ajustar el rendimiento del almacén de datos según sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="a9e24-146">Fine-tune the performance of the data store depending on your requirements.</span></span> <span data-ttu-id="a9e24-147">Por ejemplo, podría desea compensar para conexiones de red lentas, en lugar de las limitaciones de memoria del equipo cliente utilizando un tamaño de caché mayor y minimizar el número de consultas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="a9e24-147">For example, you might want to compensate for slow network connections rather than client-computer memory limitations by using a larger cache size and minimizing the number of database queries.</span></span>  
  
 <span data-ttu-id="a9e24-148">Para obtener más información sobre almacenamiento en caché los valores de una base de datos externo, vea [Cómo: Implementar el modo Virtual con la carga de datos Just-In-Time en el Windows Forms DataGridView Control](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="a9e24-148">For more information about caching values from an external database, see [How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9e24-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9e24-149">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="a9e24-150">Ajuste del rendimiento del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a9e24-150">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a9e24-151">Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a9e24-151">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a9e24-152">Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a9e24-152">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [<span data-ttu-id="a9e24-153">Filtrar para implementar el modo virtual en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a9e24-153">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
