---
title: ICorDebugMDA::GetOSThreadId (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetOSThreadId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type:
- apiref
ms.openlocfilehash: c7ab77e9316023a97d2eafe8bcccc2b45e240cd0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207826"
---
# <a name="icordebugmdagetosthreadid-method"></a>ICorDebugMDA::GetOSThreadId (Método)
Obtiene el identificador del subproceso del sistema operativo (SO) en el que se ejecuta el Asistente para la depuración administrada (MDA) representado por [ICorDebugMDA](icordebugmda-interface.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pOsTid`  
 enuncia Puntero al identificador del subproceso del sistema operativo.  
  
## <a name="remarks"></a>Observaciones  
 El subproceso del sistema operativo se usa en lugar de una expresión ICorDebugThread para permitir situaciones en las que se desencadena un MDA en un subproceso nativo o en un subproceso administrado que todavía no ha entrado en código administrado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugMDA (Interfaz)](icordebugmda-interface.md)
- [Diagnóstico de errores con asistentes de depuraciones administradas](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
