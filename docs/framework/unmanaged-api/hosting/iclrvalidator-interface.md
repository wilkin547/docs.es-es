---
description: 'Más información acerca de: interfaz ICLRValidator'
title: ICLRValidator (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator
helpviewer_keywords:
- ICLRValidator interface [.NET Framework hosting]
ms.assetid: 2edd0a10-77fb-4173-91eb-f2970cc364d0
topic_type:
- apiref
ms.openlocfilehash: 72ff94915d35967b6a8a87b022789ca697f61711
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636759"
---
# <a name="iclrvalidator-interface"></a>ICLRValidator (Interfaz)

Proporciona métodos para validar imágenes ejecutables portables (PE) y notificar errores de validación.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método FormatEventInfo](iclrvalidator-formateventinfo-method.md)|Obtiene un mensaje detallado sobre el error de validación especificado.|  
|[Método Validate](iclrvalidator-validate-method.md)|Valida el ejecutable portable o el lenguaje intermedio de Microsoft (MSIL) en el archivo especificado.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** IValidator. idl, IValidator. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRErrorReportingManager (Interfaz)](iclrerrorreportingmanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [CLRRuntimeHost (Coclase)](clrruntimehost-coclass.md)
