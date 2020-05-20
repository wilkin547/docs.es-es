---
title: 'IXCLRDataMethodDefinition:: EnumInstance (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ae1ef2a3c8cf9e042ab9ab233ed993f8e36b2fce
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420947"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a>IXCLRDataMethodDefinition:: EnumInstance (método)

Enumera las instancias de esta definición de método.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a>Parámetros

`handle`\
[in, out] Identificador para enumerar las instancias de.

`instance`\
enuncia Instancia enumerada.

## <a name="remarks"></a>Observaciones

El método proporcionado forma parte de la `IXCLRDataMethodDefinition` interfaz y corresponde a la sexta ranura de la tabla del método virtual.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
**Encabezado:** Ninguna  
**Biblioteca:** Ninguna  
**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Consulta también

- [Enumeración CLRDataSourceType](clrdatasourcetype-enumeration.md)
- [Depuración](index.md)
- [Interfaz IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)
- [Interfaz IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)
