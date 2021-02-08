---
description: 'Más información sobre: IXCLRDataMethodInstance:: GetRepresentativeEntryAddress (método)'
title: 'IXCLRDataMethodInstance:: GetRepresentativeEntryAddress (método)'
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
helpviewer.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 21cc6c50ab460c0e3a3a92c11fcfe51d4a2a4606
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800804"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a>IXCLRDataMethodInstance:: GetRepresentativeEntryAddress (método)

Obtiene la dirección de punto de entrada más representativa para la compilación nativa de todos los puntos de entrada posibles para un método.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a>Parámetros

`addr`\
enuncia Dirección del punto de entrada nativo más representativo para el método.

## <a name="remarks"></a>Observaciones

El método proporcionado forma parte de la [ `IXCLRDataMethodInstance` interfaz](ixclrdatamethodinstance-interface.md) y corresponde a la ranura del vigésimo de la tabla del método virtual.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
**Encabezado:** Ninguna  
**Biblioteca:** Ninguna  
**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaz IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)
