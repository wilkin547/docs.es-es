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
ms.openlocfilehash: d3816c8a3b6204b053505aa888eb28d696f8990b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677854"
---
# <a name="iclrerrorreportingmanager-interface"></a>ICLRErrorReportingManager (Interfaz)

Proporciona métodos que permiten al host configurar volcados de pila personalizados para el informe de errores.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md)|Especifica la configuración de los volcados de pila personalizados para el informe de errores.|  
|[Método EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md)|Borra la configuración de volcado de la pila personalizada establecida por una llamada anterior a `BeginCustomDump` .|  
|[Método GetBucketParametersForCurrentException](iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|Obtiene el depósito de Watson para la excepción actual en el subproceso que realiza la llamada.|  
  
## <a name="remarks"></a>Comentarios  

 El `BeginCustomDump` método establece la configuración personalizada del volcado de la pila. El `EndCustomDump` método borra la configuración de volcado de la pila personalizada y libera cualquier estado asociado. Se debe llamar después de completar el volcado de memoria personalizado.  
  
> [!IMPORTANT]
> Si no se llama a `EndCustomDump` , se produce una pérdida de memoria.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ECustomDumpItemKind (Enumeración)](ecustomdumpitemkind-enumeration.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
