---
title: Interfaz IXCLRDataMethodInstance
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance Interface
helpviewer.keywords:
- IXCLRDataMethodInstance Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: c51825433bbc86c897c097475d5c15c855f6ec8b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790407"
---
# <a name="ixclrdatamethodinstance-interface"></a>Interfaz IXCLRDataMethodInstance

Proporciona métodos para consultar información sobre una instancia de método.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Métodos

| Método                                                                                                                  | Descripción                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [GetILAddressMap](ixclrdatamethodinstance-getiladdressmap-method.md) | Obtiene el IL para direccionar la información de asignación. |
| [GetRepresentativeEntryAddress](ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | Obtiene la dirección de punto de entrada más representativa para la compilación nativa de todos los puntos de entrada posibles para un método. |

## <a name="remarks"></a>Notas

Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Sin embargo, es una interfaz COM que se deriva de `IUnknown` con GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` que se puede obtener a través de los mecanismos COM habituales.

## <a name="requirements"></a>Requisitos de

**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado:** Ninguna  
**Biblioteca:** Ninguna  
**.NET Framework versiones:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaces de depuración](debugging-interfaces.md)
