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
ms.openlocfilehash: 1bdc958f2516bcd7c2eb74312fbf478e6d49535a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948813"
---
# <a name="icordebugprocess4-interface"></a>Interfaz ICorDebugProcess4

Proporciona compatibilidad para fuera del control de ejecución del proceso.

## <a name="methods"></a>Métodos

| Método                                                                 | Descripción                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) | Notifica a la canalización ICorDebug que fuera del depurador de proceso continúa la ejecución del depurado. |

## <a name="remarks"></a>Comentarios

Esta interfaz reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Sin embargo, es una interfaz COM que deriva de `IUnknown` con GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` que puede obtenerse a través de los mecanismos de COM habituales.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado**: Ninguna

**Biblioteca:** Ninguna

**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
- [Depuración](index.md)
