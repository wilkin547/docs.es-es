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
ms.openlocfilehash: 66195ea9df4c8e9ce847b38f7d020a3bebffcd37
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865186"
---
# <a name="icorprofilercallback4rejiterror-method"></a>ICorProfilerCallback4::ReJITError (Método)
Notifica al generador de perfiles que el compilador Just-in-Time (JIT) encontró un error en el proceso de recompilación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a>Parameters  
 `moduleID`  
 de `ModuleID` en el que se realizó el intento de recompilación con errores.  
  
 `methodId`  
 de `MethodDef` del método en el que se realizó el intento de recompilación con errores.  
  
 `functionId`  
 de Instancia de la función que se va a compilar o marcar para volver a compilar. Este valor puede ser `NULL` si el error se produjo por cada método en lugar de por cada instancia (por ejemplo, si el generador de perfiles especificó un token de metadatos no válido para el método que se va a volver a compilar).  
  
 `hrStatus`  
 de HRESULT que indica la naturaleza del error. Vea la sección Estados HRESULTs para obtener una lista de valores.  
  
## <a name="return-value"></a>Valor devuelto  
 Los valores devueltos de esta devolución de llamada se pasan por alto.  
  
## <a name="status-hresults"></a>HRESULT de estado  
  
|HRESULT de la matriz de estados|Descripción|  
|--------------------------|-----------------|  
|E_INVALIDARG|El token de `moduleID` o `methodDef` es `NULL`.|  
|CORPROF_E_DATAINCOMPLETE|El módulo no está totalmente cargado aún o está en proceso de descarga.|  
|CORPROF_E_MODULE_IS_DYNAMIC|El módulo especificado se generó dinámicamente (por ejemplo, por `Reflection.Emit`) y, por lo tanto, este método no lo admite.|  
|CORPROF_E_FUNCTION_IS_COLLECTIBLE|Se crea una instancia del método en un ensamblado recopilable y, por tanto, no se puede volver a compilar. Tenga en cuenta que se pueden crear instancias de los tipos y funciones definidos en un contexto de reflexión no (por ejemplo, `List<MyCollectibleStruct>`) en un ensamblado recopilable.|  
|E_OUTOFMEMORY|El CLR se quedó sin memoria al intentar marcar el método especificado para la recompilación JIT.|  
|Otro|El sistema operativo devolvió un error fuera del control del CLR. Por ejemplo, si se produce un error en una llamada del sistema para cambiar la protección de acceso de una página de memoria, se muestra el error del sistema operativo.|  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](icorprofilercallback-interface.md)
- [ICorProfilerCallback4 (interfaz)](icorprofilercallback4-interface.md)
