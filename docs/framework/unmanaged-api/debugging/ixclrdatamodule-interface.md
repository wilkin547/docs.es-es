---
description: 'Más información acerca de: interfaz IXCLRDataModule'
title: Interfaz IXCLRDataModule
ms.date: 01/16/2019
api.name:
- IXCLRDataModule Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule Interface
helpviewer.keywords:
- IXCLRDataModule Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 403d4dd3db64f2855347562da7217a3562985c7d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800752"
---
# <a name="ixclrdatamodule-interface"></a>Interfaz IXCLRDataModule

Proporciona métodos para consultar información sobre un módulo cargado.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Métodos

| Método                                                                                                                                | Descripción                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [GetMethodDefinitionByToken](ixclrdatamodule-getmethoddefinitionbytoken-method.md) | Obtiene la definición de método correspondiente a un token de metadatos determinado. |
| [Solicitud](ixclrdatamodule-request-method.md)                                       | Solicita que rellene el búfer proporcionado con los datos del módulo.       |
| [GetVersionId](ixclrdatamodule-getversionid-method.md)                             | Obtiene el identificador de versión del módulo.                                       |

## <a name="remarks"></a>Observaciones

Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Sin embargo, es una interfaz COM que se deriva de `IUnknown` con `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` el GUID que se puede obtener a través de los mecanismos com habituales.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
**Encabezado:** Ninguna  
**Biblioteca:** Ninguna  
**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaces para depuración](debugging-interfaces.md)
