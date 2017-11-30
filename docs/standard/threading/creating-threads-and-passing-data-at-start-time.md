---
title: Crear subprocesos y analizar los datos en el inicio
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], creating
- threading [.NET Framework], passing data to threads
- threading [.NET Framework], retrieving data from threads
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61808dc804cc627ab368a5250414dfcc5f54c87e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="creating-threads-and-passing-data-at-start-time"></a><span data-ttu-id="77f5a-102">Crear subprocesos y analizar los datos en el inicio</span><span class="sxs-lookup"><span data-stu-id="77f5a-102">Creating Threads and Passing Data at Start Time</span></span>
<span data-ttu-id="77f5a-103">Cuando se crea un proceso de sistema operativo, el sistema operativo inserta un subproceso para ejecutar el código en dicho proceso, incluido cualquier dominio de aplicación original.</span><span class="sxs-lookup"><span data-stu-id="77f5a-103">When an operating-system process is created, the operating system injects a thread to execute code in that process, including any original application domain.</span></span> <span data-ttu-id="77f5a-104">Desde ese momento, los dominios de aplicación se pueden crear y destruir sin ningún subproceso del sistema operativo necesariamente que se crea o se destruye.</span><span class="sxs-lookup"><span data-stu-id="77f5a-104">From that point on, application domains can be created and destroyed without any operating system threads necessarily being created or destroyed.</span></span> <span data-ttu-id="77f5a-105">Si se administra el código que se ejecuta código, un <xref:System.Threading.Thread> objeto para el subproceso que se ejecuta en el dominio de aplicación actual se puede obtener mediante la recuperación estático <xref:System.Threading.Thread.CurrentThread%2A> propiedad de tipo <xref:System.Threading.Thread>.</span><span class="sxs-lookup"><span data-stu-id="77f5a-105">If the code being executed is managed code, then a <xref:System.Threading.Thread> object for the thread executing in the current application domain can be obtained by retrieving the static <xref:System.Threading.Thread.CurrentThread%2A> property of type <xref:System.Threading.Thread>.</span></span> <span data-ttu-id="77f5a-106">En este tema se describe la creación de subprocesos y se analiza las alternativas para pasar datos al procedimiento de subproceso.</span><span class="sxs-lookup"><span data-stu-id="77f5a-106">This topic describes thread creation and discusses alternatives for passing data to the thread procedure.</span></span>  
  
