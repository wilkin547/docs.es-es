---
title: Interfaz ISOSDacInterface
ms.date: 02/01/2019
api.name:
- ISOSDacInterface Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface Interface
helpviewer.keywords:
- ISOSDacInterface Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ccaf479fc4fb90007b4999e95ee03bdd0529321e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922153"
---
# <a name="isosdacinterface-interface"></a>Interfaz ISOSDacInterface

Proporciona métodos auxiliares para acceder a ellos desde `SOS`.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Métodos

| Método                                                                                                               | Descripción                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [GetMethodDescData](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescdata-method.md) | Obtiene los datos para el puntero de MethodDesc determinado. |
| [GetMethodDescPtrFromIP](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescptrfromip-method.md) | Recupera el puntero de la MethodDesc correspondiente del método que contiene la dirección de instrucción nativo especificado. |
| [GetModuleData](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmoduledata-method.md)| Captura los datos correspondientes al módulo cargado en una dirección dada. |

## <a name="remarks"></a>Comentarios

Esta interfaz reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Sin embargo, es una interfaz COM que deriva de `IUnknown` con GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` que puede obtenerse a través de los mecanismos de COM habituales.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado**: Ninguna  
**Biblioteca:** Ninguna  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Vea también

- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
