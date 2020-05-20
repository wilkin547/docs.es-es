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
ms.openlocfilehash: 54748fdeaf911591c21f4495335e54c777878f04
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615844"
---
# <a name="iclrcontrol-interface"></a>ICLRControl (Interfaz)
Proporciona métodos que permiten a un host obtener referencias y configurar aspectos del Common Language Runtime (CLR).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetCLRManager](iclrcontrol-getclrmanager-method.md)|Obtiene un puntero de interfaz a una instancia de cualquiera de los tipos de administrador que el host puede usar para configurar CLR.|  
|[SetAppDomainManagerType (Método)](iclrcontrol-setappdomainmanagertype-method.md)|Establece un tipo derivado de <xref:System.AppDomainManager> como el tipo para los administradores de dominio de aplicación.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [ICLRAssemblyIdentityManager (Interfaz)](iclrassemblyidentitymanager-interface.md)
- [ICLRDebugManager (Interfaz)](iclrdebugmanager-interface.md)
- [ICLRGCManager (Interfaz)](iclrgcmanager-interface.md)
- [ICLRHostBindingPolicyManager (Interfaz)](iclrhostbindingpolicymanager-interface.md)
- [ICLRHostProtectionManager (Interfaz)](iclrhostprotectionmanager-interface.md)
- [ICLROnEventManager (Interfaz)](iclroneventmanager-interface.md)
- [ICLRPolicyManager (Interfaz)](iclrpolicymanager-interface.md)
- [IHostControl (Interfaz)](ihostcontrol-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
