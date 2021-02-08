---
description: 'Más información sobre: IXCLRDataProcess:: EndEnumModules (método)'
title: 'IXCLRDataProcess:: EndEnumModules (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 454d4fa3616f9ba8312dc3d1ac02c228625aa488
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800713"
---
# <a name="ixclrdataprocessendenummodules-method"></a>IXCLRDataProcess:: EndEnumModules (método)

Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de módulos.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a>Parámetros

`handle`\
enuncia Identificador para enumerar los módulos.

## <a name="remarks"></a>Observaciones

El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura del 26 de la tabla del método virtual.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).
**Encabezado:** Ninguna **biblioteca:** ninguna **.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaz IXCLRDataProcess](ixclrdataprocess-interface.md)
