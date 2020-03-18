---
title: Temporizadores
description: Obtenga información sobre los temporizadores de .NET que se pueden usar en un entorno multiproceso.
ms.date: 07/03/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
author: pkulikov
ms.openlocfilehash: d7d1fa13b02fe7425fa9b4cb81ba20297a23fe4b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73128950"
---
# <a name="timers"></a><span data-ttu-id="61f3a-103">Temporizadores</span><span class="sxs-lookup"><span data-stu-id="61f3a-103">Timers</span></span>

<span data-ttu-id="61f3a-104">.NET proporciona dos temporizadores que se pueden usar en un entorno multiproceso:</span><span class="sxs-lookup"><span data-stu-id="61f3a-104">.NET provides two timers to use in a multithreaded environment:</span></span>

- <span data-ttu-id="61f3a-105"><xref:System.Threading.Timer?displayProperty=nameWithType>, que ejecuta un único método de devolución de llamada en un subproceso <xref:System.Threading.ThreadPool> a intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="61f3a-105"><xref:System.Threading.Timer?displayProperty=nameWithType>, which executes a single callback method on a <xref:System.Threading.ThreadPool> thread at regular intervals.</span></span>
- <span data-ttu-id="61f3a-106"><xref:System.Timers.Timer?displayProperty=nameWithType>, que de forma predeterminada genera un evento en un subproceso <xref:System.Threading.ThreadPool> a intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="61f3a-106"><xref:System.Timers.Timer?displayProperty=nameWithType>, which by default raises an event on a <xref:System.Threading.ThreadPool> thread at regular intervals.</span></span>

> [!NOTE]
> <span data-ttu-id="61f3a-107">Algunas implementaciones de .NET pueden incluir temporizadores adicionales:</span><span class="sxs-lookup"><span data-stu-id="61f3a-107">Some .NET implementations may include additional timers:</span></span>
>
> - <span data-ttu-id="61f3a-108"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType>: un componente de Windows Forms que produce un evento a intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="61f3a-108"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType>: a Windows Forms component that fires an event at regular intervals.</span></span> <span data-ttu-id="61f3a-109">El componente no tiene interfaz de usuario y está diseñado para su uso en un entorno de un único subproceso.</span><span class="sxs-lookup"><span data-stu-id="61f3a-109">The component has no user interface and is designed for use in a single-threaded environment.</span></span>  
> - <span data-ttu-id="61f3a-110"><xref:System.Web.UI.Timer?displayProperty=nameWithType>: un componente de ASP.NET que realiza postbacks de página web asincrónicos o sincrónicos en un intervalo definido.</span><span class="sxs-lookup"><span data-stu-id="61f3a-110"><xref:System.Web.UI.Timer?displayProperty=nameWithType>: an ASP.NET component that performs asynchronous or synchronous web page postbacks at a regular interval.</span></span>
> - <span data-ttu-id="61f3a-111"><xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType>: un temporizador que se integra en la cola de <xref:System.Windows.Threading.Dispatcher> que se procesa en un intervalo de tiempo especificado y con una prioridad especificada.</span><span class="sxs-lookup"><span data-stu-id="61f3a-111"><xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType>: a timer that is integrated into the <xref:System.Windows.Threading.Dispatcher> queue which is processed at a specified interval of time and at a specified priority.</span></span>

## <a name="the-systemthreadingtimer-class"></a><span data-ttu-id="61f3a-112">La clase System.Threading.Timer</span><span class="sxs-lookup"><span data-stu-id="61f3a-112">The System.Threading.Timer class</span></span>

<span data-ttu-id="61f3a-113">La clase <xref:System.Threading.Timer?displayProperty=nameWithType> permite llamar de forma continua a un delegado en intervalos de tiempo especificados.</span><span class="sxs-lookup"><span data-stu-id="61f3a-113">The <xref:System.Threading.Timer?displayProperty=nameWithType> class enables you to continuously call a delegate at specified time intervals.</span></span> <span data-ttu-id="61f3a-114">Esta clase también se puede usar para programar una sola llamada a un delegado en un intervalo de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="61f3a-114">You also can use this class to schedule a single call to a delegate in a specified time interval.</span></span> <span data-ttu-id="61f3a-115">El delegado se ejecuta en un subproceso <xref:System.Threading.ThreadPool>.</span><span class="sxs-lookup"><span data-stu-id="61f3a-115">The delegate is executed on a <xref:System.Threading.ThreadPool> thread.</span></span>

