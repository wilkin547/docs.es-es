---
title: ICLRAppDomainResourceMonitor::GetCurrentCpuTime (Método)
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type:
- apiref
ms.openlocfilehash: b411190ff36410c1d293f1e48b31975be8a13aee
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616039"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a>ICLRAppDomainResourceMonitor::GetCurrentCpuTime (Método)
Obtiene el tiempo total de procesador usado por todos los subprocesos mientras se ejecutaba en el dominio de aplicación actual, desde que se creó el dominio de aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwAppDomainId`  
 de IDENTIFICADOR del dominio de aplicación solicitado.  
  
 `pMilliseconds`  
 enuncia Puntero al tiempo total de procesador usado por todos los subprocesos mientras se ejecutaba en el dominio de aplicación actual desde que se creó el dominio de aplicación. Este parámetro puede ser `null`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|COR_E_APPDOMAINUNLOADED|El dominio de aplicación se ha descargado o no existe.|  
|E_FAIL|La supervisión de recursos del dominio de aplicación no está habilitada.<br /><br /> o bien<br /><br /> Todos los demás errores.|  
  
## <a name="remarks"></a>Observaciones  
 Este método es el equivalente no administrado de la propiedad administrada <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [ICLRAppDomainResourceMonitor (Interfaz)](iclrappdomainresourcemonitor-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [Supervisión de recursos del dominio de aplicación](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [Hospedar aplicaciones de WPF](index.md)
