---
title: ICorProfilerFunctionControl::SetILFunctionBody (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type:
- apiref
ms.openlocfilehash: f6e2cfe47bdd212e39549544b06bf5b11033a956
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429888"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a>ICorProfilerFunctionControl::SetILFunctionBody (Método)
Reemplaza el cuerpo del Lenguaje intermedio común (CIL) del método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cbNewILMethodHeader`  
 [in] El tamaño total del nuevo CIL, incluido el encabezado y cualquier estructura que venga después del cuerpo.  
  
 `pbNewILMethodHeader`  
 [in] Puntero al nuevo encabezado de CIL.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT concretos.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El reemplazo se ha realizado correctamente.|  
  
## <a name="remarks"></a>Comentarios  
 Unlike the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body. This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface or allocated within a particular range. sino que se puede asignar en cualquier montón. The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerFunctionControl (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
