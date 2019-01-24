---
title: ICorRuntimeHost::GetConfiguration (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b10ec088f087c45b8a75805e326bc543bb64b3d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665089"
---
# <a name="icorruntimehostgetconfiguration-method"></a>ICorRuntimeHost::GetConfiguration (Método)
Obtiene un objeto que permite al host especificar la configuración de devolución de llamada de common language runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pConfiguration`  
 [out] Un puntero a la dirección de un [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) objeto que se puede usar para configurar el CLR.  
  
## <a name="remarks"></a>Comentarios  
 El CLR debe configurarse antes de su inicialización; en caso contrario, el `GetConfiguration` método devuelve un HRESULT que indica un error.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>Vea también
- [ICorRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
