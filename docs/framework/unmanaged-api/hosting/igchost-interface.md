---
description: 'Más información acerca de: interfaz IGCHost'
title: IGCHost (Interfaz)
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
ms.openlocfilehash: 73b1125eb66a38373da85769ab80ddcaf0b955c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709599"
---
# <a name="igchost-interface"></a>IGCHost (Interfaz)

Proporciona métodos para obtener información sobre el sistema de recolección de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos no utilizados.  
  
> [!NOTE]
> A partir del .NET Framework 4,5, puede usar el método [igchost2 (:: setgcstartuplimitsex (](igchost2-setgcstartuplimitsex-method.md) para establecer el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados en valores mayores que el `DWORD` límite impuesto por el método [setgcstartuplimits (](igchost-setgcstartuplimits-method.md) .  
  
> [!NOTE]
> Esta interfaz solo es para uso experto. Puede afectar al rendimiento de una aplicación si se usa de forma incorrecta.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método Collect](igchost-collect-method.md)|Obliga a que se produzca una colección para la generación dada, independientemente del estado de la recolección de elementos no utilizados actual.|  
|[GetStats (Método)](igchost-getstats-method.md)|Obtiene las estadísticas para el estado actual del sistema de recolección de elementos no utilizados.|  
|[Método GetThreadStats](igchost-getthreadstats-method.md)|Obtiene las estadísticas por subproceso para la recolección de elementos no utilizados.|  
|[Método SetGCStartupLimits](igchost-setgcstartuplimits-method.md)|Establece el tamaño del segmento y el tamaño máximo de la generación 0.|  
|[Método SetVirtualMemLimit](igchost-setvirtualmemlimit-method.md)|Establece el tamaño máximo de la memoria virtual del tiempo de ejecución.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** GCHost. idl, GCHost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje](hosting-interfaces.md)
- [CorRuntimeHost (Coclase)](corruntimehost-coclass.md)
