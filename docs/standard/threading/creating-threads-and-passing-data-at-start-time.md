---
title: Creación de subprocesos y análisis los datos en el inicio
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], creating
- threading [.NET Framework], passing data to threads
- threading [.NET Framework], retrieving data from threads
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
ms.openlocfilehash: a628cbb4c9ec8e1c9ccd9fd73e72a82ecf2b2836
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138100"
---
# <a name="creating-threads-and-passing-data-at-start-time"></a><span data-ttu-id="f349d-102">Creación de subprocesos y análisis los datos en el inicio</span><span class="sxs-lookup"><span data-stu-id="f349d-102">Creating threads and passing data at start time</span></span>

<span data-ttu-id="f349d-103">Cuando se crea un proceso de sistema operativo, el sistema operativo inserta un subproceso para ejecutar el código en dicho proceso, incluido cualquier dominio de aplicación original.</span><span class="sxs-lookup"><span data-stu-id="f349d-103">When an operating-system process is created, the operating system injects a thread to execute code in that process, including any original application domain.</span></span> <span data-ttu-id="f349d-104">Desde ese momento, los dominios de aplicación se pueden crear y destruir sin que se cree o destruya necesariamente ningún subproceso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f349d-104">From that point on, application domains can be created and destroyed without any operating system threads necessarily being created or destroyed.</span></span> <span data-ttu-id="f349d-105">Si el código ejecutado es código administrado, se puede obtener un objeto <xref:System.Threading.Thread> para el subproceso que se ejecuta en el dominio de aplicación actual mediante la recuperación de la propiedad <xref:System.Threading.Thread.CurrentThread%2A> estática de tipo <xref:System.Threading.Thread>.</span><span class="sxs-lookup"><span data-stu-id="f349d-105">If the code being executed is managed code, then a <xref:System.Threading.Thread> object for the thread executing in the current application domain can be obtained by retrieving the static <xref:System.Threading.Thread.CurrentThread%2A> property of type <xref:System.Threading.Thread>.</span></span> <span data-ttu-id="f349d-106">En este tema se describe la creación de subprocesos y se analizan las alternativas para pasar datos al procedimiento de los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="f349d-106">This topic describes thread creation and discusses alternatives for passing data to the thread procedure.</span></span>  
  
