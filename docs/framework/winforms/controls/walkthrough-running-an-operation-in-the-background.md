---
title: 'Tutorial: Ejecutar una operación en segundo plano'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
ms.openlocfilehash: c1881ffa1c6fca546b086efea59d2263af853949
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59308450"
---
# <a name="walkthrough-running-an-operation-in-the-background"></a><span data-ttu-id="dc734-102">Tutorial: Ejecutar una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="dc734-102">Walkthrough: Running an Operation in the Background</span></span>
<span data-ttu-id="dc734-103">Si tiene una operación que tarda mucho tiempo en completarse y no desea causar retrasos en la interfaz de usuario, puede utilizar la clase <xref:System.ComponentModel.BackgroundWorker> para ejecutar la operación en otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="dc734-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="dc734-104">Para obtener una lista completa del código utilizado en este ejemplo, vea [Cómo: Ejecutar una operación en segundo plano](how-to-run-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="dc734-104">For a complete listing of the code used in this example, see [How to: Run an Operation in the Background](how-to-run-an-operation-in-the-background.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc734-105">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="dc734-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="dc734-106">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="dc734-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="dc734-107">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="dc734-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-run-an-operation-in-the-background"></a><span data-ttu-id="dc734-108">Para ejecutar una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="dc734-108">To run an operation in the background</span></span>  
  
1. <span data-ttu-id="dc734-109">Con el formulario activo en el Diseñador de Windows Forms, arrastre dos <xref:System.Windows.Forms.Button> controla desde el **cuadro de herramientas** al formulario y, a continuación, establezca el `Name` y <xref:System.Windows.Forms.Control.Text%2A> las propiedades de los botones de acuerdo con la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="dc734-109">With your form active in the Windows Forms Designer, drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** to the form, and then set the `Name` and <xref:System.Windows.Forms.Control.Text%2A> properties of the buttons according to the following table.</span></span>  
  
    |<span data-ttu-id="dc734-110">Botón</span><span class="sxs-lookup"><span data-stu-id="dc734-110">Button</span></span>|<span data-ttu-id="dc734-111">Name</span><span class="sxs-lookup"><span data-stu-id="dc734-111">Name</span></span>|<span data-ttu-id="dc734-112">Texto</span><span class="sxs-lookup"><span data-stu-id="dc734-112">Text</span></span>|  
    |------------|----------|----------|  
    |`button1`|`startBtn`|**<span data-ttu-id="dc734-113">Iniciar</span><span class="sxs-lookup"><span data-stu-id="dc734-113">Start</span></span>**|  
    |`button2`|`cancelBtn`|**<span data-ttu-id="dc734-114">Cancelar</span><span class="sxs-lookup"><span data-stu-id="dc734-114">Cancel</span></span>**|  
  
2. <span data-ttu-id="dc734-115">Abra el **cuadro de herramientas**, haga clic en el **componentes** pestaña y, a continuación, arrastre el <xref:System.ComponentModel.BackgroundWorker> componente al formulario.</span><span class="sxs-lookup"><span data-stu-id="dc734-115">Open the **Toolbox**, click the **Components** tab, and then drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span>  
  
     <span data-ttu-id="dc734-116">El `backgroundWorker1` componente aparecerá en el **Bandeja de componentes**.</span><span class="sxs-lookup"><span data-stu-id="dc734-116">The `backgroundWorker1` component appears in the **Component Tray**.</span></span>  
  
3. <span data-ttu-id="dc734-117">En la ventana **Propiedades** , establezca la propiedad <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="dc734-117">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> property to `true`.</span></span>  
  
4. <span data-ttu-id="dc734-118">En el **propiedades** ventana, haga clic en el **eventos** botón y, a continuación, haga doble clic en el <xref:System.ComponentModel.BackgroundWorker.DoWork> y <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> eventos para crear controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="dc734-118">In the **Properties** window, click on the **Events** button, and then double-click the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> events to create event handlers.</span></span>  
  
5. <span data-ttu-id="dc734-119">Inserte el código que requieren mucho tiempo en el <xref:System.ComponentModel.BackgroundWorker.DoWork> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="dc734-119">Insert your time-consuming code into the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
6. <span data-ttu-id="dc734-120">Extraer los parámetros requeridos por la operación desde el <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> propiedad de la <xref:System.ComponentModel.DoWorkEventArgs> parámetro.</span><span class="sxs-lookup"><span data-stu-id="dc734-120">Extract any parameters required by the operation from the <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs> parameter.</span></span>  
  
7. <span data-ttu-id="dc734-121">Asignar el resultado del cálculo a la <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> propiedad de la <xref:System.ComponentModel.DoWorkEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="dc734-121">Assign the result of the computation to the <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span>  
  
     <span data-ttu-id="dc734-122">Esta forma se estén disponibles para el <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="dc734-122">This is will be available to the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]  
  
