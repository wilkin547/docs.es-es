---
title: Estructura DacpMethodDescData
ms.date: 02/01/2019
api.name:
- DacpMethodDescData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpMethodDescData Structure
helpviewer.keywords:
- DacpMethodDescData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 567dc3942f79b6bfd29338b9103083aa64e66451
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203202"
---
# <a name="dacpmethoddescdata-structure"></a>Estructura DacpMethodDescData

Define un búfer de transporte para obtener información de tiempo de ejecución de un método.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```
struct DacpMethodDescData
{
    int             bHasNativeCode;
    int             bIsDynamic;
    unsigned short  wSlotNumber;
    CLRDATA_ADDRESS NativeCodeAddr;
    CLRDATA_ADDRESS data;
    CLRDATA_ADDRESS MethodDescPtr;
    CLRDATA_ADDRESS nativeCodeInfo;
    CLRDATA_ADDRESS moduleInfo;
    mdToken         MDToken;
    CLRDATA_ADDRESS payloadGC;
    CLRDATA_ADDRESS payloadGC2;
    CLRDATA_ADDRESS managedDynamicMethodObject;
    CLRDATA_ADDRESS requestedIP;
    DacpReJitData   rejitDataCurrent;
    DacpReJitData   rejitDataRequested;
    unsigned long   cJittedRejitVersions;
};
```

## <a name="members"></a>Miembros

| Miembro                       | Descripción                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | Indica si el tiempo de ejecución tiene disponible para la instancia especificada del método de código nativo. |
| `bIsDynamic`                 | Indica si el método se genera dinámicamente a través de la generación de código ligero.           |
| `wSlotNumber`                | Número de ranura del método en la tabla de métodos.                                                   |
| `NativeCodeAddr`             | Direcciones nativo inicial del método.                                                            |
| `data`                       | Puntero a un búfer utilizado internamente por el tiempo de ejecución.                                             |
| `MethodDescPtr`              | Puntero a la `MethodDesc` en el tiempo de ejecución.                                                     |
| `nativeCodeInfo`             | Puntero a un búfer que se usa internamente el tiempo de ejecución para realizar un seguimiento de los métodos.                            |
| `moduleInfo`                 | Puntero a un búfer utilizado internamente por el tiempo de ejecución para obtener información de módulo.                      |
| `MDToken`                    | Token asociado con el método especificado.                                                         |
| `payloadGC`                  | Puntero a un búfer de la colección de elementos no utilizados lo utilizado internamente el tiempo de ejecución.                          |
| `payloadGC2`                 | Puntero a un búfer de la colección de elementos no utilizados lo utilizado internamente el tiempo de ejecución.                          |
| `managedDynamicMethodObject` | Si el método es dinámico, el tiempo de ejecución utiliza internamente este búfer para obtener información de seguimiento.     |
| `requestedIP`                | Se usa para rellenar la estructura por solicitud cuando se especifica una dirección de código nativo.                    |
| `rejitDataCurrent`           | Información acerca de la última versión instrumentada del método.                                   |
| `rejitDataRequested`         | Información de ReJIT de la dirección solicitada nativa.                                             |
| `cJittedRejitVersions`       | Número de veces que el método ha sido rejitted a través de la instrumentación.                           |

## <a name="remarks"></a>Comentarios

Esta estructura reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Para ello, defina la estructura según lo especificado anteriormente.

## <a name="requirements"></a>Requisitos
**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado**: Ninguna  
**Biblioteca:** Ninguna  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Tipos de datos comunes](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)
