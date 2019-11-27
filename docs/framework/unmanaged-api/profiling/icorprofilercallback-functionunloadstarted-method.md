---
title: ICorProfilerCallback::FunctionUnloadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.FunctionUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type:
- apiref
ms.openlocfilehash: f57a3ed70267de65daed85305ad7d623b4ca0337
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448020"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a>ICorProfilerCallback::FunctionUnloadStarted (Método)
Notifica al generador de perfiles que el tiempo de ejecución ha empezado a descargar una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
## <a name="parameters"></a>Parámetros  
 `functionId`  
 de IDENTIFICADOR de la función que se está descargando.  
  
## <a name="remarks"></a>Comentarios  
 El valor del parámetro `functionId` ya no es válido después de que este método vuelva al autor de la llamada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
