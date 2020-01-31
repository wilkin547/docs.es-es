---
title: ICorProfilerFunctionControl::SetILFunctionBody (método)
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
ms.openlocfilehash: bebc0cf6ac7912ea3a6641e0c729b759e865dac3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864666"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a>ICorProfilerFunctionControl::SetILFunctionBody (método)
Reemplaza el cuerpo del Lenguaje intermedio común (CIL) del método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a>Parameters  
 `cbNewILMethodHeader`  
 [in] El tamaño total del nuevo CIL, incluido el encabezado y cualquier estructura que venga después del cuerpo.  
  
 `pbNewILMethodHeader`  
 [in] Puntero al nuevo encabezado de CIL.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT concretos.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El reemplazo se ha realizado correctamente.|  
  
## <a name="remarks"></a>Notas  
 A diferencia del método [ICorProfilerInfo:: SetILFunctionBody (](icorprofilerinfo-setilfunctionbody-method.md) , el método `SetILFunctionBody` administra la memoria necesaria para el nuevo cuerpo de CIL. Esto significa que no es necesario asignar el cuerpo de CIL proporcionado por el generador de perfiles utilizando la interfaz [IMethodMalloc](imethodmalloc-interface.md) o asignada dentro de un intervalo determinado. sino que se puede asignar en cualquier montón. El generador de perfiles puede liberar la memoria usada para su cuerpo de CIL después de que `SetILFunctionBody` devuelve.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerFunctionControl (interfaz)](icorprofilerfunctioncontrol-interface.md)
