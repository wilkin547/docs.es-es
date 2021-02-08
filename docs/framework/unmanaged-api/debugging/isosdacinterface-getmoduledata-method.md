---
description: 'Más información sobre: ISOSDacInterface:: GetModuleData (método)'
title: 'ISOSDacInterface:: GetModuleData (método)'
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetModuleData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetModuleData Method
helpviewer.keywords:
- ISOSDacInterface::GetModuleData Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: c01f55d55d5ee9082dee4b3adb3022bb17807aa2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790391"
---
# <a name="isosdacinterfacegetmoduledata-method"></a>ISOSDacInterface:: GetModuleData (método)

Captura los datos correspondientes al módulo cargado en una dirección determinada.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a>Parámetros

`moduleAddr`\
de Dirección del módulo para el que se va a recuperar información.

`data`\
enuncia [Estructura DacpModuleData](dacpmoduledata-structure.md) que contiene la información del módulo cargado.

## <a name="remarks"></a>Observaciones

El método proporcionado forma parte de la `ISOSDacInterface` interfaz y corresponde a la ranura decimocuarta de la tabla del método virtual.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
**Encabezado:** Ninguna  
**Biblioteca:** Ninguna  
**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaz ISOSDacInterface](isosdacinterface-interface.md)
