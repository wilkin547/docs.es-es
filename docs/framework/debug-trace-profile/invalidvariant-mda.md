---
title: MDA de invalidVariant
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 426b9df449b12d2f34fa70fc721cc050fa3e4ddd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="invalidvariant-mda"></a>MDA de invalidVariant
El asistente para la depuración administrada (MDA) de `invalidVariant` se activa cuando se encuentra una estructura `VARIANT` no válida durante una llamada de código nativo o no administrado a un código administrado.  
  
## <a name="symptoms"></a>Síntomas  
 Comportamiento inesperado durante una transición entre código nativo y administrado que implica el cálculo de referencias de `VARIANT` a un objeto.  
  
## <a name="cause"></a>Motivo  
 El código nativo está pasando una estructura `VARIANT` incorrecta al código administrado.  El motor en tiempo de ejecución intenta calcular las referencias de `VARIANT` a un objeto y activa el MDA si `VARIANT` no es válido. Los ejemplos de `VARIANT` no válidas incluyen `VARIANT` con `VARTYPE` VT_EMPTY &#124; VT_BYREF o `VARIANT` con `VARTYPE` VT_VARIANT.  
  
## <a name="resolution"></a>Resolución  
 El paso de `VARIANT` por parte del código nativo o no administrado debe garantizar que `VARIANT` se forme e inicialice correctamente.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el comportamiento del tiempo de ejecución.  
  
## <a name="output"></a>Resultado  
 Un mensaje de MDA que indica que el motor en tiempo de ejecución detectó una `VARIANT` no válida pasada a código administrado mediante un módulo no administrado.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Serialización de interoperabilidad](../../../docs/framework/interop/interop-marshaling.md)
