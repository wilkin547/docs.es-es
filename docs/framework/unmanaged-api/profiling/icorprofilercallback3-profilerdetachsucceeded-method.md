---
title: "ICorProfilerCallback3::ProfilerDetachSucceeded (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback3.ProfilerDetachSucceeded Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerDetachSucceeded
helpviewer_keywords:
- ProfilerDetachSucceeded method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerDetachSucceeded method [.NET Framework profiling]
ms.assetid: 05164966-16ce-4cc9-a530-43a640c00711
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d06671917094752287836800ebc492d5f0a5b595
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback3profilerdetachsucceeded-method"></a>ICorProfilerCallback3::ProfilerDetachSucceeded (Método)
Notifica al generador de perfiles que Common Language Runtime (CLR) está a punto de descargar el archivo DLL del generador de perfiles.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ProfilerDetachSucceeded();  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Se omite el valor devuelto por esta devolución de llamada.  
  
## <a name="remarks"></a>Comentarios  
 La devolución de llamada `ProfilerDetachSucceeded` se emite después de que todos los subprocesos han salido del código del generador de perfiles. Cuando se llama a este método, el generador de perfiles debe realizar tareas de última hora que no son adecuadas para su destructor, tales como notificar a su interfaz de usuario o registrar componentes. Sin embargo, el generador de perfiles no debe llamar a funciones en las interfaces que se proporcionan con el CLR durante esta devolución de llamada (como el [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) o `IMetaData*` interfaces).  
  
 El CLR crea una entrada en el registro de eventos de aplicación de Windows para indicar que la operación de desasociación ha sido correcta.  
  
 Después de que el generador de perfiles vuelva de esta devolución de llamada, el CLR libera el objeto de generador de perfiles y descarga el archivo DLL del generador de perfiles. Por lo tanto, el generador de perfiles no debe realizar acciones que puedan hacer que la ejecución se realice dentro del archivo DLL del generador de perfiles después de que vuelva de esta devolución de llamada. Por ejemplo, no debe crear subprocesos ni registrar devoluciones de llamada de temporizador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [ICorProfilerInfo3 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
