---
title: 'Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31806d3ed13776e26634914b48bc887297ea4dab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="a13c1-102">Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a13c1-102">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a13c1-103">Si desea mostrar grandes cantidades de datos tabulares en una <xref:System.Windows.Forms.DataGridView> control, puede establecer la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad `true` y administrar de manera explícita la interacción del control con su almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="a13c1-103">When you want to display very large quantities of tabular data in a <xref:System.Windows.Forms.DataGridView> control, you can set the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property to `true` and explicitly manage the control's interaction with its data store.</span></span> <span data-ttu-id="a13c1-104">Esto le permite ajustar el rendimiento del control en esta situación.</span><span class="sxs-lookup"><span data-stu-id="a13c1-104">This lets you fine-tune the performance of the control in this situation.</span></span>  
  
 <span data-ttu-id="a13c1-105">El <xref:System.Windows.Forms.DataGridView> control proporciona varios eventos que puede controlar para interactuar con un almacén de datos personalizado.</span><span class="sxs-lookup"><span data-stu-id="a13c1-105">The <xref:System.Windows.Forms.DataGridView> control provides several events that you can handle to interact with a custom data store.</span></span> <span data-ttu-id="a13c1-106">Este tutorial le guía a través del proceso de implementar estos controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="a13c1-106">This walkthrough guides you through the process of implementing these event handlers.</span></span> <span data-ttu-id="a13c1-107">El ejemplo de código en este tema usa un origen de datos muy simple con fines meramente ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="a13c1-107">The code example in this topic uses a very simple data source for illustration purposes.</span></span> <span data-ttu-id="a13c1-108">En un entorno de producción, normalmente se cargará solo las filas que se debe mostrar en una memoria caché y controlar <xref:System.Windows.Forms.DataGridView> eventos para interactuar con y actualizar la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="a13c1-108">In a production setting, you will typically load only the rows you need to display into a cache, and handle <xref:System.Windows.Forms.DataGridView> events to interact with and update the cache.</span></span> <span data-ttu-id="a13c1-109">Para obtener más información, vea [implementar el modo Virtual con la carga de datos Just en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span><span class="sxs-lookup"><span data-stu-id="a13c1-109">For more information, see [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span></span>  
  
 <span data-ttu-id="a13c1-110">Para copiar el código de este tema como una sola lista, vea [Cómo: implementar el modo Virtual en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="a13c1-110">To copy the code in this topic as a single listing, see [How to: Implement Virtual Mode in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="a13c1-111">Crear el formulario</span><span class="sxs-lookup"><span data-stu-id="a13c1-111">Creating the Form</span></span>  
  
#### <a name="to-implement-virtual-mode"></a><span data-ttu-id="a13c1-112">Para implementar el modo virtual</span><span class="sxs-lookup"><span data-stu-id="a13c1-112">To implement virtual mode</span></span>  
  
1.  <span data-ttu-id="a13c1-113">Cree una clase que deriva de <xref:System.Windows.Forms.Form> y contiene un <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="a13c1-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="a13c1-114">El siguiente código contiene alguna inicialización básica.</span><span class="sxs-lookup"><span data-stu-id="a13c1-114">The following code contains some basic initialization.</span></span> <span data-ttu-id="a13c1-115">Declara algunas de las variables que se utilizarán en pasos posteriores, se proporciona un `Main` (método) y proporciona un diseño de forma simple en el constructor de clase.</span><span class="sxs-lookup"><span data-stu-id="a13c1-115">It declares some variables that will be used in later steps, provides a `Main` method, and provides a simple form layout in the class constructor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2.  <span data-ttu-id="a13c1-116">Implemente un controlador para el formulario <xref:System.Windows.Forms.Form.Load> eventos que inicializan el <xref:System.Windows.Forms.DataGridView> control y rellena el almacén de datos con valores de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a13c1-116">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> control and populates the data store with sample values.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3.  <span data-ttu-id="a13c1-117">Implemente un controlador para el <xref:System.Windows.Forms.DataGridView.CellValueNeeded> eventos que recupera el valor de celda solicitado desde el almacén de datos o la `Customer` objeto actualmente en Editar.</span><span class="sxs-lookup"><span data-stu-id="a13c1-117">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValueNeeded> event that retrieves the requested cell value from the data store or the `Customer` object currently in edit.</span></span>  
  
     <span data-ttu-id="a13c1-118">Este evento se produce siempre que el <xref:System.Windows.Forms.DataGridView> control necesita pintar una celda.</span><span class="sxs-lookup"><span data-stu-id="a13c1-118">This event occurs whenever the <xref:System.Windows.Forms.DataGridView> control needs to paint a cell.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4.  <span data-ttu-id="a13c1-119">Implemente un controlador para el <xref:System.Windows.Forms.DataGridView.CellValuePushed> eventos que almacena un valor de celda editado en el `Customer` objeto que representa la fila editada.</span><span class="sxs-lookup"><span data-stu-id="a13c1-119">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValuePushed> event that stores an edited cell value in the `Customer` object representing the edited row.</span></span> <span data-ttu-id="a13c1-120">Este evento se produce cuando el usuario confirma un cambio del valor de celda.</span><span class="sxs-lookup"><span data-stu-id="a13c1-120">This event occurs whenever the user commits a cell value change.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5.  <span data-ttu-id="a13c1-121">Implemente un controlador para el <xref:System.Windows.Forms.DataGridView.NewRowNeeded> eventos que se crea un nuevo `Customer` objeto que representa una fila recién creada.</span><span class="sxs-lookup"><span data-stu-id="a13c1-121">Implement a handler for the <xref:System.Windows.Forms.DataGridView.NewRowNeeded> event that creates a new `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="a13c1-122">Este evento se produce cada vez que el usuario escribe la fila para nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="a13c1-122">This event occurs whenever the user enters the row for new records.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6.  <span data-ttu-id="a13c1-123">Implemente un controlador para el <xref:System.Windows.Forms.DataGridView.RowValidated> evento que guarda filas nuevas o modificadas en el almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="a13c1-123">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowValidated> event that saves new or modified rows to the data store.</span></span>  
  
     <span data-ttu-id="a13c1-124">Este evento se produce cuando el usuario cambia la fila actual.</span><span class="sxs-lookup"><span data-stu-id="a13c1-124">This event occurs whenever the user changes the current row.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7.  <span data-ttu-id="a13c1-125">Implemente un controlador para el <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> evento que indica si la <xref:System.Windows.Forms.DataGridView.CancelRowEdit> evento se producirá cuando el usuario señala la reversión de la fila presionando la tecla ESC dos veces en modo de edición o una vez fuera del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="a13c1-125">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event that indicates whether the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event will occur when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span>  
  
     <span data-ttu-id="a13c1-126">De forma predeterminada, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> se produce después de crear una nueva versión de fila cuando se han modificado las celdas de la fila actual, a menos que la <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> propiedad está establecida en `true` en el <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="a13c1-126">By default, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> occurs upon row reversion when any cells in the current row have been modified unless the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property is set to `true` in the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span> <span data-ttu-id="a13c1-127">Este evento es útil cuando el ámbito de confirmación se determina en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a13c1-127">This event is useful when the commit scope is determined at run time.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8.  <span data-ttu-id="a13c1-128">Implemente un controlador para el <xref:System.Windows.Forms.DataGridView.CancelRowEdit> eventos que descartan los valores de la `Customer` objeto que representa la fila actual.</span><span class="sxs-lookup"><span data-stu-id="a13c1-128">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event that discards the values of the `Customer` object representing the current row.</span></span>  
  
     <span data-ttu-id="a13c1-129">Este evento se produce cuando el usuario señala la reversión de la fila presionando la tecla ESC dos veces en modo de edición o una vez fuera del modo de edición.</span><span class="sxs-lookup"><span data-stu-id="a13c1-129">This event occurs when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span> <span data-ttu-id="a13c1-130">Este evento no se produce si no se han modificado ninguna celda en la fila actual o si el valor de la <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> propiedad se ha establecido en `false` en un <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="a13c1-130">This event does not occur if no cells in the current row have been modified or if the value of the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property has been set to `false` in a <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. <span data-ttu-id="a13c1-131">Implemente un controlador para el <xref:System.Windows.Forms.DataGridView.UserDeletingRow> eventos que elimine una existente `Customer` objeto desde el almacén de datos o descarta una que no haya guardado `Customer` objeto que representa una fila recién creada.</span><span class="sxs-lookup"><span data-stu-id="a13c1-131">Implement a handler for the <xref:System.Windows.Forms.DataGridView.UserDeletingRow> event that deletes an existing `Customer` object from the data store or discards an unsaved `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="a13c1-132">Este evento se produce cuando el usuario elimina una fila haciendo clic en un encabezado de fila y presionando la tecla SUPR.</span><span class="sxs-lookup"><span data-stu-id="a13c1-132">This event occurs whenever the user deletes a row by clicking a row header and pressing the DELETE key.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. <span data-ttu-id="a13c1-133">Implementar un simple `Customers` clase para representar los elementos de datos utilizados por este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="a13c1-133">Implement a simple `Customers` class to represent the data items used by this code example.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="a13c1-134">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="a13c1-134">Testing the Application</span></span>  
 <span data-ttu-id="a13c1-135">Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.</span><span class="sxs-lookup"><span data-stu-id="a13c1-135">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="a13c1-136">Para comprobar el formulario</span><span class="sxs-lookup"><span data-stu-id="a13c1-136">To test the form</span></span>  
  
-   <span data-ttu-id="a13c1-137">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a13c1-137">Compile and run the application.</span></span>  
  
     <span data-ttu-id="a13c1-138">Verá un <xref:System.Windows.Forms.DataGridView> control rellenado con tres registros del cliente.</span><span class="sxs-lookup"><span data-stu-id="a13c1-138">You will see a <xref:System.Windows.Forms.DataGridView> control populated with three customer records.</span></span> <span data-ttu-id="a13c1-139">Puede modificar los valores de varias celdas de una fila y presione ESC dos veces en modo de edición y una vez fuera del modo de edición para revertir toda la fila a sus valores originales.</span><span class="sxs-lookup"><span data-stu-id="a13c1-139">You can modify the values of multiple cells in a row and press ESC twice in edit mode and once outside of edit mode to revert the entire row to its original values.</span></span> <span data-ttu-id="a13c1-140">Al modificar, agregar o eliminar filas en el control, `Customer` se modifica, se agregan o se eliminan también los objetos del almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="a13c1-140">When you modify, add, or delete rows in the control, `Customer` objects in the data store are modified, added, or deleted as well.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a13c1-141">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a13c1-141">Next Steps</span></span>  
 <span data-ttu-id="a13c1-142">Esta aplicación proporciona una descripción básica de los eventos que debe controlar para implementar el modo virtual en el <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="a13c1-142">This application gives you a basic understanding of the events you must handle to implement virtual mode in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a13c1-143">Puede mejorar esta aplicación básica de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="a13c1-143">You can improve this basic application in a number of ways:</span></span>  
  
-   <span data-ttu-id="a13c1-144">Implementar un almacén de datos que almacena en caché los valores de una base de datos externo.</span><span class="sxs-lookup"><span data-stu-id="a13c1-144">Implement a data store that caches values from an external database.</span></span> <span data-ttu-id="a13c1-145">La memoria caché debe recuperar y descartar los valores según sea necesario para que sólo contenga lo que es necesario para su presentación y consume una pequeña cantidad de memoria en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="a13c1-145">The cache should retrieve and discard values as necessary so that it only contains what is necessary for display while consuming a small amount of memory on the client computer.</span></span>  
  
-   <span data-ttu-id="a13c1-146">Ajustar el rendimiento del almacén de datos dependiendo de los requisitos.</span><span class="sxs-lookup"><span data-stu-id="a13c1-146">Fine-tune the performance of the data store depending on your requirements.</span></span> <span data-ttu-id="a13c1-147">Por ejemplo, puede compensar para conexiones de red lentas, en lugar de las limitaciones de memoria del equipo cliente utilizando un tamaño de caché y minimizando el número de consultas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="a13c1-147">For example, you might want to compensate for slow network connections rather than client-computer memory limitations by using a larger cache size and minimizing the number of database queries.</span></span>  
  
 <span data-ttu-id="a13c1-148">Para obtener más información sobre el almacenamiento en caché de los valores de una base de datos externo, vea [Cómo: implementar el modo Virtual con la carga de datos Just en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="a13c1-148">For more information about caching values from an external database, see [How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a13c1-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="a13c1-149">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <xref:System.Windows.Forms.DataGridView.CellValueNeeded>  
 <xref:System.Windows.Forms.DataGridView.CellValuePushed>  
 <xref:System.Windows.Forms.DataGridView.NewRowNeeded>  
 <xref:System.Windows.Forms.DataGridView.RowValidated>  
 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>  
 <xref:System.Windows.Forms.DataGridView.CancelRowEdit>  
 <xref:System.Windows.Forms.DataGridView.UserDeletingRow>  
 [<span data-ttu-id="a13c1-150">Ajuste del rendimiento del control DataGridView en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a13c1-150">Performance Tuning in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="a13c1-151">Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a13c1-151">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="a13c1-152">Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a13c1-152">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 [<span data-ttu-id="a13c1-153">Implementar el modo virtual en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a13c1-153">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
