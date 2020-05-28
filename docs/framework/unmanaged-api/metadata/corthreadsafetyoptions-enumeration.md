---
title: CorThreadSafetyOptions (Enumeración)
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
ms.openlocfilehash: 8c0527a7bc3cde7344bf809dc8e6f5a3fac04852
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007512"
---
# <a name="corthreadsafetyoptions-enumeration"></a>CorThreadSafetyOptions (Enumeración)

Especifica marcas para seleccionar opciones de seguridad para subprocesos.

## <a name="syntax"></a>Sintaxis

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a>Miembros

|Miembro|Descripción|
|------------|-----------------|
|`MDThreadSafetyDefault`|Valor predeterminado. Igual a `MDThreadSafetyOff`.|
|`MDThreadSafetyOff`|Indica que no se puede establecer un bloqueo de lector/escritor.|
|`MDThreadSafetyOn`|Indica que se puede establecer un bloqueo de lectura/escritura.|

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorHdr. h

**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](metadata-enumerations.md)
