---
title: ICLRMemoryNotificationCallback::OnMemoryNotification (Método)
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback.OnMemoryNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification
helpviewer_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification method [.NET Framework hosting]
- OnMemoryNotification method [.NET Framework hosting]
ms.assetid: 5612a44d-56cc-4f34-af31-8c9809ba9431
topic_type:
- apiref
ms.openlocfilehash: f9b2715801ebcaff3d97962540a4b1b103bbd53b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730479"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a>ICLRMemoryNotificationCallback::OnMemoryNotification (Método)

Notifica al Common Language Runtime (CLR) la carga de memoria en el equipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `eMemoryAvailable`  
 de Uno de los valores de [ememoryavailable (](ememoryavailable-enumeration.md) , que indica la presión de memoria que el equipo está experimentando actualmente.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`OnMemoryNotification` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  

 CLR registra una devolución de llamada en `OnMemoryNotification` mediante una llamada al método [IHostMemoryManager:: RegisterMemoryNotificationCallback (](ihostmemorymanager-registermemorynotificationcallback-method.md) . El motor en tiempo de ejecución usa la información devuelta en la devolución de llamada para liberar memoria adicional cuando el host informa de que los recursos de memoria se están agotando.  
  
> [!NOTE]
> Las llamadas a no se `OnMemoryNotification` bloquean nunca. Siempre devuelven inmediatamente.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IHostMemoryManager (Interfaz)](ihostmemorymanager-interface.md)
- [Método RegisterMemoryNotificationCallback](ihostmemorymanager-registermemorynotificationcallback-method.md)
- [ICLRMemoryNotificationCallback (Interfaz)](iclrmemorynotificationcallback-interface.md)
