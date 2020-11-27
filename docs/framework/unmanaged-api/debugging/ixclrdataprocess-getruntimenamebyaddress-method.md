---
title: 'IXCLRDataProcess:: GetRuntimeNameByAddress (método)'
ms.date: 4/27/2020
api.name:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: tommcdon
ms.author: tommcdon
ms.openlocfilehash: 6648bdafe6e5cdd402bcfa02a148c57f0f1e209e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275571"
---
# <a name="ixclrdataprocessgetruntimenamebyaddress-method"></a>IXCLRDataProcess:: GetRuntimeNameByAddress (método)

Obtiene un nombre para la dirección especificada.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetRuntimeNameByAddress(
    [in] CLRDATA_ADDRESS address,
    [in] ULONG32 flags,
    [in] ULONG32 bufLen,
    [out] ULONG32 *nameLen,
    [out, size_is(bufLen)] WCHAR nameBuf[],
    [out] CLRDATA_ADDRESS* displacement
);
```

## <a name="parameters"></a>Parámetros

`address`\
de `CLRDATA_ADDRESS` Valor que representa una dirección de código.

`flags`\
de Establezca en ' 0 '.

`bufLen`\
de Longitud del búfer.

`namLen`\
enuncia Puntero al número de caracteres devueltos.

`namBuf`\
[out, size_is ( `bufLen` )] búfer de entrada de longitud `bufLen` que almacena el nombre en tiempo de ejecución.

`displacement`\
enuncia `CLRDATA_ADDRESS` Puntero al desplazamiento de código del símbolo devuelto.

## <a name="remarks"></a>Comentarios

El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura 16 de la tabla del método virtual.

> [!NOTE]
> Si el búfer no es suficientemente grande para el nombre, este método devuelve `S_FALSE` y establece `nameLen` en la longitud de búfer necesaria.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [los requisitos del sistema](../../get-started/system-requirements.md)\
**Encabezado:** Ninguna
**Biblioteca:** Ninguna
**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaz IXCLRDataProcess](ixclrdataprocess-interface.md)
