---
title: ICorDebugProcess4::P método rocessStateChanged
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
ms.openlocfilehash: 910c411d2c63ce2c6cf262e28e08546657dc2a4c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213574"
---
# <a name="icordebugprocess4processstatechanged-method"></a>ICorDebugProcess4::P método rocessStateChanged

Notifica a la canalización ICorDebug que el depurador fuera de proceso está continuando la ejecución del depurador.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a>Parámetros

 `eChange`\
de Miembro de la [enumeración CorDebugStateChange](cordebugstatechange-enumeration.md) que describe un cambio en el estado de ejecución del proceso.

## <a name="remarks"></a>Observaciones

El método proporcionado forma parte de la `ICorDebugProcess4` interfaz y corresponde a la cuarta ranura de la tabla del método virtual.

## <a name="requirements"></a>Requisitos

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

 **Encabezado:** Ninguna

 **Biblioteca:** Ninguna

 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugProcess4](icordebugprocess4-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
