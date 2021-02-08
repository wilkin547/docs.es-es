---
description: 'Más información sobre: ISOSDacInterface:: GetMethodDescData (método)'
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
ms.openlocfilehash: a1284aa4d810ed9d6db7ad3c1b471702b1dad54d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790430"
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

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaz ISOSDacInterface](isosdacinterface-interface.md)
