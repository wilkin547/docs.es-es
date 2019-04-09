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
ms.openlocfilehash: cbea6c0562c68ae5d18247dc97bc53eb9dfbfd7e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104115"
---
# <a name="dacpgetmoduleaddress-structure"></a>Estructura DacpGetModuleAddress

Define el contenedor para una solicitud de dirección del módulo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```
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
| [Request](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-request-method.md) | Realiza una solicitud para rellenar la estructura de la estructura de tiempo de ejecución determinado. |

## <a name="remarks"></a>Comentarios

Esta estructura reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Para ello, defina la estructura según lo especificado anteriormente, donde `CLRDATA_ADDRESS` es un entero de 64 bits sin signo.

## <a name="requirements"></a>Requisitos
**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado**: Ninguna  
**Biblioteca:** Ninguna  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
