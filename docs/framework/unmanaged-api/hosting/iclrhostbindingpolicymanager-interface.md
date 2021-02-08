---
description: 'Más información acerca de: interfaz ICLRHostBindingPolicyManager'
title: ICLRHostBindingPolicyManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
ms.openlocfilehash: 07a18d622ff8d8483fe6dcb0242cb5f1ee284b14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789949"
---
# <a name="iclrhostbindingpolicymanager-interface"></a>ICLRHostBindingPolicyManager (Interfaz)

Proporciona métodos para que el host evalúe la Directiva de enlace actual y comunique los cambios de la Directiva para un ensamblado especificado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método EvaluatePolicy](iclrhostbindingpolicymanager-evaluatepolicy-method.md)|Evalúa la Directiva de enlace en nombre del host.|  
|[Método ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|Modifica la Directiva de enlace para el ensamblado especificado y crea una nueva versión de la Directiva.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRAssemblyIdentityManager (Interfaz)](iclrassemblyidentitymanager-interface.md)
- [IHostAssemblyStore (Interfaz)](ihostassemblystore-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
