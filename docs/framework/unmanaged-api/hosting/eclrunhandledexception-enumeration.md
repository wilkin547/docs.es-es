---
title: EClrUnhandledException (Enumeración)
ms.date: 03/30/2017
api_name:
- EClrUnhandledException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrUnhandledException
helpviewer_keywords:
- EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eeff8aa0336c0c497e306825c6c77f4f8745ca7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431810"
---
# <a name="eclrunhandledexception-enumeration"></a>EClrUnhandledException (Enumeración)
Describe las opciones disponibles para administrar las excepciones que son no está controladas en código de usuario.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|Especifica que se produce el comportamiento predeterminado. El proceso se cierra.|  
|`eHostDeterminedPolicy`|Especifica que common language runtime (CLR) omite las excepciones no controladas y permite que el host determine las acciones posteriores.|  
  
## <a name="remarks"></a>Comentarios  
 Para especificar que CLR se comporte como en versiones anteriores, use el `eHostDeterminedPolicy` miembro.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [EClrFailure (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [EClrOperation (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [ICLRPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [SetUnhandledExceptionPolicy (método)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)  
 [IHostPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
