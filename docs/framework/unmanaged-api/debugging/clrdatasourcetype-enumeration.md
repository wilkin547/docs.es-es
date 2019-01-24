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
ms.openlocfilehash: c8b3f338659e2784db8deca3e1776e7926c30c32
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506089"
---
# <a name="clrdatasourcetype-enumeration"></a>Enumeración CLRDataSourceType

Proporciona valores que son usados por la estructura CLRDATA_IL_ADDRESS_MAP.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a>Miembros

| Miembro                        | Descripción                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | Para indicar que se aplica nada más |

## <a name="remarks"></a>Comentarios

Esta enumeración reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Para ello, definir una enumeración definida anteriormente en el código. Esto también es un alias para `CLRDATA_ENUM` como se mencionó en [tipos de datos comunes](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado**: Ninguna  
**Biblioteca:** Ninguna  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
