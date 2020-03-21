---
title: ICorDebugProcess4::ProcessStateChanged Método
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: a6f36f5b86b4fa58ce2a4ef4aa23d527f797a5a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178628"
---
# <a name="icordebugprocess4processstatechanged-method"></a>ICorDebugProcess4::ProcessStateChanged Método

Notifica a la canalización ICorDebug que el depurador fuera de proceso continúa la ejecución del depurador.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a>Parámetros

 `eChange`\
[en] Miembro de la [corDebugStateChange enumeración](cordebugstatechange-enumeration.md) que describe un cambio en el estado de ejecución del proceso.

## <a name="remarks"></a>Observaciones

El método proporcionado forma `ICorDebugProcess4` parte de la interfaz y corresponde a la cuarta ranura de la tabla de métodos virtuales.

## <a name="requirements"></a>Requisitos

 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).

 **Encabezado:** Ninguno

 **Biblioteca:** Ninguno

 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugProcess4](icordebugprocess4-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
- [Depuración](index.md)
