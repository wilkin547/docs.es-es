---
title: MDA de marshalCleanupError
description: Revise el Asistente para la depuración administrada (MDA) marshalCleanupError, que se invoca porque se produjo un error inesperado al limpiar las estructuras temporales.
ms.date: 03/30/2017
helpviewer_keywords:
- cleanup operations
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- marshaling cleanup error
- MarshalCleanupError MDA
- memory, cleanup errors
ms.assetid: 2f5d9e7c-ae51-4155-a435-54347aa1f091
ms.openlocfilehash: 3c7498d6f51484de3a2e84d611a2634f53724ab6
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051617"
---
# <a name="marshalcleanuperror-mda"></a>MDA de marshalCleanupError
El asistente para la depuración administrada (MDA, por sus siglas en inglés) `marshalCleanupError` se activa cuando Common Language Runtime (CLR) detecta un error al intentar limpiar la memoria y las estructuras temporales que se usan para serializar tipos de datos entre los límites del código nativo y administrado.  
  
## <a name="symptoms"></a>Síntomas  
 Se produce una fuga de memoria al realizar transiciones de código nativo y administrado, cuando no se restaura un estado de runtime (por ejemplo, una referencia cultural de subproceso) o si la limpieza de <xref:System.Runtime.InteropServices.SafeHandle> tiene errores.  
  
## <a name="cause"></a>Causa  
 Se produjo un error inesperado al limpiar las estructuras temporales.  
  
## <a name="resolution"></a>Resolución  
 Revise todas las implementaciones de destructor, finalizador y cálculo de referencias de <xref:System.Runtime.InteropServices.SafeHandle> para comprobar si hay errores.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR.  
  
## <a name="output"></a>Output  
 Un mensaje que indica que se produjo un error en la operación durante la limpieza.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnóstico de errores con asistentes de depuraciones administradas](diagnosing-errors-with-managed-debugging-assistants.md)
- [Serialización de interoperabilidad](../interop/interop-marshaling.md)
