---
title: ICLRRuntimeInfo::BindAsLegacyV2Runtime (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a0ea4bd222500015f6c78cb0455539aa2c24e681
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765620"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a>ICLRRuntimeInfo::BindAsLegacyV2Runtime (Método)
Enlaza el tiempo de ejecución actual para todas heredado common language runtime (CLR) versión 2 activación Directiva las decisiones.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT concretos:  
  
|HRESULT|DESCRIPCIÓN|  
|-------------|-----------------|  
|S_OK|Enlace se ha realizado correctamente o ya estaba enlazada este tiempo de ejecución que CLR versión 2 activación directiva runtime heredado.|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|Un runtime diferente ya estaba enlazado a la directiva de 2 activación de versión CLR heredada.|  
  
## <a name="remarks"></a>Comentarios  
 Si ya está enlazado el tiempo de ejecución actual para todos los heredados CLR versión 2 activación las decisiones de directiva (por ejemplo, mediante el `useLegacyV2RuntimeActivationPolicy` atributo el [ \<Inicio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) en el archivo de configuración), este método no devuelve un resultado de error; en su lugar, el resultado es S_OK, tal como lo sería si el método tenía enlazar correctamente la directiva de activación heredada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MetaHost.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRRuntimeInfo (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [Elemento \<startup>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
