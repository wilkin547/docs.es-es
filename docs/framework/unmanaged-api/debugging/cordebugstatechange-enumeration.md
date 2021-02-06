---
description: 'Más información sobre: enumeración CorDebugStateChange'
title: Enumeración CorDebugStateChange
ms.date: 02/07/2019
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
ms.openlocfilehash: 1900baa77432daa10d0f1a32dd9cb25198b86ed1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661823"
---
# <a name="cordebugstatechange-enumeration"></a>Enumeración CorDebugStateChange

Describe la cantidad de datos almacenados en caché que se debe descartar según los cambios en el proceso.

## <a name="syntax"></a>Sintaxis

```cpp
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a>Members

| Miembro            | Descripción                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | El proceso alcanzó un nuevo estado de memoria por ejecución directa.            |
| `FLUSH_ALL`       | La memoria del proceso puede ser diferente de forma arbitraria de lo que era anteriormente. |

## <a name="remarks"></a>Observaciones

 Un miembro de la `CorDebugStateChange` enumeración se proporciona como argumento cuando el depurador llama al `ProcessStateChanged` método con [ICorDebugProcess4::P rocessstatechanged](icordebugprocess4-processstatechanged-method.md) o [método icordebugprocess6::P rocessstatechanged](icordebugprocess6-processstatechanged-method.md)

## <a name="requirements"></a>Requisitos

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

 **Encabezado:** CorDebug.idl, CorDebug.h

 **Biblioteca:** CorGuids.lib

 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
- [Depuración](index.md)
