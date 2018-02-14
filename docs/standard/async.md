---
title: "Información general de Async"
description: "Obtenga información sobre cómo la programación de Async es una técnica clave que ayuda a controlar las operaciones simultáneas y de E/S de bloqueo en varios núcleos."
keywords: .NET, .NET Core
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 1e38e9d9-8284-46ee-a15f-199adc4f26f4
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f2dddc21dfb124fe97c397a156743981a67e4037
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="async-overview"></a><span data-ttu-id="fe74a-104">Información general de Async</span><span class="sxs-lookup"><span data-stu-id="fe74a-104">Async Overview</span></span>

<span data-ttu-id="fe74a-105">No hace tanto tiempo, las aplicaciones funcionaban más rápido simplemente al comprar un PC o servidor nuevo y después se detuvo esa tendencia.</span><span class="sxs-lookup"><span data-stu-id="fe74a-105">Not so long ago, apps got faster simply by buying a newer PC or server and then that trend stopped.</span></span> <span data-ttu-id="fe74a-106">De hecho, se ha invertido.</span><span class="sxs-lookup"><span data-stu-id="fe74a-106">In fact, it reversed.</span></span> <span data-ttu-id="fe74a-107">Aparecieron teléfonos móviles con chips ARM de núcleo único de 1 GHz y cargas de trabajo de servidor que pasaron a máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="fe74a-107">Mobile phones appeared with 1ghz single core ARM chips and server workloads transitioned to VMs.</span></span> <span data-ttu-id="fe74a-108">Los usuarios seguían queriendo una interfaz de usuario dinámica y los propietarios de empresas querían servidores que se ajustaran a su negocio.</span><span class="sxs-lookup"><span data-stu-id="fe74a-108">Users still want responsive UI and business owners want servers that scale with their business.</span></span> <span data-ttu-id="fe74a-109">La transición al móvil y a la nube y una población conectada a Internet de más de 3 mil millones de usuarios ha generado un nuevo conjunto de patrones de software.</span><span class="sxs-lookup"><span data-stu-id="fe74a-109">The transition to mobile and cloud and an internet-connected population of >3B users has resulted in a new set of software patterns.</span></span> 

* <span data-ttu-id="fe74a-110">Se espera que las aplicaciones cliente estén siempre activadas y conectadas, y que respondan adecuadamente a la interacción del usuario (p. ej., función táctil) con altas calificaciones en la tienda de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="fe74a-110">Client applications are expected to be always-on, always-connected and constantly responsive to user interaction (for example, touch) with high app store ratings!</span></span>
* <span data-ttu-id="fe74a-111">Se espera que los servicios controlen los picos de tráfico al escalar y reducir verticalmente con facilidad.</span><span class="sxs-lookup"><span data-stu-id="fe74a-111">Services are expected to handle spikes in traffic by gracefully scaling up and down.</span></span> 

<span data-ttu-id="fe74a-112">La programación de Async es una técnica clave que facilita controlar las operaciones simultáneas y de E/S de bloqueo en varios núcleos.</span><span class="sxs-lookup"><span data-stu-id="fe74a-112">Async programming is a key technique that makes it straightforward to handle blocking I/O and concurrent operations on multiple cores.</span></span> <span data-ttu-id="fe74a-113">.NET proporciona a servicios y aplicaciones la capacidad de ser dinámicos y elásticos con modelos de programación asincrónicos de nivel de lenguaje y fáciles de usar en C#, VB y F#.</span><span class="sxs-lookup"><span data-stu-id="fe74a-113">.NET provides the capability for apps and services to be responsive and elastic with easy-to-use, language-level asynchronous programming models in C#, VB, and F#.</span></span>

## <a name="why-write-async-code"></a><span data-ttu-id="fe74a-114">¿Por qué escribir código asincrónico?</span><span class="sxs-lookup"><span data-stu-id="fe74a-114">Why Write Async Code?</span></span>

<span data-ttu-id="fe74a-115">Las aplicaciones modernas usan de forma intensiva la E/S de archivos y redes.</span><span class="sxs-lookup"><span data-stu-id="fe74a-115">Modern apps make extensive use of file and networking I/O.</span></span> <span data-ttu-id="fe74a-116">Tradicionalmente, las API de E/S bloquean de manera predeterminada, lo que da lugar a experiencias de usuario y uso del hardware pobres a menos que quiera aprender y usar patrones exigentes.</span><span class="sxs-lookup"><span data-stu-id="fe74a-116">I/O APIs traditionally block by default, resulting in poor user experiences and hardware utilization unless you want to learn and use challenging patterns.</span></span> <span data-ttu-id="fe74a-117">Las API asincrónicas basadas en tareas y el modelo de programación asincrónico de nivel de lenguaje invierten este modelo, de modo que establecen la ejecución asincrónica como la predeterminada con algunos conceptos nuevos que aprender.</span><span class="sxs-lookup"><span data-stu-id="fe74a-117">Task-based async APIs and the language-level asynchronous programming model invert this model, making async execution the default with few new concepts to learn.</span></span>

<span data-ttu-id="fe74a-118">El código asincrónico tiene las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="fe74a-118">Async code has the following characteristics:</span></span>

* <span data-ttu-id="fe74a-119">Controla más solicitudes del servidor al producir subprocesos que controlan más solicitudes mientras esperan a que devuelvan las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="fe74a-119">Handles more server requests by yielding threads to handle more requests while waiting for I/O requests to return.</span></span>
* <span data-ttu-id="fe74a-120">Permite que las interfaces de usuario sean más dinámicas al ceder subprocesos a la interacción de la interfaz de usuario mientras esperan las solicitudes de E/S y al pasar trabajo de ejecución prolongada a otros núcleos de CPU.</span><span class="sxs-lookup"><span data-stu-id="fe74a-120">Enables UIs to be more responsive by yielding threads to UI interaction while waiting for I/O requests and by transitioning long-running work to other CPU cores.</span></span>
* <span data-ttu-id="fe74a-121">Muchas de las API de .NET más recientes son asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="fe74a-121">Many of the newer .NET APIs are asynchronous.</span></span>
* <span data-ttu-id="fe74a-122">Es fácil escribir código asincrónico en .NET.</span><span class="sxs-lookup"><span data-stu-id="fe74a-122">It's easy to write async code in .NET!</span></span>

## <a name="whats-next"></a><span data-ttu-id="fe74a-123">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="fe74a-123">What's next?</span></span>

<span data-ttu-id="fe74a-124">Para profundizar en los conceptos y la programación de Async, consulte [Async en profundidad](async-in-depth.md) y [Task-based asynchronous programming](~/docs/standard/parallel-programming/task-based-asynchronous-programming.md) (Programación asincrónica basada en tareas).</span><span class="sxs-lookup"><span data-stu-id="fe74a-124">For a deep dive into async concepts and programming, see [Async in depth](async-in-depth.md) and [Task-based asynchronous programming](~/docs/standard/parallel-programming/task-based-asynchronous-programming.md).</span></span>
