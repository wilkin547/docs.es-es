---
title: "ICorProfilerFunctionControl::SetILFunctionBody (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionControl.SetILFunctionBody
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9469435186a5aef130ca4ebef27a4613afeb921c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerFunctionControl (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
