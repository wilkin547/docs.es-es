---
title: IHostControl (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
ms.openlocfilehash: 444a78705c61d5a53764f55185ef1a907830bd71
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195878"
---
# <a name="ihostcontrol-interface"></a>IHostControl (Interfaz)
Proporciona métodos para configurar la carga de ensamblados y para determinar qué interfaces de hospedaje admite el host.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetHostManager (método)](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|Obtiene un puntero de interfaz a la implementación del host de la interfaz con el `IID`especificado.|  
|[SetAppDomainManager (método)](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|Notifica al host que se ha creado un dominio de aplicación.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.AppDomainManager>
- [ICLRRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
