---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a9d9cff0360e4eb27584fe0f22c1c20396ff8f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966256"
---
# <a name="iclrerrorreportingmanager-interface"></a>ICLRErrorReportingManager (Interfaz)
Proporciona métodos que permiten al host configurar volcados de pila personalizados para el informe de errores.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|[BeginCustomDump (método)](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|Especifica la configuración de los volcados de pila personalizados para el informe de errores.|  
|[EndCustomDump (método)](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|Borra la configuración de volcado de la pila personalizada establecida por una llamada anterior a `BeginCustomDump`.|  
|[GetBucketParametersForCurrentException (método)](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|Obtiene el depósito de Watson para la excepción actual en el subproceso que realiza la llamada.|  
  
## <a name="remarks"></a>Comentarios  
 El `BeginCustomDump` método establece la configuración personalizada del volcado de la pila. El `EndCustomDump` método borra la configuración de volcado de la pila personalizada y libera cualquier estado asociado. Se debe llamar después de completar el volcado de memoria personalizado.  
  
> [!IMPORTANT]
> Si no se `EndCustomDump` llama a, se produce una pérdida de memoria.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ECustomDumpItemKind (enumeración)](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
