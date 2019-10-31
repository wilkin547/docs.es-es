---
title: ICorDebugHeapValue3::GetThreadOwningMonitorLock (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type:
- apiref
ms.openlocfilehash: ec265525d01dab0669939569501fce91b500a900
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127490"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a>ICorDebugHeapValue3::GetThreadOwningMonitorLock (Método)
Devuelve el subproceso administrado que posee el bloqueo de monitor en este objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppThread`  
 enuncia Subproceso administrado que posee el bloqueo de monitor en este objeto.  
  
 `pAcquisitionCount`  
 enuncia Número de veces que este subproceso tendría que liberar el bloqueo antes de que vuelva a ser propiedad.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|S_FALSE|Ningún subproceso administrado posee el bloqueo de monitor en este objeto.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Comentarios  
 Si un subproceso administrado posee el bloqueo de monitor en este objeto:  
  
- El método devuelve S_OK.  
  
- El objeto Thread es válido hasta que se cierra el subproceso.  
  
 Si ningún subproceso administrado posee el bloqueo de monitor en este objeto, `ppThread` y `pAcquisitionCount` no se modifican y el método devuelve S_FALSE.  
  
 Si `ppThread` o `pAcquisitionCount` no es un puntero válido, el resultado es indefinido.  
  
 Si se produce un error de modo que no se pueda determinar cuál es el propietario del subproceso, si existe, el bloqueo de monitor en este objeto, el método devuelve un valor HRESULT que indica un error.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