## <a name="creating-a-thread"></a><span data-ttu-id="f349d-107">Creación de un subproceso</span><span class="sxs-lookup"><span data-stu-id="f349d-107">Creating a thread</span></span>

 <span data-ttu-id="f349d-108">Al crear un objeto <xref:System.Threading.Thread>, se crea un subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="f349d-108">Creating a new <xref:System.Threading.Thread> object creates a new managed thread.</span></span> <span data-ttu-id="f349d-109">La clase <xref:System.Threading.Thread> tiene constructores que adoptan un delegado <xref:System.Threading.ThreadStart> o un delegado <xref:System.Threading.ParameterizedThreadStart>; el delegado ajusta el método invocado por el nuevo subproceso cuando llama al método <xref:System.Threading.Thread.Start%2A>.</span><span class="sxs-lookup"><span data-stu-id="f349d-109">The <xref:System.Threading.Thread> class has constructors that take a <xref:System.Threading.ThreadStart> delegate or a <xref:System.Threading.ParameterizedThreadStart> delegate; the delegate wraps the method that is invoked by the new thread when you call the <xref:System.Threading.Thread.Start%2A> method.</span></span> <span data-ttu-id="f349d-110">Al llamar a <xref:System.Threading.Thread.Start%2A> más de una vez, se inicia <xref:System.Threading.ThreadStateException>.</span><span class="sxs-lookup"><span data-stu-id="f349d-110">Calling <xref:System.Threading.Thread.Start%2A> more than once causes a <xref:System.Threading.ThreadStateException> to be thrown.</span></span>  
  
 <span data-ttu-id="f349d-111">El método <xref:System.Threading.Thread.Start%2A> se devuelve inmediatamente, a menudo antes de que se haya iniciado realmente el nuevo subproceso.</span><span class="sxs-lookup"><span data-stu-id="f349d-111">The <xref:System.Threading.Thread.Start%2A> method returns immediately, often before the new thread has actually started.</span></span> <span data-ttu-id="f349d-112">Puede usar las propiedades <xref:System.Threading.Thread.ThreadState%2A> y <xref:System.Threading.Thread.IsAlive%2A> para determinar el estado del subproceso en cualquier momento, pero estas propiedades nunca deben utilizarse para sincronizar las actividades de los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="f349d-112">You can use the <xref:System.Threading.Thread.ThreadState%2A> and <xref:System.Threading.Thread.IsAlive%2A> properties to determine the state of the thread at any one moment, but these properties should never be used for synchronizing the activities of threads.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f349d-113">Una vez que se inicia un subproceso, no es necesario conservar una referencia al objeto <xref:System.Threading.Thread>.</span><span class="sxs-lookup"><span data-stu-id="f349d-113">Once a thread is started, it is not necessary to retain a reference to the <xref:System.Threading.Thread> object.</span></span> <span data-ttu-id="f349d-114">El subproceso continúa ejecutándose hasta que finaliza el procedimiento del subproceso.</span><span class="sxs-lookup"><span data-stu-id="f349d-114">The thread continues to execute until the thread procedure ends.</span></span>  
  
 <span data-ttu-id="f349d-115">En el ejemplo de código siguiente se crean dos subprocesos para llamar a métodos estáticos e instancias en otro objeto.</span><span class="sxs-lookup"><span data-stu-id="f349d-115">The following code example creates two new threads to call instance and static methods on another object.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads"></a><span data-ttu-id="f349d-116">Paso de datos a subprocesos</span><span class="sxs-lookup"><span data-stu-id="f349d-116">Passing data to threads</span></span>

 <span data-ttu-id="f349d-117">En .NET Framework 2.0, el delegado <xref:System.Threading.ParameterizedThreadStart> ofrece una forma sencilla de pasar un objeto que contiene datos a un subproceso al llamar a la sobrecarga del método <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f349d-117">In the .NET Framework version 2.0, the <xref:System.Threading.ParameterizedThreadStart> delegate provides an easy way to pass an object containing data to a thread when you call the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload.</span></span> <span data-ttu-id="f349d-118">Vea <xref:System.Threading.ParameterizedThreadStart> para obtener código muestra.</span><span class="sxs-lookup"><span data-stu-id="f349d-118">See <xref:System.Threading.ParameterizedThreadStart> for a code example.</span></span>  
  
 <span data-ttu-id="f349d-119">El uso del delegado <xref:System.Threading.ParameterizedThreadStart> no es una forma con seguridad de tipos de pasar datos, porque la sobrecarga del método <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> acepta cualquier objeto.</span><span class="sxs-lookup"><span data-stu-id="f349d-119">Using the <xref:System.Threading.ParameterizedThreadStart> delegate is not a type-safe way to pass data, because the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload accepts any object.</span></span> <span data-ttu-id="f349d-120">Una alternativa consiste en encapsular el procedimiento de subprocesos y los datos en una clase del asistente y utilizar el delegado <xref:System.Threading.ThreadStart> para ejecutar el procedimiento de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="f349d-120">An alternative is to encapsulate the thread procedure and the data in a helper class and use the <xref:System.Threading.ThreadStart> delegate to execute the thread procedure.</span></span> <span data-ttu-id="f349d-121">En el siguiente ejemplo se muestra esta técnica:</span><span class="sxs-lookup"><span data-stu-id="f349d-121">The following example demonstrates this technique:</span></span>

 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  

<span data-ttu-id="f349d-122">Ninguno de estos delegados, <xref:System.Threading.ThreadStart> ni <xref:System.Threading.ParameterizedThreadStart>, tiene un valor devuelto, porque no hay ningún lugar para devolver los datos de una llamada asincrónica.</span><span class="sxs-lookup"><span data-stu-id="f349d-122">Neither <xref:System.Threading.ThreadStart> nor <xref:System.Threading.ParameterizedThreadStart> delegate has a return value, because there is no place to return the data from an asynchronous call.</span></span> <span data-ttu-id="f349d-123">Para recuperar los resultados de un método de subproceso, puede utilizar un método de devolución de llamada, como se muestra en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="f349d-123">To retrieve the results of a thread method, you can use a callback method, as shown in the next section.</span></span>
  
## <a name="retrieving-data-from-threads-with-callback-methods"></a><span data-ttu-id="f349d-124">Recuperación de datos de subprocesos con métodos de devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="f349d-124">Retrieving data from threads with callback methods</span></span>

 <span data-ttu-id="f349d-125">En el ejemplo siguiente se muestra un método de devolución de llamada que recupera datos de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="f349d-125">The following example demonstrates a callback method that retrieves data from a thread.</span></span> <span data-ttu-id="f349d-126">El constructor de la clase que contiene los datos y el método del subproceso también acepta a un delegado que representa el método de devolución de llamada; antes de que finalice el método del subproceso, invoca al delegado de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f349d-126">The constructor for the class that contains the data and the thread method also accepts a delegate representing the callback method; before the thread method ends, it invokes the callback delegate.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="f349d-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="f349d-127">See also</span></span>

- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadStart>
- <xref:System.Threading.ParameterizedThreadStart>
- <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f349d-128">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="f349d-128">Threading</span></span>](index.md)
- [<span data-ttu-id="f349d-129">Usar subprocesos y subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="f349d-129">Using Threads and Threading</span></span>](using-threads-and-threading.md)
