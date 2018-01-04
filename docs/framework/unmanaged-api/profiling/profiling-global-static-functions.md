---
title: "Funciones estáticas globales para generación de perfiles"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 66f22557dd6020ff5040d5aaf76cb12e9ae9965c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="profiling-global-static-functions"></a>Funciones estáticas globales para generación de perfiles
Esta sección describen las funciones de API no administradas que utiliza la API de generación de perfiles.  
  
## <a name="in-this-section"></a>En esta sección  
  
## <a name="net-framework-version-1-profiling-functions"></a>Funciones de generación de perfiles de .NET framework versión 1  
 [FunctionEnter (Función)](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)  
 Notifica al generador de perfiles que se pasan a una función de control. En desuso en .NET Framework 2.0.  
  
 [FunctionLeave (Función)](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)  
 Notifica al generador de perfiles que una función está a punto de devolver al llamador. En desuso en .NET Framework 2.0.  
  
 [FunctionTailcall (Función)](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md)  
 Notifica al generador de perfiles que la función en ejecución está a punto de realizar una llamada de cola a otra función. En desuso en .NET Framework 2.0.  
  
## <a name="net-framework-version-2-profiling-functions"></a>Funciones de generación de perfiles de .NET framework versión 2  
 [FunctionIDMapper (Función)](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)  
 Notifica al generador de perfiles que el identificador especificado de una función puede reasignarse a otro identificador que se usará en el [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), y [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) devoluciones de llamada de esa función. También permite al generador de perfiles indicar si desea recibir devoluciones de llamada para esa función  
  
 [FunctionEnter2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 Notifica al generador de perfiles que el control se pasa a una función y proporciona información sobre la pila de argumentos de marco y la función. En desuso en el [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [FunctionLeave2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 Notifica al generador de perfiles que una función se va a devolver al llamador y proporciona información sobre el valor de retorno de marco y la función de pila. En desuso en el [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [FunctionTailcall2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 Notifica al generador de perfiles que la función en ejecución está a punto de realizar una llamada de cola a otra función y proporciona información sobre el marco de pila. En desuso en el [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StackSnapshotCallback (Función)](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)  
 Proporciona el generador de perfiles con información sobre cada marco administrado y cada ejecución de marcos no administrados en la pila durante un recorrido de pila, que se inicia mediante la [ICorProfilerInfo2:: DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) método.  
  
## <a name="net-framework-version-4-profiling-functions"></a>Funciones de generación de perfiles de .NET framework versión 4  
 [FunctionIDMapper2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 Notifica al generador de perfiles que el identificador especificado de una función puede reasignarse a otro identificador que se usará en el [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), y [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), o[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), y [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) devoluciones de llamada de esa función. También permite al generador de perfiles indicar si desea recibir devoluciones de llamada para esa función.  
  
 `FunctionIDMapper2`extiende la [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) funcionando con un `clientData` parámetro, que los generadores de perfiles pueden usar para eliminar la ambigüedad entre los Runtime.  
  
 [FunctionEnter3 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 Notifica al generador de perfiles que se pasan a una función de control.  
  
 [FunctionEnter3WithInfo (Función)](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 Notifica al generador de perfiles que se pasan a una función de control y proporciona un identificador que puede pasarse a [ICorProfilerInfo3:: Getfunctionenter3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) para recuperar los argumentos de marco y la función de la pila.  
  
 [FunctionLeave3 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 Notifica al generador de perfiles que se devuelve de una función de control.  
  
 [FunctionLeave3WithInfo (Función)](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 Notifica al generador de perfiles que se devuelve de una función de control y proporciona un identificador que puede pasarse a [ICorProfilerInfo3:: Getfunctionleave3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) para recuperar el marco de pila y el valor devuelto.  
  
 [FunctionTailcall3 (Función)](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 Notifica al generador de perfiles que la función en ejecución está a punto de realizar una llamada de cola a otra función.  
  
 [FunctionTailcall3WithInfo (Función)](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 Notifica al generador de perfiles que la función en ejecución está a punto de realizar una llamada de cola a otra función y proporciona un identificador que puede pasarse a [ICorProfilerInfo3:: Getfunctiontailcall3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) para recuperar el marco de pila.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Información general sobre la generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [Enumeraciones para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [Estructuras para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
