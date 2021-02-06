---
description: 'Más información acerca de: ICLRMetaHostPolicy (interfaz)'
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
ms.openlocfilehash: b14ad417617c32242f8a59844f7c1f1a8d05c78d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637422"
---
# <a name="iclrmetahostpolicy-interface"></a>ICLRMetaHostPolicy (Interfaz)

Proporciona el método [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) , que devuelve un puntero a una interfaz Common Language Runtime (CLR) basándose en un criterio de Directiva, un ensamblado administrado, una versión y un archivo de configuración.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md)|Proporciona una interfaz de CLR preferida basada en un criterio de Directiva, un ensamblado administrado, una versión y un archivo de configuración.|  
  
## <a name="remarks"></a>Observaciones  

 Puede obtener una referencia a esta interfaz mediante una llamada a la función [CLRCreateInstance](clrcreateinstance-function.md) como se muestra en el código siguiente:  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> En realidad, esta interfaz no carga ni activa CLR, sino que simplemente devuelve la versión de CLR preferida en función de las versiones disponibles que se instalan o cargan.  
  
 La API de hospedaje de .NET Framework 4 consolida las directivas para que los hosts con necesidades específicas puedan usar la funcionalidad básica sin incurrir en penalizaciones imprevistas. Por ejemplo, muchas de las exportaciones de MSCorEE.dll se enlazarán a un CLR específico, aunque es posible que un método no lo requiera lógicamente. La enumeración [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) proporciona directivas de enlace que son comunes a la mayoría de los hosts.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
