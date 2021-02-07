---
description: 'Más información acerca de: ICorDebugProcess4::P rocessStateChanged (método)'
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
ms.openlocfilehash: 35a76b3c6dd9b37d3f06f23bc2ffea82f125a29e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746482"
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

## <a name="see-also"></a>Vea también

- [Interfaz ICorDebugProcess4](icordebugprocess4-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
