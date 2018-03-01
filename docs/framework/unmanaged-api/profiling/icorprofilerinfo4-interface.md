---
title: ICorProfilerInfo4 (Interfaz)
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
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 83629d0fc8288d118ec31c38473cb63335bb1d48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4-interface"></a>ICorProfilerInfo4 (Interfaz)
Proporciona métodos que los generadores de perfiles de código usan para comunicarse con el common language runtime (CLR) para controlar la supervisión de eventos y la información de la solicitud. . El `ICorProfilerInfo4` interfaz es una extensión de la otra `ICorProfilerInfo` interfaces. Proporciona nuevos métodos para admitir la nueva compilación just-in-time (JIT), agregado en el [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnumJITedFunctions2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|Devuelve un enumerador para todas las funciones que anteriormente estaban compilados JIT y recompilado con JIT.|  
|[EnumThreads (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|Obtiene un enumerador que proporciona métodos para iterar secuencialmente por la colección de todos los subprocesos administrados en el proceso perfilado.|  
|[GetCodeInfo3 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|Obtiene las extensiones de código nativo asociadas con la versión recompilada con JIT de la función especificada.|  
|[GetFunctionFromIP2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|Asigna un puntero de instrucción de código administrado a la versión recompilada con JIT de una función especificada.|  
|[GetILToNativeMapping2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|Obtiene una asignación de desplazamientos del lenguaje intermedio (MSIL) a los desplazamientos nativos para el código incluido en la versión recompilada con JIT de la función especificada de Microsoft.|  
|[GetObjectSize2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|Devuelve el tamaño de un objeto especificado.|  
|[GetReJITIDs (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|Devuelve una matriz de identificadores que identifican todas las recompilado con JIT versiones de la función especificada que todavía se asignarán.|  
|[InitializeCurrentThread (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|Inicializa el subproceso actual antes de generador de perfiles posterior llamadas de API en el mismo subproceso, por lo que se puede evitar que un interbloqueo.|  
|[RequestReJIT (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|Solicita una recompilación con JIT de todas las instancias de las funciones especificadas.|  
|[RequestRevert (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|Revierte todas las instancias de las funciones especificadas a sus versiones originales.|  
  
## <a name="remarks"></a>Comentarios  
 El CLR implementa los métodos de la interfaz `ICorProfilerInfo4` usando el modelo de subprocesamiento libre. Cada método devuelve un valor HRESULT para indicar un resultado correcto o erróneo. Para obtener una lista de los posibles códigos devueltos, consulte el archivo CorError.h.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
