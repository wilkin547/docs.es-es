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
ms.openlocfilehash: febe6766c7a35228820421eee975c777988efd1f
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396491"
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

## <a name="parameters"></a>Parámetros

`handle`\
enuncia Identificador para enumerar las instancias de.

## <a name="remarks"></a>Comentarios

El método proporcionado forma parte de la `IXCLRDataMethodDefinition` interfaz y corresponde a la séptima ranura de la tabla del método virtual.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado:** Ninguna  
**Biblioteca:** Ninguna  
**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaz IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)
