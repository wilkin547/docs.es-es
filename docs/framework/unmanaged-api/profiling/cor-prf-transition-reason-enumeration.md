---
title: COR_PRF_TRANSITION_REASON (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_TRANSITION_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_TRANSITION_REASON
helpviewer_keywords:
- COR_PRF_TRANSITION_REASON enumeration [.NET Framework profiling]
ms.assetid: da941118-01b7-4197-ae5b-9f2f8adcd623
topic_type:
- apiref
ms.openlocfilehash: 6d8b408675127cde399a8346f2b9734a0e038cb5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427146"
---
# <a name="cor_prf_transition_reason-enumeration"></a>COR_PRF_TRANSITION_REASON (Enumeración)
Indica el motivo para una transición desde código administrado a no administrado, y o viceversa.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|La transición se debe a una llamada a una función.|  
|`COR_PRF_TRANSITION_RETURN`|La transición se debe a un valor devuelto de una función.|  
  
## <a name="remarks"></a>Comentarios  
 Cuando se produce una transición, el generador de perfiles recibe una devolución de llamada [ICorProfilerCallback:: ManagedToUnmanagedTransition (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) o [ICorProfilerCallback:: UnmanagedToManagedTransition (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) , que proporciona un valor de la enumeración `COR_PRF_TRANSITION_REASON` para indicar el motivo de la transición.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
