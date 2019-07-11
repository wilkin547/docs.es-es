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
ms.openlocfilehash: 2e27082ba4c35bc10eb65139b2af6c81c10d79a6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739120"
---
# <a name="dacpmoduledata-structure"></a>Estructura DacpModuleData

Define un búfer de transporte para obtener información de tiempo de ejecución de un módulo.

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

## <a name="members"></a>Miembros

| Member    | DESCRIPCIÓN                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | Dirección del objeto de módulo.                                           |
| `File`    | Un puntero al archivo ejecutable portable (PE).                       |
| `ilBase`  | Básico de la dirección de la imagen cargada.                                 |
| `payLoad` | Un búfer de carga para obtener información de módulos adicionales utilizado por el tiempo de ejecución. |

## <a name="remarks"></a>Comentarios

Esta estructura reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Para ello, defina la estructura según lo especificado anteriormente.

## <a name="requirements"></a>Requisitos
**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado**: None  
**Biblioteca:** None  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
