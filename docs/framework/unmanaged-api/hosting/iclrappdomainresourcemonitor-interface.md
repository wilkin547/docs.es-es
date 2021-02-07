---
description: 'Más información acerca de: interfaz ICLRAppDomainResourceMonitor'
title: ICLRAppDomainResourceMonitor (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor
helpviewer_keywords:
- ICLRAppDomainResourceMonitor interface [.NET Framework hosting]
ms.assetid: 72fa83a1-8997-41d7-b355-ab177a24a303
topic_type:
- apiref
ms.openlocfilehash: 85321eabedb6912efabe57553732f8c6a4063155
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753905"
---
# <a name="iclrappdomainresourcemonitor-interface"></a>ICLRAppDomainResourceMonitor (Interfaz)

Proporciona métodos que inspeccionan el uso de la CPU y la memoria de un dominio de aplicación.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetCurrentAllocated](iclrappdomainresourcemonitor-getcurrentallocated-method.md)|Obtiene el tamaño total, en bytes, de todas las asignaciones de memoria realizadas por el dominio de aplicación desde que se creó, sin restar la memoria que se ha recolectado como elemento no utilizado.|  
|[Método GetCurrentSurvived](iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|Obtiene el número de bytes que sobrevivieron a la última recolección completa de elementos no utilizados bloqueada y a la que hace referencia el dominio de aplicación actual.|  
|[Método GetCurrentCpuTime](iclrappdomainresourcemonitor-getcurrentcputime-method.md)|Obtiene el tiempo total de procesador usado por todos los subprocesos mientras se ejecutaba en el dominio de aplicación actual, desde que se creó el dominio de aplicación.|  
  
## <a name="remarks"></a>Observaciones  

 La `ICLRAppDomainResourceMonitor` interfaz proporciona una funcionalidad similar a las siguientes propiedades administradas:  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Elemento \<appDomainResourceMonitoring>](../../configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [Supervisión de recursos del dominio de aplicación](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
