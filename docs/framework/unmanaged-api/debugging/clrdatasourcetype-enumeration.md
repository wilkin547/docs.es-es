---
title: Enumeración CLRDataSourceType
ms.date: 01/16/2019
api.name:
- CLRDataSourceType Enumeration
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDataSourceType Enumeration
helpviewer.keywords:
- CLRDataSourceType Enumeration [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7ace405e2624f15b1cdb6d383222ae87c93289bb
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274095"
---
# <a name="clrdatasourcetype-enumeration"></a>Enumeración CLRDataSourceType

Proporciona valores que se usan en la estructura CLRDATA_IL_ADDRESS_MAP.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```cpp
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a>Miembros

| Miembro                        | Descripción                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | Para indicar que no se aplica nada más |

## <a name="remarks"></a>Comentarios

Esta enumeración reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Para usarlo, defina una enumeración tal y como se definió anteriormente en el código. También se puede aplicar un alias `CLRDATA_ENUM` a como se mencionó en [tipos de datos comunes](../common-data-types-unmanaged-api-reference.md).

## <a name="requirements"></a>Requisitos

**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
**Encabezado**: Ninguna  
**Biblioteca** Ninguna  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Enumeraciones de depuración](debugging-enumerations.md)
