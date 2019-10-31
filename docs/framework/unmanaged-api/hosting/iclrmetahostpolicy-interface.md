---
title: ICLRMetaHostPolicy (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
ms.openlocfilehash: 277c13895374116eb67f6515f45df638f61b0453
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140859"
---
# <a name="iclrmetahostpolicy-interface"></a>ICLRMetaHostPolicy (Interfaz)
Proporciona el método [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) , que devuelve un puntero a una interfaz Common Language Runtime (CLR) basándose en un criterio de Directiva, un ensamblado administrado, una versión y un archivo de configuración.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetRequestedRuntime (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|Proporciona una interfaz de CLR preferida basada en un criterio de Directiva, un ensamblado administrado, una versión y un archivo de configuración.|  
  
## <a name="remarks"></a>Comentarios  
 Puede obtener una referencia a esta interfaz mediante una llamada a la función [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) como se muestra en el código siguiente:  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> En realidad, esta interfaz no carga ni activa CLR, sino que simplemente devuelve la versión de CLR preferida en función de las versiones disponibles que se instalan o cargan.  
  
 La API de hospedaje de .NET Framework 4 consolida las directivas para que los hosts con necesidades específicas puedan usar la funcionalidad básica sin incurrir en penalizaciones imprevistas. Por ejemplo, muchas de las exportaciones de MSCorEE. dll se enlazarán a un CLR específico, aunque es posible que un método no lo requiera lógicamente. La enumeración [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) proporciona directivas de enlace que son comunes a la mayoría de los hosts.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
