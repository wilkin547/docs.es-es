---
title: Método IXCLRDataProcess::StartEnumMethodInstancesByAddress
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 9afbf0665b114169661a74b60c744203d160fed3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662626"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a>Método IXCLRDataProcess::StartEnumMethodInstancesByAddress

Proporciona un identificador para enumerar las instancias de método de `AppDomain` a partir de una dirección determinada.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

### <a name="parameters"></a>Parámetros

`address` [in] La dirección de la primera instancia de método.

`appDomain` [in] El dominio de aplicación de las instancias de método.

`handle` [out] Un identificador para enumerar las instancias de método.

## <a name="remarks"></a>Comentarios

El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura de la tabla de métodos virtuales 27.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado**: Ninguna  
**Biblioteca:** Ninguna  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Enumeración CLRDataSourceType](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Interfaz IXCLRDataProcess](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
