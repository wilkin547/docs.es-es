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
ms.openlocfilehash: b46a04d67f59c5031b5bd195cef4cc2275e1e5e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793807"
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

## <a name="members"></a>Miembros

| Miembro    | Descripción                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | Dirección del objeto de módulo.                                           |
| `File`    | Puntero al archivo portable ejecutable (PE).                       |
| `ilBase`  | Dirección de la base de la imagen cargada.                                 |
| `payLoad` | Búfer de carga para la información adicional del módulo que utiliza el motor en tiempo de ejecución. |

## <a name="remarks"></a>Notas

Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Para usarlo, defina la estructura tal y como se especificó anteriormente.

## <a name="requirements"></a>Requisitos de
**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado:** Ninguna  
**Biblioteca:** Ninguna  
**.NET Framework versiones:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Estructuras de depuración](debugging-structures.md)
