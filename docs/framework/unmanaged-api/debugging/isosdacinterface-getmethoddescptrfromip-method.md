---
title: 'ISOSDacInterface:: GetMethodDescPtrFromIP (método)'
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 0c8d91c11205e06857b4a6e7edfedcd087270d00
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396934"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a>ISOSDacInterface:: GetMethodDescPtrFromIP (método)

Recupera el puntero de la MethodDesc correspondiente al método que contiene la dirección de instrucción nativa especificada.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a>Parámetros

`ip`\
de Una dirección dentro del método en tiempo de ejecución.

`ppMD`\
enuncia La dirección de `MethodDesc` para el método determinado.

## <a name="remarks"></a>Comentarios

El método proporcionado forma parte de la [ `ISOSDacInterface` interfaz](isosdacinterface-interface.md) y corresponde a la ranura 22 de la tabla del método virtual.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado:** Ninguna  
**Biblioteca:** Ninguna  
**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaz ISOSDacInterface](isosdacinterface-interface.md)
