---
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
ms.openlocfilehash: 8757642db6c4375cf55d1f7288669c4c8a752a38
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790404"
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

## <a name="remarks"></a>Notas

Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca. Sin embargo, es una interfaz COM que se deriva de `IUnknown` con GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` que se puede obtener a través de los mecanismos COM habituales.

## <a name="requirements"></a>Requisitos de

**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado:** Ninguna  
**Biblioteca:** Ninguna  
**.NET Framework versiones:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaces de depuración](debugging-interfaces.md)
