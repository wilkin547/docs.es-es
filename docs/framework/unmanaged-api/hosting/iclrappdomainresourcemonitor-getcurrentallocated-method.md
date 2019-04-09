---
title: ICLRAppDomainResourceMonitor::GetCurrentAllocated (Método)
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fcd7a3aa1a6c034985099c24071429384563700
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129394"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a>ICLRAppDomainResourceMonitor::GetCurrentAllocated (Método)
Obtiene el tamaño total, en bytes, de todas las asignaciones de memoria que el dominio de aplicación se han realizado desde que se creó, sin restar la memoria que se ha recopilado de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwAppDomainId`  
 [in] El Id. del dominio de aplicación solicitado.  
  
 `pBytesAllocated`  
 [out] Un puntero al tamaño total de todas las asignaciones de memoria.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|COR_E_APPDOMAINUNLOADED|El dominio de aplicación se ha descargado o no existe.|  
  
## <a name="remarks"></a>Comentarios  
 Este método es el equivalente administrado de los recursos administrados <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> propiedad.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MetaHost.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRAppDomainResourceMonitor (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [Supervisión de recursos de dominio de aplicación](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md)
