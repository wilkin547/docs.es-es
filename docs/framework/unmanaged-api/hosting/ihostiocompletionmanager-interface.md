---
title: IHostIoCompletionManager (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type:
- apiref
ms.openlocfilehash: 51d79c398c94ec355528140325da2c25422cbad9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133847"
---
# <a name="ihostiocompletionmanager-interface"></a>IHostIoCompletionManager (Interfaz)
Proporciona métodos que permiten que el Common Language Runtime (CLR) interactúe con los puertos de finalización de e/s proporcionados por el host.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Bind (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|Enlaza un identificador a un puerto de finalización de e/s.|  
|[CloseIoCompletionPort (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|Cierra un puerto que se creó mediante una llamada anterior a `CreateIoCompletionPort`.|  
|[CreateIoCompletionPort (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|Solicita que el host cree un nuevo puerto de finalización de e/s.|  
|[GetAvailableThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|Obtiene el número de subprocesos de finalización de e/s que no están procesando actualmente solicitudes.|  
|[GetHostOverlappedSize (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|Obtiene el tamaño de los datos personalizados que el host pretende anexar a las solicitudes de e/s.|  
|[GetMaxThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|Obtiene el número máximo de subprocesos que el host puede asignar a las solicitudes de e/s de servicio.|  
|[GetMinThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|Obtiene el número mínimo de subprocesos que proporciona el host para las solicitudes de e/s de servicio.|  
|[InitializeHostOverlapped (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|Proporciona al host la oportunidad de inicializar los datos personalizados sobre una solicitud de e/s.|  
|[SetCLRIoCompletionManager (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|Proporciona al host un puntero de interfaz a una instancia de [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) implementada por CLR.|  
|[SetMaxThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|Establece el número máximo de subprocesos que el host asigna a las solicitudes de e/s de servicio.|  
|[SetMinThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|Establece el número mínimo de subprocesos que el host debe asignar a la finalización de e/s.|  
  
## <a name="remarks"></a>Comentarios  
 `IHostIoCompletionManager` corresponde a la interfaz de `ICLRIoCompletionManager` implementada por CLR. CLR llama a los métodos de `IHostIoCompletionManager` para enlazar los identificadores a los puertos proporcionados por el host y el host llama a los métodos de `ICLRIoCompletionManager` para notificar la finalización de las solicitudes de e/s.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
