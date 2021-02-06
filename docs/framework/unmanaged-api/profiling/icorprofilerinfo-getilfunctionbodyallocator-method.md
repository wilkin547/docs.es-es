---
description: 'Más información acerca de: ICorProfilerInfo:: Getilfunctionbodyallocator ((método)'
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
ms.openlocfilehash: 25d059d784fe64231d4d2ff3d23b4820443873cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647432"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a>ICorProfilerInfo::GetILFunctionBodyAllocator (Método)

Obtiene una interfaz que proporciona un método para asignar la memoria que se va a usar para intercambiar el cuerpo de un método en el código del lenguaje intermedio de Microsoft (MSIL).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a>Parámetros  

 `moduleId`  
 de IDENTIFICADOR del módulo en el que reside el método.  
  
 `ppMalloc`  
 enuncia Puntero a una interfaz [IMethodMalloc](imethodmalloc-interface.md) que proporciona un método para asignar la memoria.  
  
## <a name="remarks"></a>Observaciones  

 Un cuerpo de método en código MSIL debe estar ubicado como una dirección virtual relativa (RVA), relativa al módulo cargado, lo que significa que sigue el módulo en un plazo de 4 GB. Para facilitar a una herramienta el intercambio del cuerpo de un método, el `GetILFunctionBodyAllocator` método garantiza que la memoria se asigna dentro de ese intervalo.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
