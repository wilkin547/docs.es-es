---
title: "ICorProfilerCallback4::ReJITError (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.ReJITError
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c746d0f7a6be96f95f1a051e22de0ad1bd2d2269
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4rejiterror-method"></a>ICorProfilerCallback4::ReJITError (Método)
Notifica al generador de perfiles que el compilador de just-in-time (JIT) encontró un error en el proceso de recompilación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `moduleID`  
 [in] El `ModuleID` en que se realizara el intento de volver a compilar errores.  
  
 `methodId`  
 [in] El `MethodDef` del método en el que se realizara el intento de volver a compilar errores.  
  
 `functionId`  
 [in] La instancia de la función que se ha vuelto a compilar o está marcado para volver a compilar. Este valor puede ser `NULL` si se produjo el error en una base por cada método en lugar de una base de cada instancia (por ejemplo, si el generador de perfiles especifica un token de metadatos no válidos para el método se vuelvan a compilar).  
  
 `hrStatus`  
 [in] Un valor HRESULT que indica la naturaleza del error. Vea la sección de valores HRESULT de estado para obtener una lista de valores.  
  
## <a name="return-value"></a>Valor devuelto  
 Los valores devueltos de esta devolución de llamada se pasan por alto.  
  
## <a name="status-hresults"></a>HRESULT de estado  
  
|HRESULT de la matriz de estados|Descripción|  
|--------------------------|-----------------|  
|E_INVALIDARG|El `moduleID` o `methodDef` token es `NULL`.|  
|CORPROF_E_DATAINCOMPLETE|El módulo no está totalmente cargado aún o está en proceso de descarga.|  
|CORPROF_E_MODULE_IS_DYNAMIC|El módulo especificado se genera dinámicamente (por ejemplo, `Reflection.Emit`) y, por tanto, no se admite este método.|  
|CORPROF_E_FUNCTION_IS_COLLECTIBLE|El método se crea una instancia en un ensamblado recopilable y, por lo tanto, no puede volver a compilar. Tenga en cuenta que los tipos y funciones definidas en un contexto de reflexión no (por ejemplo, `List<MyCollectibleStruct>`) se pueden crear instancias en un ensamblado recopilable.|  
|E_OUTOFMEMORY|El CLR se quedó sin memoria al intentar marcar el método especificado para la recompilación con JIT.|  
|Otros|El sistema operativo devolvió un error fuera del control del CLR. Por ejemplo, si se produce un error en una llamada del sistema para cambiar la protección de acceso de una página de memoria, se muestra el error del sistema operativo.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback4 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
