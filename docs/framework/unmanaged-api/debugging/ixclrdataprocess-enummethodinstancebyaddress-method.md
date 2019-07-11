---
title: Método IXCLRDataProcess::EnumMethodInstanceByAddress
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
ms.openlocfilehash: 89b89a0cb056a0515bf0859069455a73f62aae4a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769617"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a>Método IXCLRDataProcess::EnumMethodInstanceByAddress

Enumera las instancias de método de este proceso empezando por un desplazamiento de dirección.

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
[in] Un identificador para enumerar las instancias de método.

`mod`\
[out] La instancia de método enumerado.

## <a name="remarks"></a>Comentarios

El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la fecha del 28 de ranura de la tabla de métodos virtuales.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).   
**Encabezado**: None   
**Biblioteca:** None   
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]   
 
## <a name="see-also"></a>Vea también

- [Enumeración CLRDataSourceType](clrdatasourcetype-enumeration.md)
- [Depuración](index.md)
- [Interfaz IXCLRDataProcess](ixclrdataprocess-interface.md)
