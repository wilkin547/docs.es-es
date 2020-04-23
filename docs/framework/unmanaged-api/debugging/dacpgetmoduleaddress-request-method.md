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
ms.openlocfilehash: 4dbe6a2c295e5afae1b6761f0c7b695fdb906428
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102912"
---
# <a name="dacpgetmoduleaddressrequest-method"></a>Método DacpGetModuleAddress::Request

Realiza una solicitud para rellenar la estructura desde la estructura de tiempo de ejecución determinada.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a>Parámetros

`pDataModule`\
[en] Un puntero al módulo de datos de semillas.

## <a name="remarks"></a>Observaciones

Esta estructura se encuentra dentro del tiempo de ejecución y no se expone a través de encabezados o archivos de biblioteca. Para usarlo, la forma más fácil es imitar la implementación:

- Devuelve el valor obtenido `Request` al llamar `IXCLRDataModule*` al método en el parámetro con los siguientes parámetros:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md)\
**Encabezado:** Ninguno
**Biblioteca:** Ninguno
**Versiones de .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Consulte también

- [Depuración](index.md)
- [Estructura DacpGetModuleAddress](dacpgetmoduleaddress-structure.md)
