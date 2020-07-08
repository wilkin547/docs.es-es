---
title: MDA de illegalPrepareConstrainedRegion
description: Revise el Asistente para la depuración administrada illegalPrepareConstrainedRegion, que se invoca si una llamada a PrepareConstrainedRegions no va seguida de una instrucción try.
ms.date: 03/30/2017
helpviewer_keywords:
- PrepareConstrainedRegions method
- managed debugging assistants (MDAs), illegal PrepareConstrainedRegions
- try/catch exception handling, managed debugging assistants
- IllegalPrepareConstrainedRegions MDA
- MDAs (managed debugging assistants), illegal PrepareConstrainedRegions
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
ms.openlocfilehash: d6a0d1d95840ebd735806c5547730ae9e0b2aace
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051290"
---
# <a name="illegalprepareconstrainedregion-mda"></a>MDA de illegalPrepareConstrainedRegion
El Asistente para la depuración administrada (MDA) `illegalPrepareConstrainedRegion` se activa cuando una llamada al método <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> no precede inmediatamente a la instrucción `try` del controlador de excepciones. Esta restricción está en el nivel de MSIL, por lo que permite tener un origen de no generación de código entre la llamada y `try` (por ejemplo comentarios).  
  
## <a name="symptoms"></a>Síntomas  
 Una región de ejecución restringida (CER) que nunca se trata como tal, sino como un simple bloque de control de excepciones (`finally` o `catch`). En consecuencia, la región no se ejecuta en el caso de una condición de memoria insuficiente o una anulación del subproceso.  
  
## <a name="cause"></a>Causa  
 El modelo de preparación para una región CER no se ha seguido correctamente.  Se trata de un evento de error. La <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> llamada al método que se usa para marcar los controladores de excepciones como la introducción de una CER en sus `catch` / `finally` / `fault` / `filter` bloques debe usarse inmediatamente antes de la `try` instrucción.  
  
## <a name="resolution"></a>Resolución  
 Asegúrese de que la llamada a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> se produce inmediatamente antes de la instrucción `try`.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR.  
  
## <a name="output"></a>Output  
 El MDA muestra el nombre del método que llama al método <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>, el desplazamiento MSIL y un mensaje que indica que la llamada no precede inmediatamente al inicio del bloque try.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra el patrón que hace que se active este MDA.  
  
```csharp
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>
- [Diagnóstico de errores con asistentes de depuraciones administradas](diagnosing-errors-with-managed-debugging-assistants.md)
- [Serialización de interoperabilidad](../interop/interop-marshaling.md)
