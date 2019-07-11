---
title: Método ISOSDacInterface::GetModuleData
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
ms.openlocfilehash: 97b297def9fba329ff6d9573f7b2e7cc811273f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764718"
---
# <a name="isosdacinterfacegetmoduledata-method"></a>Método ISOSDacInterface::GetModuleData

Captura los datos correspondientes al módulo cargado en una dirección dada.

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
[in] La dirección del módulo para recuperar información.

`data`\
[out] El [DacpModuleData estructura](dacpmoduledata-structure.md) para contener la información del módulo cargado.

## <a name="remarks"></a>Comentarios

El método proporcionado forma parte de la `ISOSDacInterface` interfaz y corresponde a la ranura de 13 de la tabla de métodos virtuales.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado**: None  
**Biblioteca:** None  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaz ISOSDacInterface](isosdacinterface-interface.md)
