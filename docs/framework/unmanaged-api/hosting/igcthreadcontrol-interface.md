---
title: IGCThreadControl (Interfaz)
ms.date: 03/30/2017
api_name:
- IGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCThreadControl
helpviewer_keywords:
- IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 3ff04d75-85ac-4df9-886d-dbaa037c0552
topic_type:
- apiref
ms.openlocfilehash: 02facbb0ff1c0f8978d4f4f720ab370f70f07fe2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721691"
---
# <a name="igcthreadcontrol-interface"></a>IGCThreadControl (Interfaz)

Proporciona métodos para participar en la programación de subprocesos que de otro modo se bloquearían para una recolección de elementos no utilizados.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método SuspensionEnding](igcthreadcontrol-suspensionending-method.md)|Notifica al host que el Runtime está reanudando los subprocesos después de una recolección de elementos no utilizados u otra suspensión.|  
|[Método SuspensionStarting](igcthreadcontrol-suspensionstarting-method.md)|Notifica al host que el motor en tiempo de ejecución está iniciando una suspensión de subprocesos para una recolección de elementos no utilizados u otra suspensión.|  
|[Método ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md)|Notifica al host que el subproceso que realiza la llamada está a punto de bloquearse, quizás para una recolección de elementos no utilizados u otra suspensión.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de hospedaje](hosting-interfaces.md)
