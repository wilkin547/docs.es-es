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
ms.openlocfilehash: 3f6928832d822422177ebd7def142422953468a0
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274295"
---
# <a name="clrdata_il_address_map-structure"></a>Estructura CLRDATA_IL_ADDRESS_MAP

Define una asignación de IL a dirección.

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

## <a name="members"></a>Miembros

| Miembro         | Descripción                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | Desplazamiento IL para el intervalo de direcciones contenido              |
| `startAddress` | Dirección de inicio del intervalo.                        |
| `endAddress`   | Dirección final del intervalo.                          |
| `type`         | Tipo de los datos. Este valor no se usa actualmente |

## <a name="remarks"></a>Comentarios

Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Para usarlo, defina la estructura como se especificó anteriormente, `CLRDATA_ADDRESS` donde es un entero de 64 bits sin signo.

## <a name="requirements"></a>Requisitos

**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
**Encabezado**: Ninguna  
**Biblioteca** Ninguna   
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Enumeración CLRDataSourceType](clrdatasourcetype-enumeration.md)
- [Depuración](index.md)
- [Estructuras de depuración](debugging-structures.md)
