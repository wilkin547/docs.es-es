---
title: ICorDebugController::Stop (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
ms.openlocfilehash: c8c6b40f7a9c63a577140209eed65436040addcb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125386"
---
# <a name="icordebugcontrollerstop-method"></a>ICorDebugController::Stop (Método)
Realiza una detención cooperativa en todos los subprocesos que ejecutan código administrado en el proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwTimeoutIgnored`  
 No se utiliza.  
  
## <a name="remarks"></a>Comentarios  
 `Stop` realiza una detención cooperativa en todos los subprocesos que ejecutan código administrado en el proceso. Durante una sesión de depuración solo administrada, los subprocesos no administrados pueden continuar ejecutándose (pero se bloquearán al intentar llamar al código administrado). Durante una sesión de depuración de interoperabilidad, los subprocesos no administrados también se detendrán. Actualmente, el valor `dwTimeoutIgnored` se omite y se trata como infinito (-1). Si se produce un error en la detención cooperativa debido a un interbloqueo, se suspenden todos los subprocesos y se devuelve E_TIMEOUT.  
  
> [!NOTE]
> `Stop` es el único método sincrónico de la API de depuración. Cuando `Stop` Devuelve S_OK, el proceso se detiene. No se proporciona ninguna devolución de llamada para notificar a los agentes de escucha de la detención. El depurador debe llamar a [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) para permitir que se reanude el proceso.  
  
 El depurador mantiene un contador de detención. Cuando el contador llega a cero, se reanuda el controlador. Cada llamada a `Stop` o cada devolución de llamada enviada incrementa el contador. Cada llamada a `ICorDebugController::Continue` disminuye el contador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
