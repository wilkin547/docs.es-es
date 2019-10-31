---
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
ms.openlocfilehash: 3c662021894acbb8eb448fa2166498254158caa4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133864"
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
 enuncia Puntero al número de bytes que debe asignar el Common Language Runtime (CLR) además del tamaño del objeto de `OVERLAPPED` de Win32.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`GetHostOverlappedSize` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 Todas las llamadas de e/s asincrónicas a las API de la plataforma Windows toman un objeto de `OVERLAPPED` Win32, que proporciona información como la posición del puntero de archivo. Para mantener el estado, las aplicaciones que realizan llamadas asincrónicas de e/s suelen agregar datos personalizados a la estructura. `GetHostOverlappedSize` e [IHostIoCompletionManager:: initializehostoverlapped (](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) proporcionan una oportunidad para que el host incluya dichos datos personalizados.  
  
 CLR llama al método `GetHostOverlappedSize` para determinar el tamaño de los datos personalizados que el host tiende a anexar al objeto `OVERLAPPED`.  
  
> [!NOTE]
> `GetHostOverlappedSize` solo se llama una vez. Los datos personalizados del host deben tener el mismo tamaño para cada solicitud de e/s.  
  
> [!IMPORTANT]
> El tamaño del propio objeto de `OVERLAPPED` no se incluye en el valor de `pcbSize`.  
  
 Para obtener más información acerca de la estructura de `OVERLAPPED`, consulte la documentación de la plataforma Windows.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.NativeOverlapped>
- [ICLRIoCompletionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [IHostIoCompletionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
