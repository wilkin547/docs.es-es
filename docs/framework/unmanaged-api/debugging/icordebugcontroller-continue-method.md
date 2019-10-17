---
title: ICorDebugController::Continue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugController.Continue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62e2be44165472e2fbf368f61b865d39a5e9fc28
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395464"
---
# <a name="icordebugcontrollercontinue-method"></a>ICorDebugController::Continue (Método)

Reanuda la ejecución de subprocesos administrados después de una llamada al [método STOP](icordebugcontroller-stop-method.md).

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT Continue (
    [in] BOOL fIsOutOfBand
);
```

## <a name="parameters"></a>Parámetros

`fIsOutOfBand`  
de Establézcalo en `true` si continúa desde un evento fuera de banda; de lo contrario, establézcalo en `false`.

## <a name="remarks"></a>Comentarios

`Continue` continúa el proceso después de una llamada al método `ICorDebugController::Stop`.

Al realizar la depuración en modo mixto, no llame a `Continue` en el subproceso de eventos Win32 a menos que vaya a continuación de un evento fuera de banda.

Un *evento en banda* es un evento administrado o un evento no administrado normal durante el cual el depurador admite la interacción con el estado administrado del proceso. En este caso, el depurador recibe la devolución de llamada [ICorDebugUnmanagedCallback (::D ebugevent](icordebugunmanagedcallback-debugevent-method.md) con su parámetro `fOutOfBand` establecido en `false`.

Un *evento fuera de banda* es un evento no administrado durante el cual no es posible la interacción con el estado administrado del proceso mientras se detiene el proceso debido al evento. En este caso, el depurador recibe la devolución de llamada `ICorDebugUnmanagedCallback::DebugEvent` con su parámetro `fOutOfBand` establecido en `true`.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado:** CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
