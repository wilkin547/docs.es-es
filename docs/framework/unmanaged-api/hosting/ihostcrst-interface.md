---
title: IHostCrst (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
ms.openlocfilehash: e8cb1486ccea11ba6edcf7bbb781a9bf210b496d
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804899"
---
# <a name="ihostcrst-interface"></a>IHostCrst (Interfaz)
Actúa como la representación del host de una sección crítica para el subprocesamiento.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método Enter](ihostcrst-enter-method.md)|Entra en la sección crítica.|  
|[Método Leave](ihostcrst-leave-method.md)|Deja la sección crítica.|  
|[Método SetSpinCount](ihostcrst-setspincount-method.md)|Establece el número de giros de la sección crítica.|  
|[TryEnter](ihostcrst-tryenter-method.md)|Intenta entrar en la sección crítica e informa de éxito o error inmediatamente.|  
  
## <a name="remarks"></a>Observaciones  
 `IHostCrst`permite que el Common Language Runtime (CLR) se comunique directamente con la representación del host de una sección crítica, en lugar de usar funciones de Win32 como `EnterCriticalSection` o `LeaveCriticalSection` .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRSyncManager (Interfaz)](iclrsyncmanager-interface.md)
- [IHostSyncManager (Interfaz)](ihostsyncmanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
