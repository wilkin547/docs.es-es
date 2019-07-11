---
title: Método DacpGetModuleAddress::Request
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress::Request Method
helpviewer.keywords:
- DacpGetModuleAddress::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 07ad83da2bc608e3c5925664a68eec4a548860e1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739228"
---
# <a name="dacpgetmoduleaddressrequest-method"></a>Método DacpGetModuleAddress::Request

Realiza una solicitud para rellenar la estructura de la estructura de tiempo de ejecución determinado.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a>Parámetros

`pDataModule`\
[in] Un puntero al módulo de datos de inicialización.

## <a name="remarks"></a>Comentarios

Esta estructura reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Para ello, la manera más fácil es imitar la implementación:

- Devolver el valor obtenido del que realiza la llamada la `Request` método en el `IXCLRDataModule*` parámetro con los siguientes parámetros: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado**: None     
**Biblioteca:** None  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaz DacpGetModuleAddress](dacpgetmoduleaddress-structure.md)
