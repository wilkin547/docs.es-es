---
title: MDA de notMarshalable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c5de75130acab30c4f73522728c00b69c1c3e8d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="notmarshalable-mda"></a><span data-ttu-id="7a3dd-102">MDA de notMarshalable</span><span class="sxs-lookup"><span data-stu-id="7a3dd-102">notMarshalable MDA</span></span>
<span data-ttu-id="7a3dd-103">El asistente para la depuración administrada (MDA) `notMarshalable` se activa cuando Common Language Runtime (CLR) encuentra un puntero a interfaz COM sin un servidor proxy/código auxiliar válido registrado o una implementación de interfaz `IMarshal` incorrecta al intentar calcular las referencias de la interfaz entre contextos.</span><span class="sxs-lookup"><span data-stu-id="7a3dd-103">The `notMarshalable` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters a COM interface pointer without a valid registered proxy/stub or an incorrect `IMarshal` interface implementation while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="7a3dd-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="7a3dd-104">Symptoms</span></span>  
 <span data-ttu-id="7a3dd-105">No se da servicio a las llamadas o las llamadas se producen en un contexto incorrecto para los punteros a interfaz COM.</span><span class="sxs-lookup"><span data-stu-id="7a3dd-105">Calls are not serviced, or calls occur in the wrong context for COM interface pointers.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="7a3dd-106">Motivo</span><span class="sxs-lookup"><span data-stu-id="7a3dd-106">Cause</span></span>  
 <span data-ttu-id="7a3dd-107">No hay ningún servidor proxy/código auxiliar registrado válido o `IMarshal` incorrecta intentando calcular las referencias de la interfaz entre los contextos.</span><span class="sxs-lookup"><span data-stu-id="7a3dd-107">No valid registered proxy/stub or an incorrect `IMarshal` while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="7a3dd-108">Resolución</span><span class="sxs-lookup"><span data-stu-id="7a3dd-108">Resolution</span></span>  
 <span data-ttu-id="7a3dd-109">Asegúrese de que tiene registrado un código auxiliar de servidor proxy y de que la implementación de `IMarshal` es válida.</span><span class="sxs-lookup"><span data-stu-id="7a3dd-109">Make sure you have a proxy stub registered and that the `IMarshal` implementation is valid.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="7a3dd-110">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="7a3dd-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="7a3dd-111">Este MDA no tiene ningún efecto en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7a3dd-111">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="7a3dd-112">Resultado</span><span class="sxs-lookup"><span data-stu-id="7a3dd-112">Output</span></span>  
 <span data-ttu-id="7a3dd-113">Un mensaje que describe el problema.</span><span class="sxs-lookup"><span data-stu-id="7a3dd-113">A message describing the problem.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="7a3dd-114">Configuración</span><span class="sxs-lookup"><span data-stu-id="7a3dd-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a3dd-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a3dd-115">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="7a3dd-116">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="7a3dd-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="7a3dd-117">Serialización para interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="7a3dd-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
