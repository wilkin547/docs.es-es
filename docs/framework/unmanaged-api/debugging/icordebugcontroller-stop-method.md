---
title: "ICorDebugController::Stop (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.Stop
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4b92d07f8d162123d20c6861d204d73789060906
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollerstop-method"></a>ICorDebugController::Stop (Método)
Realiza una detención cooperativa en todos los subprocesos que ejecutan código administrado en el proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `dwTimeoutIgnored`  
 No usado.  
  
## <a name="remarks"></a>Comentarios  
 `Stop`realiza un código de detención cooperativa en todos los subprocesos en ejecución administrada en el proceso. Durante una sesión de depuración solo administrado, pueden continuar ejecutándose los subprocesos no administrados (pero se bloqueará al intentar llamar al código administrado). Durante una sesión de depuración de interoperabilidad, también se detendrá los subprocesos no administrados. El `dwTimeoutIgnored` valor actualmente se omite y se trata como infinito (-1). Si se produce un error en la detención cooperativa debido a un interbloqueo, se suspenden todos los subprocesos y se devuelve E_TIMEOUT.  
  
> [!NOTE]
>  `Stop`es el único método sincrónico de la API de depuración. Cuando `Stop` devuelve S_OK, el proceso se detiene. No se proporciona ninguna devolución de llamada para notificar a los agentes de escucha de la detención. El depurador debe llamar a [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) para permitir que se reanude el proceso.  
  
 El depurador mantiene un contador de detención. Cuando el contador llega a cero, se reanuda el controlador. Cada llamada a `Stop` o cada devolución de llamada enviada incrementa el contador. Cada llamada a `ICorDebugController::Continue` disminuye el contador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 
