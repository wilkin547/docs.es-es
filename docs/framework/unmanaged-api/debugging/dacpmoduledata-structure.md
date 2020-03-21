---
title: Estructura DacpModuleData
ms.date: 02/01/2019
api.name:
- DacpModuleData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpModuleData Structure
helpviewer.keywords:
- DacpModuleData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: c24bdce64eb7e208bf3830940d7beab1ebf92e78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179187"
---
# <a name="dacpmoduledata-structure"></a>Estructura DacpModuleData

Define un búfer de transporte para la información de tiempo de ejecución de un módulo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File;
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a>Members

| Member    | Descripción                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | Dirección del objeto module.                                           |
| `File`    | Un puntero al archivo ejecutable portátil (PE).                       |
| `ilBase`  | La dirección de la base de la imagen cargada.                                 |
| `payLoad` | Un búfer de carga útil para la información de módulo adicional utilizada por el tiempo de ejecución. |

## <a name="remarks"></a>Observaciones

Esta estructura se encuentra dentro del tiempo de ejecución y no se expone a través de encabezados o archivos de biblioteca. Para utilizarla, defina la estructura como se especificó anteriormente.

## <a name="requirements"></a>Requisitos
**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado:** Ninguno  
**Biblioteca:** Ninguno  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Consulte también

- [Depuración](index.md)
- [Estructuras de depuración](debugging-structures.md)
