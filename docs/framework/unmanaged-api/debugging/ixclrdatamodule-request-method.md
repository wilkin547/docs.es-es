---
title: 'IXCLRDataModule:: Request (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::Request Method
helpviewer.keywords:
- IXCLRDataModule::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3c18fc5c947cbb89fc4e9aed60d3cedcbe22d749
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420817"
---
# <a name="ixclrdatamodulerequest-method"></a>IXCLRDataModule:: Request (método)

Solicita que rellene el búfer proporcionado con los datos del módulo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a>Parámetros

`reqCode`\
de Tipo de solicitud que se va a enviar.

`inBufferSize`\
[in] tamaño del búfer de entrada que se va a pasar.

`inBuffer`\
[in, size_is (inBufferSize)] Puntero de búfer para los datos sin procesar que se van a enviar en la solicitud.

`outBufferSize`\
de Tamaño del búfer de salida.

`outBuffer`\
[out, size_is (outBufferSize)] Puntero de búfer que se utiliza para almacenar la respuesta de solicitud.

## <a name="remarks"></a>Observaciones

El método proporcionado forma parte de la `IXCLRDataModule` interfaz y corresponde a la ranura 37th de la tabla del método virtual.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).
**Encabezado:** Ninguna **biblioteca:** ninguna **.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Consulta también

- [Depuración](index.md)
- [Interfaz IXCLRDataModule](ixclrdatamodule-interface.md)
