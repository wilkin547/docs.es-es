---
title: Interfaz ICorDebugProcess4
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4
helpviewer_keywords:
- ICorDebugProcess4 interface [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: fcf725ea98fa4351e72cf592f92968ee2233ecb0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213587"
---
# <a name="icordebugprocess4-interface"></a>Interfaz ICorDebugProcess4

Proporciona compatibilidad para el control de ejecución fuera de proceso.

## <a name="methods"></a>Métodos

| Método                                                                 | Descripción                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) | Notifica a la canalización ICorDebug que el depurador fuera de proceso está continuando la ejecución del depurador. |

## <a name="remarks"></a>Observaciones

Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Sin embargo, es una interfaz COM que se deriva de `IUnknown` con `E930C679-78AF-4953-8AB7-B0AABF0F9F80` el GUID que se puede obtener a través de los mecanismos com habituales.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** Ninguna

**Biblioteca:** Ninguna

**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
