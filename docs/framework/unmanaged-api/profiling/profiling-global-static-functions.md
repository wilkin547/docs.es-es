---
title: Funciones estáticas globales para generación de perfiles
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
ms.openlocfilehash: 1b0ad42e6b34e99212e112f6a594b0a36b6715e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723082"
---
# <a name="profiling-global-static-functions"></a>Funciones estáticas globales para generación de perfiles

En esta sección se describen las funciones de la API no administradas que utiliza la API de generación de perfiles.  
  
## <a name="in-this-section"></a>En esta sección  
  
## <a name="net-framework-version-1-profiling-functions"></a>Funciones de generación de perfiles de .NET Framework versión 1  

 [FunctionEnter (Función)](functionenter-function.md)  
 Notifica al generador de perfiles que el control se pasa a una función. En desuso en el .NET Framework 2,0.  
  
 [FunctionLeave (Función)](functionleave-function.md)  
 Notifica al generador de perfiles que una función está a punto de volver al llamador. En desuso en el .NET Framework 2,0.  
  
 [FunctionTailcall (Función)](functiontailcall-function.md)  
 Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función. En desuso en el .NET Framework 2,0.  
  
## <a name="net-framework-version-2-profiling-functions"></a>Funciones de generación de perfiles de .NET Framework versión 2  

 [FunctionIDMapper (Función)](functionidmapper-function.md)  
 Notifica al generador de perfiles que el identificador especificado de una función puede reasignarse a un identificador alternativo que se va a usar en las devoluciones de llamada [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)y [FunctionTailcall2](functiontailcall2-function.md) para esa función. También permite al generador de perfiles indicar si desea recibir devoluciones de llamada para esa función.  
  
 [FunctionEnter2 (Función)](functionenter2-function.md)  
 Notifica al generador de perfiles que el control se pasa a una función y proporciona información sobre el marco de pila y los argumentos de la función. En desuso en el .NET Framework 4.  
  
 [FunctionLeave2 (Función)](functionleave2-function.md)  
 Notifica al generador de perfiles que una función está a punto de volver al autor de la llamada y proporciona información sobre el marco de pila y el valor devuelto de la función. En desuso en el .NET Framework 4.  
  
 [FunctionTailcall2 (Función)](functiontailcall2-function.md)  
 Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función y proporciona información sobre el marco de pila. En desuso en el .NET Framework 4.  
  
 [StackSnapshotCallback (Función)](stacksnapshotcallback-function.md)  
 Proporciona al generador de perfiles información sobre cada marco administrado y cada ejecución de marcos no administrados en la pila durante un recorrido de pila, iniciado por el método [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .  
  
## <a name="net-framework-version-4-profiling-functions"></a>Funciones de generación de perfiles de .NET Framework versión 4  

 [FunctionIDMapper2 (Función)](functionidmapper2-function.md)  
 Notifica al generador de perfiles que el identificador especificado de una función puede reasignarse a un identificador alternativo que se va a usar en las devoluciones de llamada [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), [FunctionTailcall3](functiontailcall3-function.md)o[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)y [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) de esa función. También permite al generador de perfiles indicar si desea recibir devoluciones de llamada para esa función.  
  
 `FunctionIDMapper2` extiende la función [FunctionIDMapper](functionidmapper-function.md) con un `clientData` parámetro, que los subarchivos pueden usar para eliminar la ambigüedad entre los tiempos de ejecución.  
  
 [FunctionEnter3 (Función)](functionenter3-function.md)  
 Notifica al generador de perfiles que el control se pasa a una función.  
  
 [FunctionEnter3WithInfo (Función)](functionenter3withinfo-function.md)  
 Notifica al generador de perfiles que el control se pasa a una función y proporciona un identificador que se puede pasar a [ICorProfilerInfo3:: GetFunctionEnter3Info (](icorprofilerinfo3-getfunctionenter3info-method.md) para recuperar el marco de pila y los argumentos de la función.  
  
 [FunctionLeave3 (Función)](functionleave3-function.md)  
 Notifica al generador de perfiles que el control se devuelve desde una función.  
  
 [FunctionLeave3WithInfo (Función)](functionleave3withinfo-function.md)  
 Notifica al generador de perfiles que el control se devuelve desde una función y proporciona un identificador que se puede pasar a [ICorProfilerInfo3:: GetFunctionLeave3Info (](icorprofilerinfo3-getfunctionleave3info-method.md) para recuperar el marco de pila y el valor devuelto.  
  
 [FunctionTailcall3 (Función)](functiontailcall3-function.md)  
 Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función.  
  
 [FunctionTailcall3WithInfo (Función)](functiontailcall3withinfo-function.md)  
 Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función y proporciona un identificador que se puede pasar a [ICorProfilerInfo3:: GetFunctionTailcall3Info (](icorprofilerinfo3-getfunctiontailcall3info-method.md) para recuperar el marco de pila.  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Información general sobre la generación de perfiles](profiling-overview.md)  
  
 [Interfaces para generación de perfiles](profiling-interfaces.md)  
  
 [Enumeraciones para generación de perfiles](profiling-enumerations.md)  
  
 [Estructuras para generación de perfiles](profiling-structures.md)
