---
title: ICorProfilerCallback4::ReJITError (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b77dcbb1acffe47524aee3cd7761e342175dcd34
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733703"
---
# <a name="icorprofilercallback4rejiterror-method"></a>ICorProfilerCallback4::ReJITError (Método)
Notifica al generador de perfiles que el compilador de just-in-time (JIT) detectó un error en el proceso de recompilación.  
  
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
 [in] El `ModuleID` en que se realizara el intento de volver a compilar con errores.  
  
 `methodId`  
 [in] El `MethodDef` del método en el que se ha intentado la recompilación con errores.  
  
 `functionId`  
 [in] La instancia de la función que se ha vuelto a compilar o está marcado para volver a compilar. Este valor puede ser `NULL` si se produjo el error según el método en lugar de una base de cada instancia (por ejemplo, si el generador de perfiles especifica un token de metadatos no válidos para el método que se vuelva a compilar).  
  
 `hrStatus`  
 [in] Un HRESULT que indica la naturaleza del error. Consulte la sección de valores HRESULT de estado para obtener una lista de valores.  
  
## <a name="return-value"></a>Valor devuelto  
 Los valores devueltos de esta devolución de llamada se pasan por alto.  
  
## <a name="status-hresults"></a>HRESULT de estado  
  
|HRESULT de la matriz de estados|Descripción|  
|--------------------------|-----------------|  
|E_INVALIDARG|El `moduleID` o `methodDef` token es `NULL`.|  
|CORPROF_E_DATAINCOMPLETE|El módulo no está totalmente cargado aún o está en proceso de descarga.|  
|CORPROF_E_MODULE_IS_DYNAMIC|El módulo especificado se genera dinámicamente (por ejemplo, si `Reflection.Emit`) y, por tanto, no se admite este método.|  
|CORPROF_E_FUNCTION_IS_COLLECTIBLE|El método se crea una instancia en un ensamblado recopilable y, por lo tanto, no puede volver a compilar. Tenga en cuenta que los tipos y funciones definidas en un contexto no reflexión (por ejemplo, `List<MyCollectibleStruct>`) se pueden crear instancias en un ensamblado recopilable.|  
|E_OUTOFMEMORY|El CLR se quedó sin memoria al intentar marcar el método especificado para la recompilación con JIT.|  
|Otros|El sistema operativo devolvió un error fuera del control del CLR. Por ejemplo, si se produce un error en una llamada del sistema para cambiar la protección de acceso de una página de memoria, se muestra el error del sistema operativo.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback4 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
