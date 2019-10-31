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
ms.openlocfilehash: 302db0d029b3811d151473323a7a60bd16a00ec1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131235"
---
# <a name="eclrunhandledexception-enumeration"></a>EClrUnhandledException (Enumeración)
Describe las opciones disponibles para administrar excepciones que no se controlan en el código de usuario.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|Especifica que se produce el comportamiento predeterminado. El proceso se ha anulado.|  
|`eHostDeterminedPolicy`|Especifica que el Common Language Runtime (CLR) omite las excepciones no controladas y permite que el host determine cualquier acción más.|  
  
## <a name="remarks"></a>Comentarios  
 Para especificar que el CLR se comporte como versiones anteriores, utilice el miembro `eHostDeterminedPolicy`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [EClrFailure (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [EClrOperation (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [ICLRPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [SetUnhandledExceptionPolicy (método)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [IHostPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
