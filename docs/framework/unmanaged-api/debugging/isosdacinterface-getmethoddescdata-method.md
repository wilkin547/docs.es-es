---
title: 'ISOSDacInterface:: GetMethodDescData (método)'
ms.date: 01/16/2019
api.name:
- ISOSDacInterface::GetMethodDescData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescData Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescData Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 105149d0abf312c33a8498e7428e3a8b23d6ae7d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421025"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a>ISOSDacInterface:: GetMethodDescData (método)

Obtiene los datos para el puntero de MethodDesc dado.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a>Parámetros

`methodDesc`\
de Dirección de la MethodDesc.

`ip`\
de Dirección IP del método.

`data`\
enuncia Los datos asociados al MethodDesc tal y como se devuelven desde las API internas.

`cRevertedRejitVersions`\
enuncia Número de versiones revertidas de rejit.

`rgRevertedRejitData`\
enuncia Los datos asociados a las versiones revertidas de rejit devueltas por las API internas.

`pcNeededRevertedRejitData`\
enuncia El número de bytes necesarios para almacenar los datos asociados a las versiones revertidas de ReJit.

## <a name="remarks"></a>Observaciones

El método proporcionado forma parte de la `ISOSDacInterface` interfaz y corresponde a la ranura 21 de la tabla del método virtual. Para poder utilizarlos, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) debe definirse como un entero de 64 bits sin signo.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
**Encabezado:** Ninguna  
**Biblioteca:** Ninguna  
**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Consulta también

- [Depuración](index.md)
- [Interfaz ISOSDacInterface](isosdacinterface-interface.md)
