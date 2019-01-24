---
title: ICLRControl (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61f9448735f5d26d122ed44c4f41c4fd2a9f7478
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614307"
---
# <a name="iclrcontrol-interface"></a>ICLRControl (Interfaz)
Proporciona métodos que permiten obtener referencias a un host y configuración aspectos de common language runtime (CLR).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetCLRManager (método)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)|Obtiene un puntero de interfaz a una instancia de cualquiera de los tipos de administrador que el host puede usar para configurar el CLR.|  
|[SetAppDomainManagerType (método)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)|Establece un tipo derivado de <xref:System.AppDomainManager> como el tipo para los administradores de dominio de aplicación.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICLRAssemblyIdentityManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [ICLRDebugManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [ICLRGCManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [ICLRHostBindingPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [ICLRHostProtectionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [ICLROnEventManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [ICLRPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [IHostControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
