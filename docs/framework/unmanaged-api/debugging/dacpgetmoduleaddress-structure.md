---
title: Estructura DacpGetModuleAddress
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 1e3a62de3259c012438c64ece26e696682ec96e6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789202"
---
# <a name="dacpgetmoduleaddress-structure"></a>Estructura DacpGetModuleAddress

Define el contenedor para una solicitud de dirección del módulo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a>Miembros

| Miembro      | Descripción                |
| ----------- | -------------------------- |
| `ModulePtr` | Puntero al módulo. |

## <a name="methods"></a>Métodos

| Método                                                                                               | Descripción                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [Solicitud](dacpgetmoduleaddress-request-method.md) | Realiza una solicitud para rellenar la estructura a partir de la estructura en tiempo de ejecución especificada. |

## <a name="remarks"></a>Notas

Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Para usarlo, defina la estructura como se especificó anteriormente, donde `CLRDATA_ADDRESS` es un entero de 64 bits sin signo.

## <a name="requirements"></a>Requisitos de
**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado:** Ninguna  
**Biblioteca:** Ninguna  
**.NET Framework versiones:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Estructuras de depuración](debugging-structures.md)
