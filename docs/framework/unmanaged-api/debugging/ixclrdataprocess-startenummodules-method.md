---
description: 'Más información sobre: IXCLRDataProcess:: StartEnumModules (método)'
title: 'IXCLRDataProcess:: StartEnumModules (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 2e90c646ee8815ec10ce0bbd7538f13d7b5dcf8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800590"
---
# <a name="ixclrdataprocessstartenummodules-method"></a>IXCLRDataProcess:: StartEnumModules (método)

Proporciona un identificador para enumerar los módulos de un proceso.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a>Parámetros

`handle`\
enuncia Identificador para enumerar los módulos.

## <a name="remarks"></a>Observaciones

El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura de 24 de la tabla del método virtual.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
**Encabezado:** Ninguna  
**Biblioteca:** Ninguna  
**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Enumeración CLRDataSourceType](clrdatasourcetype-enumeration.md)
- [Depuración](index.md)
- [Interfaz IXCLRDataProcess](ixclrdataprocess-interface.md)
