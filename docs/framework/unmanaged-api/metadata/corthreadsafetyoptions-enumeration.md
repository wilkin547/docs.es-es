---
description: 'Más información sobre: enumeración Corthreadsafetyoptions ('
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
ms.openlocfilehash: 7915bcf5e7b71fa84ea83642467c1600cd38712d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707324"
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

## <a name="members"></a>Members

|Miembro|Descripción|
|------------|-----------------|
|`MDThreadSafetyDefault`|Valor predeterminado. Igual a `MDThreadSafetyOff`.|
|`MDThreadSafetyOff`|Indica que no se puede establecer un bloqueo de lector/escritor.|
|`MDThreadSafetyOn`|Indica que se puede establecer un bloqueo de lectura/escritura.|

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorHdr. h

**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](metadata-enumerations.md)
