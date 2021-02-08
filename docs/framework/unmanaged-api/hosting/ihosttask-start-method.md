---
description: 'Más información acerca de: IHostTask:: Start (método)'
title: IHostTask::Start (Método)
ms.date: 03/30/2017
api_name:
- IHostTask.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type:
- apiref
ms.openlocfilehash: 48352a3df49ba2ef3e008ed211da19f54deb82f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784631"
---
# <a name="ihosttaskstart-method"></a>IHostTask::Start (Método)

Solicita que el host mueva la tarea representada por la instancia actual de [IHostTask](ihosttask-interface.md) de un estado suspendido a activo, en el que se puede ejecutar el código.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El inicio se devolvió correctamente.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Observaciones  

 `Start` siempre devuelve un valor HRESULT de S_OK, excepto en los casos en los que se ha producido un error catastrófico.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRTask (Interfaz)](iclrtask-interface.md)
- [ICLRTaskManager (Interfaz)](iclrtaskmanager-interface.md)
- [IHostTask (Interfaz)](ihosttask-interface.md)
- [IHostTaskManager (Interfaz)](ihosttaskmanager-interface.md)
