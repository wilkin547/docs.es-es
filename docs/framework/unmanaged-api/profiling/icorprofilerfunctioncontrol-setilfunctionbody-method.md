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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d5b6cab555144c25c5984d74d19d5e81aa1a196d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454973"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a>ICorProfilerFunctionControl::SetILFunctionBody (Método)
Reemplaza el cuerpo del Lenguaje intermedio común (CIL) del método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
#### <a name="parameters"></a>Parámetros  
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
 A diferencia de la [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) método, el `SetILFunctionBody` método administra la memoria necesaria para el nuevo cuerpo CIL. Esto significa que el cuerpo CIL proporcionado por el generador de perfiles no tiene que asignar mediante la [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interfaz o dentro de un intervalo determinado. sino que se puede asignar en cualquier montón. El generador de perfiles puede liberar la memoria utilizada para el cuerpo CIL después `SetILFunctionBody` devuelve.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerFunctionControl (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
