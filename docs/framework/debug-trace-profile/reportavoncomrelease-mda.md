---
title: MDA de reportAVOnComRelease
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), reference counting errors
- exceptions, reference counting errors
- ReportAvOnComRelease MDA
- COM release access violations
- user reference counting errors
- managed debugging assistants (MDAs), reference counting errors
- report access violation on Com release
- reference counting errors
ms.assetid: a2b86b63-08b2-4943-b344-3c2cf46ccd31
ms.openlocfilehash: fca6b209e6432678a264f10762adb3871e3596ce
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217219"
---
# <a name="reportavoncomrelease-mda"></a><span data-ttu-id="bf25c-102">MDA de reportAVOnComRelease</span><span class="sxs-lookup"><span data-stu-id="bf25c-102">reportAvOnComRelease MDA</span></span>
<span data-ttu-id="bf25c-103">El asistente para la depuración administrada (MDA, por sus siglas en inglés) `reportAvOnComRelease` se activa cuando se producen excepciones que se deben a errores de recuento de referencias de usuario mientras se realiza la interoperabilidad COM y se usan los métodos <xref:System.Runtime.InteropServices.Marshal.Release%2A> o <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> en combinación con llamadas COM sin formato.</span><span class="sxs-lookup"><span data-stu-id="bf25c-103">The `reportAvOnComRelease` managed debugging assistant (MDA) is activated when exceptions are thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="bf25c-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="bf25c-104">Symptoms</span></span>  
 <span data-ttu-id="bf25c-105">Infracciones de acceso y deterioro de la memoria.</span><span class="sxs-lookup"><span data-stu-id="bf25c-105">Access violations and memory corruption.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="bf25c-106">Causa</span><span class="sxs-lookup"><span data-stu-id="bf25c-106">Cause</span></span>  
 <span data-ttu-id="bf25c-107">En ocasiones, se produce una excepción debido a errores de recuento de referencias de usuario mientras se realiza la interoperabilidad COM y se usan los métodos <xref:System.Runtime.InteropServices.Marshal.Release%2A> o <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> en combinación con llamadas COM sin formato.</span><span class="sxs-lookup"><span data-stu-id="bf25c-107">Occasionally, an exception is thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span> <span data-ttu-id="bf25c-108">Normalmente, esta excepción se descarta porque, de lo contrario, se produciría una infracción de acceso en el CLR y la caída del mismo.</span><span class="sxs-lookup"><span data-stu-id="bf25c-108">Normally, this exception is discarded because not doing so would cause an access violation in the CLR, bringing it down.</span></span> <span data-ttu-id="bf25c-109">Cuando se habilita el asistente, esas excepciones se pueden detectar y notificar en vez de simplemente descartarlas.</span><span class="sxs-lookup"><span data-stu-id="bf25c-109">When this assistant is enabled, such exceptions can be detected and reported instead of being simply discarded.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="bf25c-110">Solución</span><span class="sxs-lookup"><span data-stu-id="bf25c-110">Resolution</span></span>  
 <span data-ttu-id="bf25c-111">Examine el código de recuento de referencias, busque errores y examine los clientes nativos de su objeto para comprobar si existen errores de recuento de referencias.</span><span class="sxs-lookup"><span data-stu-id="bf25c-111">Examine your reference counting code and search for errors as well as examining the native clients of your object for reference counting errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="bf25c-112">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="bf25c-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="bf25c-113">Hay dos modos disponibles.</span><span class="sxs-lookup"><span data-stu-id="bf25c-113">Two modes are available.</span></span> <span data-ttu-id="bf25c-114">Si el atributo `allowAv` es `true`, el asistente evita que el runtime descarte la infracción de acceso.</span><span class="sxs-lookup"><span data-stu-id="bf25c-114">If the `allowAv` attribute is `true`, the assistant prevents the runtime from discarding the access violation.</span></span> <span data-ttu-id="bf25c-115">Si `allowAv` es `false` —que es el valor predeterminado—, el runtime descarta la infracción de acceso, pero el usuario recibe un mensaje de advertencia donde se le indica que se produjo una excepción y se descartó.</span><span class="sxs-lookup"><span data-stu-id="bf25c-115">If `allowAv` is `false`, which is the default, the runtime discards the access violation, but a warning message is reported to the user to indicate that an exception was thrown and discarded.</span></span>  
  
## <a name="output"></a><span data-ttu-id="bf25c-116">Output</span><span class="sxs-lookup"><span data-stu-id="bf25c-116">Output</span></span>  
 <span data-ttu-id="bf25c-117">Si es posible, el resultado contiene la vtable original del puntero de interfaz COM.</span><span class="sxs-lookup"><span data-stu-id="bf25c-117">If possible, the output contains the COM interface pointer's original vtable.</span></span> <span data-ttu-id="bf25c-118">De lo contrario, aparece un mensaje con información.</span><span class="sxs-lookup"><span data-stu-id="bf25c-118">Otherwise, an informational message is displayed.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="bf25c-119">Configuración</span><span class="sxs-lookup"><span data-stu-id="bf25c-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reportAvOnComRelease />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf25c-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf25c-120">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="bf25c-121">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="bf25c-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="bf25c-122">Serialización para interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="bf25c-122">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
