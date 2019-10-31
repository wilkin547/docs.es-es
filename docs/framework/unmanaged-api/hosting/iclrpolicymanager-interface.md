---
title: ICLRPolicyManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
ms.openlocfilehash: 59aa904d4c67326b60381d3476eaab179d7fa42b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140804"
---
# <a name="iclrpolicymanager-interface"></a>ICLRPolicyManager (Interfaz)
Proporciona métodos que permiten al host especificar las acciones de directiva que deben realizarse en caso de que se produzcan errores y tiempos de espera.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[SetActionOnFailure (método)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|Especifica la acción de la Directiva que debe realizar el Common Language Runtime (CLR) cuando se produce el error especificado.|  
|[SetActionOnTimeout (método)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|Especifica la acción de la Directiva que el CLR debe realizar cuando se agota el tiempo de espera de la operación especificada.|  
|[SetDefaultAction (método)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|Especifica la acción de la Directiva que el CLR debe realizar cuando se produce la operación especificada.|  
|[SetTimeout (método)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|Establece un valor de tiempo de espera para la operación especificada.|  
|[SetTimeoutAndAction (método)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|Establece un valor de tiempo de espera para la operación especificada y especifica la acción de la Directiva que el CLR debe realizar cuando se produce la operación.|  
|[SetUnhandledExceptionPolicy (método)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|Especifica el comportamiento de CLR cuando se produce una excepción no controlada.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [EClrFailure (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [EClrOperation (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [EPolicyAction (enumeración)](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
