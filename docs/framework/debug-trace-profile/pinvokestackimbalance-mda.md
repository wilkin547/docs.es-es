---
title: MDA de pInvokeStackImbalance
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b33a3edc5780ecf07e7809ca327a304d748110f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="pinvokestackimbalance-mda"></a><span data-ttu-id="2e602-102">MDA de pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="2e602-102">pInvokeStackImbalance MDA</span></span>
<span data-ttu-id="2e602-103">El Asistente para la depuración administrada (MDA) `pInvokeStackImbalance` se activa cuando CLR detecta que la profundidad de la pila después de la llamada de invocación de plataforma no coincide con la profundidad de pila esperada, según la convención de llamada especificada en el atributo <xref:System.Runtime.InteropServices.DllImportAttribute> y la declaración de los parámetros en la firma administrada.</span><span class="sxs-lookup"><span data-stu-id="2e602-103">The `pInvokeStackImbalance` managed debugging assistant (MDA) is activated when the CLR detects that the stack depth after a platform invoke call does not match the expected stack depth, given the calling convention specified in the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute as well as the declaration of the parameters in the managed signature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e602-104">El MDA `pInvokeStackImbalance` solo se implementa para plataformas de x86 de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="2e602-104">The `pInvokeStackImbalance` MDA is implemented only for 32-bit x86 platforms.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e602-105">En .NET Framework versión 3.5, el MDA `pInvokeStackImbalance` está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2e602-105">In the .NET Framework version 3.5, the `pInvokeStackImbalance` MDA is disabled by default.</span></span> <span data-ttu-id="2e602-106">Cuando se usa la versión 3.5 de .NET Framework con Visual Studio 2005, el MDA `pInvokeStackImbalance` aparecerá en la lista **Asistentes para la depuración administrada** en el cuadro de diálogo **Excepciones** (que se muestra al hacer clic en **Excepciones** en el menú **Depurar**).</span><span class="sxs-lookup"><span data-stu-id="2e602-106">When you use the .NET Framework version 3.5 with Visual Studio 2005, the `pInvokeStackImbalance` MDA will appear in the **Managed Debugging Assistants** list in the **Exceptions** dialog box (which is displayed when you click **Exceptions** on the **Debug** menu).</span></span> <span data-ttu-id="2e602-107">Pero activar o desactivar la casilla **Thrown** para `pInvokeStackImbalance` no habilita ni deshabilita el MDA; solo controla si Visual Studio inicia una excepción cuando se activa el MDA.</span><span class="sxs-lookup"><span data-stu-id="2e602-107">However, selecting or clearing the **Thrown** check box for `pInvokeStackImbalance` does not enable or disable the MDA; it only controls whether Visual Studio throws an exception when the MDA is activated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="2e602-108">Síntomas</span><span class="sxs-lookup"><span data-stu-id="2e602-108">Symptoms</span></span>  
 <span data-ttu-id="2e602-109">Una aplicación se encuentra con una infracción de acceso o daños en la memoria cuando se realiza una llamada de invocación de plataforma o después de realizar una.</span><span class="sxs-lookup"><span data-stu-id="2e602-109">An application encounters an access violation or memory corruption when making or following a platform invoke call.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="2e602-110">Motivo</span><span class="sxs-lookup"><span data-stu-id="2e602-110">Cause</span></span>  
 <span data-ttu-id="2e602-111">La firma administrada de la llamada de invocación de plataforma podría no coincidir con la firma no administrada del método al que se llama.</span><span class="sxs-lookup"><span data-stu-id="2e602-111">The managed signature of the platform invoke call might not match the unmanaged signature of the method being called.</span></span>  <span data-ttu-id="2e602-112">Esta falta de coincidencia puede deberse a que la firma administrada no declara el número correcto de parámetros o no especifica el tamaño adecuado para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="2e602-112">This mismatch can be caused by the managed signature not declaring the correct number of parameters or not specifying the appropriate size for the parameters.</span></span>  <span data-ttu-id="2e602-113">El MDA también puede activarse porque la convención de llamada, posiblemente especificada por el atributo <xref:System.Runtime.InteropServices.DllImportAttribute>, no coincide con la convención de llamada no administrada.</span><span class="sxs-lookup"><span data-stu-id="2e602-113">The MDA can also activate because the calling convention, possibly specified by the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute, does not match the unmanaged calling convention.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="2e602-114">Resolución</span><span class="sxs-lookup"><span data-stu-id="2e602-114">Resolution</span></span>  
 <span data-ttu-id="2e602-115">Revise la firma de la invocación de plataforma administrada y la convención de llamada para confirmar que coincide con la firma y la convención de llamada del destino nativo.</span><span class="sxs-lookup"><span data-stu-id="2e602-115">Review the managed platform invoke signature and calling convention to confirm it matches the signature and calling convention of the native target.</span></span>  <span data-ttu-id="2e602-116">Pruebe a especificar explícitamente la convención de llamada en ambos lados, administrado y no administrado.</span><span class="sxs-lookup"><span data-stu-id="2e602-116">Try explicitly specifying the calling convention on both the managed and unmanaged sides.</span></span> <span data-ttu-id="2e602-117">También es posible, aunque no probable, que la función no administrada haya desequilibrado la pila por algún otro motivo, por ejemplo, un error en el compilador no administrado.</span><span class="sxs-lookup"><span data-stu-id="2e602-117">It is also possible, although not as likely, that the unmanaged function unbalanced the stack for some other reason, such as a bug in the unmanaged compiler.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="2e602-118">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="2e602-118">Effect on the Runtime</span></span>  
 <span data-ttu-id="2e602-119">Obliga a todas las llamadas de invocación de plataforma a tomar la ruta de acceso no optimizada en CLR.</span><span class="sxs-lookup"><span data-stu-id="2e602-119">Forces all platform invoke calls to take the nonoptimized path in the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="2e602-120">Salida</span><span class="sxs-lookup"><span data-stu-id="2e602-120">Output</span></span>  
 <span data-ttu-id="2e602-121">El mensaje del MDA indica el nombre de la llamada al método de invocación de plataforma que causa el desequilibrio de la pila.</span><span class="sxs-lookup"><span data-stu-id="2e602-121">The MDA message gives the name of the platform invoke method call that is causing the stack imbalance.</span></span>  <span data-ttu-id="2e602-122">Un mensaje de ejemplo de una llamada de invocación de plataforma en el método `SampleMethod` es:</span><span class="sxs-lookup"><span data-stu-id="2e602-122">A sample message of a platform invoke call on method `SampleMethod` is:</span></span>  
  
```  
A call to PInvoke function 'SampleMethod' has unbalanced the stack.   
This is likely because the managed PInvoke signature does not match   
the unmanaged target signature. Check that the calling convention and   
parameters of the PInvoke signature match the target unmanaged signature.  
```  
  
## <a name="configuration"></a><span data-ttu-id="2e602-123">Configuración</span><span class="sxs-lookup"><span data-stu-id="2e602-123">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeStackImbalance />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e602-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e602-124">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="2e602-125">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="2e602-125">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="2e602-126">Serialización para interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="2e602-126">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
