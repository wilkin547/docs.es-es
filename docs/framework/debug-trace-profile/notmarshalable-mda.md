---
title: MDA de notMarshalable
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), interface pointer not marshalable
- interface pointer not marshalable MDA
- MDAs (managed debugging assistants), interface pointer not marshalable
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- marshalable interface pointers
- MDAs (managed debugging assistants), marshaling
- notMarshalable MDA
ms.assetid: 96e7b2c1-843f-4d64-b519-740c3a18b50a
ms.openlocfilehash: 45db0e70b2446fa6e3175409bcc3844042f0acc0
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217286"
---
# <a name="notmarshalable-mda"></a><span data-ttu-id="4d563-102">MDA de notMarshalable</span><span class="sxs-lookup"><span data-stu-id="4d563-102">notMarshalable MDA</span></span>
<span data-ttu-id="4d563-103">El asistente para la depuración administrada (MDA) `notMarshalable` se activa cuando Common Language Runtime (CLR) encuentra un puntero a interfaz COM sin un servidor proxy/código auxiliar válido registrado o una implementación de interfaz `IMarshal` incorrecta al intentar serializar la interfaz entre contextos.</span><span class="sxs-lookup"><span data-stu-id="4d563-103">The `notMarshalable` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters a COM interface pointer without a valid registered proxy/stub or an incorrect `IMarshal` interface implementation while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="4d563-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="4d563-104">Symptoms</span></span>  
 <span data-ttu-id="4d563-105">No se da servicio a las llamadas o las llamadas se producen en un contexto incorrecto para los punteros a interfaz COM.</span><span class="sxs-lookup"><span data-stu-id="4d563-105">Calls are not serviced, or calls occur in the wrong context for COM interface pointers.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="4d563-106">Causa</span><span class="sxs-lookup"><span data-stu-id="4d563-106">Cause</span></span>  
 <span data-ttu-id="4d563-107">No hay ningún servidor proxy/código auxiliar registrado válido o `IMarshal` incorrecta intentando serializar la interfaz entre los contextos.</span><span class="sxs-lookup"><span data-stu-id="4d563-107">No valid registered proxy/stub or an incorrect `IMarshal` while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="4d563-108">Solución</span><span class="sxs-lookup"><span data-stu-id="4d563-108">Resolution</span></span>  
 <span data-ttu-id="4d563-109">Asegúrese de que tiene registrado un código auxiliar de servidor proxy y de que la implementación de `IMarshal` es válida.</span><span class="sxs-lookup"><span data-stu-id="4d563-109">Make sure you have a proxy stub registered and that the `IMarshal` implementation is valid.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="4d563-110">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="4d563-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="4d563-111">Este MDA no tiene ningún efecto en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4d563-111">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="4d563-112">Output</span><span class="sxs-lookup"><span data-stu-id="4d563-112">Output</span></span>  
 <span data-ttu-id="4d563-113">Un mensaje que describe el problema.</span><span class="sxs-lookup"><span data-stu-id="4d563-113">A message describing the problem.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="4d563-114">Configuración</span><span class="sxs-lookup"><span data-stu-id="4d563-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d563-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d563-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="4d563-116">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="4d563-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="4d563-117">Serialización para interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="4d563-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
