---
title: Interfaz IXCLRDataMethodDefinition
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition Interface
helpviewer.keywords:
- IXCLRDataMethodDefinition Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 708c681a98113a406249a360c2fc81087e5b97f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790426"
---
# <a name="ixclrdatamethoddefinition-interface"></a>Interfaz IXCLRDataMethodDefinition

Proporciona métodos para consultar información sobre una definición de método.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Métodos

Los métodos siguientes son algunos de los métodos disponibles en la interfaz.

| Método                                                                                                                          | Descripción                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [StartEnumInstances](ixclrdatamethoddefinition-startenuminstances-method.md) | Proporciona un identificador para la enumeración de instancias de método para un `IXCLRDataAppDomain`determinado. |
| [EnumInstance](ixclrdatamethoddefinition-enuminstance-method.md)             | Enumera las instancias de esta definición de método.                                         |
| [EndEnumInstances](ixclrdatamethoddefinition-endenuminstances-method.md)     | Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de la instancia.         |

## <a name="remarks"></a>Notas

Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Sin embargo, es una interfaz COM que se deriva de `IUnknown` con GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` que se puede obtener a través de los mecanismos COM habituales.

## <a name="requirements"></a>Requisitos de

**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado:** Ninguna  
**Biblioteca:** Ninguna  
**.NET Framework versiones:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaces de depuración](debugging-interfaces.md)
