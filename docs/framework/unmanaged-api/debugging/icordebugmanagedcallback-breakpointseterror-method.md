---
title: ICorDebugManagedCallback::BreakpointSetError (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.BreakpointSetError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::BreakpointSetError
helpviewer_keywords:
- BreakpointSetError method [.NET Framework debugging]
- ICorDebugManagedCallback::BreakpointSetError method [.NET Framework debugging]
ms.assetid: f2b773a4-c4d0-429c-9717-51d6e2ed86af
topic_type:
- apiref
ms.openlocfilehash: cac8393408de626efe2360999e259780eac29f38
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721340"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a>ICorDebugManagedCallback::BreakpointSetError (Método)

Notifica al depurador que el Common Language Runtime no pudo enlazar con precisión un punto de interrupción establecido antes de que una función se compilara Just-in-Time (JIT).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pAppDomain`  
 de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el punto de interrupción sin enlazar.  
  
 `pThread`  
 de Un puntero a un objeto ICorDebugThread que representa el subproceso que contiene el punto de interrupción sin enlazar.  
  
 `pBreakpoint`  
 de Un puntero a un objeto ICorDebugBreakpoint que representa el punto de interrupción sin enlazar.  
  
 `dwError`  
 de Entero que indica el error.  
  
## <a name="remarks"></a>Comentarios  

 Nunca se alcanzará el punto de interrupción dado. El depurador debe desactivarlo y volver a enlazarlo.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugManagedCallback (Interfaz)](icordebugmanagedcallback-interface.md)
