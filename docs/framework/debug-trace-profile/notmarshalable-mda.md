---
title: MDA de notMarshalable
description: Revise el Asistente para la depuración administrada de notMarshalable, que puede activar si las llamadas no se realizan en el contexto incorrecto para los punteros de interfaz COM.
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
ms.openlocfilehash: 344c275d8645b16de3ecb06517297df06323ced4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254563"
---
# <a name="notmarshalable-mda"></a><span data-ttu-id="bb760-103">MDA de notMarshalable</span><span class="sxs-lookup"><span data-stu-id="bb760-103">notMarshalable MDA</span></span>

<span data-ttu-id="bb760-104">El asistente para la depuración administrada (MDA) `notMarshalable` se activa cuando Common Language Runtime (CLR) encuentra un puntero a interfaz COM sin un servidor proxy/código auxiliar válido registrado o una implementación de interfaz `IMarshal` incorrecta al intentar serializar la interfaz entre contextos.</span><span class="sxs-lookup"><span data-stu-id="bb760-104">The `notMarshalable` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters a COM interface pointer without a valid registered proxy/stub or an incorrect `IMarshal` interface implementation while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="bb760-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="bb760-105">Symptoms</span></span>  

 <span data-ttu-id="bb760-106">No se da servicio a las llamadas o las llamadas se producen en un contexto incorrecto para los punteros a interfaz COM.</span><span class="sxs-lookup"><span data-stu-id="bb760-106">Calls are not serviced, or calls occur in the wrong context for COM interface pointers.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="bb760-107">Causa</span><span class="sxs-lookup"><span data-stu-id="bb760-107">Cause</span></span>  

 <span data-ttu-id="bb760-108">No hay ningún servidor proxy/código auxiliar registrado válido o `IMarshal` incorrecta intentando serializar la interfaz entre los contextos.</span><span class="sxs-lookup"><span data-stu-id="bb760-108">No valid registered proxy/stub or an incorrect `IMarshal` while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="bb760-109">Solución</span><span class="sxs-lookup"><span data-stu-id="bb760-109">Resolution</span></span>  

 <span data-ttu-id="bb760-110">Asegúrese de que tiene registrado un código auxiliar de servidor proxy y de que la implementación de `IMarshal` es válida.</span><span class="sxs-lookup"><span data-stu-id="bb760-110">Make sure you have a proxy stub registered and that the `IMarshal` implementation is valid.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="bb760-111">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="bb760-111">Effect on the Runtime</span></span>  

 <span data-ttu-id="bb760-112">Este MDA no tiene ningún efecto en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bb760-112">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="bb760-113">Resultados</span><span class="sxs-lookup"><span data-stu-id="bb760-113">Output</span></span>  

 <span data-ttu-id="bb760-114">Un mensaje que describe el problema.</span><span class="sxs-lookup"><span data-stu-id="bb760-114">A message describing the problem.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="bb760-115">Configuración</span><span class="sxs-lookup"><span data-stu-id="bb760-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb760-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb760-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="bb760-117">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="bb760-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="bb760-118">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="bb760-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
