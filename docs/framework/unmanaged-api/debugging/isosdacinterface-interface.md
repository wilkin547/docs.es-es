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
ms.openlocfilehash: c9b4e6e5b36fe38b6c0ea78f6d1848d155008bcc
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420973"
---
# <a name="isosdacinterface-interface"></a>Interfaz ISOSDacInterface

Proporciona métodos auxiliares para tener acceso a los datos de `SOS` .

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Métodos

| Método                                                                                                               | Descripción                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [GetMethodDescData](isosdacinterface-getmethoddescdata-method.md) | Obtiene los datos para el puntero de MethodDesc dado. |
| [GetMethodDescPtrFromIP](isosdacinterface-getmethoddescptrfromip-method.md) | Recupera el puntero de la MethodDesc correspondiente al método que contiene la dirección de instrucción nativa especificada. |
| [GetModuleData](isosdacinterface-getmoduledata-method.md)| Captura los datos correspondientes al módulo cargado en una dirección determinada. |

## <a name="remarks"></a>Observaciones

Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Sin embargo, es una interfaz COM que se deriva de `IUnknown` con `436f00f2-b42a-4b9f-870c-e73db66ae930` el GUID que se puede obtener a través de los mecanismos com habituales.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
**Encabezado:** Ninguna  
**Biblioteca:** Ninguna  
**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Consulta también

- [Depuración](index.md)
- [Interfaces para depuración](debugging-interfaces.md)
