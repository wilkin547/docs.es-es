---
description: 'Más información acerca de: interfaz IXCLRDataProcess'
title: Interfaz IXCLRDataProcess
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: b611491e5c9a5957c07a305a3f395b67ad208649
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800648"
---
# <a name="ixclrdataprocess-interface"></a>Interfaz IXCLRDataProcess

Proporciona métodos para consultar información sobre un proceso.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Métodos

| Método                                                                                                                                               | Descripción                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [GetRuntimeNameByAddress](ixclrdataprocess-getruntimenamebyaddress-method.md)                     | Obtiene un nombre para la dirección especificada.                                                               |
| [GetAppDomainByUniqueId](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | Obtiene un `AppDomain` en un proceso por su identificador único.                                              |
| [StartEnumModules](ixclrdataprocess-startenummodules-method.md)                                   | Proporciona un identificador para enumerar los módulos de un proceso.                                        |
| [EnumModule](ixclrdataprocess-enummodule-method.md)                                               | Enumera los módulos de este proceso.                                                         |
| [EndEnumModules](ixclrdataprocess-endenummodules-method.md)                                       | Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de módulos.               |
| [StartEnumMethodInstancesByAddress](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | Proporciona un identificador para enumerar las instancias de método de que `AppDomain` empiezan en una dirección determinada. |
| [EnumMethodInstanceByAddress](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | Enumera las instancias de método de este proceso a partir de un desplazamiento de dirección.                  |
| [EndEnumMethodInstancesByAddress](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de la instancia.             |

## <a name="remarks"></a>Observaciones

Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Sin embargo, es una interfaz COM que se deriva de `IUnknown` con `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` el GUID que se puede obtener a través de los mecanismos com habituales.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).
**Encabezado:** Ninguna  
**Biblioteca:** Ninguna  
**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaces para depuración](debugging-interfaces.md)
