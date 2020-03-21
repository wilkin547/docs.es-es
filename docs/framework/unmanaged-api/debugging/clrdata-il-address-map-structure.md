---
title: Estructura CLRDATA_IL_ADDRESS_MAP
ms.date: 01/16/2019
api.name:
- CLRDATA_IL_ADDRESS_MAP Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure
helpviewer.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e680a7a0dc3209d1988f6c84be0864572a74b3a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179375"
---
# <a name="clrdata_il_address_map-structure"></a>Estructura CLRDATA_IL_ADDRESS_MAP

Define una asignación de IL para direccionar.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a>Members

| Member         | Descripción                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | Desplazamiento de IL para el rango de direcciones contenido              |
| `startAddress` | La dirección de inicio del rango.                        |
| `endAddress`   | La dirección final del rango.                          |
| `type`         | Tipo de los datos. Este valor no se utiliza actualmente |

## <a name="remarks"></a>Observaciones

Esta estructura se encuentra dentro del tiempo de ejecución y no se expone a través de encabezados o archivos de biblioteca. Para usarlo, defina la estructura como `CLRDATA_ADDRESS` se especificó anteriormente, donde hay un entero sin signo de 64 bits.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
**Encabezado:** Ninguno  
**Biblioteca:** Ninguna versión de **.NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Consulte también

- [CLRDataSourceType (enumeración)](clrdatasourcetype-enumeration.md)
- [Depuración](index.md)
- [Estructuras de depuración](debugging-structures.md)
