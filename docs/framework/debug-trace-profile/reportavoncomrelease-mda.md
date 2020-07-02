---
title: MDA de reportAVOnComRelease
description: Revise el Asistente para la depuración administrada (MDA) de reportAvOnComRelease, que puede activarse debido a infracciones de acceso y a daños en la memoria en .NET.
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
ms.openlocfilehash: f9ba343060cb4d16de5909a5b619353546aca8ca
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803615"
---
# <a name="reportavoncomrelease-mda"></a><span data-ttu-id="ffbb2-103">MDA de reportAVOnComRelease</span><span class="sxs-lookup"><span data-stu-id="ffbb2-103">reportAvOnComRelease MDA</span></span>
<span data-ttu-id="ffbb2-104">El asistente para la depuración administrada (MDA, por sus siglas en inglés) `reportAvOnComRelease` se activa cuando se producen excepciones que se deben a errores de recuento de referencias de usuario mientras se realiza la interoperabilidad COM y se usan los métodos <xref:System.Runtime.InteropServices.Marshal.Release%2A> o <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> en combinación con llamadas COM sin formato.</span><span class="sxs-lookup"><span data-stu-id="ffbb2-104">The `reportAvOnComRelease` managed debugging assistant (MDA) is activated when exceptions are thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="ffbb2-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="ffbb2-105">Symptoms</span></span>  
 <span data-ttu-id="ffbb2-106">Infracciones de acceso y deterioro de la memoria.</span><span class="sxs-lookup"><span data-stu-id="ffbb2-106">Access violations and memory corruption.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="ffbb2-107">Causa</span><span class="sxs-lookup"><span data-stu-id="ffbb2-107">Cause</span></span>  
 <span data-ttu-id="ffbb2-108">En ocasiones, se produce una excepción debido a errores de recuento de referencias de usuario mientras se realiza la interoperabilidad COM y se usan los métodos <xref:System.Runtime.InteropServices.Marshal.Release%2A> o <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> en combinación con llamadas COM sin formato.</span><span class="sxs-lookup"><span data-stu-id="ffbb2-108">Occasionally, an exception is thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span> <span data-ttu-id="ffbb2-109">Normalmente, esta excepción se descarta porque, de lo contrario, se produciría una infracción de acceso en el CLR y la caída del mismo.</span><span class="sxs-lookup"><span data-stu-id="ffbb2-109">Normally, this exception is discarded because not doing so would cause an access violation in the CLR, bringing it down.</span></span> <span data-ttu-id="ffbb2-110">Cuando se habilita el asistente, esas excepciones se pueden detectar y notificar en vez de simplemente descartarlas.</span><span class="sxs-lookup"><span data-stu-id="ffbb2-110">When this assistant is enabled, such exceptions can be detected and reported instead of being simply discarded.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="ffbb2-111">Resolución</span><span class="sxs-lookup"><span data-stu-id="ffbb2-111">Resolution</span></span>  
 <span data-ttu-id="ffbb2-112">Examine el código de recuento de referencias, busque errores y examine los clientes nativos de su objeto para comprobar si existen errores de recuento de referencias.</span><span class="sxs-lookup"><span data-stu-id="ffbb2-112">Examine your reference counting code and search for errors as well as examining the native clients of your object for reference counting errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ffbb2-113">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="ffbb2-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="ffbb2-114">Hay dos modos disponibles.</span><span class="sxs-lookup"><span data-stu-id="ffbb2-114">Two modes are available.</span></span> <span data-ttu-id="ffbb2-115">Si el atributo `allowAv` es `true`, el asistente evita que el runtime descarte la infracción de acceso.</span><span class="sxs-lookup"><span data-stu-id="ffbb2-115">If the `allowAv` attribute is `true`, the assistant prevents the runtime from discarding the access violation.</span></span> <span data-ttu-id="ffbb2-116">Si `allowAv` es `false` —que es el valor predeterminado—, el runtime descarta la infracción de acceso, pero el usuario recibe un mensaje de advertencia donde se le indica que se produjo una excepción y se descartó.</span><span class="sxs-lookup"><span data-stu-id="ffbb2-116">If `allowAv` is `false`, which is the default, the runtime discards the access violation, but a warning message is reported to the user to indicate that an exception was thrown and discarded.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ffbb2-117">Output</span><span class="sxs-lookup"><span data-stu-id="ffbb2-117">Output</span></span>  
 <span data-ttu-id="ffbb2-118">Si es posible, el resultado contiene la vtable original del puntero de interfaz COM.</span><span class="sxs-lookup"><span data-stu-id="ffbb2-118">If possible, the output contains the COM interface pointer's original vtable.</span></span> <span data-ttu-id="ffbb2-119">De lo contrario, aparece un mensaje con información.</span><span class="sxs-lookup"><span data-stu-id="ffbb2-119">Otherwise, an informational message is displayed.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="ffbb2-120">Configuración</span><span class="sxs-lookup"><span data-stu-id="ffbb2-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reportAvOnComRelease />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ffbb2-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="ffbb2-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="ffbb2-122">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="ffbb2-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="ffbb2-123">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="ffbb2-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
