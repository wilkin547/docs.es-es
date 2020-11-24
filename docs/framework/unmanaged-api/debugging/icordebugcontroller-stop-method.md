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
ms.openlocfilehash: 11cc6e4108a2064a8a9fcefa760bf3c3411d63fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679863"
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
 No se usa.  
  
## <a name="remarks"></a>Comentarios  

 `Stop` realiza una detención cooperativa en todos los subprocesos que ejecutan código administrado en el proceso. Durante una sesión de depuración solo administrada, los subprocesos no administrados pueden continuar ejecutándose (pero se bloquearán al intentar llamar al código administrado). Durante una sesión de depuración de interoperabilidad, los subprocesos no administrados también se detendrán. El `dwTimeoutIgnored` valor se omite actualmente y se trata como infinito (-1). Si se produce un error en la detención cooperativa debido a un interbloqueo, se suspenden todos los subprocesos y se devuelve E_TIMEOUT.  
  
> [!NOTE]
> `Stop` es el único método sincrónico de la API de depuración. Cuando `Stop` devuelve S_OK, el proceso se detiene. No se proporciona ninguna devolución de llamada para notificar a los agentes de escucha de la detención. El depurador debe llamar a [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) para permitir que se reanude el proceso.  
  
 El depurador mantiene un contador de detención. Cuando el contador llega a cero, se reanuda el controlador. Cada llamada a `Stop` o a cada devolución de llamada enviada incrementa el contador. Cada llamada a `ICorDebugController::Continue` disminuye el contador.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también
