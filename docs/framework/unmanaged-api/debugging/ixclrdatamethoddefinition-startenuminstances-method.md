---
title: 'IXCLRDataMethodDefinition:: StartEnumInstances (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::StartEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: b0c37c666f23f04239ed827246b87c43ee8d5ad9
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420934"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a>IXCLRDataMethodDefinition:: StartEnumInstances (método)

Proporciona un identificador para la enumeración de instancias de método para un determinado `IXCLRDataAppDomain` .

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a>Parámetros

`appDomain`\
de AppDomain para la enumeración.

`handle`\
enuncia Identificador para enumerar las instancias de.

## <a name="remarks"></a>Observaciones

El método proporcionado forma parte de la `IXCLRDataMethodDefinition` interfaz y corresponde a la quinta ranura de la tabla del método virtual.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
**Encabezado:** Ninguna  
**Biblioteca:** Ninguna  
**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Consulta también

- [Enumeración CLRDataSourceType](clrdatasourcetype-enumeration.md)
- [Depuración](index.md)
- [Interfaz IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)
