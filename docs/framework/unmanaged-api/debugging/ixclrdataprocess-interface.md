---
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
ms.openlocfilehash: e7e53615e38d0ab76f9e7c0a753be3c13780057d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178370"
---
# <a name="ixclrdataprocess-interface"></a>Interfaz IXCLRDataProcess

Proporciona métodos para consultar información sobre un proceso.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Métodos

| Método                                                                                                                                               | Descripción                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [GetAppDomainByUniqueId](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | Obtiene un `AppDomain` proceso en un proceso por su identificador único.                                              |
| [StartEnumModules](ixclrdataprocess-startenummodules-method.md)                                   | Proporciona un identificador para enumerar los módulos de un proceso.                                        |
| [EnumModule](ixclrdataprocess-enummodule-method.md)                                               | Enumera los módulos de este proceso.                                                         |
| [EndEnumModules](ixclrdataprocess-endenummodules-method.md)                                       | Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración del módulo.               |
| [StartEnumMethodInstancesByAddress](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | Proporciona un identificador para enumerar las `AppDomain` instancias de método de inicio en una dirección determinada. |
| [EnumMethodInstanceByAddress](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | Enumera las instancias de método de este proceso a partir de un desplazamiento de dirección.                  |
| [EndEnumMethodInstancesByAddress](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | Libera los recursos utilizados por los iteradores internos utilizados durante la enumeración de instancias.             |

## <a name="remarks"></a>Observaciones

Esta interfaz se encuentra dentro del tiempo de ejecución y no se expone a través de encabezados o archivos de biblioteca. Sin embargo, es una interfaz `IUnknown` COM `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` que deriva de con GUID que se puede obtener a través de los mecanismos COM habituales.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).
**Encabezado:** Ninguno  
**Biblioteca:** Ninguno  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Consulte también

- [Depuración](index.md)
- [Interfaces de depuración](debugging-interfaces.md)
