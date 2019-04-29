---
title: Método IXCLRDataMethodInstance::GetRepresentativeEntryAddress
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
ms.openlocfilehash: 6f204e2ed9cb1409d53432355467bb11946f8809
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775537"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a>Método IXCLRDataMethodInstance::GetRepresentativeEntryAddress

Obtiene la dirección del punto de entrada más representativa de la compilación nativa de todos los puntos de entrada posibles para un método.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a>Parámetros

`addr`\
[out] La dirección del punto de entrada nativo más representativo del método.

## <a name="remarks"></a>Comentarios

El método proporcionado forma parte de la [ `IXCLRDataMethodInstance` interfaz](ixclrdatamethodinstance-interface.md) y corresponde a la ranura de 19 de la tabla de métodos virtuales.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado**: Ninguna  
**Biblioteca:** Ninguna  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaz IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)
