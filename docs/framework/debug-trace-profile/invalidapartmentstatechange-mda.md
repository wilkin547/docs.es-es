---
title: MDA de invalidApartmentStateChange
description: Obtenga información sobre el Asistente para la depuración administrada (MDA) de invalidApartmentStateChange en .NET, que se activa si hay problemas con el estado de contenedor COM.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid apartment state
- managed debugging assistants (MDAs), invalid apartment state
- InvalidApartmentStateChange MDA
- invalid apartment state changes
- threading [.NET Framework], apartment states
- apartment states
- threading [.NET Framework], managed debugging assistants
- COM apartment states
ms.assetid: e56fb9df-5286-4be7-b313-540c4d876cd7
ms.openlocfilehash: c6f7b6a5e450d4167946d22b2ada268ea2b0135f
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051832"
---
# <a name="invalidapartmentstatechange-mda"></a><span data-ttu-id="7f1aa-103">MDA de invalidApartmentStateChange</span><span class="sxs-lookup"><span data-stu-id="7f1aa-103">invalidApartmentStateChange MDA</span></span>
<span data-ttu-id="7f1aa-104">El Asistente para la depuración administrada (MDS) `invalidApartmentStateChange` se activa por cualquiera de estos dos problemas:</span><span class="sxs-lookup"><span data-stu-id="7f1aa-104">The `invalidApartmentStateChange` managed debugging assistant (MDS) is activated by either of two problems:</span></span>  
  
- <span data-ttu-id="7f1aa-105">Se realiza un intento de cambiar el estado de contenedor COM de un subproceso que ya se ha inicializado por COM a un estado de contenedor diferente.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-105">An attempt is made to change the COM apartment state of a thread that has already been initialized by COM to a different apartment state.</span></span>  
  
- <span data-ttu-id="7f1aa-106">El estado de contenedor COM de un subproceso cambia de forma inesperada.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-106">The COM apartment state of a thread changes unexpectedly.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="7f1aa-107">Síntomas</span><span class="sxs-lookup"><span data-stu-id="7f1aa-107">Symptoms</span></span>  
  
- <span data-ttu-id="7f1aa-108">El estado de contenedor COM de un subproceso no es el que se solicitó.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-108">A thread's COM apartment state is not what was requested.</span></span> <span data-ttu-id="7f1aa-109">Esto puede provocar que se usen servidores proxy para los componentes COM que tienen un modelo de subprocesos diferente del actual.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-109">This may cause proxies to be used for COM components that have a threading model different from the current one.</span></span> <span data-ttu-id="7f1aa-110">A su vez, esto puede hacer que se inicie una excepción <xref:System.InvalidCastException> al llamar al objeto COM a través de interfaces que no están configuradas para la serialización entre contenedores.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-110">This in turn may cause an <xref:System.InvalidCastException> to be thrown when calling the COM object through interfaces that are not set up for cross-apartment marshaling.</span></span>  
  
- <span data-ttu-id="7f1aa-111">El estado de contenedor COM del subproceso es diferente de lo esperado.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-111">The COM apartment state of the thread is different than expected.</span></span> <span data-ttu-id="7f1aa-112">Esto puede causar una excepción <xref:System.Runtime.InteropServices.COMException> con un valor HRESULT de RPC_E_WRONG_THREAD, así como una excepción <xref:System.InvalidCastException> cuando se realizan llamadas en un [contenedor RCW](../../standard/native-interop/runtime-callable-wrapper.md).</span><span class="sxs-lookup"><span data-stu-id="7f1aa-112">This can cause a <xref:System.Runtime.InteropServices.COMException> with an HRESULT of RPC_E_WRONG_THREAD as well as a <xref:System.InvalidCastException> when making calls on a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW).</span></span> <span data-ttu-id="7f1aa-113">Esto puede hacer que varios subprocesos tengan acceso al mismo tiempo a algunos componentes COM de un único subproceso, lo que puede provocar daños o pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-113">This can also cause some single-threaded COM components to be accessed by multiple threads at the same time, which can lead to corruption or data loss.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="7f1aa-114">Causa</span><span class="sxs-lookup"><span data-stu-id="7f1aa-114">Cause</span></span>  
  
