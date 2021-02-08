---
description: 'Más información sobre: ICorDebugThread4:: Getcurrentcustomdebuggernotification ((método)'
title: ICorDebugThread4::GetCurrentCustomDebuggerNotification (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetCurrentCustomDebuggerNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetCurrentCustomDebuggerNotification
helpviewer_keywords:
- GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
- ICorDebugThread4::GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
ms.assetid: 57e0f2d2-5f0e-4e2d-99ec-3f26632eb693
topic_type:
- apiref
ms.openlocfilehash: 20d9449e98b9ab91dbdec84ba026e91514d5b3cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800947"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a>ICorDebugThread4::GetCurrentCustomDebuggerNotification (Método)

Obtiene el objeto [ICorDebugManagedCallback3 (:: customnotification (](icordebugmanagedcallback3-customnotification-method.md) actual en el subproceso actual.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a>Parámetros

`ppNotificationObject`\
enuncia Puntero al `ICorDebugManagedCallback3::CustomNotification` objeto actual en el subproceso actual.

## <a name="remarks"></a>Observaciones

El valor de `ppNotificationObject` es NULL si no se llama al método desde una `ICorDebugManagedCallback3::CustomNotification` devolución de llamada o si no existe ningún objeto de notificación actual.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a>Vea también

- [ICorDebugThread4 (Interfaz)](icordebugthread4-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
