---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 676489880cb30ca540cb78d70797dbf4eedf7395
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739585"
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

## <a name="members"></a>Miembros

| Member            | DESCRIPCIÓN                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | El proceso alcanzó un nuevo estado de memoria por ejecución directa.            |
| `FLUSH_ALL`       | La memoria del proceso puede ser diferente de forma arbitraria de lo que era anteriormente. |

## <a name="remarks"></a>Comentarios

 Un miembro de la `CorDebugStateChange` enumeración se proporciona como un argumento cuando el depurador llama a la `ProcessStateChanged` método con [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) o [ICorDebugProcess6:: ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)

## <a name="requirements"></a>Requisitos

 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

 **Encabezado**: CorDebug.idl, CorDebug.h

 **Biblioteca:** CorGuids.lib

 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
- [Depuración](index.md)
