---
title: 'IXCLRDataProcess:: EnumMethodInstanceByAddress (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: f3800a5980304394dd648111fe23a3bb0890c575
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395107"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a>IXCLRDataProcess:: EnumMethodInstanceByAddress (método)

Enumera las instancias de método de este proceso a partir de un desplazamiento de dirección.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a>Parámetros

`handle`\
de Identificador para enumerar las instancias de método.

`mod`\
enuncia Instancia de método enumerado.

## <a name="remarks"></a>Comentarios

El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura 29 de la tabla del método virtual.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).
**Encabezado:** Ninguna **biblioteca:** ninguna **.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Vea también

- [Enumeración CLRDataSourceType](clrdatasourcetype-enumeration.md)
- [Depuración](index.md)
- [Interfaz IXCLRDataProcess](ixclrdataprocess-interface.md)
