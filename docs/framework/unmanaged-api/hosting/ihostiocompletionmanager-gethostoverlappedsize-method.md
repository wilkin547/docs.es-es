---
description: 'Más información sobre: IHostIoCompletionManager:: Gethostoverlappedsize ((método)'
title: IHostIoCompletionManager::GetHostOverlappedSize (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetHostOverlappedSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type:
- apiref
ms.openlocfilehash: 2a2ebe1da82c5702269b634eadfe98b72739e3df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708572"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a>IHostIoCompletionManager::GetHostOverlappedSize (Método)

Obtiene el tamaño de los datos personalizados que el host pretende anexar a las solicitudes de e/s.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pcbSize`  
 enuncia Puntero al número de bytes que debe asignar el Common Language Runtime (CLR) además del tamaño del `OVERLAPPED` objeto Win32.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`GetHostOverlappedSize` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Observaciones  

 Todas las llamadas de e/s asincrónicas a las API de la plataforma Windows toman un `OVERLAPPED` objeto Win32, que proporciona información como la posición del puntero de archivo. Para mantener el estado, las aplicaciones que realizan llamadas asincrónicas de e/s suelen agregar datos personalizados a la estructura. `GetHostOverlappedSize` y [IHostIoCompletionManager:: initializehostoverlapped (](ihostiocompletionmanager-initializehostoverlapped-method.md) proporcionan una oportunidad para que el host incluya estos datos personalizados.  
  
 CLR llama al `GetHostOverlappedSize` método para determinar el tamaño de los datos personalizados que el host tiende a anexar al `OVERLAPPED` objeto.  
  
> [!NOTE]
> `GetHostOverlappedSize` solo se llama una vez. Los datos personalizados del host deben tener el mismo tamaño para cada solicitud de e/s.  
  
> [!IMPORTANT]
> El tamaño del `OVERLAPPED` propio objeto no se incluye en el valor de `pcbSize` .  
  
 Para obtener más información acerca de la `OVERLAPPED` estructura, vea la documentación de la plataforma Windows.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.NativeOverlapped>
- [ICLRIoCompletionManager (Interfaz)](iclriocompletionmanager-interface.md)
- [IHostIoCompletionManager (Interfaz)](ihostiocompletionmanager-interface.md)
