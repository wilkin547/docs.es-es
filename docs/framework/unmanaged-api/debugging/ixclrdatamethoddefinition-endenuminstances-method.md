---
title: 'IXCLRDataMethodDefinition:: EndEnumInstances (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EndEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 605a4244d20ef6c0b7af3c2b26b65ff2a63fa9dd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790456"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a>IXCLRDataMethodDefinition:: EndEnumInstances (método)

Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de la instancia.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a>Parameters

`handle`\
enuncia Identificador para enumerar las instancias de.

## <a name="remarks"></a>Notas

El método proporcionado forma parte de la interfaz `IXCLRDataMethodDefinition` y corresponde a la quinta ranura de la tabla del método virtual.

## <a name="requirements"></a>Requisitos de

**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado:** Ninguna  
**Biblioteca:** Ninguna  
**.NET Framework versiones:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaz IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)
