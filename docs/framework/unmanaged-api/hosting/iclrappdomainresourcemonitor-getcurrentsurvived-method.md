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
ms.openlocfilehash: a73c0731c79dea3a0c411fe27a864ec9ac4e20b2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616026"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a>ICLRAppDomainResourceMonitor::GetCurrentSurvived (Método)
Obtiene el número de bytes que sobrevivieron a la última recolección completa de elementos no utilizados bloqueada y a la que hace referencia el dominio de aplicación actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwAppDomainId`  
 de IDENTIFICADOR del dominio de aplicación solicitado.  
  
 `pAppDomainBytesSurvived`  
 enuncia Puntero al número de bytes que sobrevivieron después de la última recolección de elementos no utilizados retenida por este dominio de aplicación. Después de una recolección completa, este número es preciso y completo. Después de una recolección efímera, este número puede estar incompleto. Este parámetro puede ser `null`.  
  
 `pRuntimeBytesSurvived`  
 enuncia Puntero al número total de bytes que sobrevivieron de la última recolección de elementos no utilizados. Después de una recolección completa, este número representa el número de bytes que se encuentran en montones administrados. Después de una recolección efímera, este número representa el número de bytes que se mantienen activos en generaciones efímeras. Este parámetro puede ser `null`.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|COR_E_APPDOMAINUNLOADED|El dominio de aplicación se ha descargado o no existe.|  
  
## <a name="remarks"></a>Observaciones  
 Las estadísticas se actualizan solo después de una recolección completa de elementos no utilizados de bloqueo; es decir, una colección que incluye todas las generaciones y que detiene la aplicación mientras se produce la recolección. Por ejemplo, la <xref:System.GC.Collect?displayProperty=nameWithType> sobrecarga del método realiza una colección completa de bloqueos. La recolección de elementos no utilizados simultánea se produce en segundo plano y no bloquea la aplicación.  
  
 El `GetCurrentSurvived` método es el equivalente no administrado de la propiedad administrada <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [ICLRAppDomainResourceMonitor (Interfaz)](iclrappdomainresourcemonitor-interface.md)
- [Supervisión de recursos del dominio de aplicación](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
