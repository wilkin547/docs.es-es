---
title: MDA de overlappedFreeError
description: Revise el Asistente para la depuración administrada (MDA) de overlappedFreeError en .NET, que puede activarse en infracciones de acceso o daños en el montón de recolección de elementos no utilizados.
ms.date: 03/30/2017
helpviewer_keywords:
- OverlappedFreeError MDA
- overlapped free method call error
- managed debugging assistants (MDAs), overlapped structures
- overlapped structures
- MDAs (managed debugging assistants), overlapped structures
- freeing overlapped structures
ms.assetid: b6ab2d48-6eee-4bab-97a3-046b3b0a5470
ms.openlocfilehash: 1bedb8ad3b9801f0d235371a397c8951ff8723b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254537"
---
# <a name="overlappedfreeerror-mda"></a>MDA de overlappedFreeError

El Asistente para la depuración administrada (MDA) `overlappedFreeError` se activa cuando se llama al método <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType> antes de que se haya completado la operación superpuesta.  
  
## <a name="symptoms"></a>Síntomas  

 Infracciones de acceso o daños en el montón de recolección de elementos no utilizados.  
  
## <a name="cause"></a>Causa  

 Una estructura superpuesta se liberó antes de finalizar la operación. Es posible que la función que está usando el puntero superpuesto escriba en la estructura más adelante, después de que se haya liberado. Esto puede provocar daños en el montón porque es posible que ahora otro objeto ocupe esa región.  
  
 Es posible que este MDA no represente un error si la operación superpuesta no se inició correctamente.  
  
## <a name="resolution"></a>Solución  

 Asegúrese de que se complete la operación de E/S que usa la estructura superpuesta antes de llamar al método <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29>.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  

 Este MDA no tiene ningún efecto en el CLR.  
  
## <a name="output"></a>Resultados  

 A continuación puede ver un resultado de ejemplo para este MDA.  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlappedStructure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <overlappedFreeError/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnóstico de errores con asistentes de depuraciones administradas](diagnosing-errors-with-managed-debugging-assistants.md)
- [Serialización de interoperabilidad](../interop/interop-marshaling.md)
