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
ms.translationtype: HT
ms.sourcegitcommit: ef6d1bf9a7153f7adf635d13b4dcfb7647ed2e33
ms.openlocfilehash: bf0cc4ed21c92a57f3f5b2cfa27ac1f054e15172
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---

# <a name="async-overview"></a><span data-ttu-id="e91de-104">Información general de Async</span><span class="sxs-lookup"><span data-stu-id="e91de-104">Async Overview</span></span>

<span data-ttu-id="e91de-105">No hace tanto tiempo, las aplicaciones funcionaban más rápido simplemente al comprar un PC o servidor nuevo y después se detuvo esa tendencia.</span><span class="sxs-lookup"><span data-stu-id="e91de-105">Not so long ago, apps got faster simply by buying a newer PC or server and then that trend stopped.</span></span> <span data-ttu-id="e91de-106">De hecho, se ha invertido.</span><span class="sxs-lookup"><span data-stu-id="e91de-106">In fact, it reversed.</span></span> <span data-ttu-id="e91de-107">Aparecieron teléfonos móviles con chips ARM de núcleo único de 1 GHz y cargas de trabajo de servidor que pasaron a máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="e91de-107">Mobile phones appeared with 1ghz single core ARM chips and server workloads transitioned to VMs.</span></span> <span data-ttu-id="e91de-108">Los usuarios seguían queriendo una interfaz de usuario dinámica y los propietarios de empresas querían servidores que se ajustaran a su negocio.</span><span class="sxs-lookup"><span data-stu-id="e91de-108">Users still want responsive UI and business owners want servers that scale with their business.</span></span> <span data-ttu-id="e91de-109">La transición al móvil y a la nube y una población conectada a Internet de más de 3 mil millones de usuarios ha generado un nuevo conjunto de patrones de software.</span><span class="sxs-lookup"><span data-stu-id="e91de-109">The transition to mobile and cloud and an internet-connected population of >3B users has resulted in a new set of software patterns.</span></span> 

* <span data-ttu-id="e91de-110">Se espera que las aplicaciones cliente estén siempre activadas y conectadas, y que respondan adecuadamente a la interacción del usuario (p. ej., función táctil) con altas calificaciones en la tienda de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e91de-110">Client applications are expected to be always-on, always-connected and constantly responsive to user interaction (for example, touch) with high app store ratings!</span></span>
* <span data-ttu-id="e91de-111">Se espera que los servicios controlen los picos de tráfico al escalar y reducir verticalmente con facilidad.</span><span class="sxs-lookup"><span data-stu-id="e91de-111">Services are expected to handle spikes in traffic by gracefully scaling up and down.</span></span> 

<span data-ttu-id="e91de-112">La programación de Async es una técnica clave que facilita controlar las operaciones simultáneas y de E/S de bloqueo en varios núcleos.</span><span class="sxs-lookup"><span data-stu-id="e91de-112">Async programming is a key technique that makes it straightforward to handle blocking I/O and concurrent operations on multiple cores.</span></span> <span data-ttu-id="e91de-113">.NET proporciona a servicios y aplicaciones la capacidad de ser dinámicos y elásticos con modelos de programación asincrónicos de nivel de lenguaje y fáciles de usar en C#, VB y F#.</span><span class="sxs-lookup"><span data-stu-id="e91de-113">.NET provides the capability for apps and services to be responsive and elastic with easy-to-use, language-level asynchronous programming models in C#, VB, and F#.</span></span>

## <a name="why-write-async-code"></a><span data-ttu-id="e91de-114">¿Por qué escribir código asincrónico?</span><span class="sxs-lookup"><span data-stu-id="e91de-114">Why Write Async Code?</span></span>

<span data-ttu-id="e91de-115">Las aplicaciones modernas usan de forma intensiva la E/S de archivos y redes.</span><span class="sxs-lookup"><span data-stu-id="e91de-115">Modern apps make extensive use of file and networking I/O.</span></span> <span data-ttu-id="e91de-116">Tradicionalmente, las API de E/S bloquean de manera predeterminada, lo que da lugar a experiencias de usuario y uso del hardware pobres a menos que quiera aprender y usar patrones exigentes.</span><span class="sxs-lookup"><span data-stu-id="e91de-116">I/O APIs traditionally block by default, resulting in poor user experiences and hardware utilization unless you want to learn and use challenging patterns.</span></span> <span data-ttu-id="e91de-117">Las API asincrónicas basadas en tareas y el modelo de programación asincrónico de nivel de lenguaje invierten este modelo, de modo que establecen la ejecución asincrónica como la predeterminada con algunos conceptos nuevos que aprender.</span><span class="sxs-lookup"><span data-stu-id="e91de-117">Task-based async APIs and the language-level asynchronous programming model invert this model, making async execution the default with few new concepts to learn.</span></span>

<span data-ttu-id="e91de-118">El código asincrónico tiene las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="e91de-118">Async code has the following characteristics:</span></span>

* <span data-ttu-id="e91de-119">Controla más solicitudes del servidor al producir subprocesos que controlan más solicitudes mientras esperan a que devuelvan las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="e91de-119">Handles more server requests by yielding threads to handle more requests while waiting for I/O requests to return.</span></span>
* <span data-ttu-id="e91de-120">Permite que las interfaces de usuario sean más dinámicas al ceder subprocesos a la interacción de la interfaz de usuario mientras esperan las solicitudes de E/S y al pasar trabajo de ejecución prolongada a otros núcleos de CPU.</span><span class="sxs-lookup"><span data-stu-id="e91de-120">Enables UIs to be more responsive by yielding threads to UI interaction while waiting for I/O requests and by transitioning long-running work to other CPU cores.</span></span>
* <span data-ttu-id="e91de-121">Muchas de las API de .NET más recientes son asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="e91de-121">Many of the newer .NET APIs are asynchronous.</span></span>
* <span data-ttu-id="e91de-122">Es fácil escribir código asincrónico en .NET.</span><span class="sxs-lookup"><span data-stu-id="e91de-122">It's easy to write async code in .NET!</span></span>

## <a name="whats-next"></a><span data-ttu-id="e91de-123">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="e91de-123">What's next?</span></span>

<span data-ttu-id="e91de-124">Para profundizar en los conceptos y la programación de Async, consulte [Async en profundidad](async-in-depth.md) y [Task-based asynchronous programming](~/docs/standard/parallel-programming/task-based-asynchronous-programming.md) (Programación asincrónica basada en tareas).</span><span class="sxs-lookup"><span data-stu-id="e91de-124">For a deep dive into async concepts and programming, see [Async in depth](async-in-depth.md) and [Task-based asynchronous programming](~/docs/standard/parallel-programming/task-based-asynchronous-programming.md).</span></span>

