---
title: ICLRAppDomainResourceMonitor::GetCurrentSurvived (Método)
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 10df17f2f21928ab89c65be7fd07afe81c468a07
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766547"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a>ICLRAppDomainResourceMonitor::GetCurrentSurvived (Método)
Obtiene el número de bytes que sobrevivieron a la última completa de la recolección de elementos no utilizados de bloqueo y que se hace referencia el dominio de aplicación actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwAppDomainId`  
 [in] El Id. del dominio de aplicación solicitado.  
  
 `pAppDomainBytesSurvived`  
 [out] Un puntero al número de bytes que sobrevivieron después de la última recolección que se incluyen en este dominio de aplicación. Después de una recolección completa, este número es precisa y completa. Después de una recolección efímera, este número puede estar incompleto. Este parámetro puede ser `null`.  
  
 `pRuntimeBytesSurvived`  
 [out] Un puntero al número total de bytes que sobrevivieron a la última recolección de elementos no utilizados. Después de una recolección completa, este número representa el número de bytes que se mantienen en montones administrados. Después de una recolección efímera, este número representa el número de bytes que se mantienen activos en generaciones efímeras. Este parámetro puede ser `null`.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|DESCRIPCIÓN|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|COR_E_APPDOMAINUNLOADED|El dominio de aplicación se ha descargado o no existe.|  
  
## <a name="remarks"></a>Comentarios  
 Las estadísticas se actualizan solo después de una recolección completa de bloqueo elementos no utilizados; es decir, se produce una colección que incluye todas las generaciones y que detiene la aplicación mientras la colección. Por ejemplo, el <xref:System.GC.Collect?displayProperty=nameWithType> sobrecarga del método realiza una recolección completa de bloqueo. Colección de elementos no utilizados simultánea se produce en segundo plano y no bloquea la aplicación.  
  
 El `GetCurrentSurvived` método es el equivalente administrado de los recursos administrados <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> propiedad.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MetaHost.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRAppDomainResourceMonitor (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [Supervisión de recursos de dominio de aplicación](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
