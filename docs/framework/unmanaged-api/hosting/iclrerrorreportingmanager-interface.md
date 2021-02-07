---
description: 'Más información acerca de: ICLRErrorReportingManager (interfaz)'
title: ICLRErrorReportingManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
ms.openlocfilehash: 094fe52858983fd0e1e5826e823932cb150b6087
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689279"
---
# <a name="iclrerrorreportingmanager-interface"></a>ICLRErrorReportingManager (Interfaz)

Proporciona métodos que permiten al host configurar volcados de pila personalizados para el informe de errores.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md)|Especifica la configuración de los volcados de pila personalizados para el informe de errores.|  
|[Método EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md)|Borra la configuración de volcado de la pila personalizada establecida por una llamada anterior a `BeginCustomDump` .|  
|[Método GetBucketParametersForCurrentException](iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|Obtiene el depósito de Watson para la excepción actual en el subproceso que realiza la llamada.|  
  
## <a name="remarks"></a>Observaciones  

 El `BeginCustomDump` método establece la configuración personalizada del volcado de la pila. El `EndCustomDump` método borra la configuración de volcado de la pila personalizada y libera cualquier estado asociado. Se debe llamar después de completar el volcado de memoria personalizado.  
  
> [!IMPORTANT]
> Si no se llama a `EndCustomDump` , se produce una pérdida de memoria.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ECustomDumpItemKind (Enumeración)](ecustomdumpitemkind-enumeration.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
