---
title: "Estructuras de depuración"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0293a20f5f735dd38b1d167ebc5057f645fa011a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-structures"></a>Estructuras de depuración
En esta sección se describen las estructuras no administradas que utiliza la API de depuración.  
  
## <a name="in-this-section"></a>En esta sección  
 [CLR_DEBUGGING_VERSION (estructura)](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md)  
 Define la versión de producto de Common Language Runtime (CLR) con fines de depuración.  
  
 [CodeChunkInfo estructura-1](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md)  
 Representa un único fragmento de código en la memoria.  
  
 [CorDebugBlockingObject (estructura)](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)  
 Define un objeto que está bloqueando un subproceso y el motivo por el que el subproceso está bloqueado.  
  
 [CorDebugEHClause (estructura)](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)  
 Representa una cláusula de control de excepciones (EH) para una parte determinada de lenguaje intermedio (IL).  
  
 [CorDebugExceptionObjectStackFrame (estructura)](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 Representa información del marco de pila de un objeto de excepción.  
  
 [CorDebugExceptionObjectStackFrame (estructura)](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 Se asigna un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID para el correspondiente [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) objeto.  
  
 COR_ACTIVE_FUNCTION  
 Contiene información sobre las funciones que están actualmente activas en los marcos de un subproceso.  
  
 [COR_ARRAY_LAYOUT (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)  
 Proporciona información sobre la distribución de un objeto de matriz en la memoria.  
  
 COR_DEBUG_IL_TO_NATIVE_MAP  
 Contiene los desplazamientos que se usan para asignar código de lenguaje intermedio de Microsoft (MSIL) a código nativo.  
  
 COR_DEBUG_STEP_RANGE  
 Contiene información de desplazamiento para un intervalo de código.  
  
 [COR_FIELD (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)  
 Proporciona información sobre un campo en un objeto.  
  
 [COR_GC_REFERENCE (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)  
 Contiene información sobre un objeto que se va a recolectar con elemento no utilizado.  
  
 [COR_HEAPINFO (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)  
 Proporciona información general sobre el montón de recolección de elementos no utilizados, incluido si es enumerable.  
  
 [COR_HEAPOBJECT (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)  
 Proporciona información sobre un objeto del montón administrado.  
  
 COR_IL_MAP  
 Especifica los cambios en el desplazamiento relativo de una función.  
  
 [COR_SEGMENT (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)  
 Contiene información sobre una región de memoria en el montón administrado.  
  
 [COR_TYPEID (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)  
 Contiene un identificador de tipos.  
  
 [COR_TYPE_LAYOUT (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 Proporciona información sobre la distribución de un objeto en la memoria.  
  
 COR_VERSION  
 Almacena la versión estándar en cuatro partes de Common Language Runtime.  
  
 [StackTrace_SimpleContext (estructura)](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)  
 Proporciona un contexto simple que se puede usar en lugar de una estructura `CONTEXT` completa.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Coclases para la depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [Funciones estáticas globales para la depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
