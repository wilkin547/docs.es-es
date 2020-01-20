---
title: Información general de Async
description: Obtenga información sobre cómo la programación de Async es una técnica clave que ayuda a controlar las operaciones simultáneas y de E/S de bloqueo en varios núcleos.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: 1e38e9d9-8284-46ee-a15f-199adc4f26f4
ms.openlocfilehash: 1570909b7b416eff81dd90a936ff5ed10aad94f1
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346085"
---
# <a name="async-overview"></a><span data-ttu-id="6925a-103">Información general de Async</span><span class="sxs-lookup"><span data-stu-id="6925a-103">Async Overview</span></span>

<span data-ttu-id="6925a-104">No hace tanto tiempo, las aplicaciones funcionaban más rápido simplemente al comprar un PC o servidor nuevo y después se detuvo esa tendencia.</span><span class="sxs-lookup"><span data-stu-id="6925a-104">Not so long ago, apps got faster simply by buying a newer PC or server and then that trend stopped.</span></span> <span data-ttu-id="6925a-105">De hecho, se ha invertido.</span><span class="sxs-lookup"><span data-stu-id="6925a-105">In fact, it reversed.</span></span> <span data-ttu-id="6925a-106">Aparecieron teléfonos móviles con chips ARM de núcleo único de 1 GHz y cargas de trabajo de servidor que pasaron a máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="6925a-106">Mobile phones appeared with 1ghz single core ARM chips and server workloads transitioned to VMs.</span></span> <span data-ttu-id="6925a-107">Los usuarios seguían queriendo una interfaz de usuario dinámica y los propietarios de empresas querían servidores que se ajustaran a su negocio.</span><span class="sxs-lookup"><span data-stu-id="6925a-107">Users still want responsive UI and business owners want servers that scale with their business.</span></span> <span data-ttu-id="6925a-108">La transición al móvil y a la nube y una población conectada a Internet de más de 3 mil millones de usuarios ha generado un nuevo conjunto de patrones de software.</span><span class="sxs-lookup"><span data-stu-id="6925a-108">The transition to mobile and cloud and an internet-connected population of >3B users has resulted in a new set of software patterns.</span></span> 

- <span data-ttu-id="6925a-109">Se espera que las aplicaciones cliente estén siempre activadas y conectadas, y que respondan adecuadamente a la interacción del usuario (p. ej., función táctil) con altas calificaciones en la tienda de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6925a-109">Client applications are expected to be always-on, always-connected and constantly responsive to user interaction (for example, touch) with high app store ratings!</span></span>
- <span data-ttu-id="6925a-110">Se espera que los servicios controlen los picos de tráfico al escalar y reducir verticalmente con facilidad.</span><span class="sxs-lookup"><span data-stu-id="6925a-110">Services are expected to handle spikes in traffic by gracefully scaling up and down.</span></span> 

<span data-ttu-id="6925a-111">La programación de Async es una técnica clave que facilita controlar las operaciones simultáneas y de E/S de bloqueo en varios núcleos.</span><span class="sxs-lookup"><span data-stu-id="6925a-111">Async programming is a key technique that makes it straightforward to handle blocking I/O and concurrent operations on multiple cores.</span></span> <span data-ttu-id="6925a-112">.NET proporciona la funcionalidad de que servicios y aplicaciones sean dinámicos y elásticos con modelos de programación asincrónicos de nivel de lenguaje y fáciles de usar en C#, Visual Basic y F#.</span><span class="sxs-lookup"><span data-stu-id="6925a-112">.NET provides the capability for apps and services to be responsive and elastic with easy-to-use, language-level asynchronous programming models in C#, Visual Basic, and F#.</span></span>

## <a name="why-write-async-code"></a><span data-ttu-id="6925a-113">¿Por qué escribir código asincrónico?</span><span class="sxs-lookup"><span data-stu-id="6925a-113">Why Write Async Code?</span></span>

