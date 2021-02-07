---
description: 'Más información acerca de: interfaz Igchost2 ('
title: IGCHost2 (Interfaz)
ms.date: 03/30/2017
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
ms.openlocfilehash: e32a4894fcff3600c9385f0f559443e23b2bc307
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709326"
---
# <a name="igchost2-interface"></a>IGCHost2 (Interfaz)

Proporciona métodos para obtener información sobre el sistema de recolección de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos no utilizados.  
  
> [!NOTE]
> En el caso del nuevo desarrollo, se recomienda utilizar la interfaz [iclrgcmanager2 (](iclrgcmanager2-interface.md) en su lugar.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[SetGCStartupLimitsEx (Método)](igchost2-setgcstartuplimitsex-method.md)|Establece el tamaño del segmento y el tamaño máximo de la generación 0. Habilita la generación 0 y los tamaños de segmento mayores que `DWORD` .|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** GCHost. idl, GCHost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje](hosting-interfaces.md)
- [Interfaces de hospedaje de CLR](clr-hosting-interfaces.md)
- [CorRuntimeHost (Coclase)](corruntimehost-coclass.md)
