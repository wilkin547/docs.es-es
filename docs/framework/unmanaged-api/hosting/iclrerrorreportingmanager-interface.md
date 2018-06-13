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
ms.openlocfilehash: bf9e04ed1d3a68fed120c4c13ad992af1f777244
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433801"
---
# <a name="iclrerrorreportingmanager-interface"></a>ICLRErrorReportingManager (Interfaz)
Proporciona métodos que permiten al host configurar los volcados de pila personalizados para informes de errores.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[BeginCustomDump (método)](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|Especifica la configuración de los volcados de pila personalizados para el informe de errores.|  
|[EndCustomDump (método)](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|Borra la configuración de volcado de pila personalizada establecida por una llamada anterior a `BeginCustomDump`.|  
|[GetBucketParametersForCurrentException (método)](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|Obtiene el depósito de Watson para la excepción actual en el subproceso que realiza la llamada.|  
  
## <a name="remarks"></a>Comentarios  
 El `BeginCustomDump` método establece la configuración de volcado de pila personalizada. El `EndCustomDump` método borra la configuración de volcado de pila personalizada y libera cualquier estado asociado. Debe llamarse una vez finalizado el volcado personalizado.  
  
> [!IMPORTANT]
>  Error al llamar a `EndCustomDump` provoca la pérdida de memoria.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ECustomDumpItemKind (enumeración)](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
