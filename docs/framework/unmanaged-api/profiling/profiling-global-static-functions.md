---
title: Funciones estáticas globales para generación de perfiles
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
ms.openlocfilehash: d1d9b0a4c61ce7c3f8f9792046fb4bddf0fdfa05
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447437"
---
# <a name="profiling-global-static-functions"></a>Funciones estáticas globales para generación de perfiles
En esta sección se describen las funciones de la API no administradas que utiliza la API de generación de perfiles.  
  
## <a name="in-this-section"></a>Esta sección  
  
## <a name="net-framework-version-1-profiling-functions"></a>Funciones de generación de perfiles de .NET Framework versión 1  
 [FunctionEnter (Función)](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)  
 Notifica al generador de perfiles que el control se pasa a una función. En desuso en el .NET Framework 2,0.  
  
 [FunctionLeave (Función)](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)  
 Notifica al generador de perfiles que una función está a punto de volver al llamador. En desuso en el .NET Framework 2,0.  
  
 [FunctionTailcall (Función)](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md)  
 Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función. En desuso en el .NET Framework 2,0.  
  
## <a name="net-framework-version-2-profiling-functions"></a>Funciones de generación de perfiles de .NET Framework versión 2  
 [FunctionIDMapper (Función)](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)  
 Notifica al generador de perfiles que el identificador especificado de una función puede reasignarse a un identificador alternativo que se va a usar en las devoluciones de llamada [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)y [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) para esa función. También permite al generador de perfiles indicar si desea recibir devoluciones de llamada para esa función.  
  
 [FunctionEnter2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 Notifica al generador de perfiles que el control se pasa a una función y proporciona información sobre el marco de pila y los argumentos de la función. En desuso en el .NET Framework 4.  
  
 [FunctionLeave2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 Notifica al generador de perfiles que una función está a punto de volver al autor de la llamada y proporciona información sobre el marco de pila y el valor devuelto de la función. En desuso en el .NET Framework 4.  
  
 [FunctionTailcall2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función y proporciona información sobre el marco de pila. En desuso en el .NET Framework 4.  
  
 [StackSnapshotCallback (Función)](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)  
 Proporciona al generador de perfiles información sobre cada marco administrado y cada ejecución de marcos no administrados en la pila durante un recorrido de pila, iniciado por el método [ICorProfilerInfo2::D ostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) .  
  
## <a name="net-framework-version-4-profiling-functions"></a>Funciones de generación de perfiles de .NET Framework versión 4  
 [FunctionIDMapper2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 Notifica al generador de perfiles que el identificador especificado de una función puede reasignarse a un identificador alternativo que se va a usar en las devoluciones de llamada [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)o[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)y [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) de esa función. También permite al generador de perfiles indicar si desea recibir devoluciones de llamada para esa función.  
  
 `FunctionIDMapper2` extiende la función [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) con un parámetro `clientData`, que los subarchivos pueden usar para eliminar la ambigüedad entre los tiempos de ejecución.  
  
 [FunctionEnter3 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 Notifica al generador de perfiles que el control se pasa a una función.  
  
 [FunctionEnter3WithInfo (Función)](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 Notifica al generador de perfiles que el control se pasa a una función y proporciona un identificador que se puede pasar a [ICorProfilerInfo3:: GetFunctionEnter3Info (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) para recuperar el marco de pila y los argumentos de la función.  
  
 [FunctionLeave3 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 Notifica al generador de perfiles que el control se devuelve desde una función.  
  
 [FunctionLeave3WithInfo (Función)](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 Notifica al generador de perfiles que el control se devuelve desde una función y proporciona un identificador que se puede pasar a [ICorProfilerInfo3:: GetFunctionLeave3Info (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) para recuperar el marco de pila y el valor devuelto.  
  
 [FunctionTailcall3 (Función)](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función.  
  
 [FunctionTailcall3WithInfo (Función)](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función y proporciona un identificador que se puede pasar a [ICorProfilerInfo3:: GetFunctionTailcall3Info (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) para recuperar el marco de pila.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Información general sobre la generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [Enumeraciones para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [Estructuras para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