## <a name="creating-a-thread"></a><span data-ttu-id="77f5a-107">Crear un subproceso</span><span class="sxs-lookup"><span data-stu-id="77f5a-107">Creating a Thread</span></span>  
 <span data-ttu-id="77f5a-108">Crear un nuevo <xref:System.Threading.Thread> objeto crea un nuevo subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="77f5a-108">Creating a new <xref:System.Threading.Thread> object creates a new managed thread.</span></span> <span data-ttu-id="77f5a-109">El <xref:System.Threading.Thread> clase tiene constructores que toman un <xref:System.Threading.ThreadStart> delegar o un <xref:System.Threading.ParameterizedThreadStart> delegar; el delegado ajusta el método que se invoca el nuevo subproceso cuando se llama a la <xref:System.Threading.Thread.Start%2A> método.</span><span class="sxs-lookup"><span data-stu-id="77f5a-109">The <xref:System.Threading.Thread> class has constructors that take a <xref:System.Threading.ThreadStart> delegate or a <xref:System.Threading.ParameterizedThreadStart> delegate; the delegate wraps the method that is invoked by the new thread when you call the <xref:System.Threading.Thread.Start%2A> method.</span></span> <span data-ttu-id="77f5a-110">Al llamar a <xref:System.Threading.Thread.Start%2A> hace más de una vez un <xref:System.Threading.ThreadStateException> que se produzca.</span><span class="sxs-lookup"><span data-stu-id="77f5a-110">Calling <xref:System.Threading.Thread.Start%2A> more than once causes a <xref:System.Threading.ThreadStateException> to be thrown.</span></span>  
  
 <span data-ttu-id="77f5a-111">El <xref:System.Threading.Thread.Start%2A> método devuelve inmediatamente, a menudo antes de que se haya iniciado realmente el nuevo subproceso.</span><span class="sxs-lookup"><span data-stu-id="77f5a-111">The <xref:System.Threading.Thread.Start%2A> method returns immediately, often before the new thread has actually started.</span></span> <span data-ttu-id="77f5a-112">Puede usar el <xref:System.Threading.Thread.ThreadState%2A> y <xref:System.Threading.Thread.IsAlive%2A> las propiedades para determinar el estado del subproceso en cualquier momento, pero estas propiedades nunca deben utilizarse para sincronizar las actividades de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="77f5a-112">You can use the <xref:System.Threading.Thread.ThreadState%2A> and <xref:System.Threading.Thread.IsAlive%2A> properties to determine the state of the thread at any one moment, but these properties should never be used for synchronizing the activities of threads.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77f5a-113">Una vez que se inicia un subproceso, no es necesario conservar una referencia a la <xref:System.Threading.Thread> objeto.</span><span class="sxs-lookup"><span data-stu-id="77f5a-113">Once a thread is started, it is not necessary to retain a reference to the <xref:System.Threading.Thread> object.</span></span> <span data-ttu-id="77f5a-114">El subproceso continúa ejecutándose hasta que finaliza el procedimiento de subproceso.</span><span class="sxs-lookup"><span data-stu-id="77f5a-114">The thread continues to execute until the thread procedure ends.</span></span>  
  
 <span data-ttu-id="77f5a-115">En el ejemplo de código siguiente se crea dos subprocesos nuevos para llamar a métodos estáticos e instancia en otro objeto.</span><span class="sxs-lookup"><span data-stu-id="77f5a-115">The following code example creates two new threads to call instance and static methods on another object.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads-and-retrieving-data-from-threads"></a><span data-ttu-id="77f5a-116">Pasar datos a subprocesos y recuperar datos de subprocesos</span><span class="sxs-lookup"><span data-stu-id="77f5a-116">Passing Data to Threads and Retrieving Data from Threads</span></span>  
 <span data-ttu-id="77f5a-117">En .NET Framework versión 2.0, el <xref:System.Threading.ParameterizedThreadStart> delegado proporciona una manera sencilla para pasar un objeto que contiene datos a un subproceso cuando se llama a la <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> sobrecarga del método.</span><span class="sxs-lookup"><span data-stu-id="77f5a-117">In the .NET Framework version 2.0, the <xref:System.Threading.ParameterizedThreadStart> delegate provides an easy way to pass an object containing data to a thread when you call the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload.</span></span> <span data-ttu-id="77f5a-118">Vea <xref:System.Threading.ParameterizedThreadStart> para obtener código muestra.</span><span class="sxs-lookup"><span data-stu-id="77f5a-118">See <xref:System.Threading.ParameterizedThreadStart> for a code example.</span></span>  
  
 <span data-ttu-id="77f5a-119">Mediante el <xref:System.Threading.ParameterizedThreadStart> delegado no es una forma de seguridad de tipos para pasar datos, porque el <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> sobrecarga del método acepta cualquier objeto.</span><span class="sxs-lookup"><span data-stu-id="77f5a-119">Using the <xref:System.Threading.ParameterizedThreadStart> delegate is not a type-safe way to pass data, because the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload accepts any object.</span></span> <span data-ttu-id="77f5a-120">Una alternativa consiste en encapsular el procedimiento de subproceso y los datos en una clase auxiliar y utilizar el <xref:System.Threading.ThreadStart> delegado para ejecutar el procedimiento de subproceso.</span><span class="sxs-lookup"><span data-stu-id="77f5a-120">An alternative is to encapsulate the thread procedure and the data in a helper class and use the <xref:System.Threading.ThreadStart> delegate to execute the thread procedure.</span></span> <span data-ttu-id="77f5a-121">Esta técnica se muestra en los dos ejemplos de código siguientes.</span><span class="sxs-lookup"><span data-stu-id="77f5a-121">This technique is shown in the two code examples that follow.</span></span>  
  
 <span data-ttu-id="77f5a-122">Ninguno de estos delegados tiene un valor devuelto, porque no hay ningún lugar para devolver los datos de una llamada asincrónica.</span><span class="sxs-lookup"><span data-stu-id="77f5a-122">Neither of these delegates has a return value, because there is no place to return the data from an asynchronous call.</span></span> <span data-ttu-id="77f5a-123">Para recuperar los resultados de un método de subproceso, puede utilizar un método de devolución de llamada, como se muestra en el segundo ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="77f5a-123">To retrieve the results of a thread method, you can use a callback method, as demonstrated in the second code example.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  
  
### <a name="retrieving-data-with-callback-methods"></a><span data-ttu-id="77f5a-124">Recuperar datos con métodos de devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="77f5a-124">Retrieving Data with Callback Methods</span></span>  
 <span data-ttu-id="77f5a-125">En el ejemplo siguiente se muestra un método de devolución de llamada que recupera datos de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="77f5a-125">The following example demonstrates a callback method that retrieves data from a thread.</span></span> <span data-ttu-id="77f5a-126">El constructor de la clase que contiene los datos y el método del subproceso también acepta a un delegado que representa el método de devolución de llamada; antes de que finalice el método del subproceso, invoca al delegado de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="77f5a-126">The constructor for the class that contains the data and the thread method also accepts a delegate representing the callback method; before the thread method ends, it invokes the callback delegate.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="77f5a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="77f5a-127">See Also</span></span>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadStart>  
 <xref:System.Threading.ParameterizedThreadStart>  
 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="77f5a-128">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="77f5a-128">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="77f5a-129">Usar subprocesos y subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="77f5a-129">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
