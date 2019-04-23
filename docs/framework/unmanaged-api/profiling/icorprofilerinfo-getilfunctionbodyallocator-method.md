---
title: ICorProfilerInfo::GetILFunctionBodyAllocator (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2cd66a895f99d62e8deaa45afab12d963aee2901
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109127"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a>ICorProfilerInfo::GetILFunctionBodyAllocator (Método)
Obtiene una interfaz que proporciona un método para asignar memoria que se usará para intercambiar el cuerpo de un método en el código de lenguaje intermedio (MSIL) de Microsoft.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a>Parámetros  
 `moduleId`  
 [in] El identificador del módulo en el que reside el método.  
  
 `ppMalloc`  
 [out] Un puntero a un [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interfaz que proporciona un método para asignar la memoria.  
  
## <a name="remarks"></a>Comentarios  
 Un cuerpo de método en código MSIL deben estar como una dirección virtual relativa (RVA), en relación con el módulo cargado, lo que significa que sigue el módulo dentro de 4 GB. Para que sea más fácil para una herramienta intercambiar el cuerpo de un método, el `GetILFunctionBodyAllocator` método garantiza que la memoria se asigna dentro de ese intervalo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
