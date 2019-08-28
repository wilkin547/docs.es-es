---
title: Información general sobre el componente BackgroundWorker
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- BackgroundWorker
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 64e9b3ab-7443-4a77-ab17-b8b8c0cb3f62
ms.openlocfilehash: e91d74b7ca5515dd63ba17a9111cadf5090dae2a
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046108"
---
# <a name="backgroundworker-component-overview"></a><span data-ttu-id="6b093-102">Información general sobre el componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="6b093-102">BackgroundWorker Component Overview</span></span>
<span data-ttu-id="6b093-103">Muchas operaciones que se realizan habitualmente pueden tardar mucho tiempo en ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="6b093-103">There are many commonly performed operations that can take a long time to execute.</span></span> <span data-ttu-id="6b093-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6b093-104">For example:</span></span>  
  
- <span data-ttu-id="6b093-105">Descargas de imágenes</span><span class="sxs-lookup"><span data-stu-id="6b093-105">Image downloads</span></span>  
  
- <span data-ttu-id="6b093-106">Invocaciones de servicios web</span><span class="sxs-lookup"><span data-stu-id="6b093-106">Web service invocations</span></span>  
  
- <span data-ttu-id="6b093-107">Descargas y cargas de archivos (incluidas aplicaciones punto a punto)</span><span class="sxs-lookup"><span data-stu-id="6b093-107">File downloads and uploads (including for peer-to-peer applications)</span></span>  
  
- <span data-ttu-id="6b093-108">Cálculos locales complejos</span><span class="sxs-lookup"><span data-stu-id="6b093-108">Complex local computations</span></span>  
  
- <span data-ttu-id="6b093-109">Transacciones de bases de datos</span><span class="sxs-lookup"><span data-stu-id="6b093-109">Database transactions</span></span>  
  