8. <span data-ttu-id="dc734-123">Inserte código para recuperar el resultado de la operación en el <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="dc734-123">Insert code for retrieving the result of your operation in the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]  
  
9. <span data-ttu-id="dc734-124">Implemente el método `TimeConsumingOperation`.</span><span class="sxs-lookup"><span data-stu-id="dc734-124">Implement the `TimeConsumingOperation` method.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]  
  
10. <span data-ttu-id="dc734-125">En el Diseñador de formularios de Windows, haga doble clic en `startButton` para crear el <xref:System.Windows.Forms.Control.Click> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="dc734-125">In the Windows Forms Designer, double-click `startButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
11. <span data-ttu-id="dc734-126">Llame a la <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> método en el <xref:System.Windows.Forms.Control.Click> controlador de eventos para `startButton`.</span><span class="sxs-lookup"><span data-stu-id="dc734-126">Call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `startButton`.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]  
  
12. <span data-ttu-id="dc734-127">En el Diseñador de formularios de Windows, haga doble clic en `cancelButton` para crear el <xref:System.Windows.Forms.Control.Click> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="dc734-127">In the Windows Forms Designer, double-click `cancelButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
13. <span data-ttu-id="dc734-128">Llame a la <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> método en el <xref:System.Windows.Forms.Control.Click> controlador de eventos para `cancelButton`.</span><span class="sxs-lookup"><span data-stu-id="dc734-128">Call the <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `cancelButton`.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]  
  
14. <span data-ttu-id="dc734-129">En la parte superior del archivo, importe los espacios de nombres System.ComponentModel y System.Threading.</span><span class="sxs-lookup"><span data-stu-id="dc734-129">At the top of the file, import the System.ComponentModel and System.Threading namespaces.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]  
  
15. <span data-ttu-id="dc734-130">Presione F6 para compilar la solución y, a continuación, presione CTRL-F5 para ejecutar la aplicación fuera del depurador.</span><span class="sxs-lookup"><span data-stu-id="dc734-130">Press F6 to build the solution, and then press CTRL-F5 to run the application outside the debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc734-131">Si presiona F5 para ejecutar la aplicación en el depurador, la excepción se produce en el `TimeConsumingOperation` método se detectará y mostrará el depurador.</span><span class="sxs-lookup"><span data-stu-id="dc734-131">If you press F5 to run the application under the debugger, the exception raised in the `TimeConsumingOperation` method is caught and displayed by the debugger.</span></span> <span data-ttu-id="dc734-132">Al ejecutar la aplicación fuera del depurador, el <xref:System.ComponentModel.BackgroundWorker> controla la excepción y lo almacena en caché en el <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> propiedad de la <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="dc734-132">When you run the application outside the debugger, the <xref:System.ComponentModel.BackgroundWorker> handles the exception and caches it in the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> property of the <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.</span></span>  
  
1. <span data-ttu-id="dc734-133">Haga clic en el **iniciar** botón para ejecutar una operación asincrónica y, a continuación, haga clic en el **cancelar** botón para detener una operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="dc734-133">Click the **Start** button to run an asynchronous operation, and then click the **Cancel** button to stop a running asynchronous operation.</span></span>  
  
     <span data-ttu-id="dc734-134">El resultado de cada operación se muestra en un elemento <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="dc734-134">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="dc734-135">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="dc734-135">Next Steps</span></span>  
  
-   <span data-ttu-id="dc734-136">Implementar un formulario que informa del progreso mientras se realiza una operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="dc734-136">Implement a form that reports progress as an asynchronous operation proceeds.</span></span> <span data-ttu-id="dc734-137">Para obtener más información, vea [Cómo: Implementar un formulario que utiliza una operación en segundo plano](how-to-implement-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="dc734-137">For more information, see [How to: Implement a Form That Uses a Background Operation](how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>  
  
-   <span data-ttu-id="dc734-138">Implemente una clase que admita el modelo asincrónico para componentes.</span><span class="sxs-lookup"><span data-stu-id="dc734-138">Implement a class that supports the Asynchronous Pattern for Components.</span></span> <span data-ttu-id="dc734-139">Para obtener más información, consulte [implementar el modelo asincrónico basado en eventos](../../../standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="dc734-139">For more information, see [Implementing the Event-based Asynchronous Pattern](../../../standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc734-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc734-140">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="dc734-141">Filtrar para implementar un formulario que usa una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="dc734-141">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="dc734-142">Filtrar para ejecutar una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="dc734-142">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="dc734-143">BackgroundWorker (Componente)</span><span class="sxs-lookup"><span data-stu-id="dc734-143">BackgroundWorker Component</span></span>](backgroundworker-component.md)
