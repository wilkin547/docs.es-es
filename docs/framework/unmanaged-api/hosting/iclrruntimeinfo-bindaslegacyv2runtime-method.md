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
ms.openlocfilehash: 4390f379e5092cc59d123631f5e6d8da82e2bd7f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703897"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a>ICLRRuntimeInfo::BindAsLegacyV2Runtime (Método)
Enlaza el tiempo de ejecución actual para todas las decisiones de la Directiva de activación de la versión 2 de Common Language Runtime heredada (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos:  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El enlace se realizó correctamente o este tiempo de ejecución ya estaba enlazado como el Runtime heredado de la Directiva de activación de la versión 2 de CLR.|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|Un tiempo de ejecución diferente ya estaba enlazado a la Directiva de activación heredada de la versión 2 de CLR.|  
  
## <a name="remarks"></a>Observaciones  
 Si el tiempo de ejecución actual ya está enlazado a todas las decisiones de la Directiva de activación heredada de la versión 2 de CLR (por ejemplo, mediante el uso del `useLegacyV2RuntimeActivationPolicy` atributo en el [ \< elemento de> de inicio](../../configure-apps/file-schema/startup/startup-element.md) del archivo de configuración), este método no devuelve ningún resultado de error; en su lugar, el resultado es S_OK, del mismo modo que si el método hubiera enlazado correctamente la Directiva  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [ICLRRuntimeInfo (Interfaz)](iclrruntimeinfo-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
- [\<Startup>, elemento](../../configure-apps/file-schema/startup/startup-element.md)
