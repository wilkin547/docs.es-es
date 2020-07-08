---
title: MDA de invalidIUnknownPointer
description: Revise el Asistente para la depuración administrada (MDA) Invalidiunknownpointer, que se activa cuando se pasa un puntero IUnknown no válido al código administrado desde código nativo.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
ms.openlocfilehash: 65d704463ed746390ff1710b590bf080013bf53d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051732"
---
# <a name="invalidiunknown-mda"></a>MDA de invalidIUnknownPointer
El asistente para la depuración administrada (MDA) de `invalidIUnknown` se activa cuando un puntero `IUnknown` no válido se pasa a código administrado de código nativo. Se produce un error en `IUnknown` a la hora de devolver un resultado correctamente cuando se solicita la interfaz `IUnknown`.  
  
## <a name="symptoms"></a>Síntomas  
 Se produce un error inesperado al calcular referencias de un puntero a una interfaz COM durante el cálculo de referencias del argumento.  
  
## <a name="cause"></a>Causa  
  Implementación de `QueryInterface` incorrecta en la interfaz COM pasada al CLR.  
  
## <a name="resolution"></a>Resolución  
 Corrija la implementación de `QueryInterface`.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR.  
  
## <a name="output"></a>Output  
 Descripción del error.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnóstico de errores con asistentes de depuraciones administradas](diagnosing-errors-with-managed-debugging-assistants.md)
- [Serialización de interoperabilidad](../interop/interop-marshaling.md)
