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
ms.openlocfilehash: 63b07dda2293d3e05bd3c8fcdc45f20a498ea54c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616312"
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
  
## <a name="remarks"></a>Observaciones  
 Para especificar que el CLR se comporte como versiones anteriores, utilice el `eHostDeterminedPolicy` miembro.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [EClrFailure (Enumeración)](eclrfailure-enumeration.md)
- [EClrOperation (Enumeración)](eclroperation-enumeration.md)
- [ICLRPolicyManager (Interfaz)](iclrpolicymanager-interface.md)
- [Método SetUnhandledExceptionPolicy](iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [IHostPolicyManager (Interfaz)](ihostpolicymanager-interface.md)
- [Enumeraciones para hosts](hosting-enumerations.md)