- <span data-ttu-id="6b093-110">Acceso a disco local, debido a su baja velocidad con relación al acceso a la memoria</span><span class="sxs-lookup"><span data-stu-id="6b093-110">Local disk access, given its slow speed relative to memory access</span></span>  
  
 <span data-ttu-id="6b093-111">Las operaciones como estas pueden hacer que la interfaz de usuario se bloquee mientras se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="6b093-111">Operations like these can cause your user interface to block while they are running.</span></span> <span data-ttu-id="6b093-112">Si quiere una interfaz de usuario con capacidad de respuesta y está sufriendo grandes retrasos asociados con estas operaciones, el componente <xref:System.ComponentModel.BackgroundWorker> ofrece una solución apropiada.</span><span class="sxs-lookup"><span data-stu-id="6b093-112">When you want a responsive UI and you are faced with long delays associated with such operations, the <xref:System.ComponentModel.BackgroundWorker> component provides a convenient solution.</span></span>  
  
 <span data-ttu-id="6b093-113">El componente <xref:System.ComponentModel.BackgroundWorker> le ofrece la posibilidad de ejecutar operaciones prolongadas de forma asincrónica ("en segundo plano"), en un subproceso diferente del subproceso principal de la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b093-113">The <xref:System.ComponentModel.BackgroundWorker> component gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span> <span data-ttu-id="6b093-114">Para usar un <xref:System.ComponentModel.BackgroundWorker>, solo tiene que decirle qué método de trabajo prolongado debe ejecutar en segundo plano y, después, llame al método <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="6b093-114">To use a <xref:System.ComponentModel.BackgroundWorker>, you simply tell it what time-consuming worker method to execute in the background, and then you call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span> <span data-ttu-id="6b093-115">El subproceso que realiza la llamada continúa ejecutándose normalmente mientras el método de trabajo se ejecuta asincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="6b093-115">Your calling thread continues to run normally while the worker method runs asynchronously.</span></span> <span data-ttu-id="6b093-116">Cuando el método termina, el <xref:System.ComponentModel.BackgroundWorker> alerta al subproceso que realizó la llamada activando el evento <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> que, opcionalmente, contiene el resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="6b093-116">When the method is finished, the <xref:System.ComponentModel.BackgroundWorker> alerts the calling thread by firing the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event, which optionally contains the results of the operation.</span></span>  
  
 <span data-ttu-id="6b093-117">El <xref:System.ComponentModel.BackgroundWorker> componente está disponible en el **cuadro de herramientas**, en la pestaña **componentes** . Para agregar un <xref:System.ComponentModel.BackgroundWorker> a su formulario, arrastre el componente <xref:System.ComponentModel.BackgroundWorker> al formulario.</span><span class="sxs-lookup"><span data-stu-id="6b093-117">The <xref:System.ComponentModel.BackgroundWorker> component is available from the **Toolbox**, in the **Components** tab. To add a <xref:System.ComponentModel.BackgroundWorker> to your form, drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span> <span data-ttu-id="6b093-118">Aparece en la bandeja de componentes y sus propiedades aparecen en la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="6b093-118">It appears in the component tray, and its properties appear in the **Properties** window.</span></span>  
  
 <span data-ttu-id="6b093-119">Para iniciar la operación asincrónica, use el método <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="6b093-119">To start your asynchronous operation, use the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span> <span data-ttu-id="6b093-120"><xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> toma un parámetro `object` opcional, que se puede usar para pasar argumentos al método de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6b093-120"><xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> takes an optional `object` parameter, which can be used to pass arguments to your worker method.</span></span> <span data-ttu-id="6b093-121">La clase <xref:System.ComponentModel.BackgroundWorker> expone el evento <xref:System.ComponentModel.BackgroundWorker.DoWork>, al que el subproceso de trabajo se asocia mediante un controlador de evento <xref:System.ComponentModel.BackgroundWorker.DoWork>.</span><span class="sxs-lookup"><span data-stu-id="6b093-121">The <xref:System.ComponentModel.BackgroundWorker> class exposes the <xref:System.ComponentModel.BackgroundWorker.DoWork> event, to which your worker thread is attached through a <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
 <span data-ttu-id="6b093-122">El controlador de evento <xref:System.ComponentModel.BackgroundWorker.DoWork> toma un parámetro <xref:System.ComponentModel.DoWorkEventArgs>, que tiene una propiedad <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A>.</span><span class="sxs-lookup"><span data-stu-id="6b093-122">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler takes a <xref:System.ComponentModel.DoWorkEventArgs> parameter, which has an <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property.</span></span> <span data-ttu-id="6b093-123">Esta propiedad recibe el parámetro de <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> y se puede pasar al método de trabajo, al que se llamará en el controlador de evento <xref:System.ComponentModel.BackgroundWorker.DoWork>.</span><span class="sxs-lookup"><span data-stu-id="6b093-123">This property receives the parameter from <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and can be passed to your worker method, which will be called in the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="6b093-124">En el ejemplo siguiente se muestra cómo asignar un resultado de un método de trabajo llamado `ComputeFibonacci`.</span><span class="sxs-lookup"><span data-stu-id="6b093-124">The following example shows how to assign a result from a worker method called `ComputeFibonacci`.</span></span> <span data-ttu-id="6b093-125">Forma parte de un ejemplo más grande, que puede encontrar en [cómo: Implementar un formulario que utiliza una operación](how-to-implement-a-form-that-uses-a-background-operation.md)en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="6b093-125">It is part of a larger example, which you can find at [How to: Implement a Form That Uses a Background Operation](how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>  
  
 [!code-cpp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
 [!code-vb[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
 <span data-ttu-id="6b093-126">Para obtener más información sobre el uso de controladores de eventos, vea [eventos](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="6b093-126">For more information on using event handlers, see [Events](../../../standard/events/index.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="6b093-127">Cuando se usa multithreading de algún tipo, se expone a posibles errores muy graves y complejos.</span><span class="sxs-lookup"><span data-stu-id="6b093-127">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="6b093-128">Vea [Procedimientos recomendados para el subprocesamiento administrado](../../../standard/threading/managed-threading-best-practices.md) antes de implementar cualquier solución que utilice multithreading.</span><span class="sxs-lookup"><span data-stu-id="6b093-128">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
 <span data-ttu-id="6b093-129">Para obtener más información sobre el <xref:System.ComponentModel.BackgroundWorker> uso de la [clase, vea cómo: Ejecutar una operación en segundo plano](how-to-run-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="6b093-129">For more information on using the <xref:System.ComponentModel.BackgroundWorker> class, see [How to: Run an Operation in the Background](how-to-run-an-operation-in-the-background.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b093-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b093-130">See also</span></span>

- [<span data-ttu-id="6b093-131">Subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="6b093-131">Managed Threading</span></span>](../../../standard/threading/index.md)
- [<span data-ttu-id="6b093-132">Información general sobre el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="6b093-132">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="6b093-133">Procedimientos: Implementar un formulario que usa una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="6b093-133">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
