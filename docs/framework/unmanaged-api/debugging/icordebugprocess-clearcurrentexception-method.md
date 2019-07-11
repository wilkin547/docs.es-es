---
title: ICorDebugProcess::ClearCurrentException (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ClearCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ad7dd3ae0e547933fdf7d579116dccc62ae579c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766149"
---
# <a name="icordebugprocessclearcurrentexception-method"></a>ICorDebugProcess::ClearCurrentException (Método)
Borra la excepción no administrada actual del subproceso especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a>Parámetros  
 `threadID`  
 [in] El identificador del subproceso en el que se borrará la excepción no administrada actual.  
  
## <a name="remarks"></a>Comentarios  
 Llame a este método antes de llamar a [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) cuando un subproceso ha notificado una excepción no administrada que se debe omitir el depurador. Esto borrará los eventos de fuera de banda (OOB) en el subproceso y pendientes en banda (IB). Se borran automáticamente todos los puntos de interrupción OOB y excepciones de paso a paso.  
  
 Use [Icordebugthread2](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) interceptar actual excepción en un subproceso administrado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