- <span data-ttu-id="7f1aa-115">El subproceso se inicializó previamente a un estado de contenedor COM diferente.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-115">The thread was previously initialized to a different COM apartment state.</span></span> <span data-ttu-id="7f1aa-116">Tenga en cuenta que el estado de contenedor de un subproceso se puede establecer de forma explícita o implícita.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-116">Note that the apartment state of a thread can be set either explicitly or implicitly.</span></span> <span data-ttu-id="7f1aa-117">Las operaciones explícitas incluyen la propiedad <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> y los métodos <xref:System.Threading.Thread.SetApartmentState%2A> y <xref:System.Threading.Thread.TrySetApartmentState%2A>.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-117">The explicit operations include the <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> property and the <xref:System.Threading.Thread.SetApartmentState%2A> and <xref:System.Threading.Thread.TrySetApartmentState%2A> methods.</span></span> <span data-ttu-id="7f1aa-118">Un subproceso creado mediante el método <xref:System.Threading.Thread.Start%2A> se establece implícitamente en <xref:System.Threading.ApartmentState.MTA> a menos que se llame a <xref:System.Threading.Thread.SetApartmentState%2A> antes de iniciar el subproceso.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-118">A thread created using the <xref:System.Threading.Thread.Start%2A> method is implicitly set to <xref:System.Threading.ApartmentState.MTA> unless <xref:System.Threading.Thread.SetApartmentState%2A> is called before the thread is started.</span></span> <span data-ttu-id="7f1aa-119">El subproceso principal de la aplicación también se inicializa implícitamente en <xref:System.Threading.ApartmentState.MTA> a menos que se especifique el atributo <xref:System.STAThreadAttribute> en el método principal.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-119">The main thread of the application is also implicitly initialized to <xref:System.Threading.ApartmentState.MTA> unless the <xref:System.STAThreadAttribute> attribute is specified on the main method.</span></span>  
  
- <span data-ttu-id="7f1aa-120">El método `CoUninitialize` (o el método `CoInitializeEx`) con un modelo de simultaneidad diferente se llama en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-120">The `CoUninitialize` method (or the `CoInitializeEx` method) with a different concurrency model is called on the thread.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="7f1aa-121">Resolución</span><span class="sxs-lookup"><span data-stu-id="7f1aa-121">Resolution</span></span>  
 <span data-ttu-id="7f1aa-122">Establecer el estado de contenedor del subproceso antes de que empiece a ejecutarse, o aplicar el atributo <xref:System.STAThreadAttribute> o <xref:System.MTAThreadAttribute> al método principal de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-122">Set the apartment state of the thread before it begins executing, or apply either the <xref:System.STAThreadAttribute> attribute or the <xref:System.MTAThreadAttribute> attribute to the main method of the application.</span></span>  
  
 <span data-ttu-id="7f1aa-123">Para la segunda causa, idealmente el código que llama al método `CoUninitialize` debe modificarse para retrasar la llamada hasta que el subproceso esté a punto de terminar y no haya ningún RCW, y sus componentes COM subyacentes sigan en uso en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-123">For the second cause, ideally, the code that calls the `CoUninitialize` method should be modified to delay the call until the thread is about to terminate and there are no RCWs and their underlying COM components still in use by the thread.</span></span> <span data-ttu-id="7f1aa-124">Pero si no es posible modificar el código que llama al método `CoUninitialize`, entonces no deben usarse contenedores RCW desde los subprocesos sin inicializar de esta manera.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-124">However, if it is not possible to modify the code that calls the `CoUninitialize` method, then no RCWs should be used from threads that are uninitialized in this way.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="7f1aa-125">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="7f1aa-125">Effect on the Runtime</span></span>  
 <span data-ttu-id="7f1aa-126">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-126">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="7f1aa-127">Output</span><span class="sxs-lookup"><span data-stu-id="7f1aa-127">Output</span></span>  
 <span data-ttu-id="7f1aa-128">El estado de contenedor COM del subproceso actual y el estado que el código intentaba aplicar.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-128">The COM apartment state of the current thread, and the state that the code was attempting to apply.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="7f1aa-129">Configuración</span><span class="sxs-lookup"><span data-stu-id="7f1aa-129">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidApartmentStateChange />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="7f1aa-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f1aa-130">Example</span></span>  
 <span data-ttu-id="7f1aa-131">En el ejemplo de código siguiente se muestra una situación que puede activar este MDA.</span><span class="sxs-lookup"><span data-stu-id="7f1aa-131">The following code example demonstrates a situation that can activate this MDA.</span></span>  
  
```csharp
using System.Threading;  
namespace ApartmentStateMDA  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Thread.CurrentThread.SetApartmentState(ApartmentState.STA);  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f1aa-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f1aa-132">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="7f1aa-133">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="7f1aa-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="7f1aa-134">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="7f1aa-134">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