<span data-ttu-id="6925a-114">Las aplicaciones modernas usan de forma intensiva la E/S de archivos y redes.</span><span class="sxs-lookup"><span data-stu-id="6925a-114">Modern apps make extensive use of file and networking I/O.</span></span> <span data-ttu-id="6925a-115">Tradicionalmente, las API de E/S bloquean de manera predeterminada, lo que da lugar a experiencias de usuario y uso del hardware pobres a menos que quiera aprender y usar patrones exigentes.</span><span class="sxs-lookup"><span data-stu-id="6925a-115">I/O APIs traditionally block by default, resulting in poor user experiences and hardware utilization unless you want to learn and use challenging patterns.</span></span> <span data-ttu-id="6925a-116">Las API asincrónicas basadas en tareas y el modelo de programación asincrónico de nivel de lenguaje invierten este modelo, de modo que establecen la ejecución asincrónica como la predeterminada con algunos conceptos nuevos que aprender.</span><span class="sxs-lookup"><span data-stu-id="6925a-116">Task-based async APIs and the language-level asynchronous programming model invert this model, making async execution the default with few new concepts to learn.</span></span>

<span data-ttu-id="6925a-117">El código asincrónico tiene las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="6925a-117">Async code has the following characteristics:</span></span>

- <span data-ttu-id="6925a-118">Controla más solicitudes del servidor al producir subprocesos que controlan más solicitudes mientras esperan a que devuelvan las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="6925a-118">Handles more server requests by yielding threads to handle more requests while waiting for I/O requests to return.</span></span>
- <span data-ttu-id="6925a-119">Permite que las interfaces de usuario sean más dinámicas al ceder subprocesos a la interacción de la interfaz de usuario mientras esperan las solicitudes de E/S y al pasar trabajo de ejecución prolongada a otros núcleos de CPU.</span><span class="sxs-lookup"><span data-stu-id="6925a-119">Enables UIs to be more responsive by yielding threads to UI interaction while waiting for I/O requests and by transitioning long-running work to other CPU cores.</span></span>
- <span data-ttu-id="6925a-120">Muchas de las API de .NET más recientes son asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="6925a-120">Many of the newer .NET APIs are asynchronous.</span></span>
- <span data-ttu-id="6925a-121">Es fácil escribir código asincrónico en .NET.</span><span class="sxs-lookup"><span data-stu-id="6925a-121">It's easy to write async code in .NET!</span></span>

## <a name="whats-next"></a><span data-ttu-id="6925a-122">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="6925a-122">What's next?</span></span>

<span data-ttu-id="6925a-123">Para obtener más información, vea el tema [Async en profundidad](async-in-depth.md).</span><span class="sxs-lookup"><span data-stu-id="6925a-123">For more information, see the [Async in depth](async-in-depth.md) topic.</span></span>

<span data-ttu-id="6925a-124">En el tema [Modelos para la programación asincrónica](asynchronous-programming-patterns/index.md), se proporciona una introducción de los tres modelos de programación asincrónica que se admiten en .NET:</span><span class="sxs-lookup"><span data-stu-id="6925a-124">The [Asynchronous Programming Patterns](asynchronous-programming-patterns/index.md) topic provides an overview of the three asynchronous programming patterns supported in .NET:</span></span>  
  
- <span data-ttu-id="6925a-125">[Asynchronous Programming Model (APM)](asynchronous-programming-patterns/asynchronous-programming-model-apm.md) [Modelo de programación asincrónica (APM)] (heredado)</span><span class="sxs-lookup"><span data-stu-id="6925a-125">[Asynchronous Programming Model (APM)](asynchronous-programming-patterns/asynchronous-programming-model-apm.md) (legacy)</span></span>  
  
- <span data-ttu-id="6925a-126">[Event-based Asynchronous Pattern (EAP)](asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) [Modelo asincrónico basado en eventos (EAP)] (heredado)</span><span class="sxs-lookup"><span data-stu-id="6925a-126">[Event-based Asynchronous Pattern (EAP)](asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (legacy)</span></span>  
  
- <span data-ttu-id="6925a-127">[Task-based Asynchronous Pattern (TAP)](asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) [Modelo asincrónico basado en tareas (TAP)] (recomendado para nuevos desarrollos)</span><span class="sxs-lookup"><span data-stu-id="6925a-127">[Task-based Asynchronous Pattern (TAP)](asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (recommended for new development)</span></span>  

<span data-ttu-id="6925a-128">Para obtener más información sobre el modelo de programación basado en tareas recomendado, consulte el tema [Programación asincrónica basada en tareas](parallel-programming/task-based-asynchronous-programming.md).</span><span class="sxs-lookup"><span data-stu-id="6925a-128">For more information about recommended task-based programming model, see the [Task-based asynchronous programming](parallel-programming/task-based-asynchronous-programming.md) topic.</span></span>
