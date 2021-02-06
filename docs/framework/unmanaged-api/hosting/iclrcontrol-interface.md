---
description: 'Más información acerca de: ICLRControl (interfaz)'
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
ms.openlocfilehash: e108506d06b746d631f4c15c37d467399de30aba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637669"
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
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRAssemblyIdentityManager (Interfaz)](iclrassemblyidentitymanager-interface.md)
- [ICLRDebugManager (Interfaz)](iclrdebugmanager-interface.md)
- [ICLRGCManager (Interfaz)](iclrgcmanager-interface.md)
- [ICLRHostBindingPolicyManager (Interfaz)](iclrhostbindingpolicymanager-interface.md)
- [ICLRHostProtectionManager (Interfaz)](iclrhostprotectionmanager-interface.md)
- [ICLROnEventManager (Interfaz)](iclroneventmanager-interface.md)
- [ICLRPolicyManager (Interfaz)](iclrpolicymanager-interface.md)
- [IHostControl (Interfaz)](ihostcontrol-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
