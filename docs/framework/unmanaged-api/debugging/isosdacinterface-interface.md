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
ms.openlocfilehash: 94349a3f7b18c8ce29bb3a71cb9d10ee4eac8036
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790476"
---
# <a name="isosdacinterface-interface"></a>Interfaz ISOSDacInterface

Proporciona métodos auxiliares para tener acceso a los datos de `SOS`.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Métodos

| Método                                                                                                               | Descripción                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [GetMethodDescData](isosdacinterface-getmethoddescdata-method.md) | Obtiene los datos para el puntero de MethodDesc dado. |
| [GetMethodDescPtrFromIP](isosdacinterface-getmethoddescptrfromip-method.md) | Recupera el puntero de la MethodDesc correspondiente al método que contiene la dirección de instrucción nativa especificada. |
| [GetModuleData](isosdacinterface-getmoduledata-method.md)| Captura los datos correspondientes al módulo cargado en una dirección determinada. |

## <a name="remarks"></a>Notas

Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Sin embargo, es una interfaz COM que se deriva de `IUnknown` con GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` que se puede obtener a través de los mecanismos COM habituales.

## <a name="requirements"></a>Requisitos de

**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado:** Ninguna  
**Biblioteca:** Ninguna  
**.NET Framework versiones:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaces de depuración](debugging-interfaces.md)
