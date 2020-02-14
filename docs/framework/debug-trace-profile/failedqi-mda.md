---
title: MDA de failedQI
ms.date: 03/30/2017
helpviewer_keywords:
- failed QueryInterface
- FailedQI MDA
- QueryInterface call failures
- MDAs (managed debugging assistants), failed QueryInterface
- managed debugging assistants (MDAs), failed QueryInterface
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
ms.openlocfilehash: 4c36ec514645a38ef1228e76bdf6dbd06e886bae
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217507"
---
# <a name="failedqi-mda"></a><span data-ttu-id="8723e-102">MDA de failedQI</span><span class="sxs-lookup"><span data-stu-id="8723e-102">failedQI MDA</span></span>
<span data-ttu-id="8723e-103">El asistente para la depuración administrada (MDA) `failedQI` se activa cuando Runtime llama a `QueryInterface` en un puntero de interfaz COM en nombre de un contenedor al que se puede llamar en tiempo de ejecución (RCW) y la llamada `QueryInterface` falla.</span><span class="sxs-lookup"><span data-stu-id="8723e-103">The `failedQI` managed debugging assistant (MDA) is activated when the runtime calls `QueryInterface` on a COM interface pointer on behalf of a runtime callable wrapper (RCW), and the `QueryInterface` call fails.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="8723e-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="8723e-104">Symptoms</span></span>  
 <span data-ttu-id="8723e-105">No se puede realizar una conversión en un contenedor RCW o se produce un error inesperado en una llamada a COM desde un contenedor RCW</span><span class="sxs-lookup"><span data-stu-id="8723e-105">A cast on an RCW fails, or a call to COM from an RCW fails unexpectedly.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="8723e-106">Causa</span><span class="sxs-lookup"><span data-stu-id="8723e-106">Cause</span></span>  
  
- <span data-ttu-id="8723e-107">La llamada se realiza desde el contexto equivocado.</span><span class="sxs-lookup"><span data-stu-id="8723e-107">The call is made from the wrong context.</span></span>  
  
- <span data-ttu-id="8723e-108">El servidor proxy registrado no puede realizar la llamada `QueryInterface` porque se intentó realizar en el contexto equivocado.</span><span class="sxs-lookup"><span data-stu-id="8723e-108">The registered proxy is failing the `QueryInterface` call because the call was attempted in the wrong context.</span></span>  
  
- <span data-ttu-id="8723e-109">Un servidor proxy propiedad de OLE devolvió un valor HRESULT de error.</span><span class="sxs-lookup"><span data-stu-id="8723e-109">An OLE-owned proxy returned a failure HRESULT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="8723e-110">Solución</span><span class="sxs-lookup"><span data-stu-id="8723e-110">Resolution</span></span>  
 <span data-ttu-id="8723e-111">Consulte la documentación sobre reglas COM recogida en el sitio de MSDN.</span><span class="sxs-lookup"><span data-stu-id="8723e-111">See the MSDN documentation on COM rules.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8723e-112">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="8723e-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="8723e-113">Si no se puede realizar la llamada `QueryInterface`, el contexto cambia y es necesario volver a intentar realizar la llamada `QueryInterface` para ver si el motivo del error era un contexto incorrecto.</span><span class="sxs-lookup"><span data-stu-id="8723e-113">If a `QueryInterface` call fails, the context is switched and the `QueryInterface` call is attempted again to see if an incorrect context was at fault.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8723e-114">Output</span><span class="sxs-lookup"><span data-stu-id="8723e-114">Output</span></span>  
 <span data-ttu-id="8723e-115">El nombre administrado de la interfaz, el GUID de la interfaz y el valor HRESULT del error.</span><span class="sxs-lookup"><span data-stu-id="8723e-115">The managed name of the interface, the GUID of the interface, and the HRESULT of the failure.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="8723e-116">Configuración</span><span class="sxs-lookup"><span data-stu-id="8723e-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8723e-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8723e-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="8723e-118">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="8723e-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="8723e-119">Serialización para interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="8723e-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