<span data-ttu-id="61f3a-116">Cuando se crea un objeto <xref:System.Threading.Timer?displayProperty=nameWithType>, se especifica un delegado <xref:System.Threading.TimerCallback> que define el método de devolución de llamada, un objeto de estado opcional que se pasa a la devolución de llamada, la cantidad de tiempo de retraso antes de la primera invocación de la devolución de llamada y el intervalo de tiempo entre las invocaciones de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="61f3a-116">When you create a <xref:System.Threading.Timer?displayProperty=nameWithType> object, you specify a <xref:System.Threading.TimerCallback> delegate that defines the callback method, an optional state object that is passed to the callback, the amount of time to delay before the first invocation of the callback, and the time interval between callback invocations.</span></span> <span data-ttu-id="61f3a-117">Para cancelar un temporizador pendiente, llame a la función <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="61f3a-117">To cancel a pending timer, call the <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="61f3a-118">En el ejemplo siguiente se crea un temporizador que llama al delegado proporcionado por primera vez después de un segundo (1000 milisegundos) y, después, lo llama cada dos segundos.</span><span class="sxs-lookup"><span data-stu-id="61f3a-118">The following example creates a timer that calls the provided delegate for the first time after one second (1000 milliseconds) and then calls it every two seconds.</span></span> <span data-ttu-id="61f3a-119">El objeto de estado del ejemplo se usa para contar el número de veces que se llama al delegado.</span><span class="sxs-lookup"><span data-stu-id="61f3a-119">The state object in the example is used to count how many times the delegate is called.</span></span> <span data-ttu-id="61f3a-120">El temporizador se detiene cuando el delegado se ha llamado al menos 10 veces.</span><span class="sxs-lookup"><span data-stu-id="61f3a-120">The timer is stopped when the delegate has been called at least 10 times.</span></span>

[!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
[!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
[!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]

<span data-ttu-id="61f3a-121">Para obtener más información y ejemplos, vea <xref:System.Threading.Timer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="61f3a-121">For more information and examples, see <xref:System.Threading.Timer?displayProperty=nameWithType>.</span></span>

## <a name="the-systemtimerstimer-class"></a><span data-ttu-id="61f3a-122">La clase System.Timers.Timer</span><span class="sxs-lookup"><span data-stu-id="61f3a-122">The System.Timers.Timer class</span></span>

<span data-ttu-id="61f3a-123">Otro temporizador que se puede usar en un entorno multiproceso es <xref:System.Timers.Timer?displayProperty=nameWithType> que, de forma predeterminada, genera un evento en un subproceso <xref:System.Threading.ThreadPool>.</span><span class="sxs-lookup"><span data-stu-id="61f3a-123">Another timer that can be used in a multithreaded environment is <xref:System.Timers.Timer?displayProperty=nameWithType> that by default raises an event on a <xref:System.Threading.ThreadPool> thread.</span></span>

<span data-ttu-id="61f3a-124">Cuando se crea un objeto <xref:System.Timers.Timer?displayProperty=nameWithType>, se puede especificar el intervalo de tiempo en el que se va a generar un evento <xref:System.Timers.Timer.Elapsed>.</span><span class="sxs-lookup"><span data-stu-id="61f3a-124">When you create a <xref:System.Timers.Timer?displayProperty=nameWithType> object, you may specify the time interval in which to raise an <xref:System.Timers.Timer.Elapsed> event.</span></span> <span data-ttu-id="61f3a-125">Use la propiedad <xref:System.Timers.Timer.Enabled%2A> para indicar si un temporizador debe generar un evento <xref:System.Timers.Timer.Elapsed>.</span><span class="sxs-lookup"><span data-stu-id="61f3a-125">Use the <xref:System.Timers.Timer.Enabled%2A> property to indicate if a timer should raise an <xref:System.Timers.Timer.Elapsed> event.</span></span> <span data-ttu-id="61f3a-126">Si necesita que un evento <xref:System.Timers.Timer.Elapsed> se genere solo una vez cuando haya transcurrido el intervalo especificado, establezca <xref:System.Timers.Timer.AutoReset%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="61f3a-126">If you need an <xref:System.Timers.Timer.Elapsed> event to be raised only once after the specified interval has elapsed, set the <xref:System.Timers.Timer.AutoReset%2A> to `false`.</span></span> <span data-ttu-id="61f3a-127">El valor predeterminado de la propiedad <xref:System.Timers.Timer.AutoReset%2A> es `true`, lo que significa que un evento <xref:System.Timers.Timer.Elapsed> se genera periódicamente durante el intervalo definido por la propiedad <xref:System.Timers.Timer.Interval%2A>.</span><span class="sxs-lookup"><span data-stu-id="61f3a-127">The default value of the <xref:System.Timers.Timer.AutoReset%2A> property is `true`, which means that an <xref:System.Timers.Timer.Elapsed> event is raised regularly at the interval defined by the <xref:System.Timers.Timer.Interval%2A> property.</span></span>

<span data-ttu-id="61f3a-128">Para obtener más información y ejemplos, vea <xref:System.Timers.Timer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="61f3a-128">For more information and examples, see <xref:System.Timers.Timer?displayProperty=nameWithType>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="61f3a-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="61f3a-129">See also</span></span>

- <xref:System.Threading.Timer?displayProperty=nameWithType>
- <xref:System.Timers.Timer?displayProperty=nameWithType>
- [<span data-ttu-id="61f3a-130">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="61f3a-130">Threading Objects and Features</span></span>](threading-objects-and-features.md)
