---
title: Método ISOSDacInterface::GetMethodDescPtrFromIP
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
ms.openlocfilehash: c92b112262aa2bede03bddc1396947b5fdfd6286
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65629990"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a>Método ISOSDacInterface::GetMethodDescPtrFromIP

Recupera el puntero de la MethodDesc correspondiente del método que contiene la dirección de instrucción nativo especificado.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a>Parámetros

`ip`\
[in] Una dirección dentro del método en tiempo de ejecución.

`ppMD`\
[out] La dirección de la `MethodDesc` para el método concreto.

## <a name="remarks"></a>Comentarios

El método proporcionado forma parte de la [ `ISOSDacInterface` interfaz](isosdacinterface-interface.md) y corresponde a la ranura de la tabla de métodos virtuales 21.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado**: Ninguna  
**Biblioteca:** Ninguna  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaz ISOSDacInterface](isosdacinterface-interface.md)
