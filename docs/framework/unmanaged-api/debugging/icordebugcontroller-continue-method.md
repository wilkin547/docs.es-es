---
title: "ICorDebugController::Continue (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.Continue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 93fc138b8610d252be5c3ca3821bb1d41c5ac6ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollercontinue-method"></a>ICorDebugController::Continue (Método)
Reanuda la ejecución de subprocesos administrados después de llamar a [método Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `fIsOutOfBand`  
 [in] Establecido en `true` si continuar desde un evento fuera de banda; de lo contrario, establézcalo en `false`.  
  
## <a name="remarks"></a>Comentarios  
 `Continue`Continúe con el proceso después de llamar a la `ICorDebugController::Stop` método.  
  
 Cuando se realiza la depuración en modo mixto, no llame a `Continue` en Win32 evento subproceso a menos que se están realizando desde un evento fuera de banda.  
  
 Un *en banda eventos* es un evento administrado o un evento no administrado normal durante el cual el depurador admite la interacción con el estado administrado del proceso. En este caso, el depurador recibe la [ICorDebugUnmanagedCallback:: DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) devolución de llamada con su `fOutOfBand` parámetro establecido en `false`.  
  
 Un *evento fuera de banda* es un evento no administrado durante el cual la interacción con el estado administrado del proceso es imposible mientras el proceso se detiene debido al evento. En este caso, el depurador recibe la `ICorDebugUnmanagedCallback::DebugEvent` devolución de llamada con su `fOutOfBand` parámetro establecido en `true`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 
